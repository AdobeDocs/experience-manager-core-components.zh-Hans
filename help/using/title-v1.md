---
title: 标题组件(v1)
seo-title: 标题组件(v1)
description: The Core Component Title Component is a section heading component that features in-place editing.
seo-description: 核心组件标题组件是一个可进行就地编辑的章节标题组件。
uuid: 5c4d276c-f0be-4122-a15e-3f7443d8b209
content-type: 引用
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-新
discoiquuid: a028ebef-2957-410c-9bab-a7040c350f2f
index: n
translation-type: tm+mt
source-git-commit: 4e74f10e2a4119484a597178dc4577b399833dbf

---


# 标题组件(v1){#title-component-v}

核心组件标题组件是一个可进行就地编辑的章节标题组件。

## 使用情况 {#usage}

标题组件用作内容部分的标题或标题。

可用的标题级别可由模板作者在设计对话框中 [定义](title-v1.md#main-pars_title_1995166862)。 内容编辑器可以从编辑对话框的可用标题级别 [中进行选择](title-v1.md#main-pars_title)。 For added convenience, simple in-place editing of the heading text is also available.

## 版本和兼容性 {#version-and-compatibility}

本文档描述了最初随AEM 6.3的核心组件版本1.0.0引入的标题组件的v1。

The following table lists the compatibility of v1 of the Title Component.

| AEM 版本 | 标题组件v1 |
|--- |--- |
| 6.3 | 兼容 |
| 6.4 | 兼容 |

>[!CAUTION]
>
>This document describes version 1 of the Title Component.
>
>For details of the current version of the Title Component, see the Title Component document.[](title.md)

## Sample Component Output {#sample-component-output}

以下是从 [We.Retail获取的示例](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)。

### 屏幕快照 {#screenshot}

![](assets/chlimage_1-36.png)

### HTML {#html}

```
<div class="cmp cmp-title aem-GridColumn aem-GridColumn--default--12">
     <h2>Welcome! This is our finest equipment!</h2>
</div>
```

### JSON {#json}

```
"title": {
              "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
              ":type": "weretail/components/content/title",
              "jcr:title": "Welcome! This is our finest equipment!",
              "type": "h2"
            }
```

>[!NOTE]
>
>从核心组件导出JSON时，需要发行1.1.0版的核心组件。 有关详细信息， [请参阅核心组件v1的兼容性信息](versions.md#main-pars_title_236368006) 。

## Edit Dialog {#edit-dialog}

The edit dialog allows the content author to define the title text as well as select the heading level.

>[!NOTE]
>
>标题的空值将导致显示页面标题。

![](assets/chlimage_1-91.png)

就地编辑器还可用于编辑标题组件的文本。

![](assets/chlimage_1-37.png)

## 设计对话框 {#design-dialog}

设计对话框允许模板作者定义标题组件在由内容作者创建时将具有的默认标题级别。

![](assets/chlimage_1-92.png)

## 技术详细信息 {#technical-details}

有关标题组件的最新技术文 [档可在GitHub上找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/title/v1/title)。

整个核心组件项目可从GitHub下载。

有关开发核心组件的更多详细信息，请参阅核 [心组件开发人员文档](developing.md)。
