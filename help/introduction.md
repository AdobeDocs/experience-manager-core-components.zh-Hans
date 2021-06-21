---
title: 核心组件简介
description: '核心组件基于最新技术和最佳实践提供强大且可扩展的基本组件。 '
role: Architect, Developer, Administrator, Business Practitioner
exl-id: d294db22-4cb0-48a4-9366-03fda5b8bb8e
source-git-commit: cc1fc14e1ca9125a24c13ac68716951ef790afea
workflow-type: tm+mt
source-wordcount: '936'
ht-degree: 24%

---

# 核心组件简介{#core-components-introduction}

在 Adobe Experience Manager 中，组件是结构化元素，用于构成所创作的页面内容。组件一直是 AEM 体验的一个基本元素，它使页面的创建过程变得简便但功能强大，使开发人员对组件的开发变得灵活且可扩展。

核心组件是一套适用于AEM的标准化Web内容管理(WCM)组件，可加快开发时间并降低网站维护成本。

## 资源 {#resources}

* **[组件库：](https://www.adobe.com/go/aem_cmp_library)** 用于查看其各种配置中的组件的一组示例。
* **组件文档（本文档）：** 对于开发人员和作者，包含有关每个组件的详细信息。
* **[核心组件GitHub存储库：](https://github.com/adobe/aem-core-wcm-components)** 有关每个组件和项目下载的开发人员详细信息。
* 开始使用:
   * **[核心组件成功：](/help/developing/success.md)** 在开始任何使用核心组件的项目之前，请务必考虑相关准则。
   * **[WKND教程：](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)** 有关构建新站点的为期两天的教程。
   * **[峰会教程：](https://expleague.azureedge.net/labs/L767/index.html)** 一个两小时的教程，用于构建新站点（来自2019年美国峰会的实验室）。
   * **[Gems网络研讨会：](https://helpx.adobe.com/cn/experience-manager/kt/eseminars/gems/AEM-Core-Components.html)** 核心组件的指导性浏览（2018年12月录制）。

## 功能 {#features}

|  |  |
|---|---|
| 可以即刻投入使用 | 核心组件是28个强大的组件，经过良好测试、广泛使用，并且性能良好。 |
| 云就绪 | 无论在[AEM as aCloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html)、在[Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams)上还是在内部部署版上，它们都只能正常工作。 |
| 可以通用 | 这些组件表示作者几乎可以装配任何布局的通用概念。 |
| 可配置 | 模板级别[内容策略](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/components-templates/templates.html#content-policies)定义页面作者可以使用或不使用的功能。 |
| 可跟踪 | [Adobe客户端数据层集成](/help/developing/data-layer/overview.md)允许跟踪访客体验的所有方面。 |
| 可访问 | 它们符合[WCAG 2.1标准](https://www.w3.org/TR/WCAG21/)，提供ARIA标签，并支持键盘导航（[已知问题](https://github.com/adobe/aem-core-wcm-components/issues?utf8=✓&amp;q=is%3Aissue+is%3Aopen+accessibility+in%3Atitle)）。 |
| SEO友好 | HTML输出是语义的，并提供[schema.org](https://schema.org)微数据批注。 |
| WebApp-Ready | [简化的JSON输出](https://docs.adobe.com/content/help/en/experience-manager-learn/foundation/development/develop-sling-model-exporter.html)允许客户端渲染，但仍可能进行[上下文内编辑](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html)。 |
| AMP支持 | 这些组件内置了[对AMP标准的支持，](/help/developing/amp.md)可加速您的移动体验。 |
| 设计工具包 | 适用于Adobe XD的[UI套件](https://experienceleague.adobe.com/docs/experience-manager-learn/assets/AEM-CoreComponents-UI-Kit.xd)允许设计人员创建线框，然后他们可以根据需要[样式](https://github.com/adobe/aem-guides-wknd/releases/download/aem-guides-wknd-0.0.2/AEM_UI-kit-WKND.xd)。 |
| 表 | 这些组件实施[样式系统](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/components-templates/style-system.html)，且标记遵循[BEM CSS约定](http://getbem.com/)。 |
| 可自定义 | 通过使用多种模式，[可轻松自定义](developing/customizing.md)，从调整HTML到重新使用高级功能。 |
| 版本控制 | [版本控制策略](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-policies)可确保在改进可能影响您的内容时，核心组件不会破坏您的网站。 |
| 可本地化 | 智能引用解析允许某些组件自动查找和[渲染相应的本地化内容](get-started/localization.md)。 |
| 开源 | 如果某些内容不如预期，[将提供改进！](https://github.com/adobe/aem-core-wcm-components/blob/master/CONTRIBUTING.md) |

## 组件 {#the-components}

当前版本的核心组件具有以下组件。

### 模板组件{#template-components}

* [页面](components/page.md)
* [导航](components/navigation.md)
* [语言导航](components/language-navigation.md)
* [痕迹导航](components/breadcrumb.md)
* [快速搜索](components/quick-search.md)

### 页面创作组件{#page-authoring-components}

* [标题](components/title.md)
* [文本](components/text.md)
* [图像](components/image.md)
* [按钮](components/button.md)
* [Teaser](components/teaser.md)
* [下载](components/download.md)
* [列表](components/list.md)
* [体验片段](components/experience-fragment.md)
* [内容片段](components/content-fragment-component.md)
* [内容片段列表](components/content-fragment-list.md)
* [嵌入](components/embed.md)
* [社交媒体共享](components/sharing.md)
* [分隔符](components/separator.md)
* [进度条](components/progress-bar.md)
* [PDF 查看器](components/pdf-viewer.md)

### 容器组件{#container-components}

* [容器](components/container.md)
* [轮播](components/carousel.md)
* [选项卡](components/tabs.md)
* [折叠](components/accordion.md)

### 表单组件 {#form-components}

* [表单容器](components/forms/form-container.md)
* [表单文本](components/forms/form-text.md)
* [表单选项](components/forms/form-options.md)
* [隐藏的表单](components/forms/form-hidden.md)
* [表单按钮](components/forms/form-button.md)

>[!NOTE]
>
>核心组件不可直接供作者使用，[开发团队必须先将它们集成到您的环境中](get-started/using.md)。集成后，即可通过[模板编辑器](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)使用和预配置模板。

>[!NOTE]
>
>个别核心组件的某些版本可能仅与特定版本的 AEM 兼容。
>
>有关兼容性信息，请参阅特定组件对应的帮助页面（可在上文中的列表中点击相应链接），或参考[核心组件版本](versions.md)文档以了解更多信息。

## 系统要求{#system-requirements}

| 核心组件 | AEM as a Cloud Service | AEM 6.5 | AEM 6.4 | Java SE | 马文 |
|---------|---------|---------|---------|---------|---------|
| [2.17.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.17.0) | 持续 | 6.5.6.0+ * | 6.4.8.4+ * | 8, 11 | 3.3.9+ |

>[!NOTE]
>
>(*)自版本2.11.0起，要求使用`org.apache.sling.models.impl`版本1.4.12或更高版本（由于[SLING-8781](https://issues.apache.org/jira/browse/SLING-8781)）。 这将在将来的Service Pack中为AEM 6.4和6.5提供。 在此之前，`core.wcm.components.all`包中包含Sling模型包。

有关以前核心组件版本的要求，请参阅[核心组件版本](versions.md)。

核心组件需要使用[可编辑的模板](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/page-authoring/template-editor-feature-video-use.html)，并且不支持经典UI或静态模板。 如果需要，请查看[AEM现代化工具](https://opensource.adobe.com/aem-modernize-tools/pages/tools.html)以使用这些现代AEM功能更新您的项目。

要设置本地开发环境，请查看[此AEM as a Cloud Service SDK](https://docs.adobe.com/content/help/en/experience-manager-learn/cloud-service/local-development-environment-set-up/overview.html)概述，或查看此文档[，了解旧版AEM](https://docs.adobe.com/content/help/en/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html)。

>[!TIP]
>
>核心组件会自动作为Cloud Service包含在AEM中，并且您始终可以获得最新版本的核心组件。
>
>有关如何在AEMaaCS和内部部署中开始使用核心组件的更多信息，请参阅[使用核心组件](/help/get-started/using.md)文档。
