---
title: 核心组件简介
description: '引入核心组件是为了基于最新技术和最佳做法，提供强大、可扩展的基本组件。 '
translation-type: tm+mt
source-git-commit: 1c6e27c163f72fd66336e8db883144dc4dd60510

---


# 核心组件简介{#core-components-introduction}

在 Adobe Experience Manager 中，组件是结构化元素，用于构成所创作的页面内容。组件一直是 AEM 体验的一个基本元素，它使页面的创建过程变得简便但功能强大，使开发人员对组件的开发变得灵活且可扩展。

核心组件是一组面向AEM的标准化Web内容管理(WCM)组件，可缩短开发时间并降低网站的维护成本。

## 资源 {#resources}

* **[组件库：](https://www.adobe.com/go/aem_cmp_library)**视图各种配置中组件的示例集合。
* **组件文档(本文档):** 对于开发人员和作者，包含每个组件的详细信息。
* 开始使用:
   * **[核心组件的成功：](/help/developing/success.md)**在开始将使用核心组件的任何项目之前，应考虑的准则。
   * **[WKND教程：](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)**用于构建新站点的两天教程。
   * **[峰会教程：](https://expleague.azureedge.net/labs/L767/index.html)**一个两小时的教程，用于构建新站点（来自2019年美国峰会上的实验室）。
   * **[Gems网络研讨会：](https://helpx.adobe.com/cn/experience-manager/kt/eseminars/gems/AEM-Core-Components.html)**核心组件的指导浏览（2018年12月录制）。

## 功能 {#features}

|  |  |
|---|---|
| 可以即刻投入使用 | 核心组件是27个强大的组件，经过测试、广泛使用并且性能良好。 |
| 云就绪 | 无论在 [AEM上还是在](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html)Adobe Managed Services上 [](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams)，还是在预置型服务上，它们都可以正常工作。 |
| 可以通用 | 这些组件代表通用概念，作者可以使用这些概念组合几乎任何布局。 |
| 可配置 | 模板级内 [容策略](https://docs.adobe.com/content/help/en/experience-manager-65/developing/platform/templates/page-templates-editable.html#content-policies) ，定义允许或不允许页面作者使用的功能。 |
| 可访问 | They comply [WCAG 2.1 standard](https://www.w3.org/TR/WCAG21/), provide ARIA labels, and support keyboard navigation ([known issues](https://github.com/adobe/aem-core-wcm-components/issues?utf8=✓&amp;q=is%3Aissue+is%3Aopen+accessibility+in%3Atitle)). |
| SEO-Friendly | The HTML output is semantic and provides [schema.org](https://schema.org) microdata annotations. |
| WebApp-Ready | 简化 [的JSON输出允许客户端渲染](https://docs.adobe.com/content/help/en/experience-manager-learn/foundation/development/develop-sling-model-exporter.html) ，但仍有可能进行上 [下文编辑](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html)。 |
| 设计套件 | Adobe XD [的UI套件使设计人员能创建线框](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/assets/overview/AEM_UI-kit_Wireframe.xd) ，然后可以根据需 [要设计样式](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/assets/overview/AEM_UI-kit_WKND.xd)。 |
| 可编辑 | The components implement the [Style System](https://docs.adobe.com/content/help/en/experience-manager-65/developing/components/style-system.html), and the markup follows [BEM CSS conventions](http://getbem.com/). |
| 可自定义 | 从调整HTML到高 [级功能重用](developing/customizing.md)，多种模式可轻松实现自定义。 |
| 版本控制 | 版 [本控制策略](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-policies) ，可确保在改进可能影响您的内容时，核心组件不会破坏您的站点。 |
| 可本地化 | Smart reference resolution allows certain components to find and [render corresponding localized content automatically](get-started/localization.md). |
| 开放源 | 如果某件事情不是应有的， [请改进！](https://github.com/adobe/aem-core-wcm-components/blob/master/CONTRIBUTING.md) |

## 组件 {#the-components}

当前版本的核心组件具有以下组件。

### 模板组件 {#template-components}

* [页面](components/page.md)
* [导航](components/navigation.md)
* [语言导航](components/language-navigation.md)
* [痕迹导航](components/breadcrumb.md)
* [快速搜索](components/quick-search.md)

### 页面创作组件 {#page-authoring-components}

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

### 容器组件 {#container-components}

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
>核心组件不可直接供作者使用，[开发团队必须先将它们集成到您的环境中](get-started/using.md)。Once integrated, they may be made available and pre-configured via the [template editor](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html).

>[!NOTE]
>
>个别核心组件的某些版本可能仅与特定版本的 AEM 兼容。
>
>有关兼容性信息，请参阅特定组件对应的帮助页面（可在上文中的列表中点击相应链接），或参考[核心组件版本](versions.md)文档以了解更多信息。

## 系统要求 {#system-requirements}

| 核心组件 | AEM 云服务 | AEM 6.5 | AEM 6.4 | AEM 6.3 | Java SE | 马文 |
---------|---------|---------|---------|---------|---------|---------
| [2.8.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.8.0) | 连续 | 6.5.0.0+ | 6.4.4.0+ | 6.3.3.4+ | 8, 11 | 3.3.9+ |

有关先前核心组件版本的要求，请参阅核 [心组件版本](versions.md)。

核心组件需要使用可编辑的模 [板](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/page-authoring/template-editor-feature-video-use.html) ，并且不支持经典UI或静态模板。 如果需要，请查看 [AEM现代化工具](https://opensource.adobe.com/aem-modernize-tools/pages/tools.html) ，以使用这些现代AEM功能更新您的项目。

要设置本地开发环境，请将 [AEM的此概述作为Cloud Service SDK查看](https://docs.adobe.com/content/help/en/experience-manager-learn/cloud-service/local-development-environment-set-up/overview.html) ，或将 [此文档用于旧版AEM](https://docs.adobe.com/content/help/en/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html)。
