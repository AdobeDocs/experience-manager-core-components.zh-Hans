---
title: 核心组件版本
description: 核心组件作为可能包含同一核心组件多个版本的发行版发布。 本文档介绍哪些版本和版本以及如何了解与核心组件和AEM的兼容性。
translation-type: tm+mt
source-git-commit: cef65c3fdf99130086136fe9019ca759bbf1926c
workflow-type: tm+mt
source-wordcount: '1717'
ht-degree: 25%

---


# 核心组件版本 {#core-components-versions}

核心组件的当前版本为2.10.0，与AEM [兼容，作为Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html)[和内部部署AEM安装](https://docs.adobe.com/content/help/en/experience-manager-65/user-guide/home.html) 。 它于2020年6月作为版本2.0.0的重要更新发布。版本2.0.0引入了新组件以及现有组件的v2更新。

## 发布历史和兼容性 {#release-history-and-compatibility}

核心组件最初随AEM 6.3一起发布，设计为灵活且与所有受支持的AEM版本兼容。 因此，一个版本的组件可以包含同一组件的多个版本。

下表说明了核心组件版本的兼容性以及哪些版本包含哪些组件版本。

### 发行历史和要求 {#release-history-requirements}

下表提供了核心组件 [的发行版本及其与AEM发行版和Java版本的兼容性](https://github.com/adobe/aem-core-wcm-components/releases)。

| 版本 | 描述 | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM 云服务 | Java | 发布日期 |
|---|---|---|---|---|---|---|---|
| [2.10.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.10.0) | 此版本引入了PDF查看器组件。 | - | 6.4.4.0+ | 6.5.0.0+ | 持续 | 8, 11 | 2020年6月17日 |
| [2.9.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.9.0) | 此版本支持与Adobe客户端数据层的集成，并引入了进度栏组件。 | - | 6.4.4.0+ | 6.5.0.0+ | 持续 | 8, 11 | 2020年5月29日 |
| [2.8.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.8.0) | 此版本侧重于修复，但增强了很小。 | 6.3.3.4+ | 6.4.4.0+ | 6.5.0.0+ | 持续 | 8, 11 | 2019年12月5日 |
| [2.7.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.7.0) | 此版本引入了新的嵌入组件 | 6.3.3.4+ | 6.4.4.0+ | 6.5.0.0+ | 持续 | 8, 11 | 2019 年 9 月 25 日 |
| [2.6.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.6.0) | 此版本引入了新的体验片段组件 | 6.3.3.4+ | 6.4.4.0+ | 6.5.0.0+ | 持续 | 8, 11 | 2019 年 9 月 6 日 |
| [2.5.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.5.0) | 此版本引入了新的Accordion、Button、容器和下载组件。 | 6.3.3.0+ | 6.4.2.0+ | 6.5.0.0+ | 持续 | 8, 11 | 2019年6月25日 |
| [2.4.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.4.0) | 此版本引入了内容片段列表组件 | 6.3.3.0+ | 6.4.2.0+ | 6.5.0.0+ | 持续 | 8, 11 | 2019年5月7日 |
| [2.3.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.2) | 此版本侧重于对组件库的细化，但也包含对分隔符组件的一些功能增强 | 6.3.3.0+ | 6.4.2.0+ | 6.5.0.0+ | 持续 | 8 | 2019年3月14日 |
| [2.3.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.0) | 此版本侧重于组件库以及新的分隔符组件，但还包含图像组件的一些功能增强 | 6.3.3.0+ | 6.4.2.0+ | - | - | 8 | 2019年2月11日 |
| [2.2.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.2) | 此版本主要侧重于错误修复，但也包含旋转组件的一些功能增强 | 6.3.3.0+ | 6.4.2.0+ | - | - | 8 | 2018年11月27日 |
| [2.2.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.0) | 引入了选项卡和传送组件，对图像、页面和标题组件进行了改进，并增强了跟踪功能 | 6.3.3.0+ | 6.4.2.0+ | - | - | 8 | 2018年10月16日 |
| [2.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.1.0) | 引入了Teaser组件、图像组件改进和大量错误修复 | 6.3.3.0+ | 6.4.2.0+ | - | - | 8 | 2018年7月13日 |
| [2.0.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.8) | 错误修复版本 | 6.3.2.0+ | 6.4.0.0+ | - | - | 8 | 2018年6月12日 |
| [2.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.6) | 其他底层改进、错误修复和小改进，包括图像翻转支持。 | 6.3.2.0+ | 6.4.0.0+ | - | - | 8 | 2018年4月11日 |
| [2.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.4) | 大多数内在的改进、错误修复，以及对图像、页面和内容片段组件的一些细微改进 | 6.3.2.0+ | 6.4.0.0+ | - | - | 8 | 2018年3月7日 |
| [2.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.0) | 引入了导航、语言导航和快速搜索组件。 为所有组件实现的样式系统。 | 6.3.2.0+ | 6.4.0.0+ | - | - | 8 | 2018年1月16日 |
| [1.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.1.0) | 在所有组件上实施JSON导出，引入内容片段组件 | 6.3.1.0 | 6.4.0.0+ | - | - | 8 | 2017年10月10日 |
| [1.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.6) | 对图像组件的多个修复 | 6.3.0.0+ | 6.4.0.0+ | - | - | 8 | 2017年8月4日 |
| [1.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.4) | 页面组件、图像组件的修复、各种全局修复和改进 | 6.3.0.0+ | 6.4.0.0+ | - | - | 8 | 2017年4月26日 |
| [1.0.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.all-1.0.2) | 图像组件中动画GIF图像的修复 | 6.3.0.0+ | 6.4.0.0+ | - | - | 7 | 2017年3月22日 |
| [1.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.0) | 核心组件的初始版本 | 6.3.0.0+ | 6.4.0.0+ | - | - | 7 | 2017年3月20日 |

>[!NOTE]
>
>与AEM一样，Adobe建议开发人员 [使用与所运行的AEM版本兼容的最新版本和可用核心组件版本](https://github.com/adobe/aem-core-wcm-components/releases/latest) ，以便从最新的修复和功能中受益。

### 组件版本和版本 {#component-versions-and-releases}

下表详细列出了核心组件在哪些版本中包含哪些组件。

|  | 版本1.0.0 - 1.0.6 | 版本1.1.0 | 版本2.0.0 - 2.0.8 | 版本2.1.0 | 版本2.2.0-2.2.0 | 版本2.3.0-2.3.2 | 版本2.4.0 | 版本2.5.0 | 版本2.6.0 | 版本2.7.0-2.8.0 | 版本2.9.0+ |
|---|---|---|---|---|---|---|---|---|---|---|---|
| **[页面](components/page.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[标题](components/title.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[图像](components/image.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[列表](components/list.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[痕迹导航](components/breadcrumb.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[社交媒体共享](components/sharing.md)** | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[表单容器](components/forms/form-container.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[表单文本](components/forms/form-text.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[表单选项](components/forms/form-options.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[隐藏的表单](components/forms/form-hidden.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[表单按钮](components/forms/form-button.md)** | v1 | v1 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 | v1、v2 |
| **[内容片段](components/content-fragment-component.md)** |  | 沙盒 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1、v2 | v1、v2 |
| **[导航](components/navigation.md)** |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[语言导航](components/language-navigation.md)** |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[快速搜索](components/quick-search.md)** |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[Teaser](components/teaser.md)** |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[选项卡](components/tabs.md)** |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[轮播](components/carousel.md)** |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[分隔符](components/separator.md)** |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 |
| **[内容片段列表](components/content-fragment-list.md)** |  |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 |
| **[折叠](components/accordion.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 |
| **[按钮](components/button.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 |
| **[容器](components/container.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 |
| **[下载](components/download.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 |
| **[体验片段](components/experience-fragment.md)** |  |  |  |  |  |  |  |  | v1 | v1 | v1 |
| **[嵌入](components/embed.md)** |  |  |  |  |  |  |  |  |  | v1 | v1 |
| **[进度条](components/progress-bar.md)** |  |  |  |  |  |  |  |  |  |  | v1 |
| **[PDF查看器](components/pdf-viewer.md)** |  |  |  |  |  |  |  |  |  |  | v1 |

## 版本和版本 {#versions-and-releases}

核心组件通过GitHub分发。 这使Adobe能够更快地向组件添加功能，并允许在AEM发布周期之外输入社区信息。

核心组件在已定义的AEM版本中可用，这些版本与它们兼容。 这意味着一个AEM版本可能支持核心组件的多个版本或多个版本。 这比以前与特定版本的AEM绑定的基础组件更具灵活性。

### 版本 {#versions}

核心组件的主要小版本是 **版本**。 每个组件都有一个版本。 版本用v **附加** 一个非零的正整数（如v1和v2）表示。 版本仅会因不向后兼容的更改而递增，而新功能的引入通常也是如此。

开发人员和管理员可以通过资源类型路径中的数字以及实现的完全限定的Java类名称识别核心组件的版本。 此版本号表示由语义版本控制准则定义的 [主要版本](https://semver.org/)。

有关核心组件版本的更多详细信息，请 [参阅核心组件的开发人员文档](developing/guidelines.md)。

### 版本 {#releases}

核心组件通过发行版提 **供** , [并代表GitHub上可用的实际已发布对象](https://github.com/adobe/aem-core-wcm-components/releases)。 版本以X.Y.Z格式的十进制数表示，并将所有核心组件作为可交付包一起收集。

* **主要版本** 可以引入现有组件的新版本以及全新的组件以及标准错误修复。 这由发行号的X组件中的增量表示。
* **重要版本** ，可向现有版本的组件引入新功能以及错误修复。 此值由发行号的Y组件中的增量表示。
* **次要版本** 仅包含错误修复。 这由发行号的Z分量中的增量表示。

>[!NOTE]
>
>版本可以包含同一组件的多个版本。
>
>同一版本的组件可显示在多个版本中。

## 核心组件支持 {#core-components-support}

核心组件是 AEM 的一个组成部分，依原样提供支持，并作为“快速入门”的一部分提供，须遵循相同的条款和条件。

与其他产品功能一样，其生命周期结束的一般规则是：

* 组件在被删除之前，先被声明弃用；
* 声明弃用之后，这些组件将最早从 AEM 版本中删除。

这为客户提供了至少一个发布周期，以便在支持结束前转移到组件的新版本。

每个组件的版本都清楚地声明了其支持的 AEM 版本。当某个 AEM 版本不再受到支持时，该版本 AEM 的核心组件也不再受到支持。

有关组件自定义支持的详细信息，请参阅相关核心组件版本的[自定义核心组件](developing/customizing.md)页面。

## 基础组件支持 {#foundation-component-support}

由于基础组件在许多版本中都是众多项目开发的基础，因此在可预见的将来，仍将继续支持这些组件。

However, Adobe&#39;s development emphasis has shifted to the Core Components and new features will be added to them, whereas [nearly all Foundation Components have been deprecated with AEM 6.5](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/siteandpage/default-components-foundation.html) and only bug fixes will be made to the Foundation Components going forward.
