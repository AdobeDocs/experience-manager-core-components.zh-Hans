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
source-git-commit: 144494c03ffed068b403d80f62fdfddc73a53748

---


# Core Components Versions{#core-components-versions}

核心组件的当前发行版为2.4.0，与AEM6.5兼容。它于2019年月发布，作为第2.0.0版的次要更新。版本2.0.0引入了新组件以及v更新现有组件。

See the section [Release History and Compatibility](#versions-and-releases) of this document for more information.

You can also check out the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library.html), which showcases the current release of the Core Components and gives examples of their usage.

## Versions and Releases {#versions-and-releases}

核心组件通过GitHub分发。这允许Adobe更快地向组件添加功能，并允许在AEM发行周期之外进行社区输入。

核心组件可通过与其兼容的定义AEM版本提供。这意味着一个AEM版本可能支持核心组件的多个版本或版本。这比以前的基础组件更灵活，该组件绑定到特定版本的AEM。

### 版本 {#versions}

The major iteration of the Core Components are the **versions**. 每个组件都有一个版本。Versions are denoted with **v** appended with a nonzero, positive integer such as v1 and v2. 版本只会增加不兼容的更改，这通常是引入新特性和功能的情况。

开发人员和管理员可以通过资源类型路径中的数字以及实现完全限定的Java类名称识别核心组件的版本。This version number represents a major version as defined by [semantic versioning guidelines](https://semver.org/).

For more details about core component versions, see the [developer documentation of the Core Components](guidelines.md).

### Releases {#releases}

The core components are made available through **releases** and [represent the actual published artifacts available on GitHub](https://github.com/adobe/aem-core-wcm-components/releases). 发行版以X.Y.Z格式表示，并将所有核心组件作为可交付包一起收集。

* **发行版** 可引入新版本的现有组件以及全新组件以及标准缺陷修复。这由发行编号的X组件中的增量表示。

* **重要版本** 可以为现有版本的组件以及缺陷修复引入新功能。这由发行编号的Y组件中的增量表示。

* **次要版本** 只包含错误修复。这由发行编号的Z组件中的增量表示。

>[!NOTE]
>
>发行版可以包含同一组件的多个版本。
>
>同一组件版本可显示在多个版本中。

## Release History and Compatibility {#release-history-and-compatibility}

核心组件最初与AEM6.3一起发布，旨在灵活、兼容所有支持的AEM版本。因此，组件的发行可能包含同一组件的多个版本。

下表说明了核心组件版本与版本中包含的组件版本的兼容性。

### Release History &amp; Supported AEM Versions {#release-history-supported-aem-versions}

The following table, the contents of which are [available on GitHub with full release details](https://github.com/adobe/aem-core-wcm-components/releases), gives an overview of the releases of the Core Components and their compatibility with AEM releases and Java versions.

| Release | 描述 | AEM 6.3 | AEM 6.4 | AEM 6.5 | Java |
|---|---|---|---|---|---|
| [2.4.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.4.0) | 此版本引入了内容片段列表组件 | 6.3.3.0+ | 6.4.2.0+ | 6.5.0.0+ | 8, 11 |
| [2.3.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.2) | 此版本侧重于对组件库进行细化，但还包含对分隔符组件的一些功能增强功能 | 6.3.3.0+ | 6.4.2.0+ | 6.5.0.0+ | 8 |
| [2.3.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.0) | 此版本侧重于组件库以及引入新的分隔符组件，但还包含对图像组件的一些功能增强功能 | 6.3.3.0+ | 6.4.2.0+ | - | 8 |
| [2.2.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.2) | 此版本主要侧重于缺陷修复，但还包含针对传送组件的一些功能增强功能 | 6.3.3.0+ | 6.4.2.0+ | - | 8 |
| [2.2.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.0) | 引入的制表符和传送组件，对图像、页面和标题组件以及增强跟踪的改进 | 6.3.3.0+ | 6.4.2.0+ | - | 8 |
| [2.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.1.0) | 引入的Teaser组件、图像组件改进和大量错误修复 | 6.3.3.0+ | 6.4.2.0+ | - | 8 |
| [2.0.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.8) | Bugfix版本 | 6.3.2.0+ | 6.4.0.0+ | - | 8 |
| [2.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.6) | 附加的改进、缺陷修复以及小改进，包括支持图像翻转。 | 6.3.2.0+ | 6.4.0.0+ | - | 8 |
| [2.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.4) | 大多数改进、缺陷修复以及对图像、页面和内容片段组件的一些细微改进 | 6.3.2.0+ | 6.4.0.0+ | - | 8 |
| [2.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.0) | 引入了导航、语言导航和快速搜索组件。为所有组件实现样式系统。 | 6.3.2.0+ | 6.4.0.0+ | - | 8 |
| [1.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.1.0) | 在所有组件上实施JSON导出，引入内容片段组件 | 6.3.1.0 | 6.4.0.0+ | - | 8 |
| [1.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.6) | 图像组件的几个修复 | 6.3.0.0+ | 6.4.0.0+ | - | 8 |
| [1.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.4) | 页面组件的修复、图像组件、各种全局修复和改进 | 6.3.0.0+ | 6.4.0.0+ | - | 8 |
| [1.0.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.all-1.0.2) | 针对图像组件中的动画GIF图像修复 | 6.3.0.0+ | 6.4.0.0+ | - | 7 |
| [1.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.0) | 核心组件的初始发行版 | 6.3.0.0+ | 6.4.0.0+ | - | 7 |

>[!NOTE]
>
>As with AEM, Adobe recommends that developers use the [latest release and versions of the Core Components](https://github.com/adobe/aem-core-wcm-components/releases/latest) available that is compatible with the version of AEM that they are running in order to benefit from the most up-to-date fixes and features.

### Component Versions &amp; Releases {#component-versions-and-releases}

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
