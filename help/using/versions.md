---
title: 核心组件版本
description: 核心组件作为可能包含同一核心组件多个版本的发行版发布。 本文档介绍了哪些版本和版本以及如何了解与核心组件和AEM的兼容性。
translation-type: tm+mt
source-git-commit: 080f53582cfa758aa99ec491f261af7cde1f5ea7

---


# 核心组件版本 {#core-components-versions}

核心组件的当前版本为2.8.0，并且与 [AEM（作为云服务）和内部部署AEM](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html)[安装兼容](https://docs.adobe.com/content/help/en/experience-manager-65/user-guide/home.html) 。 它于2019年12月发布，作为版本2.0.0的重要更新。版本2.0.0引入了新组件以及现有组件的v2更新。

有关详细信 [息，请参阅本文档的发行历史](#versions-and-releases) 和兼容性一节。

您还可以查看组件 [库](https://adobe.com/go/aem_cmp_library)，它显示核心组件的当前版本并提供其使用示例。

## 版本和版本 {#versions-and-releases}

核心组件通过GitHub分发。 这使Adobe能够更快地向组件添加功能，并允许在AEM发布周期之外进行社区输入。

核心组件在定义的AEM版本中可用，这些版本与之兼容。 这意味着一个AEM版本可能支持核心组件的多个版本或版本。 这比以前与特定版本的AEM绑定的基础组件更具灵活性。

### 版本 {#versions}

核心组件的主要小版本是 **版本**。 每个组件都有一个版本。 版本用 **v** ，附加一个非零正整数（如v1和v2）表示。 版本仅会因不向后兼容的更改而递增，这通常是引入新特性和功能的情况。

开发人员和管理员可以按其资源类型路径中的数字和其实现的完全限定的Java类名称识别核心组件的版本。 此版本号表示由语义版本控制准则定义的 [主要版本](https://semver.org/)。

有关核心组件版本的更多详细信息，请参 [阅核心组件的开发人员文档](guidelines.md)。

### 版本 {#releases}

核心组件通过发行版提供 **** , [并代表GitHub上可用的实际已发布对象](https://github.com/adobe/aem-core-wcm-components/releases)。 版本以X.Y.Z格式的十进制数表示，并将所有核心组件作为可交付的包一起收集。

* **主要版本** ，可以引入现有组件的新版本，以及全新的组件和标准错误修复。 这由发行号的X组件中的增量表示。
* **重要版本** ，可向现有版本的组件引入新功能以及错误修复。 这由发行号的Y组件中的增量表示。
* **次要版本** ，仅包含错误修复。 这由发行号的Z分量中的增量表示。

>[!NOTE]
>
>版本可以包含同一组件的多个版本。
>
>同一版本的组件可显示在多个版本中。

## 发布历史和兼容性 {#release-history-and-compatibility}

核心组件最初随AEM 6.3一起发布，设计为灵活且与所有支持的AEM版本兼容。 因此，一个版本的组件可以包含同一组件的多个版本。

下表说明了核心组件版本的兼容性以及包含哪些版本的组件版本。

### 发布历史记录和支持的AEM版本 {#release-history-supported-aem-versions}

下表提供了GitHub的内容，其中包含 [完整版本详细信息](https://github.com/adobe/aem-core-wcm-components/releases)，概述了核心组件的版本及其与AEM版本和Java版本的兼容性。

| 版本 | 描述 | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM作为云服务 | Java | 发布日期 |
|---|---|---|---|---|---|---|---|
| [2.8.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.8.0) | 此版本侧重于修复，但增强了很小。 | 6.3.3.4+ | 6.4.4.0+ | 6.5.0.0+ | 连续 | 8, 11 | 2019年12月5日 |
| [2.7.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.7.0) | 此版本引入了新的嵌入组件 | 6.3.3.4+ | 6.4.4.0+ | 6.5.0.0+ | 连续 | 8, 11 | 2019 年 9 月 25 日 |
| [2.6.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.6.0) | 此版本引入了新的体验片段组件 | 6.3.3.4+ | 6.4.4.0+ | 6.5.0.0+ | 连续 | 8, 11 | 2019 年 9 月 6 日 |
| [2.5.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.5.0) | 此版本引入了新的Accordion、Button、Container和Download组件。 | 6.3.3.0+ | 6.4.2.0+ | 6.5.0.0+ | 连续 | 8, 11 | 2019年6月25日 |
| [2.4.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.4.0) | 此版本引入了内容片段列表组件 | 6.3.3.0+ | 6.4.2.0+ | 6.5.0.0+ | 连续 | 8, 11 | 2019年5月7日 |
| [2.3.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.2) | 此版本侧重于对组件库的细化，但同时包含对分隔符组件的一些功能增强 | 6.3.3.0+ | 6.4.2.0+ | 6.5.0.0+ | 连续 | 8 | 2019年3月14日 |
| [2.3.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.0) | 此版本侧重于组件库以及新的分隔符组件，但同时包含图像组件的一些功能增强 | 6.3.3.0+ | 6.4.2.0+ | - | - | 8 | 2019年2月11日 |
| [2.2.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.2) | 此版本主要侧重于错误修复，但还包含传送组件的一些功能增强 | 6.3.3.0+ | 6.4.2.0+ | - | - | 8 | 2018年11月27日 |
| [2.2.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.0) | 引入了选项卡和传送组件，对图像、页面和标题组件进行了改进，并增强了跟踪功能 | 6.3.3.0+ | 6.4.2.0+ | - | - | 8 | 2018年10月16日 |
| [2.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.1.0) | 引入了Teaser组件、图像组件改进和大量错误修复 | 6.3.3.0+ | 6.4.2.0+ | - | - | 8 | 2018年7月13日 |
| [2.0.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.8) | 错误修复版本 | 6.3.2.0+ | 6.4.0.0+ | - | - | 8 | 2018年6月12日 |
| [2.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.6) | 其他内在改进、错误修复和小改进，包括图像翻转支持。 | 6.3.2.0+ | 6.4.0.0+ | - | - | 8 | 2018年4月11日 |
| [2.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.4) | 大多数内在改进、错误修复以及对图像、页面和内容片段组件的一些小改进 | 6.3.2.0+ | 6.4.0.0+ | - | - | 8 | 2018年3月7日 |
| [2.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.0) | 引入了导航、语言导航和快速搜索组件。 为所有组件实现的样式系统。 | 6.3.2.0+ | 6.4.0.0+ | - | - | 8 | 2018年1月16日 |
| [1.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.1.0) | 在所有组件上实现JSON导出，介绍内容片段组件 | 6.3.1.0 | 6.4.0.0+ | - | - | 8 | 2017年10月10日 |
| [1.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.6) | 对图像组件的若干修复 | 6.3.0.0+ | 6.4.0.0+ | - | - | 8 | 2017年8月4日 |
| [1.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.4) | 页面组件、图像组件的修复、各种全局修复和改进 | 6.3.0.0+ | 6.4.0.0+ | - | - | 8 | 2017年4月26日 |
| [1.0.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.all-1.0.2) | 对图像组件中GIF动画图像的修复 | 6.3.0.0+ | 6.4.0.0+ | - | - | 7 | 2017年3月22日 |
| [1.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.0) | 核心组件的初始版本 | 6.3.0.0+ | 6.4.0.0+ | - | - | 7 | 2017年3月20日 |

>[!NOTE]
>
>与AEM一样，Adobe建议开发人员使用与所运行的AEM版本兼容的最新版本和可用核心组件版本 [](https://github.com/adobe/aem-core-wcm-components/releases/latest) ，以便从最新修复和功能中受益。

### 组件版本和版本 {#component-versions-and-releases}

下表详细列出了核心组件的各个版本中包含哪些组件。

|  | 版本1.0.0 - 1.0.6 | 版本1.1.0 | 版本2.0.0 - 2.0.8 | 版本2.1.0 | 版本2.2.0-2.2.0 | 版本2.3.0-2.3.2 | 版本2.4.0 | 版本2.5.0 | 版本2.6.0 | 版本2.7.0+ |
|---|---|---|---|---|---|---|---|---|---|---|
| **[页面](page.md)** | v1 | v1 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 |
| **[标题](title.md)** | v1 | v1 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 |
| **[图像](image.md)** | v1 | v1 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 |
| **[列表](list.md)** | v1 | v1 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 |
| **[痕迹导航](breadcrumb.md)** | v1 | v1 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 |
| **[社交媒体共享](sharing.md)** | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[表单容器](form-container.md)** | v1 | v1 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 |
| **[表单文本](form-text.md)** | v1 | v1 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 |
| **[表单选项](form-options.md)** | v1 | v1 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 |
| **[隐藏的表单](form-hidden.md)** | v1 | v1 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 |
| **[表单按钮](form-button.md)** | v1 | v1 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 | v1,v2 |
| **[内容片段](content-fragment-component.md)** |  | 沙盒 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[导航](navigation.md)** |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[语言导航](language-navigation.md)** |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[快速搜索](quick-search.md)** |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Teaser](teaser.md)** |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[选项卡](tabs.md)** |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 |
| **[轮播](carousel.md)** |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 |
| **[分隔符](separator.md)** |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 |
| **[内容片段列表](content-fragment-list.md)** |  |  |  |  |  |  | v1 | v1 | v1 | v1 |
| **[折叠](accordion.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 |
| **[按钮](button.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 |
| **[容器](separator.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 |
| **[下载](separator.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 |
| **[体验片段](separator.md)** |  |  |  |  |  |  |  |  | v1 | v1 |
| **[嵌入](separator.md)** |  |  |  |  |  |  |  |  |  | v1 |

## 文档 {#documentation}

[使用核心组件进行创作](authoring.md) ，描述核心组件的使用情况以及向内容作者和模板作者公开的功能。 每个组件都有详细的说明。

[组件库是](https://adobe.com/go/aem_cmp_library) 大多数核心组件的当前版本的展示，说明了它们的使用方式。

[开发核心组件](developing.md) ，介绍核心组件的技术功能、如何在项目中使用它们、如何自定义和最佳实践。

[核心组件简介](introduction.md) 概述了核心组件在不同版本、用例和支持之间的兼容性。

[WKND教程是AEM开发（包括使用核心组件）的一个极好的分步介绍。](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)
