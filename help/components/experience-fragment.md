---
title: 体验片段组件
description: 体验片段组件允许内容作者向页面添加体验片段变量。
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

---


# 体验片段组件{#experience-fragment-component}

核心组件体验片段组件允许内容作者在支持本地化站点结构的同时将体验片段变体放置在页面上。

## 使用情况 {#usage}

核心组件体验片段组件允许内容作者从现有体验片段变量中进行选择，并将其放在内容页面上。 体验片段组件还支持本地化的站点结构。

* 组件的属性可以在配置对话框中 [定义](#configure-dialog)。
* 将组件添加到页面时的默认值可以在设计对话框中 [定义](#design-dialog)。

## 本地化的站点结构支持 {#localized-site-structure}

体验片段组件可适应本地化的站点结构，并根据页面的本地化呈现适当的体验片段。 为此，体验片段必须满足以下条件。

* 体验片段组件会添加到模板。
* 该模板用于创建新内容页面，该页面是下面本地化结构的一部分 `/content/<site>`。
* 内容页面上引用的体验片段是下面本地化的体验片段结构的一部分，该结构遵循与下面的站点相同的模式，包括使 `/content/experience-fragments``/content/<site>` 用相同的组件名称。

在这种情况下，具有与当前页面相同的本地化（语言、Blueprint或Live Copy）的片段将作为模板的一部分呈现。

此行为仅限于添加到模板的体验片段组件。 添加到单个内容页面的体验片段组件将呈现在组件中配置的确切体验片段再现。

* 有关体验片段组件的本地化功能如何工作的示例，请参 [阅以下部分](#example)。
* 有关核心组件的本地化功能如何协同工作的示例，请参阅核 [心组件的本地化功能页面](/help/get-started/localization.md)。

### 示例 {#example}

假设您的内容类似于：

```
/content
+-- experience-fragments
   \-- we-retail
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
+-- we-retail
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

请注意，下面的 `/content/experience-fragments/we-retail` 结构反映了的结构 `/content/we-retail`。

在这种情况下，如果将体验片段组件放 `/content/experience-fragments/we-retail/us/en/footerTextXf` 置到模板上，则基于该模板创建的本地化页面将自动呈现与本地化内容页面相对应的本地化体验片段。

因此，如果您导航到使用相同模 `/content/we-retail/ch/de` 板的下方的内容页面，将 `/content/experience-fragments/we-retail/ch/de/footerTextXf` 呈现而不是呈现 `/content/experience-fragments/we-retail/us/en/footerTextXf`。

### 回退 {#fallback}

体验片段组件将尝试按照以下顺序查找相应的本地化组件。

1. 首先，它会尝试找到语言根。
1. 如果找不到，则会尝试查找蓝图。
1. 如果找不到，它会尝试查找Live Copy。
1. 如果未找到，则默认为组件中配置的体验片段。

## 版本和兼容性 {#version-and-compatibility}

体验片段组件的当前版本为v1，该版本于2019年9月随核心组件的2.6.0版一起推出，本文档对此进行了说明。

下表详细列出了组件的所有受支持版本、与组件版本兼容的AEM版本，以及指向先前版本的文档的链接。

| 组件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM作为云服务 |
|--- |--- |--- |---|---|
| v1 | 兼容 | 兼容 | 兼容 | 兼容 |

有关核心组件版本和版本的详细信息，请参阅文档核 [心组件版本](/help/versions.md)。

## 示例组件输出 {#sample-component-output}

要体验体验片段组件以及查看其配置选项以及HTML和JSON输出的示例，请访问组件 [库](https://adobe.com/go/aem_cmp_library_xf)。

## 技术详细信息 {#technical-details}

有关体验片段组件的最新技 [术文档可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_xf_v1)。

有关开发核心组件的更多详细信息，请参阅核 [心组件开发人员文档](/help/developing/overview.md)。

## 配置对话框 {#configure-dialog}

配置对话框允许内容作者选择应在页面上呈现的体验片段变量。

![](/help/assets/screen-shot-2019-08-23-10.49.21.png)

使用“打 **开选择对话框** ”按钮打开组件选择器以选择要添加到内容页面的体验片段组件变体。

如果您将体验片段组件添加到模板，请注意，如果体验片段已本地化，则它将自动本地化，因此页面上呈现的内容可能与您显式选择的组件不同。 [有关详细信息](#example) ，请参阅上面的示例。

## 设计对话框 {#design-dialog}

设计对话框允许模板作者定义可供使用体验片段组件的内容作者使用的选项以及放置体验片段组件时设置的默认值。

![](/help/assets/screen-shot-2019-08-23-10.48.36.png)

体验片段组件支持AEM样 [式系统](/help/get-started/authoring.md#component-styling)。
