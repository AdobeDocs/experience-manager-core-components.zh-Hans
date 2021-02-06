---
title: 将Adobe客户端数据层与核心组件结合使用
description: 将Adobe客户端数据层与核心组件结合使用
translation-type: tm+mt
source-git-commit: 1ada05d5089ccef95d41d47468776654e397f31d
workflow-type: tm+mt
source-wordcount: '893'
ht-degree: 3%

---


# 将Adobe客户端数据层与核心组件{#data-layer-core-components}一起使用

Adobe客户端数据层的目标是通过提供一种标准化方法来公开和访问任何脚本的任何类型数据，从而减少对网站进行测试的工作量。

Adobe客户端数据层与平台无关，但完全集成到核心组件中以与AEM一起使用。

与核心组件一样，Adobe客户端数据层的代码可在GitHub上找到，并提供开发人员文档。 此文档概述了核心组件与数据层的交互方式，但GitHub文档中会提供完整的技术详细信息。

>[!TIP]
>
>有关Adobe客户端数据层的详细信息，[请参阅其GitHub存储库中的资源。](https://github.com/adobe/adobe-client-data-layer)
>
>有关Adobe客户端数据层与核心组件集成的更多技术详细信息，请参阅核心组件存储库中的[`DATA_LAYER_INTEGRATION.md`](https://github.com/adobe/aem-core-wcm-components/blob/master/DATA_LAYER_INTEGRATION.md)文件。

## 安装和激活{#installation-activation}

从核心组件2.9.0版开始，数据层作为AEM客户端库随核心组件一起分发，无需安装。 默认情况下，由[AEM Project Archetype v. 24+](/help/developing/archetype/overview.md)生成的所有项目都包括已激活的数据层。

要手动激活数据层，必须为其创建[上下文感知配置](/help/developing/context-aware-configs.md):

1. 在`/conf/<mySite>`文件夹下创建以下结构，其中`<mySite>`是站点项目的名称：
   * `/conf/<mySite>/sling:configs/com.adobe.cq.wcm.core.components.internal.DataLayerConfig`
   * 其中每个节点的`jcr:primaryType`设置为`nt:unstructured`。
1. 添加一个名为`enabled`的布尔属性，并将其设置为`true`。

   ![WKND参考站点中DataLayerConfig的位置](/help/assets/datalayer-contextaware-sling-config.png)

   *WKND参考站点中DataLayerConfig的位置*

1. 将`sling:configRef`属性添加到`/content`下站点的`jcr:content`节点(例如，`/content/<mySite>/jcr:content`)，并将其从上一步设置为`/conf/<mySite>`。

1. 启用后，您可以通过在编辑器外加载站点的页面来验证激活。 Inspect页面源和`<body>`标记应包含属性`data-cmp-data-layer-enabled`

   ```html
   <body class="page basicpage" id="page-id" data-cmp-data-layer-enabled>
       <script>
         window.adobeDataLayer = window.adobeDataLayer || [];
         adobeDataLayer.push({
             page: JSON.parse("{\x22page\u002D6c5d4b9fdd\x22:{\x22xdm:language\x22:\x22en\x22,\x22repo:path\x22:\x22\/content\/wknd\/language\u002Dmasters\/en.html\x22,\x22xdm:tags\x22:[],\x22xdm:template\x22:\x22\/conf\/wknd\/settings\/wcm\/templates\/landing\u002Dpage\u002Dtemplate\x22,\x22@type\x22:\x22wknd\/components\/page\x22,\x22dc:description\x22:\x22WKND is a collective of outdoors, music, crafts, adventure sports, and travel enthusiasts that want to share our experiences, connections, and expertise with the world.\x22,\x22dc:title\x22:\x22WKND Adventures and Travel\x22,\x22repo:modifyDate\x22:\x222020\u002D09\u002D29T07:50:13Z\x22}}"),
             event:'cmp:show',
             eventInfo: {
                 path: 'page.page\u002D6c5d4b9fdd'
             }
         });
       </script>
   ```

1. 您还可以打开浏览器的开发人员工具，在控制台中`adobeDataLayer` JavaScript对象应可用。 输入以下命令以获取当前页面的数据层状态：

   ```javascript
   window.adobeDataLayer.getState();
   ```

## 核心组件模式{#data-schemas}

以下是核心组件与数据层一起使用的列表模式。

### 组件/容器项模式{#item}

组件/容器项模式用于以下组件：

* [痕迹导航](/help/components/breadcrumb.md)
* [按钮](/help/components/button.md)
* [语言导航](/help/components/language-navigation.md)
* [列表](/help/components/list.md)
* [导航](/help/components/navigation.md)
* [Teaser](/help/components/teaser.md)
* [文本](/help/components/text.md)
* [标题](/help/components/title.md)

组件/容器项模式定义如下。

```javascript
id: {                   // component ID
    @type               // resource type
    repo:modifyDate     // last modified date
    dc:title            // title
    dc:description      // description
    xdm:text            // text
    xdm:linkURL         // link URL
    parentId            // parent component ID
}
```

以下[事件符](#events)与组件/容器项模式相关：

* `cmp:click`

### 页面模式{#page}

页面模式由以下组件使用：

* [页面](/help/components/page.md)

页面模式定义如下。

```javascript
id: {
    @type
    repo:modifyDate
    dc:title
    dc:description
    xdm:text
    xdm:linkURL
    parentId
    xdm:tags            // page tags
    repo:path           // page path
    xdm:template        // page template
    xdm:language        // page language
}
```

页面加载时将触发`cmp:show`事件。 此事件从紧靠在开始`<body>`标签下的内嵌JavaScript中调度，使它成为数据层事件序列中最早的事件。

### 容器模式{#container}

容器模式由以下组件使用：

* [折叠](/help/components/accordion.md)
* [选项卡](/help/components/tabs.md)
* [轮播](/help/components/carousel.md)

容器模式定义如下。

```javascript
id: {
    @type
    repo:modifyDate
    dc:title
    dc:description
    xdm:text
    xdm:linkURL
    parentId
    shownItems          // array of the displayed item IDs
}
```

以下[事件](#events)与容器模式相关：

* `cmp:click`
* `cmp:show`
* `cmp:hide`

### 图像模式{#image}

图像模式由以下组件使用：

* [图像](/help/components/image.md)

图像模式定义如下。

```javascript
id: {
    @type
    repo:modifyDate
    dc:title
    dc:description
    xdm:text
    xdm:linkURL
    parentId
    image               // asset detail (see below section)
}
```

以下[事件符](#events)与图像模式相关：

* `cmp:click`

### 资产模式{#asset}

资产模式在[图像组件中使用。](/help/components/image.md)

资产模式定义如下。

```javascript
id: {
    repo:id             // asset UUID
    repo:path           // asset path
    @type               // asset resource type
    xdm:tags            // asset tags
    repo:modifyDate
}
```

以下[事件](#events)与资产模式相关：

* `cmp:click`

## 核心组件事件{#events}

核心组件通过数据层触发的事件很多。 与数据层交互的最佳实践是[注册事件监听器](https://github.com/adobe/adobe-client-data-layer/wiki#addeventlistener)和&#x200B;*，然后*&#x200B;根据触发事件的事件类型和／或组件执行操作。 这将避免使用异步脚本的潜在竞争条件。

以下是AEM核心组件提供的开箱即用事件:

* **`cmp:click`** -单击可单击的元素(具有属性 `data-cmp-clickable` 的元素)会使数据层触发 `cmp:click` 事件。
* **`cmp:show`** 和 **`cmp:hide`** -操作折叠面板（展开／折叠）、旋转（下一个／上一个按钮）和选项卡（选项卡选择）组件，分别导致数据层触 `cmp:show` 发和 `cmp:hide` 事件。`cmp:show`事件在页面加载时也会被调度，并应为第一个事件。
* **`cmp:loaded`** -一旦数据层填充了页面上的核心组件，数据层就会触发 `cmp:loaded` 事件。

### 事件由组件{#events-components}触发

下表列表了触发事件的标准核心组件以及这些事件。

| 组件 | 事件 |
|---|---|
| [折叠](/help/components/accordion.md) | `cmp:show` 和 `cmp:hide` |
| [按钮](/help/components/button.md) | `cmp:click` |
| [痕迹导航](/help/components/breadcrumb.md) | `cmp:click` |
| [轮播](/help/components/carousel.md) | `cmp:show` 和 `cmp:hide` |
| [语言导航](/help/components/language-navigation.md) | `cmp:click` |
| [导航](/help/components/navigation.md) | `cmp:click` |
| [页面](/help/components/page.md) | `cmp:show` |
| [选项卡](/help/components/tabs.md) | `cmp:show` 和 `cmp:hide` |
| [Teaser](/help/components/teaser.md) | `cmp:click` |

### 事件路径信息{#event-path-info}

AEM核心组件触发的每个数据层事件都将包含具有以下JSON对象的有效负荷：

```json
eventInfo: {
    path: '<component-path>'
}
```

其中`<component-path>`是触发事件的数据层中组件的JSON路径。  该值通过`event.eventInfo.path`可用，因为它可用作`adobeDataLayer.getState(<component-path>)`的参数，该参数检索触发事件的组件的当前状态，允许自定义代码访问其他数据并将其添加到数据层。

例如：

```javascript
function logEventObject(event) {
    if(event.hasOwnProperty("eventInfo") && event.eventInfo.hasOwnProperty("path")) {
        var dataObject = window.adobeDataLayer.getState(event.eventInfo.path);
        console.debug("The component that triggered this event: ");
        console.log(dataObject);
    }
}

window.adobeDataLayer = window.adobeDataLayer || [];
window.adobeDataLayer.push(function (dl) {
     dl.addEventListener("cmp:show", logEventObject);
});
```

## 教程

想要更详细地了解数据层和核心组件？ [查看此实践教程](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/integrations/adobe-client-data-layer/data-layer-overview.html)。

>[!TIP]
>
>要进一步探索数据层的灵活性，请查看集成选项，包括如何为自定义组件启用数据层。
