---
title: 标题组件(v1)
description: 核心组件标题组件是可进行就地编辑的区域标题组件。
index: n
role: Architect, Developer, Admin, User
exl-id: 79549ac0-82f2-4ea0-9cce-d534d0b47b5c
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 2%

---

# 标题组件(v1) {#title-component-v}

核心组件标题组件是可进行就地编辑的区域标题组件。

## 使用 {#usage}

标题组件将用作内容部分的标题或标题。

可用的标题级别可由模板作者在[设计对话框](#design-dialog)中定义。 内容编辑器可以从[编辑对话框](#edit-dialog)的可用标题级别中进行选择。 为了方便起见，还提供了标题文本的简单就地编辑功能。

## 版本和兼容性 {#version-and-compatibility}

本文档介绍了标题组件的v1，该组件最初随AEM 6.3核心组件版本1.0.0一起引入。

下表列出了标题组件v1的兼容性。

| AEM 版本 | 标题组件v1 |
|--- |--- |
| 6.3 | 兼容 |
| 6.4 | 兼容 |

>[!CAUTION]
>
>本文档介绍标题组件版本1。
>
>有关标题组件当前版本的详细信息，请参阅[标题组件](/help/components/title.md)文档。

## 组件输出示例 {#sample-component-output}

以下是从[We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)获取的示例。

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
>从核心组件导出JSON时，需要安装核心组件版本1.1.0。 有关更多信息，请参阅核心组件v1](/help/versions.md)的[兼容性信息。

## 编辑对话框 {#edit-dialog}

编辑对话框允许内容作者定义标题文本并选择标题级别。

>[!NOTE]
>
>标题的空值将导致页面标题显示。

![](/help/assets/chlimage_1-91.png)

就地编辑器还可用于编辑标题组件的文本。

![](/help/assets/chlimage_1-37.png)

## “设计”对话框 {#design-dialog}

设计对话框允许模板作者定义标题组件在由内容作者创建时将具有的默认标题级别。

![](/help/assets/chlimage_1-92.png)

## 技术详细信息 {#technical-details}

有关标题组件[的最新技术文档，请参阅GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/title/v1/title)。

可以从GitHub下载整个核心组件项目。

有关开发核心组件的更多详细信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。
