---
title: 核心组件版本
seo-title: 核心组件版本
description: 核心组件作为发行版发布，它们可能包含同一核心组件的多个版本。本文档介绍了哪些版本和版本以及如何了解与核心组件和AEM的兼容性。
seo-description: 核心组件作为发行版发布，它们可能包含同一核心组件的多个版本。本文档介绍了哪些版本和版本以及如何了解与核心组件和AEM的兼容性。
uuid: a916a923-8c5e-456a-84b5-b52228 e21434
contentOwner: 用户
content-type: 引用
topic-tags: introduction
products: SG_ EXPERIENCE MANAGER/CORECOMMPANES-new
discoiquuid: a3a98b2f-65bf-4493-82ad-01717938dfc
translation-type: tm+mt
source-git-commit: 63e75079e41d3091ca57bfc3129e700675bf4939

---


# 核心组件版本{#core-components-versions}

核心组件的当前发行版为2.6.0，与AEM6.5兼容。它于2019年月发布，作为第2.0.0版的重要更新。版本2.0.0引入了新组件以及v更新现有组件。

有关更多信息，请参阅本文档的 [“发行历史记录和兼容性](#versions-and-releases) ”。

您也可以查看 [组件库，该库](http://opensource.adobe.com/aem-core-wcm-components/library.html)展示了核心组件的当前版本并提供了其用法示例。

## 版本和版本 {#versions-and-releases}

核心组件通过GitHub分发。这允许Adobe更快地向组件添加功能，并允许在AEM发行周期之外进行社区输入。

核心组件可通过与其兼容的定义AEM版本提供。这意味着一个AEM版本可能支持核心组件的多个版本或版本。这比以前的基础组件更灵活，该组件绑定到特定版本的AEM。

### 版本 {#versions}

核心组件的主要迭代版本是 **版本**。每个组件都有一个版本。版本表示 **v** 附加了一个非零的正整数，如v和v2。版本只会增加不兼容的更改，这通常是引入新特性和功能的情况。

开发人员和管理员可以通过资源类型路径中的数字以及实现完全限定的Java类名称识别核心组件的版本。此版本号表示 [由语义版本控制准则定义的主要版本](https://semver.org/)。

有关核心组件版本的更多详细信息，请参阅核心组件 [的开发人员文档](guidelines.md)。

### 发行版 {#releases}

核心组件可通过 **发行版** 获得， [并代表GitHub上可用的实际发布的伪像](https://github.com/adobe/aem-core-wcm-components/releases)。发行版以X.Y.Z格式表示，并将所有核心组件作为可交付包一起收集。

* **发行版** 可引入新版本的现有组件以及全新组件以及标准缺陷修复。这由发行编号的X组件中的增量表示。
* **重要版本** 可以为现有版本的组件以及缺陷修复引入新功能。这由发行编号的Y组件中的增量表示。
* **次要版本** 只包含错误修复。这由发行编号的Z组件中的增量表示。

>[!NOTE]
>
>发行版可以包含同一组件的多个版本。
>
>同一组件版本可显示在多个版本中。

## 发行历史和兼容性 {#release-history-and-compatibility}

核心组件最初与AEM6.3一起发布，旨在灵活、兼容所有支持的AEM版本。因此，组件的发行可能包含同一组件的多个版本。

下表说明了核心组件版本与版本中包含的组件版本的兼容性。

### 发行历史记录和支持的AEM版本 {#release-history-supported-aem-versions}

下表列出了在GitHub上 [提供完整版本详细信息](https://github.com/adobe/aem-core-wcm-components/releases)的内容，包括核心组件版本及其与AEM版本和Java版本的兼容性。

| Release | 描述 | AEM 6.3 | AEM 6.4 | AEM 6.5 | Java | 发布日期 |
|---|---|---|---|---|---|---|
| [2.6.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.6.0) | 此版本引入了新的体验片段组件 | 6.3.3.0+ | 6.4.2.0+ | 6.5.0.0+ | 8, 11 | 2019年月 |
| [2.5.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.5.0) | 此版本引入了新的Accordion、Button、Container和Download组件。 | 6.3.3.0+ | 6.4.2.0+ | 6.5.0.0+ | 8, 11 | 2019年月25日 |
| [2.4.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.4.0) | 此版本引入了内容片段列表组件 | 6.3.3.0+ | 6.4.2.0+ | 6.5.0.0+ | 8, 11 | 2019年月日 |
| [2.3.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.2) | 此版本侧重于对组件库进行细化，但还包含对分隔符组件的一些功能增强功能 | 6.3.3.0+ | 6.4.2.0+ | 6.5.0.0+ | 8 | 2019年月14日 |
| [2.3.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.0) | 此版本侧重于组件库以及引入新的分隔符组件，但还包含对图像组件的一些功能增强功能 | 6.3.3.0+ | 6.4.2.0+ | - | 8 | 2019年月11日 |
| [2.2.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.2) | 此版本主要侧重于缺陷修复，但还包含针对传送组件的一些功能增强功能 | 6.3.3.0+ | 6.4.2.0+ | - | 8 | 2018年11月27日 |
| [2.2.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.0) | 引入的制表符和传送组件，对图像、页面和标题组件以及增强跟踪的改进 | 6.3.3.0+ | 6.4.2.0+ | - | 8 | 2018年10月16日 |
| [2.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.1.0) | 引入的Teaser组件、图像组件改进和大量错误修复 | 6.3.3.0+ | 6.4.2.0+ | - | 8 | 2018年月13日 |
| [2.0.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.8) | Bugfix版本 | 6.3.2.0+ | 6.4.0.0+ | - | 8 | 2018年月12日 |
| [2.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.6) | 附加的改进、缺陷修复以及小改进，包括支持图像翻转。 | 6.3.2.0+ | 6.4.0.0+ | - | 8 | 2018年月11日 |
| [2.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.4) | 大多数改进、缺陷修复以及对图像、页面和内容片段组件的一些细微改进 | 6.3.2.0+ | 6.4.0.0+ | - | 8 | 2018年月日 |
| [2.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.0) | 引入了导航、语言导航和快速搜索组件。为所有组件实现样式系统。 | 6.3.2.0+ | 6.4.0.0+ | - | 8 | 2016年月16日 |
| [1.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.1.0) | 在所有组件上实施JSON导出，引入内容片段组件 | 6.3.1.0 | 6.4.0.0+ | - | 8 | 2017年10月10日 |
| [1.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.6) | 图像组件的几个修复 | 6.3.0.0+ | 6.4.0.0+ | - | 8 | 2017年月日 |
| [1.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.4) | 页面组件的修复、图像组件、各种全局修复和改进 | 6.3.0.0+ | 6.4.0.0+ | - | 8 | 2017年月26日 |
| [1.0.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.all-1.0.2) | 针对图像组件中的动画GIF图像修复 | 6.3.0.0+ | 6.4.0.0+ | - | 7 | 2017年月22日 |
| [1.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.0) | 核心组件的初始发行版 | 6.3.0.0+ | 6.4.0.0+ | - | 7 | 2017年月20日 |

>[!NOTE]
>
>与AEM一样，Adobe建议开发人员使用核心组件的 [最新版本和版本，这些组件](https://github.com/adobe/aem-core-wcm-components/releases/latest) 与AEM版本兼容，可从最新的修复和功能中受益。

### 组件版本和发行版 {#component-versions-and-releases}

下表详细说明了核心组件版本包含的组件版本。

|  | 版本1.0.0-1.0.6 | 版本1.1.0 | 版本2.0.0-2.0.8 | 版本2.1.0 | 版本2.2。-2.2.0 | 2.3.0 |
|---|---|---|---|---|---|---|
| **[Page](page.md)** | v1 | v1 | v1，v2 | v1，v2 | v1，v2 | v1，v2 |
| **[标题](title.md)** | v1 | v1 | v1，v2 | v1，v2 | v1，v2 | v1，v2 |
| **[图像](image.md)** | v1 | v1 | v1，v2 | v1，v2 | v1，v2 | v1，v2 |
| **[列表](list.md)** | v1 | v1 | v1，v2 | v1，v2 | v1，v2 | v1，v2 |
| **[痕迹导航](breadcrumb.md)** | v1 | v1 | v1，v2 | v1，v2 | v1，v2 | v1，v2 |
| **[社交媒体共享](sharing.md)** | v1 | v1 | v1 | v1 | v1 | v1 |
| **[表单容器](form-container.md)** | v1 | v1 | v1，v2 | v1，v2 | v1，v2 | v1，v2 |
| **[表单文本](form-text.md)** | v1 | v1 | v1，v2 | v1，v2 | v1，v2 | v1，v2 |
| **[表单选项](form-options.md)** | v1 | v1 | v1，v2 | v1，v2 | v1，v2 | v1，v2 |
| **[隐藏的表单](form-hidden.md)** | v1 | v1 | v1，v2 | v1，v2 | v1，v2 | v1，v2 |
| **[表单按钮](form-button.md)** | v1 | v1 | v1，v2 | v1，v2 | v1，v2 | v1，v2 |
| **[内容片段](content-fragment-component.md)** |  | 沙盒 | v1 | v1 | v1 | v1 |
| **[导航](navigation.md)** |  |  | v1 | v1 | v1 | v1 |
| **[语言导航](language-navigation.md)** |  |  | v1 | v1 | v1 | v1 |
| **[快速搜索](quick-search.md)** |  |  | v1 | v1 | v1 | v1 |
| **[Teaser](teaser.md)** |  |  |  | v1 | v1 | v1 |
| **[选项卡](tabs.md)** |  |  |  |  | v1 | v1 |
| **[Carousel](carousel.md)** |  |  |  |  | v1 | v1 |
| **[分隔符](separator.md)** |  |  |  |  |  | v1 |

## 文档 {#documentation}

[使用核心组件](authoring.md) 创作描述了核心组件以及内容作者和模板作者公开的功能。每个组件详细记录。

[组件库](http://opensource.adobe.com/aem-core-wcm-components/library.html) 是大多数核心组件的当前版本展示，illustrating如何使用它们。

[开发核心组件](developing.md) 描述核心组件的技术功能、如何在项目中使用这些组件、如何自定义和最佳实践。

[核心组件介绍](introduction.md) 概述了各个版本、使用案例和支持的核心组件兼容性。
