---
title: 标题组件(v1)
seo-title: 标题组件(v1)
description: 核心组件标题组件是具有就地编辑功能的章节标题组件。
seo-description: 核心组件标题组件是具有就地编辑功能的章节标题组件。
uuid: 5c4d276c-f0 be-4122-a15 e-3f7443 d8 b209
content-type: 引用
products: SG_ EXPERIENCE MANAGER/CORECOMMPANES-new
discoiquuid: a028edbef-2957-410c-9bab-a7040 c350 f2 f
index: n
translation-type: tm+mt
source-git-commit: 1bbec9b1f109df88964dce051a58d111bf6cafaa

---


# 标题组件(v1){#title-component-v}

核心组件标题组件是具有就地编辑功能的章节标题组件。

## 使用情况 {#usage}

标题组件旨在用作内容部分的标题或标题。

可用的标题级别可由设计对话框中的模板作者 [定义](title-v1.md#main-pars_title_1995166862)。内容编辑器可以从 [编辑对话框](title-v1.md#main-pars_title)中的可用标题级别中进行选择。为了方便起见，还提供了简单的位置文本就地编辑功能。

## 版本和兼容性 {#version-and-compatibility}

本文档描述了标题组件的v1，该组件最初随AEM6.3的核心组件版本1.0.0一起引入。

下表列出了标题组件的v1的兼容性。

| AEM 版本 | 标题组件v1 |
|--- |--- |
| 6.3 | 兼容 |
| 6.4 | 兼容 |

>[!CAUTION]
>
>本文档描述标题组件的版本1。
>
>有关标题组件当前版本的详细信息，请参阅 [标题组件](title.md) 文档。

## 示例组件输出 {#sample-component-output}

以下示例取自 [We. Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)。

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
>核心组件中的JSON导出需要核心组件版本1.1.0。有关更多信息，请参见核心组件v [](versions.md#main-pars_title_236368006) 的兼容性信息。

## 编辑对话框 {#edit-dialog}

编辑对话框允许内容作者定义标题文本以及选择标题级别。

>[!NOTE]
>
>标题的空值将导致显示页面标题。

![](assets/chlimage_1-91.png)

就地编辑器还可用于编辑标题组件的文本。

![](assets/chlimage_1-37.png)

## 设计对话框 {#design-dialog}

设计对话框允许模板作者定义内容作者创建时标题组件将具有的默认标题级别。

![](assets/chlimage_1-92.png)

## 技术详细信息 {#technical-details}

有关标题组件 [的最新技术文档可在GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/title/v1/title)上找到。

可以从GitHub下载整个核心组件项目。

有关开发核心组件的更多详细信息，请参阅 [核心组件开发人员文档](developing.md)。
