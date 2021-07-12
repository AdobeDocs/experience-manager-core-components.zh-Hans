---
title: 体验片段组件
description: 体验片段组件允许内容作者向页面添加体验片段变量。
role: Architect, Developer, Admin, User
exl-id: 103f729a-084d-4b6a-a239-d8ef8902eb95
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '816'
ht-degree: 1%

---

# 体验片段组件{#experience-fragment-component}

核心组件体验片段组件允许内容作者在支持本地化网站结构的同时，将体验片段变量放置到页面上。

## 使用 {#usage}

核心组件体验片段组件允许内容作者从现有体验片段变量中进行选择，然后将一个体验片段变量放置到内容页面上。 体验片段组件还支持本地化的站点结构。

* 可以在[配置对话框](#configure-dialog)中定义组件的属性。
* 将组件添加到页面时的默认值，可在[设计对话框](#design-dialog)中定义。

## 本地化的站点结构支持 {#localized-site-structure}

体验片段组件自适应于本地化的站点结构，并根据页面的本地化呈现适当的体验片段。 要实现此目的，体验片段必须满足以下条件。

* 体验片段组件即会添加到模板。
* 该模板用于创建新内容页面，该页面是`/content/<site>`下本地化结构的一部分。
* 内容页面上引用的体验片段是`/content/experience-fragments`下本地化体验片段结构的一部分，该结构遵循与`/content/<site>`下站点相同的模式，包括使用相同的组件名称。

在这种情况下，与当前页面具有相同本地化（语言、Blueprint或Live Copy）的片段将作为模板的一部分呈现。

此行为仅限于添加到模板的体验片段组件。 添加到单个内容页面的体验片段组件将呈现组件中配置的确切体验片段演绎版。

* 有关体验片段组件的本地化功能如何工作的示例，请参阅[以下部分](#example)。
* 有关核心组件的本地化功能如何协同工作的示例，请参阅核心组件页面](/help/get-started/localization.md)的[本地化功能。

### 示例 {#example}

假设您的内容如下所示：

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

请注意，下面的`/content/experience-fragments/wknd`结构反映`/content/wknd`的结构。

在这种情况下，如果体验片段组件`/content/experience-fragments/wknd/us/en/footerTextXf`放置在模板上，则基于该模板创建的本地化页面将自动呈现与本地化内容页面对应的本地化体验片段。

因此，如果您导航到使用相同模板的`/content/wknd/ch/de`下的内容页面，将呈现`/content/experience-fragments/wknd/ch/de/footerTextXf`，而不是`/content/experience-fragments/wknd/us/en/footerTextXf`。

### 回退 {#fallback}

体验片段组件将尝试按以下顺序查找相应的本地化组件。

1. 首先，它会尝试找到语言根。
1. 如果未找到，则会尝试查找蓝图。
1. 如果未找到，则会尝试查找Live Copy。
1. 如果未找到，则默认使用组件中配置的体验片段。

## 版本和兼容性 {#version-and-compatibility}

体验片段组件的当前版本为v1，该版本在2019年9月随核心组件2.6.0版引入，在本文档中进行了描述。

下表详细列出了组件的所有受支持版本、组件版本与之兼容的AEM版本，以及指向以前版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | 兼容 | 兼容 | 兼容 |

有关核心组件版本和版本的更多信息，请参阅文档[核心组件版本](/help/versions.md)。

## 组件输出示例 {#sample-component-output}

要体验体验片段组件并查看其配置选项以及HTML和JSON输出的示例，请访问[组件库](https://adobe.com/go/aem_cmp_library_xf)。

## 技术详细信息 {#technical-details}

有关体验片段组件[的最新技术文档可在GitHub](https://adobe.com/go/aem_cmp_tech_xf_v1)上找到。

有关开发核心组件的更多详细信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## 配置对话框 {#configure-dialog}

配置对话框允许内容作者选择应在页面上呈现的体验片段变量。

![体验片段组件的编辑对话框](/help/assets/experience-fragment-edit.png)

使用&#x200B;**打开选择对话框**&#x200B;按钮打开组件选择器，以选择要添加到内容页面的体验片段组件变量。

如果您将体验片段组件添加到模板，请注意，如果体验片段已本地化，则它将自动本地化，因此页面上呈现的内容可能与您明确选择的组件有所不同。 [有关更多信](#example) 息，请参阅上面的示例。

您还可以定义&#x200B;**ID**。 此选项允许控制HTML和[数据层](/help/developing/data-layer/overview.md)中组件的唯一标识符。

* 如果留为空白，则会自动为您生成唯一ID，并且可以通过检查生成的页面找到该ID。
* 如果指定了ID，则作者有责任确保该ID是唯一的。
* 更改ID可能会影响CSS、JS和数据层跟踪。

## “设计”对话框 {#design-dialog}

设计对话框允许模板作者定义可供内容作者使用的选项，这些选项在放置体验片段组件时使用体验片段组件和设置的默认值。

### “样式”选项卡 {#styles-tab}

体验片段组件支持AEM [样式系统](/help/get-started/authoring.md#component-styling)。
