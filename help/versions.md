---
title: 核心组件版本
description: 核心组件作为发行版本发布，发行版本可能包含相同核心组件的多个版本。本文档介绍了什么是发行版本和版本，以及如何了解核心组件与 AEM 的兼容性。
role: Architect, Developer, Admin, User
exl-id: 7d4dbe46-4013-4217-b815-cdb1462072c6
source-git-commit: 0d004c90e789f23ff9e121fbd8ae11df9c9748b2
workflow-type: tm+mt
source-wordcount: '2874'
ht-degree: 99%

---

# 核心组件版本 {#core-components-versions}

核心组件的当前发行版本是 2.22.0，与 [AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html?lang=zh-Hans) 和[内部部署 AEM](https://experienceleague.adobe.com/docs/experience-manager-65/user-guide/home.html?lang=zh-Hans) 安装兼容。

## 发行版本历史记录和兼容性 {#release-history-and-compatibility}

核心组件设计为灵活且与支持的所有 AEM 版本兼容。因此，组件的一个发行版本可以包含同一组件的多个版本。

以下各表说明了核心组件发行版本的兼容性，以及哪些发行版本中包含了哪些组件版本。

### 发行版本历史记录和要求 {#release-history-requirements}

下表的内容在 [GitHub 上提供，包含完整的发行版本详细信息](https://github.com/adobe/aem-core-wcm-components/releases)，概述了核心组件的发行版本及其与 AEM 发行版本和 Java 版本的兼容性。

| 发行版本 | 描述 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service | Java | 发布日期 |
|---|---|---|---|---|---|---|
| [2.22.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.22.0) | 此版本引入了 [列表组件](/help/components/list.md) 以及 [Teaser](/help/components/teaser.md) 及更新 [PDF查看器。](/help/components/pdf-viewer.md) | - | 6.5.14.0+ * | 连续 | 8, 11 | 2023 年 2 月 9 日 |
| [2.21.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.21.2) | 这是一个补丁版本，它修复了 v1 和 v2 中 [Teaser 组件](/help/components/teaser.md)的问题。 | - | 6.5.13.0+ * | 连续 | 8, 11 | 2022 年 9 月 12 日 |
| [2.21.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.21.0) | 此版本包括许多增强功能，其中包括发布了 LinkHandler API、改进了[图像组件](/help/components/image.md)和[数据层](/help/developing/data-layer/overview.md)以及改进了多面板组件。 | - | 6.5.13.0+ * | 连续 | 8, 11 | 2022 年 9 月 12 日 |
| [2.20.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.20.8) | 此版本修复了通过 AdaptiveImageServlet 传送 SVG 图像的问题。 | - | 6.5.13.0+ * | 连续 | 8, 11 | 2022 年 8 月 4 日 |
| [2.20.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.20.6) | 此补丁版本修复了新的[目录组件的问题。](/help/components/tableofcontents.md) | - | 6.5.13.0+ * | 连续 | 8, 11 | 2022 年 7 月 7 日 |
| [2.20.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.20.4) | 此补丁版本修复了新的[目录组件的问题。](/help/components/tableofcontents.md) | - | 6.5.13.0+ * | 连续 | 8, 11 | 2022 年 6 月 29 日 |
| [2.20.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.20.2) | 这是一个修补程序版本，修复了新的 AEMaaCS [网络优化资产投放服务中的问题。](/help/developing/web-optimized-image-delivery.md) | - | 6.5.13.0+ * | 连续 | 8, 11 | 2022 年 6 月 20 日 |
| [2.20.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.20.0) | 此版本添加了一个新的[目录组件](/help/components/tableofcontents.md)，增加了对 AEMaaCS [网络优化资产投放服务](/help/developing/web-optimized-image-delivery.md)的支持，并包括错误修复。 | - | 6.5.13.0+ * | 连续 | 8, 11 | 2022 年 6 月 9 日 |
| [2.19.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.19.0) | 这一发行版本引入了[搜索组件](/help/components/quick-search.md)的一个新版本、[按钮组件](/help/components/button.md)的一些新功能，以及多项辅助功能改进和错误修复。 | - | 6.5.10.0+ * | 连续 | 8、11 | 2022 年 4 月 7 日 |
| [2.18.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.18.8) | 此版本修复了 AEMaaCS 的一个问题。 | - | 6.5.10.0+ * | 连续 | 8, 11 | 2022 年 3 月 17 日 |
| [2.18.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.18.6) | 这是一个补丁发行版本。 | - | 6.5.10.0+ * | 连续 | 8, 11 | 2022 年 3 月 |
| [2.18.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.18.0) | 核心组件的这个主要发行版本引入了新链接处理程序，它跨多个组件的新版本，以及许多辅助功能改进和错误修复。 | - | 6.5.10.0+ * | 连续 | 8, 11 | 2022 年 2 月 16 日 |
| [2.17.14](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.12) | 这是一个补丁发行版本。 | 6.4.8.4+ * | 6.5.6.0+ * | 连续 | 8, 11 | 2021 年 12 月 13 日 |
| [2.17.12](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.12) | 这是一个补丁发行版本，修复了上一个版本引入的回归。 | 6.4.8.4+ * | 6.5.6.0+ * | 连续 | 8, 11 | 2021 年 10 月 1 日 |
| [2.17.10](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.10) | 此补丁增强了[列表](/help/components/list.md)和[导航](/help/components/navigation.md)组件以显示重定向目标的外部 URL，支持即将发布的 v2 的 [Teaser](/help/components/teaser.md) 组件的页面图像继承以及包含其他错误修复。 | 6.4.8.4+ * | 6.5.6.0+ * | 连续 | 8, 11 | 2021 年 8 月 31 日 |
| [2.17.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.8) | 这是一个补丁发行版本，用于修复之前引入的无法向后兼容的更改。 | 6.4.8.4+ * | 6.5.6.0+ * | 连续 | 8, 11 | 2021 年 8 月 2 日 |
| [2.17.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.6) | 此补丁发行版本添加了对页面的站点地图的支持，并包括各种辅助功能改进。 | 6.4.8.4+ * | 6.5.6.0+ * | 连续 | 8, 11 | 2021 年 7 月 29 日 |
| [2.17.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.2) | 此补丁发行版本包括对[数据层](/help/developing/data-layer/overview.md)不可用于 AEMaaCS 的修复。 | 6.4.8.4+ * | 6.5.6.0+ * | 连续 | 8, 11 | 2021 年 7 月 8 日 |
| [2.17.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.0) | 此发行版本包括许多支持链接处理程序功能的新组件版本的技术预览版，以及精选图像功能的技术预览版，该图像功能适用于[页面组件。](/help/components/page.md)其中还包括了多个错误修复。 | 6.4.8.4+ * | 6.5.6.0+ * | 连续 | 8, 11 | 2021 年 6 月 16 日 |
| [2.16.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.16.4) | 此补丁发行版用于修复新的链接处理程序的问题。 | 6.4.8.1+ * | 6.5.5.0+ * | 连续 | 8, 11 | 2021 年 5 月 19 日 |
| [2.16.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.16.2) | 此补丁发行版本主要修复了新的链接处理程序的问题，并增加了对 [PWA](/help/components/page.md#pwa-support) 多页应用程序的支持。 | 6.4.8.1+ * | 6.5.5.0+ * | 连续 | 8, 11 | 2021 年 5 月 15 日 |
| [2.16.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.16.0) | 此发行版本重点提供了可访问性改进以及向现有组件引入了新的链接处理程序。 | 6.4.8.1+ * | 6.5.5.0+ * | 连续 | 8, 11 | 2021 年 4 月 22 日 |
| [2.15.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.15.2) | 此补丁发行版本主要修复了[数据层](/help/developing/data-layer/overview.md)的向后兼容性问题以及特定情况下的 IT 测试失败。 | 6.4.8.1+ * | 6.5.5.0+ * | 连续 | 8, 11 | 2021 年 3 月 16 日 |
| [2.15.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.15.0) | 此发行版本包括了对[页面组件中的渐进式 Web 应用程序 (PWA)](/help/components/page.md#pwa-support) 的支持，并支持 [Adobe 数据层](/help/developing/data-layer/overview.md)版本 2.0.0。 | 6.4.8.1+ * | 6.5.5.0+ * | 连续 | 8, 11 | 2021 年 2 月 23 日 |
| [2.14.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.14.0) | 此发行版本包括了用于[嵌入组件](/help/components/embed.md)的新选项，并在[页面](/help/components/page.md)级别引入了 Brand Slug 且解决了许多问题。 | 6.4.8.1+ * | 6.5.5.0+ * | 连续 | 8, 11 | 2021 年 2 月 9 日 |
| [2.13.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.13.2) | 此补丁发行版本解决了在 AEMaaCS 上使用时 RTE 出现的问题。 | 6.4.8.1+ * | 6.5.5.0+ * | 连续 | 8, 11 | 2020 年 12 月 16 日 |
| [2.13.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.13.0) | 此发行版本包括用于[图像组件](/help/components/image.md)的新 Dynamic Media 功能。 | 6.4.8.1+ * | 6.5.5.0+ * | 连续 | 8, 11 | 2020 年 12 月 4 日 |
| [2.12.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.12.2) | 这是 2.12.0 的补丁发行版本，包含小修复。 | 6.4.8.1+ * | 6.5.5.0+ * | 连续 | 8, 11 | 2020 年 11 月 11 日 |
| [2.12.1](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.12.1) | 这是 2.12.0 的补丁发行版本，修复了[图像组件](/help/components/image.md)中的重大错误。 | 6.4.8.1+ * | 6.5.5.0+ * | 连续 | 8, 11 | 2020 年 11 月 5 日 |
| [2.12.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.12.0) | 此发行版本引入了[新的 POST 表单处理程序、](/help/components/forms/form-container.md#post-data)通过上下文感知配置[包括自定义 CSS、JavaScript 和元数据标记的能力](/help/developing/including-clientlibs.md#context-aware-loading)以及`DataLayerBuilder`[在自定义组件中简化数据层集成](/help/developing/data-layer/integrations.md#enabling-custom-components)的实用程序。 | 6.4.8.1+ * | 6.5.5.0+ * | 连续 | 8, 11 | 2020 年 10 月 29 日 |
| [2.11.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.11.0) | 此发行版本引入了 [AMP 支持](/help/developing/amp.md)。 | 6.4.8.1+ * | 6.5.5.0+ * | 连续 | 8, 11 | 2020 年 7 月 20 日 |
| [2.10.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.10.0) | 此发行版本引入了 [PDF 查看器组件](/help/components/pdf-viewer.md)。 | 6.4.8.1+ | 6.5.5.0+ | 连续 | 8, 11 | 2020 年 6 月 17 日 |
| [2.9.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.9.0) | 此发行版本启用了与 [Adobe 客户端数据层](/help/developing/data-layer/overview.md)的集成并引入了[进度条组件](/help/components/progress-bar.md)。 | 6.4.8.0+ | 6.5.4.0+ | 连续 | 8, 11 | 2020 年 5 月 29 日 |
| [2.8.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.8.0) | 此发行版本重点进行了修复并包括一些小的增强功能。 | 6.4.4.0+ | 6.5.0.0+ | 连续 | 8, 11 | 2019 年 12 月 5 日 |
| [2.7.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.7.0) | 此发行版本引入了新的[嵌入组件](/help/components/embed.md)。 | 6.4.4.0+ | 6.5.0.0+ | 连续 | 8, 11 | 2019 年 9 月 25 日 |
| [2.6.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.6.0) | 此发行版本引入了新的[体验片段组件](/help/components/experience-fragment.md)。 | 6.4.4.0+ | 6.5.0.0+ | 连续 | 8, 11 | 2019 年 9 月 6 日 |
| [2.5.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.5.0) | 此发行版本引入了新的[折叠](/help/components/accordion.md)、[按钮](/help/components/button.md)、[容器](/help/components/container.md)和[下载组件](/help/components/download.md)。 | 6.4.2.0+ | 6.5.0.0+ | 连续 | 8, 11 | 2019 年 6 月 25 日 |
| [2.4.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.4.0) | 此发行版本引入了[内容片段列表组件](/help/components/content-fragment-list.md)。 | 6.4.2.0+ | 6.5.0.0+ | 连续 | 8, 11 | 2019 年 5 月 7 日 |
| [2.3.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.2) | 此发行版本重点对[组件库](https://aemcomponents.dev)进行了改良，但还包括了一些针对[分隔符组件](/help/components/separator.md)的功能增强。 | 6.4.2.0+ | 6.5.0.0+ | 连续 | 8 | 2019 年 3 月 14 日 |
| [2.3.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.3.0) | 此发行版本重点针对[组件库](https://aemcomponents.dev)进行了改进，以及引入了新的[分隔符组件](/help/components/separator.md)，但还包括了一些针对[图像组件](/help/components/image.md)的功能增强。 | 6.4.2.0+ | - | - | 8 | 2019 年 2 月 11 日 |
| [2.2.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.2) | 此发行版本主要针对错误修复，但还包括了一些针对[轮盘组件](/help/components/carousel.md)的功能增强。 | 6.4.2.0+ | - | - | 8 | 2018 年 11 月 27 日 |
| [2.2.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.2.0) | 此发行版本引入了[选项卡组件](/help/components/tabs.md)和[轮盘组件](/help/components/carousel.md)，还包括对[图像组件](/help/components/image.md)、[页面组件](/help/components/page.md)和[标题组件](/help/components/title.md)的改进，并增强了跟踪功能。 | 6.4.2.0+ | - | - | 8 | 2018 年 10 月 16 日 |
| [2.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.1.0) | 此发行版本引入了 [Teaser 组件](/help/components/teaser.md)以及对[图像组件](/help/components/image.md)的改进，并修复了多个错误。 | 6.4.2.0+ | - | - | 8 | 2018 年 7 月 13 日 |
| [2.0.8](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.8) | 这是错误修复发行版本。 | 6.4.0.0+ | - | - | 8 | 2018 年 6 月 12 日 |
| [2.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.6) | 此发行版本添加了底层改进、错误修复以及小改进，包括支持[图像组件](/help/components/image.md)中的图像翻转。 | 6.4.0.0+ | - | - | 8 | 2018 年 4 月 11 日 |
| [2.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.4) | 此发行版本大部分重点放在底层改进、错误修复以及对[图像组件](/help/components/image.md)、[页面组件](/help/components/page.md)和[内容片段组件](/help/components/content-fragment-component.md)的一些小改进。 | 6.4.0.0+ | - | - | 8 | 2018 年 3 月 7 日 |
| [2.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.0.0) | 此发行版本引入了[导航组件](/help/components/navigation.md)、[语言导航组件](/help/components/language-navigation.md)和[快速搜索组件](/help/components/quick-search.md)，并为所有组件实施了[样式系统](/help/get-started/authoring.md#component-styling)。 | 6.4.0.0+ | - | - | 8 | 2018 月 1 月 16 日 |
| [1.1.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.1.0) | 此发行版本在所有组件上实施了 JSON 导出，并引入了[内容片段组件](/help/components/content-fragment-component.md)。 | 6.4.0.0+ | - | - | 8 | 2017 年 10 月 10 日 |
| [1.0.6](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.6) | 此发行版本添加了对[图像组件](/help/components/image.md)的多个修复。 | 6.4.0.0+ | - | - | 8 | 2017 年 8 月 4 日 |
| [1.0.4](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.4) | 此发行版本添加了对[页面组件](/help/components/page.md)、[图像组件](/help/components/image.md)的修复，以及各种全局修复和改进。 | 6.4.0.0+ | - | - | 8 | 2017 年 4 月 26 日 |
| [1.0.2](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.all-1.0.2) | 此发行版本添加了对[图像组件](/help/components/image.md)的动画 GIF 图像的修复。 | 6.4.0.0+ | - | - | 7 | 2017 年 3 月 22 日 |
| [1.0.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-1.0.0) | 核心组件的初始发行版本 | 6.4.0.0+ | - | - | 7 | 2017 年 3 月 20 日 |

>[!NOTE]
>
>(*) 自版本 2.11.0 开始，需要 `org.apache.sling.models.impl` 版本 1.4.12 或更高版本（由于 [SLING-8781](https://issues.apache.org/jira/browse/SLING-8781)）。这会在将来的服务包中为 AEM 6.4 和 6.5 提供。在此之前，Sling 模型捆绑包将包含在 `core.wcm.components.all` 包中。

>[!TIP]
>
>对于 AEM，Adobe 建议开发人员使用可与所运行 AEM 版本兼容的[核心组件的最新发行版本和版本](https://github.com/adobe/aem-core-wcm-components/releases/latest)，以获得最新的修复和功能好处。

### 组件版本和发行版本 {#component-versions-and-releases}

下表详细列出了哪些组件的哪些版本包括在核心组件的哪些发行版本中。

|  | 发行版本 1.0.0 – 1.0.6 | 发行版本 1.1.0 | 发行版本 2.0.0 – 2.0.8 | 发行版本 2.1.0 | 发行版本 2.2.0 – 2.2.0 | 发行版本 2.3.0 – 2.3.2 | 发行版本 2.4.0 | 发行版本 2.5.0 | 发行版本 2.6.0 | 发行版本 2.7.0 – 2.8.0 | 发行版本 2.9.0 – 2.17.14 | 发行版本 2.18.0 | 发行版本 2.19.0 | 版本2.20.0-2.21.2 | 版本2.22.0+ |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| **[页面](components/page.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1、v2、v3 | v1、v2、v3 | v1、v2、v3 | v1、v2、v3 |
| **[标题](components/title.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1、v2、v3 | v1、v2、v3 | v1、v2、v3 | v1、v2、v3 |
| **[图像](components/image.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1、v2、v3 | v1、v2、v3 | v1、v2、v3 | v1、v2、v3 |
| **[列表](components/list.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1、v2、v3 | v1、v2、v3 | v1、v2、v3 | v1、v2、v3, v4 |
| **[痕迹导航](components/breadcrumb.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1、v2、v3 | v1、v2、v3 | v1、v2、v3 | v1、v2、v3 |
| **[社交媒体共享](components/sharing.md)** | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1，已弃用 | v1，已弃用 | v1，已弃用 | v1，已弃用 |
| **[表单容器](components/forms/form-container.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1，v2 |
| **[表单文本](components/forms/form-text.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1，v2 |
| **[表单选项](components/forms/form-options.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1，v2 |
| **[表单隐藏](components/forms/form-hidden.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1，v2 |
| **[表单按钮](components/forms/form-button.md)** | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1，v2 |
| **[内容片段](components/content-fragment-component.md)** |  | 沙盒 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1, v2 | v1，v2 |
| **[导航](components/navigation.md)** |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[语言导航](components/language-navigation.md)** |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[快速搜索](components/quick-search.md)** |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1, v2 | v1, v2 | v1, v2 |
| **[Teaser](components/teaser.md)** |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[选项卡](components/tabs.md)** |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[轮盘](components/carousel.md)** |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[分隔符](components/separator.md)** |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[内容片段列表](components/content-fragment-list.md)** |  |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[折叠](components/accordion.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[按钮](components/button.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[容器](components/container.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 | v1 | v1 | v1 |
| **[下载](components/download.md)** |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[体验片段](components/experience-fragment.md)** |  |  |  |  |  |  |  |  | v1 | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[嵌入](components/embed.md)** |  |  |  |  |  |  |  |  |  | v1 | v1 | v1, v2 | v1, v2 | v1, v2 | v1, v2 |
| **[进度条](components/progress-bar.md)** |  |  |  |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 |
| **[PDF 查看器](components/pdf-viewer.md)** |  |  |  |  |  |  |  |  |  |  | v1 | v1 | v1 | v1 | v1 |
| **[目录](components/tableofcontents.md)** |  |  |  |  |  |  |  |  |  |  |  |  |  | v1 | v1 |

## 版本和发行版本 {#versions-and-releases}

核心组件通过 GitHub 分发。这使得 Adobe 可以更快地向组件添加功能，还可以允许社区在 AEM 发行版本周期之外输入内容。

核心组件与定义的兼容 AEM 版本一起提供。这意味着一个 AEM 版本可以支持核心组件的多个版本或发行版本。

### 版本 {#versions}

核心组件的主要迭代就是&#x200B;**版本**。每个组件有一个版本。版本使用 **v** 加上非零正整数表示，例如 v1 和 v2。只有进行了不向后兼容的更改时才增加版本，这通常是引入了新的特性和功能。

开发人员和管理员可以按照其资源类型路径中的数字以及其实施中的完全限定 Java 类名，来识别核心组件的版本。此版本数字表示按照[语义版本控制指南](https://semver.org/)定义的主版本。

有关核心组件版本的详细信息，请参阅[核心组件开发人员文档](developing/guidelines.md)。

### 发行版本 {#releases}

通过&#x200B;**发行版**&#x200B;提供核心组件，并且核心组件[表示可在 GitHub 上找到的真实发布的构件。](https://github.com/adobe/aem-core-wcm-components/releases)用 `X.Y.Z` 格式的小数表示发行版，并且发行版将所有核心组件收集在一起作为可交付的包。

* **主要发行版本**&#x200B;引入了全新组件、对现有组件版本的改进以及标准错误修复。这由发行版本编号中 `X` 部分的增加来表示。
* **次要发行版本**&#x200B;引入了新组件、现有组件版本的新功能以及错误修复。这由发行版本编号中 `Y` 部分的增加来表示。
* **补丁发行版本**&#x200B;仅包含错误修复。这由发行版本编号中 `Z` 部分的增加来表示。

>[!NOTE]
>
>发行版本可以包含相同组件的多个版本。
>
>组件的相同版本可以显示为多个发行版本。

## 核心组件支持 {#core-components-support}

核心组件是 AEM 的一个组成部分，作为“快速入门”的一部分提供，遵循相同的条款和条件。

与其他产品功能一样，其生命周期结束的一般规则是：

* 组件在被删除之前，先被声明弃用；
* 声明弃用之后，这些组件将最早从 AEM 版本中删除。

这为客户提供了至少一个发布周期，以便在支持结束前转移到组件的新版本。

每个组件的版本都清楚地声明了其支持的 AEM 版本。当某个 AEM 版本不再受到支持时，该版本 AEM 的核心组件也不再受到支持。

有关组件自定义支持的详细信息，请参阅相关核心组件版本的[自定义核心组件](developing/customizing.md)页面。

## 基础组件支持 {#foundation-component-support}

Adobe 的开发重点已经转向核心组件，并将继续添加新功能。

[几乎所有的基础组件已在 AEM 6.5 中弃用](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/siteandpage/default-components-foundation.html?lang=zh-Hans)，未来只考虑修复基础组件的重大错误。
