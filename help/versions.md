---
title: 核心组件版本
description: 核心组件作为可能包含同一核心组件多个版本的发行版发布。 本文档介绍哪些版本和版本以及如何了解与核心组件和AEM的兼容性。
translation-type: tm+mt
source-git-commit: c64276bb95aeaef4223fc2a0dc2c3cfdf8609f5a
workflow-type: tm+mt
source-wordcount: '1848'
ht-degree: 22%

---


# 核心组件版本 {#core-components-versions}

核心组件的当前版本是2.12.1，它与AEM兼容， [作为Cloud Service和](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html) 内部部署AEM安装 [](https://docs.adobe.com/content/help/en/experience-manager-65/user-guide/home.html) 。 它于2020年11月作为2.12.0的修补程序版本发布。版本2.12.0引入了表单、元数据和数据层的几个新功能。

## 发布历史和兼容性 {#release-history-and-compatibility}

核心组件设计为灵活且与所有支持的AEM版本兼容。 因此，一个版本的组件可以包含同一组件的多个版本。

下表说明了核心组件版本的兼容性以及哪些版本包含哪些组件版本。

### 发行历史和要求 {#release-history-requirements}

下表提供了核心组件 [的发行版本及其与AEM发行版和Java版本的兼容性](https://github.com/adobe/aem-core-wcm-components/releases)。

| 版本 | 描述 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service | Java | 发布日期 |
|---|---|---|---|---|---|---|
| [2.12.1](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.11.1) | 这是2.12.0的修补程序版本，用于修复图像组件中的一个主要错误。 | 6.4.8.1+ * | 6.5.5.0+ * | 持续 | 8, 11 | 2020年11月5日 |
| [2.12.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.11.0) | 此版本引入了 [一个新的POST表单处理程序；](/help/components/forms/form-container.md#post-data) 通过上下文感知配置包含自定义CSS、 [Javascript和元数据标记；](/help/developing/including-clientlibs.md#context-aware-loading) 以及简化 `DataLayerBuilder` 自定义组 [件中数据层集成的实用程序。](/help/developing/data-layer/integrations.md#enabling-custom-components) | 6.4.8.1+ * | 6.5.5.0+ * | 持续 | 8, 11 | 2020年10月29日 |
| [2.11.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.11.0) | 此版本引入了 [AMP支持。](/help/developing/amp.md) | 6.4.8.1+ * | 6.5.5.0+ * | 持续 | 8, 11 | 2020年7月20日 |
| [2.10.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.10.0) | 此版本引入了 [PDF查看器组件。](/help/components/pdf-viewer.md) | 6.4.8.1+ | 6.5.5.0+ | 持续 | 8, 11 | 2020年6月17日 |
| [2.9.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.9.0) | 此版本支持与Adobe客 [户端层集成](/help/developing/data-layer/overview.md) ，并引入了 [进度栏组件。](/help/components/progress-bar.md) | 6.4.8.0+ | 6.5.4.0+ | 持续 | 8, 11 | 2020年5月29日 |
| [2.8.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.8.0) | 此版本侧重于修复，但增强了很小。 | 6.4.4.0+ | 6.5.0.0+ | 持续 | 8, 11 | 2019年12月5日 |
| [2.7.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.7.0) | 此版本引入了新的 [嵌入组件。](/help/components/embed.md) | 6.4.4.0+ | 6.5.0.0+ | 持续 | 8, 11 | 2019 年 9 月 25 日 |
| [2.6.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.6.0) | 此版本引入了新的 [体验片段组件。](/help/components/experience-fragment.md) | 6.4.4.0+ | 6.5.0.0+ | 持续 | 8, 11 | 2019 年 9 月 6 日 |
| [2.5.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.5.0) | 此版本引入了新 [的Accordion](/help/components/accordion.md) 、 [Button](/help/components/button.md) 、 [](/help/components/container.md)[容器和下载组件。](/help/components/download.md) | 6.4.2.0+ | 6.5.0.0+ | 持续 | 8, 11 | 2019年6月25日 |
| [2.4.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.4.0) | 此版本引入了内 [容片段列表组件。](/help/components/content-fragment-list.md) | 6.4.2.0+ | 6.5.0.0+ | 持续 | 8, 11 | 2019年5月7日 |
| [2.3.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.2) | 此版本侧重于对组件库 [的细化](https://aemcomponents.dev) ，但还包含对分隔符组件的某 [些功能增强。](/help/components/separator.md) | 6.4.2.0+ | 6.5.0.0+ | 持续 | 8 | 2019年3月14日 |
| [2.3.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.0) | 此版本侧重于组 [件库](https://aemcomponents.dev) ，并引入了新 [的分隔符组件](/help/components/separator.md) ，但还包含图像组件的某 [些功能增强。](/help/components/image.md) | 6.4.2.0+ | - | - | 8 | 2019年2月11日 |
| [2.2.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.2) | 此版本主要侧重于错误修复，但也包含旋转组件的一些功 [能增强。](/help/components/carousel.md) | 6.4.2.0+ | - | - | 8 | 2018年11月27日 |
| [2.2.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.0) | 此版本引入了 [选项卡组](/help/components/tabs.md) 件和传送 [组件，并对图像组件、](/help/components/carousel.md) 页面组件 [、](/help/components/image.md) 页标题组件和进行了改进， [](/help/components/page.md)[](/help/components/title.md) 并增强了跟踪功能。 | 6.4.2.0+ | - | - | 8 | 2018年10月16日 |
| [2.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.1.0) | 此版本引入了 [Teaser组件](/help/components/teaser.md) ，并改进了图 [像组件](/help/components/image.md) 和大量错误修复。 | 6.4.2.0+ | - | - | 8 | 2018年7月13日 |
| [2.0.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.8) | 这是一个错误修复版本。 | 6.4.0.0+ | - | - | 8 | 2018年6月12日 |
| [2.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.6) | 此版本新增了内在改进、错误修复和小改进，包括支持图像组件中的图 [像翻转。](/help/components/image.md) | 6.4.0.0+ | - | - | 8 | 2018年4月11日 |
| [2.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.4) | 此版本主要侧重于内在改进、错误修复以及对图像组件、页面组件和内 [容片段组](/help/components/image.md) 件的 [一些小](/help/components/page.md) 微改 [进。](/help/components/content-fragment-component.md) | 6.4.0.0+ | - | - | 8 | 2018年3月7日 |
| [2.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.0) | 此版本引入了 [导航组件、](/help/components/navigation.md) 语言 [导航组件](/help/components/language-navigation.md) 和快速搜 [索组件，并为所](/help/components/quick-search.md) 有组件实 [](/help/get-started/authoring.md#component-styling) 现了样式系统。 | 6.4.0.0+ | - | - | 8 | 2018年1月16日 |
| [1.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.1.0) | 此版本对所有组件实施JSON导出并引入内 [容片段组件。](/help/components/content-fragment-component.md) | 6.4.0.0+ | - | - | 8 | 2017年10月10日 |
| [1.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.6) | 此版本为图像组件添加了多 [个修复。](/help/components/image.md) | 6.4.0.0+ | - | - | 8 | 2017年8月4日 |
| [1.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.4) | 此版本为页面组件、图 [像组件添](/help/components/page.md) 加 [了修复，并](/help/components/image.md) 添加了各种全局修复和改进。 | 6.4.0.0+ | - | - | 8 | 2017年4月26日 |
| [1.0.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.all-1.0.2) | 此版本为图像组件中的动画GIF图像添 [加了修复。](/help/components/image.md) | 6.4.0.0+ | - | - | 7 | 2017年3月22日 |
| [1.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.0) | 核心组件的初始版本。 | 6.4.0.0+ | - | - | 7 | 2017年3月20日 |

>[!NOTE]
>
>(*)自版本2.11.0起， `org.apache.sling.models.impl` 版本1.4.12或更高版本是必需的(由 [于SLING-8781](https://issues.apache.org/jira/browse/SLING-8781))。 这将在将来的服务包中为AEM 6.4和6.5提供。 在此之前，Sling Models捆绑包包含在包 `core.wcm.components.all` 中。

>[!TIP]
>
>与AEM一样，Adobe建议开发人 [员使用最新版本和可用的核心组件版本](https://github.com/adobe/aem-core-wcm-components/releases/latest) ，这些版本与他们运行的AEM版本兼容，以便从最新的修复和功能中受益。

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
| **[PDF 查看器](components/pdf-viewer.md)** |  |  |  |  |  |  |  |  |  |  | v1 |

## 版本和版本 {#versions-and-releases}

核心组件通过GitHub分发。 这使Adobe能够更快地向组件添加功能，并允许AEM发布周期外的社区输入。

核心组件在已定义的AEM版本中可用，与其兼容。 这意味着一个AEM版本可能支持核心组件的多个版本或版本。 这比以前与AEM的特定版本绑定的基础组件更具灵活性。

### 版本 {#versions}

核心组件的主要小版本是 **版本**。 每个组件都有一个版本。 版本用v **附加** 一个非零的正整数（如v1和v2）表示。 版本仅会因不向后兼容的更改而递增，而新功能的引入通常也是如此。

开发人员和管理员可以通过资源类型路径中的数字以及他们实现的完全限定的Java类名称来识别核心组件的版本。 此版本号表示由语义版本控制准则定义的 [主要版本](https://semver.org/)。

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

Adobe的开发重点已转向核心组件，并将继续增加新功能。

[几乎所有基础组件都已在AEM 6.5中弃用](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/siteandpage/default-components-foundation.html) ，今后将只考虑基础组件的主要错误修复。
