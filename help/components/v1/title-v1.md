---
title: 标题组件 (v1)
description: 核心组件标题组件是章节标题组件，具备就地编辑的功能。
index: n
role: Architect, Developer, Admin, User
exl-id: 79549ac0-82f2-4ea0-9cce-d534d0b47b5c
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 100%

---

# 标题组件 (v1) {#title-component-v}

核心组件标题组件是章节标题组件，具备就地编辑的功能。

## 用途 {#usage}

标题组件旨在用作内容章节的标题。

可用的标题级别可由模板作者在[“设计”对话框](#design-dialog)中定义。内容编辑者可以在[“编辑”对话框](#edit-dialog)中从可用标题级别选择。为了增加便利性，可以简单地就地编辑标题文本。

## 版本和兼容性 {#version-and-compatibility}

本文档介绍了标题组件 (v1)，它最初随带 AEM 6.3 的核心组件 1.0.0 版引入。

下表列出了标题组件 (v1) 的兼容性。

| AEM 版本 | 标题组件 v1 |
|--- |--- |
| 6.3 | 兼容 |
| 6.4 | 兼容 |

>[!CAUTION]
>
>本文档介绍了版本 1 的标题组件。
>
>有关当前版本的标题组件的详细信息，请参阅[标题组件](/help/components/title.md)文档。

## 示例组件输出 {#sample-component-output}

以下是摘自 [We.Retail](https://helpx.adobe.com/cn/experience-manager/6-4/sites/developing/using/we-retail.html) 的示例。

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
>从核心组件执行 JSON 导出需要版本 1.1.0 的核心组件。 有关更多信息，请参阅[核心组件 v1 的兼容性信息](/help/versions.md)。

## “编辑”对话框 {#edit-dialog}

内容作者可以使用“编辑”对话框定义标题文本以及选择标题级别。

>[!NOTE]
>
>标题的值为空将导致显示页面标题。

![](/help/assets/chlimage_1-91.png)

就地编辑器也可以用于编辑标题组件的文本。

![](/help/assets/chlimage_1-37.png)

## “设计”对话框 {#design-dialog}

模板作者可以使用“设计”对话框定义内容作者在创建标题组件时具有的默认标题级别。

![](/help/assets/chlimage_1-92.png)

## 技术详细信息 {#technical-details}

[在 GitHub 上可找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/title/v1/title)有关标题组件的最新技术文档。

从 GitHub 可下载整个核心组件项目。

在[核心组件开发人员文档](/help/developing/overview.md)中可找到有关开发核心组件的其他详细信息。
