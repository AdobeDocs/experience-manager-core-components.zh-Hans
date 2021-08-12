---
title: 核心组件版本
description: 核心组件以发行版形式发布，其中可能包含同一核心组件的多个版本。 本文档介绍哪些版本和版本，以及如何了解与核心组件和AEM的兼容性。
role: Architect, Developer, Admin, User
exl-id: 7d4dbe46-4013-4217-b815-cdb1462072c6
source-git-commit: cc8c3275bf251b4c390ee66588f34bac7c0ec218
workflow-type: tm+mt
source-wordcount: '2233'
ht-degree: 20%

---

# 核心组件版本 {#core-components-versions}

核心组件的当前版本为2.17.8，且与[AEM as a Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html)和[本地AEM](https://docs.adobe.com/content/help/en/experience-manager-65/user-guide/home.html)安装兼容。

## 发行历史记录和兼容性 {#release-history-and-compatibility}

核心组件旨在提供灵活且与所有受支持的AEM版本兼容。 因此，一个版本的组件可以包含同一组件的多个版本。

下表说明了核心组件版本与其中包含哪些组件版本的兼容性。

### 发行历史和要求 {#release-history-requirements}

下表（其内容在GitHub上提供，且提供了完整版本详细信息](https://github.com/adobe/aem-core-wcm-components/releases)），概述了核心组件的版本及其与AEM版本和Java版本的兼容性。[

| 发行版本 | 描述 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service | Java | 发布日期 |
|---|---|---|---|---|---|---|
| [2.17.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.8) | 此修补程序版本这是一个修补程序版本，用于修复先前引入的向后不兼容的更改。 | 6.4.8.4+ * | 6.5.6.0+ * | 持续 | 8, 11 | 2021年8月2日 |
| [2.17.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.6) | 此修补程序版本增加了对页面站点映射的支持，并包含各种辅助功能改进。 | 6.4.8.4+ * | 6.5.6.0+ * | 持续 | 8, 11 | 2021年7月29日 |
| [2.17.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.2) | 此修补程序版本修复了[数据层](/help/developing/data-layer/overview.md)不适用于AEMaaCS的问题。 | 6.4.8.4+ * | 6.5.6.0+ * | 持续 | 8, 11 | 2021年7月8日 |
| [2.17.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.0) | 此版本包括许多支持链接处理程序功能的新组件版本的技术预览，以及[页面组件的特色图像功能的技术预览。](/help/components/page.md) 还包含若干错误修复。 | 6.4.8.4+ * | 6.5.6.0+ * | 持续 | 8, 11 | 2021年6月16日 |
| [2.16.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.16.4) | 这是用于修复新链接处理程序问题的修补程序版本。 | 6.4.8.1+ * | 6.5.5.0+ * | 持续 | 8, 11 | 2021年5月19日 |
| [2.16.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.16.2) | 这是一个修补程序版本，主要修复了新链接处理程序的问题，并添加了支持多页应用程序进行[PWA的增强功能。](/help/components/page.md#pwa-support) | 6.4.8.1+ * | 6.5.5.0+ * | 持续 | 8, 11 | 2021年5月15日 |
| [2.16.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.16.0) | 此版本重点改进了辅助功能，并对现有组件引入了新的链接处理程序。 | 6.4.8.1+ * | 6.5.5.0+ * | 持续 | 8, 11 | 2021年4月22日 |
| [2.15.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.15.2) | 这是一个修补程序版本，主要修复了[数据层](/help/developing/data-layer/overview.md)向后兼容性和IT测试在某些情况下失败的问题。 | 6.4.8.1+ * | 6.5.5.0+ * | 持续 | 8, 11 | 2021 年 3 月 16 日 |
| [2.15.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.15.0) | 此版本包括对页面组件](/help/components/page.md#pwa-support)中的[渐进式Web应用程序(PWA)的支持，并支持[Adobe数据层版本2.0.0。](/help/developing/data-layer/overview.md) | 6.4.8.1+ * | 6.5.5.0+ * | 持续 | 8, 11 | 2021年2月23日 |
| [2.14.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.14.0) | 此版本包含[嵌入组件](/help/components/embed.md)的新选项，在[页面](/help/components/page.md)级别引入了品牌概要信息，并解决了许多问题。 | 6.4.8.1+ * | 6.5.5.0+ * | 持续 | 8, 11 | 2021年2月9日 |
| [2.13.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.13.2) | 这是一个修补程序版本，用于解决在AEMaaCS上使用RTE时出现的问题 | 6.4.8.1+ * | 6.5.5.0+ * | 持续 | 8, 11 | 2020年12月16日 |
| [2.13.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.13.0) | 此版本包括[图像组件的新Dynamic Media功能。](/help/components/image.md) | 6.4.8.1+ * | 6.5.5.0+ * | 持续 | 8, 11 | 2020年12月4日 |
| [2.12.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.12.2) | 这是2.12.0的修补程序版本，其中包括小修复。 | 6.4.8.1+ * | 6.5.5.0+ * | 持续 | 8, 11 | 2020年11月11日 |
| [2.12.1](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.12.1) | 这是2.12.0的修补程序版本，用于修复[图像组件中的一个主要错误。](/help/components/image.md) | 6.4.8.1+ * | 6.5.5.0+ * | 持续 | 8, 11 | 2020年11月5日 |
| [2.12.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.12.0) | 此版本引入了[新的POST表单处理程序；](/help/components/forms/form-container.md#post-data)通过上下文感知配置包含自定义CSS、Javascript和元数据[标记的功能；](/help/developing/including-clientlibs.md#context-aware-loading)和`DataLayerBuilder`实用程序，用于[简化自定义组件中的数据层集成。](/help/developing/data-layer/integrations.md#enabling-custom-components) | 6.4.8.1+ * | 6.5.5.0+ * | 持续 | 8, 11 | 2020年10月29日 |
| [2.11.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.11.0) | 此版本引入了[AMP支持。](/help/developing/amp.md) | 6.4.8.1+ * | 6.5.5.0+ * | 持续 | 8, 11 | 2020年7月20日 |
| [2.10.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.10.0) | 此版本引入了[PDF查看器组件。](/help/components/pdf-viewer.md) | 6.4.8.1+ | 6.5.5.0+ | 持续 | 8, 11 | 2020年6月17日 |
| [2.9.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.9.0) | 此版本支持与[Adobe客户端数据层](/help/developing/data-layer/overview.md)的集成，并引入了[进度条组件。](/help/components/progress-bar.md) | 6.4.8.0+ | 6.5.4.0+ | 持续 | 8, 11 | 2020年5月29日 |
| [2.8.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.8.0) | 此版本重点针对包含小型增强功能的修复。 | 6.4.4.0+ | 6.5.0.0+ | 持续 | 8, 11 | 2019年12月5日 |
| [2.7.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.7.0) | 此版本引入了新的[嵌入组件。](/help/components/embed.md) | 6.4.4.0+ | 6.5.0.0+ | 持续 | 8, 11 | 2019 年 9 月 25 日 |
| [2.6.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.6.0) | 此版本引入了新的[体验片段组件。](/help/components/experience-fragment.md) | 6.4.4.0+ | 6.5.0.0+ | 持续 | 8, 11 | 2019 年 9 月 6 日 |
| [2.5.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.5.0) | 此版本引入了新的[折叠面板、](/help/components/accordion.md) [按钮、](/help/components/button.md) [容器、](/help/components/container.md)和[下载组件。](/help/components/download.md) | 6.4.2.0+ | 6.5.0.0+ | 持续 | 8, 11 | 2019年6月25日 |
| [2.4.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.4.0) | 此版本引入了[内容片段列表组件。](/help/components/content-fragment-list.md) | 6.4.2.0+ | 6.5.0.0+ | 持续 | 8, 11 | 2019年5月7日 |
| [2.3.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.2) | 此版本重点对[组件库](https://aemcomponents.dev)进行了细化，但还包含对[分隔符组件的一些功能增强。](/help/components/separator.md) | 6.4.2.0+ | 6.5.0.0+ | 持续 | 8 | 2019年3月14日 |
| [2.3.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.0) | 此版本重点介绍[组件库](https://aemcomponents.dev)以及新的[分隔符组件](/help/components/separator.md)，但还包含对[图像组件的一些功能增强。](/help/components/image.md) | 6.4.2.0+ | - | - | 8 | 2019年2月11日 |
| [2.2.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.2) | 此版本主要侧重于错误修复，但也包含对[轮播组件的一些功能增强。](/help/components/carousel.md) | 6.4.2.0+ | - | - | 8 | 2018年11月27日 |
| [2.2.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.0) | 此版本引入了[选项卡组件](/help/components/tabs.md)和[轮播组件](/help/components/carousel.md)，并对[图像组件、](/help/components/image.md) [页面组件、](/help/components/page.md)和[标题组件](/help/components/title.md)和增强的跟踪功能进行了改进。 | 6.4.2.0+ | - | - | 8 | 2018年10月16日 |
| [2.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.1.0) | 此版本引入了[Teaser组件](/help/components/teaser.md)，并对[图像组件](/help/components/image.md)进行了改进，并进行了大量错误修复。 | 6.4.2.0+ | - | - | 8 | 2018年7月13日 |
| [2.0.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.8) | 这是一个错误修复版本。 | 6.4.0.0+ | - | - | 8 | 2018年6月12日 |
| [2.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.6) | 此版本添加了一些现成改进、错误修复和小改进，包括在[图像组件中支持图像翻转。](/help/components/image.md) | 6.4.0.0+ | - | - | 8 | 2018年4月11日 |
| [2.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.4) | 此版本主要侧重于以下方面的改进、错误修复，以及对[图像组件、](/help/components/image.md) [页面组件、](/help/components/page.md)和[内容片段组件进行的一些细微改进。](/help/components/content-fragment-component.md) | 6.4.0.0+ | - | - | 8 | 2018年3月7日 |
| [2.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.0) | 此版本引入了[导航组件](/help/components/navigation.md) [语言导航组件](/help/components/language-navigation.md)和[快速搜索组件](/help/components/quick-search.md)，并为所有组件实施了[样式系统](/help/get-started/authoring.md#component-styling)。 | 6.4.0.0+ | - | - | 8 | 2018年1月16日 |
| [1.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.1.0) | 此版本在所有组件上实施JSON导出，并引入了[内容片段组件。](/help/components/content-fragment-component.md) | 6.4.0.0+ | - | - | 8 | 2017年10月10日 |
| [1.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.6) | 此版本为[图像组件添加了多项修复。](/help/components/image.md) | 6.4.0.0+ | - | - | 8 | 2017年8月4日 |
| [1.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.4) | 此版本添加了对[页面组件、](/help/components/page.md) [图像组件、](/help/components/image.md)的修复，以及各种全局修复和改进。 | 6.4.0.0+ | - | - | 8 | 2017年4月26日 |
| [1.0.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.all-1.0.2) | 此版本在[图像组件中添加了对GIF动画图像的修复。](/help/components/image.md) | 6.4.0.0+ | - | - | 7 | 2017年3月22日 |
| [1.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.0) | 核心组件的初始版本。 | 6.4.0.0+ | - | - | 7 | 2017年3月20日 |

>[!NOTE]
>
>(*)自版本2.11.0起，要求使用`org.apache.sling.models.impl`版本1.4.12或更高版本（由于[SLING-8781](https://issues.apache.org/jira/browse/SLING-8781)）。 这将在将来的Service Pack中为AEM 6.4和6.5提供。 在此之前，`core.wcm.components.all`包中包含Sling模型包。

>[!TIP]
>
>与AEM一样，Adobe建议开发人员使用与所运行的AEM版本兼容的[最新版本和核心组件](https://github.com/adobe/aem-core-wcm-components/releases/latest)版本，以便从最新的修复和功能中受益。

### 组件版本和版本 {#component-versions-and-releases}

下表详细列出了核心组件的哪些版本中包含哪些组件。

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

核心组件通过GitHub进行分发。 这允许Adobe更快地向组件添加功能，并且还允许在AEM发行周期之外输入社区内容。

核心组件在定义的AEM版本中可用，与这些版本兼容。 这意味着一个AEM版本可能支持核心组件的多个版本或版本。 这比之前与特定版本的AEM绑定的基础组件具有更大的灵活性。

### 版本 {#versions}

核心组件的主要小版本是&#x200B;**版本**。 每个组件都有一个版本。 版本以&#x200B;**v**&#x200B;表示，并附加一个非零的正整数，如v1和v2。 仅对于向后不兼容的更改，版本才会递增，这通常也是引入新特性和功能的情况。

开发人员和管理员可以通过其资源类型路径中的数字以及其实施的完全限定的Java类名称来识别核心组件的版本。 此版本号表示由[语义版本控制准则](https://semver.org/)定义的主要版本。

有关核心组件版本的更多详细信息，请参阅核心组件](developing/guidelines.md)的[开发人员文档。

### 版本 {#releases}

核心组件通过&#x200B;**发行版**&#x200B;和[提供，这些组件表示GitHub](https://github.com/adobe/aem-core-wcm-components/releases)上可用的实际已发布工件。 版本的表示格式为X.Y.Z的十进制数，并将所有核心组件作为交付包一起收集。

* **主要** 版本可以引入现有组件的新版本，以及全新组件和标准错误修复。这由发行号的X组件中的增量表示。
* **重要** 版本可以对现有版本的组件引入新功能以及错误修复。这由发行号的Y组件中的增量表示。
* **次要** 版本仅包含错误修复。这由发行号的Z组件中的增量表示。

>[!NOTE]
>
>版本可以包含同一组件的多个版本。
>
>同一版本的组件可能会显示在多个版本中。

## 核心组件支持 {#core-components-support}

核心组件是 AEM 的一个组成部分，依原样提供支持，并作为“快速入门”的一部分提供，须遵循相同的条款和条件。

与其他产品功能一样，其生命周期结束的一般规则是：

* 组件在被删除之前，先被声明弃用；
* 声明弃用之后，这些组件将最早从 AEM 版本中删除。

这为客户提供了至少一个发布周期，以便在支持结束前转移到组件的新版本。

每个组件的版本都清楚地声明了其支持的 AEM 版本。当某个 AEM 版本不再受到支持时，该版本 AEM 的核心组件也不再受到支持。

有关组件自定义支持的详细信息，请参阅相关核心组件版本的[自定义核心组件](developing/customizing.md)页面。

## 基础组件支持 {#foundation-component-support}

Adobe的开发重点已转移到核心组件上，并将继续添加新功能。

[AEM 6.5中几乎所有基础组件都已弃用](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/siteandpage/default-components-foundation.html) ，今后只会考虑基础组件的主要错误修复。
