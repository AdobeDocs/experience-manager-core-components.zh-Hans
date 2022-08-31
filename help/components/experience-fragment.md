---
title: 体验片段组件
description: 使用体验片段组件，内容作者可以向页面添加体验片段变体。
role: Architect, Developer, Admin, User
exl-id: 103f729a-084d-4b6a-a239-d8ef8902eb95
source-git-commit: 327c239b02e0aecee878784c918bfa98d960530e
workflow-type: ht
source-wordcount: '893'
ht-degree: 100%

---

# 体验片段组件{#experience-fragment-component}

使用核心组件体验片段组件，内容作者可以在支持本地化网站结构时，在页面上放置体验片段变体。

## 用途 {#usage}

使用核心组件体验片段组件，内容作者可以从现有体验片段变体中选择并将其放在内容页面上。体验片段组件还支持本地化的网站结构。

* 组件的属性可在[“配置”对话框](#configure-dialog)中定义。
* 将组件添加到页面时的组件默认值可以在[“设计”对话框](#design-dialog)中定义。

## 版本和兼容性 {#version-and-compatibility}

体验片段组件的当前版本是 v2，此版本随 2022 年 2 月的核心组件发行版 2.18.0 的发布引入，具体说明见本文。

下表详细说明了该组件的所有受支持版本、与该组件的版本兼容的 AEM 版本以及指向早期版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v2 | - | 兼容 | 兼容 |
| [v1](v1/experience-fragment.md) | 兼容 | 兼容 | 兼容 |

有关核心组件版本的更多信息，请参阅文档[核心组件版本](/help/versions.md)。

## 本地化网站结构支持 {#localized-site-structure}

体验片段组件可以适应本地化的网站结构，并根据页面的本地化渲染正确的体验片段。为此，体验片段必须满足以下条件。

* 模板中添加了体验片段组件。
* 该模板用于创建新的内容页面，这些页面是 `/content/<site>` 以下的本地化结构的一部分。
* 在内容页面上引用的体验片段属于 `/content/experience-fragments` 以下的本地化体验结构的一部分，遵循与 `/content/<site>` 以下的网站相同的模式，包括使用相同的组件名称。

在本例中，与当前页面具有相同本地化（语言、Blueprint 或实时副本）的片段将作为模板的一部分渲染。

此行为仅限添加到模板的体验片段组件。添加到单独内容页面的体验片段组件将渲染在页面中配置的准确体验片段再现。

* 有关体验片段组件本地化功能的工作方式示例，请参阅[以下部分](#example)。
* 有关核心组件的本地化功能如何配合使用的示例，请参阅[核心组件页面的本地化功能](/help/get-started/localization.md)。

### 示例 {#example}

假设您的内容与以下内容类似：

```
/content
+-- experience-fragments
   \-- wknd
      +-- language-masters
      +-- us
         +-- en
            +-- footerTextXf
            \-- headerTextXf
         \-- es
            +-- footerTextXf
            \-- headerTextXf
      \-- ch
         +-- de
            +-- footerTextXf
            \-- headerTextXf
         +-- fr
            +-- footerTextXf
            \-- headerTextXf
         \-- it
            +-- footerTextXf
            \-- headerTextXf
+-- wknd
   +-- language-masters
   +-- us
      +-- en
      \-- es
   +-- ch
      +-- de
      +-- fr
      \-- it
+-- wknd-events
\-- wknd-shop
```

请注意，`/content/experience-fragments/wknd` 以下的结构镜像了 `/content/wknd` 的结构。

在本例中，如果体验片段组件 `/content/experience-fragments/wknd/us/en/footerTextXf` 放在模板上，则根据该模板创建的本地化页面将自动渲染与本地化内容页面对应的本地化体验片段。

因此，如果您要导航到 `/content/wknd/ch/de` 下使用同一模板的内容页面，则将渲染 `/content/experience-fragments/wknd/ch/de/footerTextXf` 而不是 `/content/experience-fragments/wknd/us/en/footerTextXf`。

### 回退 {#fallback}

体验片段组件将尝试按照以下顺序查找对应的本地化组件。

1. 首先尝试查找语言根。
1. 如果未找到，则尝试查找 Blueprint。
1. 如果未找到，则尝试查找实时副本。
1. 如果未找到，则它会默认为在组件中配置的体验片段。

## 示例组件输出 {#sample-component-output}

要对体验片段组件进行体验并查看其配置选项示例以及 HTML 和 JSON 输出，请访问[组件库](https://adobe.com/go/aem_cmp_library_xf_cn)。

## 技术详细信息 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_xf_v2_cn)有关体验片段组件的最新技术文档。

在[核心组件开发人员文档](/help/developing/overview.md)中可找到有关开发核心组件的其他详细信息。

## “配置”对话框 {#configure-dialog}

利用“配置”对话框，内容作者可以选择应在页面上渲染的体验片段变体。

![体验片段组件的“编辑”对话框](/help/assets/experience-fragment-edit.png)

使用&#x200B;**打开选择对话框**&#x200B;按钮可打开组件选择器，来选择要添加到内容页面中的体验片段组件变体。

如果您将体验片段组件添加到模板，请注意，如果体验片段已本地化，则它会自动本地化，因此根据您明确选择的组件，页面上渲染的内容会变化。有关更多信息，[请参阅以上示例](#example)。

您还可以定义 **ID**。利用此选项，可以控制 HTML 和 [Data Layer](/help/developing/data-layer/overview.md) 中的组件的唯一标识符。

* 如果留空，系统会自动为您生成一个唯一 ID，可以通过检查结果页面找到该 ID。
* 如果指定一个 ID，作者有责任确保它是唯一的。
* 更改此 ID 会对 CSS、JS 和数据层跟踪产生影响。

### “样式”选项卡 {#styles-tab-edit}

![体验片段组件“编辑”对话框的“样式”选项卡](/help/assets/experience-fragment-edit-styles.png)

体验片段组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。

使用下拉菜单选择要应用于该组件的样式。在“编辑”对话框中所做的选择与从组件工具栏中选择的操作效果相同。

必须在[“设计”对话框](#design-dialog)中为此组件配置样式，以便下拉菜单可用。

## “设计”对话框 {#design-dialog}

使用“设计”对话框，模板作者可以定义哪些选项可供使用体验片段组件的内容作者使用，以及在放置体验片段组件时的默认设置。

### “样式”选项卡 {#styles-tab}

体验片段组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。
