---
title: 标题组件
seo-title: 标题组件
description: 'null'
seo-description: 核心组件标题组件是具有就地编辑功能的章节标题组件。
uuid: cf190861-e5 cd-42b8-9193-842b8 df8 c5 c6
contentOwner: 用户
content-type: 引用
topic-tags: 创作
products: SG_ EXPERIENCE MANAGER/CORECOMMPANES-new
discoiquuid: 243efc75-fcf9-427d-9303-9642b0602991
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: eef608fb06001485aa2c2c0b574af412ed7f15a4

---


# 标题组件{#title-component}

核心组件标题组件是具有就地编辑功能的章节标题组件。

## 使用情况 {#usage}

标题组件旨在用作内容部分的标题或标题。The available heading levels can be defined by the template author in the [design dialog](#design-dialog). The content editor can select from available headings levels in the [edit dialog](#edit-dialog). 为了方便起见，还提供了简单的位置文本就地编辑功能。

## Version and Compatibility {#version-and-compatibility}

标题组件的当前版本为v2，它是在2018年月核心组件发行版中引入的，该版本在本文档中进行了介绍。

下表详细说明了组件的所有支持版本、组件版本的AEM版本以及以前版本的文档链接。

| 组件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|---|---|---|---|
| v2 | 兼容 | 兼容 | 兼容 |
| [v1](title-v1.md) | 兼容 | 兼容 | 兼容 |

For more information about Core Component versions and releases, see the document [Core Components Versions](versions.md).

## Sample Component Output {#sample-component-output}

To experience the Title Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library/title.html).

### Technical Details {#technical-details}

The latest technical documentation about the Title Component [can be found on GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/title/v2/title).

Further details about developing Core Components can be found in the [Core Components developer documentation](developing.md).

## Edit Dialog {#edit-dialog}

编辑对话框允许内容作者定义标题文本以及选择标题级别。

* **标题** -如果空，将使用页面标题
* **类型/大小** -定义标题的标题级别
* **链接** -定义标题将链接到的内容。这可以是内容页面、外部URL或页面锚点的路径。

![](assets/screenshot_2018-10-19at110055.png)

>[!CAUTION]
>
>在核心组件的版本2.2.0中引入了为标题定义链接的功能。

就地编辑器还可用于编辑标题组件的文本。

![](assets/chlimage_1-37.png)

## Design Dialog {#design-dialog}

设计对话框允许模板作者定义内容作者创建时标题组件将具有的默认标题级别。

### Sizes Tab {#sizes-tab}

![](assets/screenshot_2018-10-19at110120.png)

* **作者允许的类型/大小** -启用或禁用内容作者使用标题组件时可使用的标题类型。
* **默认类型/大小**-定义内容作者将标题组件添加到页面时将自动分配的标题类型。
* **禁用** 链接-禁用标题组件中的链接支持，以禁止内容作者从标题链接。

>[!CAUTION]
>
>在核心组件的版本2.2.0中引入了为标题定义链接的功能。

### Styles Tab {#styles-tab}

The Title Component supports the AEM [Style System](authoring.md#component-styling).