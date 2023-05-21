---
title: 将 Adobe Client Data Layer 与核心组件配合使用
description: 将 Adobe Client Data Layer 与核心组件配合使用
feature: Core Components, Adobe Client Data Layer
role: Architect, Developer, Admin
exl-id: 55c984d3-deb7-4eda-a81d-7768791d2b46
source-git-commit: 2ac16b15718128feefbe903e92f276b16fe96f69
workflow-type: tm+mt
source-wordcount: '972'
ht-degree: 100%

---

# 将 Adobe Client Data Layer 与核心组件配合使用 {#data-layer-core-components}

Adobe Client Data Layer 的目标是通过提供一种标准化方法，来公开和访问任何脚本的任何类型的数据，从而减少检测网站所需的工作量。

Adobe Client Data Layer 与平台无关，而是与核心组件完全集成以用于 AEM。

与核心组件一样，Adobe Client Data Layer 的代码在 GitHub 上与其开发人员文档一起提供。本文档概述核心组件如何与 Data Layer 交互，但如果要查看完整的技术详细信息，请参考 GitHub 文档。

>[!TIP]
>
>有关 Adobe Client Data Layer 的更多信息，[请参阅其 GitHub 存储库中的资源](https://github.com/adobe/adobe-client-data-layer)。
>
>有关 Adobe Client Data Layer 与核心组件集成的其他技术详细信息，请参阅核心组件存储库中的 [`DATA_LAYER_INTEGRATION.md`](https://github.com/adobe/aem-core-wcm-components/blob/master/DATA_LAYER_INTEGRATION.md) 文件。

## 安装和激活 {#installation-activation}

截止到核心组件发行版本 2.9.0，Data Layer 作为 AEM Client Library 随核心组件分发，无需安装。对于 [AEM 项目原型 v. 24+](/help/developing/archetype/overview.md) 生成的所有项目，默认情况下包含激活的 Data Layer。

要手动激活 Data Layer，您必须为其创建[上下文感知配置](/help/developing/context-aware-configs.md)：

1. 在 `/conf/<mySite>` 文件夹下创建以下结构，其中 `<mySite>` 是网站项目的名称：
   * `/conf/<mySite>/sling:configs/com.adobe.cq.wcm.core.components.internal.DataLayerConfig`
   * 其中每个节点必须将 `jcr:primaryType` 设置为 `nt:unstructured`。
1. 添加名为 `enabled` 的布尔值属性并将其设置为 `true`。

   ![WKND 参考网站中 DataLayerConfig 的位置](/help/assets/datalayer-contextaware-sling-config.png)

   *WKND 参考网站中 DataLayerConfig 的位置*

1. 将 `sling:configRef` 属性添加到网站的 `jcr:content` 节点的 `/content` 之下（例如，`/content/<mySite>/jcr:content`），并将其设置为之前步骤中的 `/conf/<mySite>`。

1. 在启用之后，您可以通过在编辑器之外加载网站的页面来验证是否已激活，例如，使用编辑器中的&#x200B;**以发布的形式查看**&#x200B;选项。检查页面源，`<body>` 标记应包括属性 `data-cmp-data-layer-enabled`

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

1. 您还可以打开浏览器的开发人员工具，然后在控制台中，`adobeDataLayer` JavaScript 对象应可用。输入以下命令以获取当前页面的 Data Layer 状态：

   ```javascript
   window.adobeDataLayer.getState();
   ```

## 支持的组件 {#supported-components}

以下组件支持 Data Layer。

* [折叠](/help/components/accordion.md)
* [痕迹导航](/help/components/breadcrumb.md)
* [按钮](/help/components/button.md)
* [轮盘](/help/components/carousel.md)
* [内容片段](/help/components/content-fragment-component.md)
* [图像](/help/components/image.md)
* [语言导航](/help/components/language-navigation.md)
* [列表](/help/components/list.md)
* [导航](/help/components/navigation.md)
* [页面](/help/components/page.md)
* [进度条](/help/components/progress-bar.md)
* [选项卡](/help/components/tabs.md)
* [Teaser](/help/components/teaser.md)
* [文本](/help/components/text.md)
* [标题](/help/components/title.md)

另请参阅[组件触发的事件](#events-components)。

## 核心组件数据架构 {#data-schemas}

以下是核心组件用于 Data Layer 的架构列表。

### 组件/容器项目架构 {#item}

组件/容器项目架构用于以下组件中：

* [痕迹导航](/help/components/breadcrumb.md)
* [按钮](/help/components/button.md)
* [语言导航](/help/components/language-navigation.md)
* [列表](/help/components/list.md)
* [导航](/help/components/navigation.md)
* [Teaser](/help/components/teaser.md)
* [文本](/help/components/text.md)
* [标题](/help/components/title.md)

组件/容器项目架构的定义如下。

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

以下[事件](#events)与组件/容器项目架构相关：

* `cmp:click`

### 页面架构 {#page}

页面架构由以下组件使用：

* [页面](/help/components/page.md)

页面架构的定义如下。

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

`cmp:show` 事件在页面加载时触发。此事件从紧跟 `<body>` 开始标记下方的内联 JavaScript 中分发，使其成为 Data Layer 事件队列中最早的事件。

### 容器架构 {#container}

容器架构由以下组件使用：

* [折叠](/help/components/accordion.md)
* [选项卡](/help/components/tabs.md)
* [轮盘](/help/components/carousel.md)

容器架构的定义如下。

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

以下[事件](#events)与容器架构相关：

* `cmp:click`
* `cmp:show`
* `cmp:hide`

### 图像架构 {#image}

图像架构由以下组件使用：

* [图像](/help/components/image.md)

图像架构的定义如下。

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

以下[事件](#events)与图像架构相关：

* `cmp:click`

### 资源架构 {#asset}

资源架构在[图像组件](/help/components/image.md)内部使用。

资源架构的定义如下。

```javascript
id: {
    repo:id             // asset UUID
    repo:path           // asset path
    @type               // asset resource type
    xdm:tags            // asset tags
    repo:modifyDate
}
```

以下[事件](#events)与资源架构相关：

* `cmp:click`

### 内容片段架构 {#content-fragment}

内容片段架构由[内容片段组件](/help/components/content-fragment-component.md)使用。

内容片段架构的定义如下。

```javascript
id: {
    @type
    repo:modifyDate
    dc:title
    dc:description
    xdm:text
    xdm:linkURL
    parentId
    elements            // array of the Content Fragment elements
}
```

内容片段元素使用的架构如下。

```javascript
{
    xdm:title           // title
    xdm:text            // text
}
```

## 核心组件事件 {#events}

核心组件通过 Data Layer 会触发多种事件。与 Data Layer 交互的最佳方法是[注册事件侦听器](https://github.com/adobe/adobe-client-data-layer/wiki#addeventlistener)，*然后*&#x200B;根据事件类型和/或触发事件的组件采取操作。这样能够避免可能与异步脚本出现的争用情况。

以下是 AEM 核心组件提供的现成事件。

* **`cmp:click`** - 单击一个可单击元素（具有 `data-cmp-clickable` 属性的元素）会导致 Data Layer 触发 `cmp:click` 事件。
* **`cmp:show`** 和 **`cmp:hide`** - 处理折叠（展开/折叠）、轮盘（下一页/上一页按钮）和选项卡（选项卡选择）组件会导致 Data Layer 分别触发 `cmp:show` 和 `cmp:hide` 事件。`cmp:show` 事件还会在页面加载时分发，并且预期成为第一个事件。
* **`cmp:loaded`** - 使用页面上的核心组件填充 Data Layer 之后，Data Layer 马上触发 `cmp:loaded` 事件。

### 组件触发的事件 {#events-components}

下表列出了触发事件的标准核心组件以及其他事件。

| 组件 | 事件 |
|---|---|
| [折叠](/help/components/accordion.md) | `cmp:show` 和 `cmp:hide` |
| [按钮](/help/components/button.md) | `cmp:click` |
| [痕迹导航](/help/components/breadcrumb.md) | `cmp:click` |
| [轮盘](/help/components/carousel.md) | `cmp:show` 和 `cmp:hide` |
| [语言导航](/help/components/language-navigation.md) | `cmp:click` |
| [导航](/help/components/navigation.md) | `cmp:click` |
| [页面](/help/components/page.md) | `cmp:show` |
| [选项卡](/help/components/tabs.md) | `cmp:show` 和 `cmp:hide` |
| [Teaser](/help/components/teaser.md) | `cmp:click` |

### 事件路径信息 {#event-path-info}

AEM 核心组件触发的每个 Data Layer 事件将包括带有以下 JSON 对象的负载：

```json
eventInfo: {
    path: '<component-path>'
}
```

其中 `<component-path>` 是 Data Layer 中触发事件的组件的 JSON 路径。该值非常重要（可通过 `event.eventInfo.path` 使用），因为它可以用作 `adobeDataLayer.getState(<component-path>)` 的参数，这将检索触发事件的组件的当前状态，允许自定义代码访问额外的数据并将其添加到 Data Layer。

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

希望更详细地探讨 Data Layer 和核心组件？[请查看此实践教程](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/integrations/adobe-client-data-layer/data-layer-overview.html)。

>[!TIP]
>
>要进一步探讨 Data Layer 的灵活性，请查看相关的集成选项，包括如何为自定义组件启用 Data Layer。
