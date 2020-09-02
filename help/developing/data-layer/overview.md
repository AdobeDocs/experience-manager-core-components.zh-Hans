---
title: 将Adobe客户端数据层与核心组件结合使用
description: 将Adobe客户端数据层与核心组件结合使用
translation-type: tm+mt
source-git-commit: 24a810ff634f8846881dfa0095e879476d0f16f0
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 4%

---


# 将Adobe客户端数据层与核心组件结合使用 {#data-layer-core-components}

Adobe客户端数据层的目标是通过提供一种标准化方法来公开和访问任何脚本的任何类型数据，从而减少对网站进行测试的工作量。

Adobe客户端数据层与平台无关，但完全集成到核心组件中以与AEM一起使用。

与核心组件一样，Adobe客户端数据层的代码可在GitHub上找到，并提供开发人员文档。 此文档概述了核心组件与数据层的交互方式，但GitHub文档中会提供完整的技术详细信息。

>[!TIP]
>
>有关Adobe客户端数据层的详细信 [息，请参阅其GitHub存储库中的资源。](https://github.com/adobe/adobe-client-data-layer)
>
>有关Adobe客户端数据层与核心组件集成的更多技术详细信息，请参 [`DATA_LAYER_INTEGRATION.md`](https://github.com/adobe/aem-core-wcm-components/blob/master/DATA_LAYER_INTEGRATION.md) 阅核心组件存储库中的文件。

## 安装和激活 {#installation-activation}

自2.9.0版核心组件起，数据层将作为clientlib与核心组件一起分发。 无需安装。

但是，默认情况下不激活数据层。 要激活数据层，必须为其创 [建上下文感知](/help/developing/context-aware-configs.md) 型配置：

1. 在节点下创建以下 `/conf` 结构：
   * `/conf/<mySite>/sling:configs/com.adobe.cq.wcm.core.components.internal.DataLayerConfig`
   * 节点类型： `nt:unstructured`
1. 添加一个名为的布 `enabled` 尔属性，并将其设 `true`置为。
1. 将属 `sling:configRef` 性添加到 `jcr:content` 您的站点的节点 `/content` (例如， `/content/<mySite>/jcr:content`)并将其设置为 `/conf/<mySite>`。

启用后，您可以通过在编辑器外加载站点的页面来验证激活。 检查页面时，您将看到Adobe客户端数据层已加载。

## 核心组件数据模式 {#data-schemas}

以下是核心组件与数据层一起使用的列表模式。

### 组件/容器项模式 {#item}

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

```
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


### 页面模式 {#page}

页面模式由以下组件使用：

* [页面](/help/components/page.md)

页面模式定义如下。

```
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

### 容器模式 {#container}

容器模式由以下组件使用：

* [折叠](/help/components/accordion.md)
* [选项卡](/help/components/tabs.md)
* [轮播](/help/components/carousel.md)

容器模式定义如下。

```
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

### 图像模式 {#image}

图像模式由以下组件使用：

* [图像](/help/components/image.md)

图像模式定义如下。

```
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

### 资产模式 {#asset}

资产模式用于图像 [组件中。](/help/components/image.md)

资产模式定义如下。

```
id: {
    repo:id             // asset UUID
    repo:path           // asset path
    @type               // asset resource type
    xdm:tags            // asset tags
    repo:modifyDate
}
```

