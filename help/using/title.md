---
title: 标题组件
seo-title: 标题组件
description: 'null'
seo-description: 核心组件标题组件是一个可进行就地编辑的章节标题组件。
uuid: cf190861-e5cd-42b8-9193-842b8df8c5c6
contentOwner: 用户
content-type: 引用
topic-tags: 创作
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-新
discoiquuid: 243efc75-fcf9-427d-9303-9642b0602991
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: eef608fb06001485aa2c2c0b574af412ed7f15a4

---


# 标题组件{#title-component}

核心组件标题组件是一个可进行就地编辑的章节标题组件。

## 使用情况 {#usage}

标题组件用作内容部分的标题或标题。 可用的标题级别可由模板作者在设计对话框中 [定义](#design-dialog)。 内容编辑器可以从编辑对话框的可用标题级别 [中进行选择](#edit-dialog)。 为了更方便起见，还可以对标题文本进行简单的就地编辑。

## 版本和兼容性 {#version-and-compatibility}

标题组件的当前版本为v2，该版本在2018年1月随核心组件的2.0.0版一起推出，本文档对此进行了说明。

下表详细列出了组件的所有受支持版本、与组件版本兼容的AEM版本，以及指向先前版本的文档的链接。

| 组件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|---|---|---|---|
| v2 | 兼容 | 兼容 | 兼容 |
| [v1](title-v1.md) | 兼容 | 兼容 | 兼容 |

有关核心组件版本和版本的详细信息，请参阅文档核 [心组件版本](versions.md)。

## 示例组件输出 {#sample-component-output}

要体验标题组件以及查看其配置选项的示例以及HTML和JSON输出，请访问组件 [库](http://opensource.adobe.com/aem-core-wcm-components/library/title.html)。

### 技术详细信息 {#technical-details}

有关标题组件的最新技术文 [档可在GitHub上找到](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/title/v2/title)。

有关开发核心组件的更多详细信息，请参阅核 [心组件开发人员文档](developing.md)。

## Edit Dialog {#edit-dialog}

编辑对话框允许内容作者定义标题文本并选择标题级别。

* **标题** -如果为空，则将使用页面标题
* **类型／大小** -定义标题的标题级别
* **链接** -定义标题将链接到的内容。 这可以是指向内容页面、外部URL或页面锚点的路径。

![](assets/screenshot_2018-10-19at110055.png)

>[!CAUTION]
>
>核心组件版本2.2.0引入了定义标题链接的功能。

就地编辑器还可用于编辑标题组件的文本。

![](assets/chlimage_1-37.png)

## 设计对话框 {#design-dialog}

设计对话框允许模板作者定义标题组件在由内容作者创建时将具有的默认标题级别。

### “大小”选项卡 {#sizes-tab}

![](assets/screenshot_2018-10-19at110120.png)

* **作者允许的类型／大小** -启用或禁用内容作者在使用标题组件时可用的标题类型。
* **默认类型／大小**-定义在内容作者将标题组件添加到页面时将自动分配的标题类型。
* **禁用链接**-禁用标题组件中链接的支持，以禁止内容作者从标题中进行链接。

>[!CAUTION]
>
>核心组件版本2.2.0引入了定义标题链接的功能。

### 样式选项卡 {#styles-tab}

标题组件支持AEM样 [式系统](authoring.md#component-styling)。