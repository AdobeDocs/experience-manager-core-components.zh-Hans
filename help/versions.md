---
title: 核心组件版本
description: 核心组件作为版本发布，其中可能包含同一核心组件的多个版本。 本文档介绍哪些版本和版本以及如何了解与核心组件和AEM的兼容性。
translation-type: tm+mt
source-git-commit: 3c5749d6660af1ad94f4911f261951e0369fa139
workflow-type: tm+mt
source-wordcount: '1971'
ht-degree: 21%

---


# 核心组件版本 {#core-components-versions}

核心组件的当前版本为2.15.0，与作为Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html)和[内部部署AEM](https://docs.adobe.com/content/help/en/experience-manager-65/user-guide/home.html)安装的[AEM兼容。

## 发行历史记录和兼容性{#release-history-and-compatibility}

核心组件设计为灵活且与所有支持的AEM版本兼容。 因此，一个版本的组件可以包含同一组件的多个版本。

下表说明了核心组件各版本的兼容性，以及哪些版本包含哪些组件版本。

### 发行历史和要求{#release-history-requirements}

下表概述了核心组件的发行版及其与AEM发行版和Java版本的兼容性。[](https://github.com/adobe/aem-core-wcm-components/releases)

| 发行版本 | 描述 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service | Java | 发布日期 |
|---|---|---|---|---|---|---|
| [2.15.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.15.0) | 此版本包括对[页面组件](/help/components/page.md)中渐进式Web应用程序的支持，并支持[Adobe数据层版本2.0.0。](/help/developing/data-layer/overview.md) | 6.4.8.1+ * | 6.5.5.0+ * | 持续 | 8, 11 | 2021年2月23日 |
| [2.14.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.14.0) | 此版本包含[嵌入组件](/help/components/embed.md)的新选项，并在[页面](/help/components/page.md)级别引入品牌辅助信息区并解决许多问题。 | 6.4.8.1+ * | 6.5.5.0+ * | 持续 | 8, 11 | 2021年2月9日 |
| [2.13.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.13.2) | 这是解决AEMaCS上使用RTE时的问题的修补程序版本 | 6.4.8.1+ * | 6.5.5.0+ * | 持续 | 8, 11 | 2020年12月16日 |
| [2.13.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.13.0) | 此版本包含用于[图像组件的新Dynamic Media功能。](/help/components/image.md) | 6.4.8.1+ * | 6.5.5.0+ * | 持续 | 8, 11 | 2020年12月4日 |
| [2.12.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.12.2) | 这是2.12.0的修补程序版本，包括小修复。 | 6.4.8.1+ * | 6.5.5.0+ * | 持续 | 8, 11 | 2020年11月11日 |
| [2.12.1](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.12.1) | 这是2.12.0的修补程序版本，用于修复[图像组件中的一个主要错误。](/help/components/image.md) | 6.4.8.1+ * | 6.5.5.0+ * | 持续 | 8, 11 | 2020年11月5日 |
| [2.12.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.12.0) | 此版本引入了[新的POST表单处理程序；](/help/components/forms/form-container.md#post-data)通过上下文感知配置包含自定义CSS、Javascript和元数据[标签的能力；](/help/developing/including-clientlibs.md#context-aware-loading)和`DataLayerBuilder`实用程序，以[简化自定义组件中的数据层集成。](/help/developing/data-layer/integrations.md#enabling-custom-components) | 6.4.8.1+ * | 6.5.5.0+ * | 持续 | 8, 11 | 2020年10月29日 |
| [2.11.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.11.0) | 此版本引入了[AMP支持。](/help/developing/amp.md) | 6.4.8.1+ * | 6.5.5.0+ * | 持续 | 8, 11 | 2020年7月20日 |
| [2.10.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.10.0) | 此版本引入了[PDF查看器组件。](/help/components/pdf-viewer.md) | 6.4.8.1+ | 6.5.5.0+ | 持续 | 8, 11 | 2020年6月17日 |
| [2.9.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.9.0) | 此版本支持与[Adobe客户端数据层](/help/developing/data-layer/overview.md)的集成，并引入了[进度栏组件。](/help/components/progress-bar.md) | 6.4.8.0+ | 6.5.4.0+ | 持续 | 8, 11 | 2020年5月29日 |
| [2.8.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.8.0) | 此版本侧重于修复，但增强了很小。 | 6.4.4.0+ | 6.5.0.0+ | 持续 | 8, 11 | 2019年12月5日 |
| [2.7.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.7.0) | 此版本引入了新的[嵌入组件。](/help/components/embed.md) | 6.4.4.0+ | 6.5.0.0+ | 持续 | 8, 11 | 2019 年 9 月 25 日 |
| [2.6.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.6.0) | 此版本引入了新的[体验片段组件。](/help/components/experience-fragment.md) | 6.4.4.0+ | 6.5.0.0+ | 持续 | 8, 11 | 2019 年 9 月 6 日 |
| [2.5.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.5.0) | 此版本引入了新的[Accordion、](/help/components/accordion.md) [Button、](/help/components/button.md) [容器、](/help/components/container.md)和[下载组件。](/help/components/download.md) | 6.4.2.0+ | 6.5.0.0+ | 持续 | 8, 11 | 2019年6月25日 |
| [2.4.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.4.0) | 此版本引入了[内容片段列表组件。](/help/components/content-fragment-list.md) | 6.4.2.0+ | 6.5.0.0+ | 持续 | 8, 11 | 2019年5月7日 |
| [2.3.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.2) | 此版本侧重于对[组件库](https://aemcomponents.dev)的细化，但还包含对[分隔符组件的一些功能增强。](/help/components/separator.md) | 6.4.2.0+ | 6.5.0.0+ | 持续 | 8 | 2019年3月14日 |
| [2.3.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.0) | 此版本侧重于[组件库](https://aemcomponents.dev)，并引入了新的[分隔符组件](/help/components/separator.md)，但还包含对[图像组件的一些功能增强。](/help/components/image.md) | 6.4.2.0+ | - | - | 8 | 2019年2月11日 |
| [2.2.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.2) | 此版本主要侧重于错误修复，但也包含对[传送组件的一些功能增强。](/help/components/carousel.md) | 6.4.2.0+ | - | - | 8 | 2018年11月27日 |
| [2.2.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.0) | 此版本引入了[选项卡组件](/help/components/tabs.md)和[传送组件](/help/components/carousel.md)，并改进了[图像组件、](/help/components/image.md)[页面组件、](/help/components/page.md)和[标题组件](/help/components/title.md)和增强的跟踪。 | 6.4.2.0+ | - | - | 8 | 2018年10月16日 |
| [2.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.1.0) | 此版本引入了[Teaser组件](/help/components/teaser.md)，并改进了[图像组件](/help/components/image.md)和大量错误修复。 | 6.4.2.0+ | - | - | 8 | 2018年7月13日 |
| [2.0.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.8) | 这是一个错误修复版本。 | 6.4.0.0+ | - | - | 8 | 2018年6月12日 |
| [2.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.6) | 此版本增加了内在改进、错误修复和小改进，包括[图像组件中支持图像翻转。](/help/components/image.md) | 6.4.0.0+ | - | - | 8 | 2018年4月11日 |
| [2.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.4) | 此版本主要侧重于内在改进、错误修复，以及对[图像组件、](/help/components/image.md) [页面组件、](/help/components/page.md)和[内容片段组件的一些细微改进。](/help/components/content-fragment-component.md) | 6.4.0.0+ | - | - | 8 | 2018年3月7日 |
| [2.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.0) | 此版本引入了[导航组件](/help/components/navigation.md) [语言导航组件](/help/components/language-navigation.md)和[快速搜索组件](/help/components/quick-search.md)，并为所有组件实现了[样式系统](/help/get-started/authoring.md#component-styling)。 | 6.4.0.0+ | - | - | 8 | 2018年1月16日 |
| [1.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.1.0) | 此版本对所有组件实施JSON导出，并引入[内容片段组件。](/help/components/content-fragment-component.md) | 6.4.0.0+ | - | - | 8 | 2017年10月10日 |
| [1.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.6) | 此版本为[图像组件添加了多个修复。](/help/components/image.md) | 6.4.0.0+ | - | - | 8 | 2017年8月4日 |
| [1.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.4) | 此版本为[页面组件、](/help/components/page.md) [图像组件、](/help/components/image.md)添加了修复程序，并增加了各种全局修复和改进。 | 6.4.0.0+ | - | - | 8 | 2017年4月26日 |
| [1.0.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.all-1.0.2) | 此版本在[图像组件中为动画GIF图像添加了修复。](/help/components/image.md) | 6.4.0.0+ | - | - | 7 | 2017年3月22日 |
| [1.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.0) | 核心组件的初始版本。 | 6.4.0.0+ | - | - | 7 | 2017年3月20日 |

>[!NOTE]
>
>(*)自版本2.11.0起，要求`org.apache.sling.models.impl`版本1.4.12或更高版本（由于[SLING-8781](https://issues.apache.org/jira/browse/SLING-8781)）。 这将在将来的Service Pack中为AEM 6.4和6.5提供。 在此之前，Sling Models捆绑包包含在`core.wcm.components.all`包中。

>[!TIP]
>
>与AEM一样，Adobe建议开发人员使用与所运行的AEM版本兼容的[最新版本和核心组件](https://github.com/adobe/aem-core-wcm-components/releases/latest)版本，以便从最新修复和功能中受益。

### 组件版本和版本{#component-versions-and-releases}

下表详细列出了核心组件的各个版本中包含哪些组件。

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
| **[PDF 查看器](components/pdf-viewer.md)** |  |  |  |  |  |  |  |  |  |  | v1 |

## 版本和版本{#versions-and-releases}

核心组件通过GitHub分发。 这使Adobe能够更快地向组件添加功能，并允许在AEM发布周期之外提供社区输入。

核心组件在已定义的AEM版本中可用，这些版本与之兼容。 这意味着一个AEM版本可能支持核心组件的多个版本或版本。 这比以前与特定版本的AEM绑定的基础组件提供了更多灵活性。

### 版本 {#versions}

核心组件的主要小版本是&#x200B;**版本**。 每个组件都有一个版本。 版本用&#x200B;**v**&#x200B;表示，并附加一个非零的正整数，如v1和v2。 版本仅会因不向后兼容的更改而递增，这通常是引入新特性和功能的情况。

开发人员和管理员可以通过资源类型路径中的数字以及他们实现的完全限定的Java类名称来识别核心组件的版本。 此版本号表示由[语义版本准则](https://semver.org/)定义的主版本。

有关核心组件版本的详细信息，请参阅核心组件](developing/guidelines.md)的[开发人员文档。

### 版本{#releases}

核心组件通过&#x200B;**发行版**&#x200B;和[提供，它们代表GitHub](https://github.com/adobe/aem-core-wcm-components/releases)上可用的实际已发布对象。 版本以X.Y.Z格式的十进制数表示，并将所有核心组件作为可交付包一起收集。

* **主要** 版本可以引入现有组件的新版本，以及全新的组件和标准错误修复。这由发行号的X组件中的增量表示。
* **重要** 版本可向现有版本的组件引入新功能并修复错误。此值由发行号的Y分量中的增量表示。
* **次要** 版本仅包含错误修复。这由发行号的Z分量中的增量表示。

>[!NOTE]
>
>版本可以包含同一组件的多个版本。
>
>同一版本的组件可以显示在多个版本中。

## 核心组件支持 {#core-components-support}

核心组件是 AEM 的一个组成部分，依原样提供支持，并作为“快速入门”的一部分提供，须遵循相同的条款和条件。

与其他产品功能一样，其生命周期结束的一般规则是：

* 组件在被删除之前，先被声明弃用；
* 声明弃用之后，这些组件将最早从 AEM 版本中删除。

这为客户提供了至少一个发布周期，以便在支持结束前转移到组件的新版本。

每个组件的版本都清楚地声明了其支持的 AEM 版本。当某个 AEM 版本不再受到支持时，该版本 AEM 的核心组件也不再受到支持。

有关组件自定义支持的详细信息，请参阅相关核心组件版本的[自定义核心组件](developing/customizing.md)页面。

## 基础组件支持 {#foundation-component-support}

Adobe的开发重点已转向核心组件，并将继续增加新功能。

[几乎所有基础组件在AEM 6.5中都已弃用](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/siteandpage/default-components-foundation.html) ，今后将只考虑基础组件的主要错误修复。
