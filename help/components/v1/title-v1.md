---
title: 标题组件(v1)
description: 核心组件标题组件是具有就地编辑功能的章节标题组件。
index: n
role: Architect, Developer, Administrator, Business Practitioner
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '342'
ht-degree: 2%

---


# 标题组件(v1){#title-component-v}

核心组件标题组件是具有就地编辑功能的章节标题组件。

## 使用 {#usage}

标题组件可用作内容部分的标题或标题。

可用标题级别可由模板作者在[设计对话框](#design-dialog)中定义。 内容编辑器可以从[编辑对话框](#edit-dialog)中的可用标题级别中进行选择。 为了更方便，还可以对标题文本进行简单的就地编辑。

## 版本和兼容性{#version-and-compatibility}

本文档描述了标题组件的v1，该组件最初随AEM 6.3的核心组件版本1.0.0引入。

下表列表了标题组件v1的兼容性。

| AEM 版本 | 标题组件v1 |
|--- |--- |
| 6.3 | 兼容 |
| 6.4 | 兼容 |

>[!CAUTION]
>
>本文档介绍标题组件的版本1。
>
>有关标题组件当前版本的详细信息，请参阅[标题组件](/help/components/title.md)文档。

## 示例组件输出{#sample-component-output}

以下是从[We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)取的示例。

### 屏幕快照 {#screenshot}

![](/help/assets/chlimage_1-36.png)

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
>从核心组件导出JSON需要1.1.0版的核心组件。 有关详细信息，请参阅核心组件v1](/help/versions.md)的[兼容性信息。

## 编辑对话框{#edit-dialog}

通过编辑对话框，内容作者可以定义标题文本并选择标题级别。

>[!NOTE]
>
>标题值为空将导致显示页面标题。

![](/help/assets/chlimage_1-91.png)

就地编辑器还可用于编辑标题组件的文本。

![](/help/assets/chlimage_1-37.png)

## 设计对话框{#design-dialog}

设计对话框允许模板作者定义标题组件在内容作者创建时将具有的默认标题级别。

![](/help/assets/chlimage_1-92.png)

## 技术详细信息{#technical-details}

有关标题组件[的最新技术文档可在GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/title/v1/title)上找到。

整个核心组件项目可从GitHub下载。

有关开发核心组件的更多详细信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。
