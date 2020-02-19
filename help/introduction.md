---
title: 核心组件简介
description: '引入核心组件是为了基于最新技术和最佳做法，提供强大、可扩展的基本组件。 '
translation-type: tm+mt
source-git-commit: fe8a121520000ffd56ae3347469590e89121eaf0

---


# 核心组件简介{#core-components-introduction}

在 Adobe Experience Manager 中，组件是结构化元素，用于构成所创作的页面内容。组件一直是 AEM 体验的一个基本元素，它使页面的创建过程变得简便但功能强大，使开发人员对组件的开发变得灵活且可扩展。

引入核心组件是为了提供强大、可扩展的基本组件，这些基本组件构建在最新的技术和最佳做法之上，并遵从辅助功能准则，且符合 WCAG 2.0 AA 标准。核心组件使页面创作更灵活、可自定义，并且对开发人员而言，很容易扩展这些组件以提供自定义功能。

## 试用核心组件

如果要立即开始尝试核心组件，请转到[组件库](https://adobe.com/go/aem_cmp_library)。组件库是大多数最新版核心组件的在线展示，可以让您与各种组件进行交互，并查看示例 HTML 和 JSON 输出。

WKND教 [程还说明了](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html) 如何使用核心组件。

## 核心组件 - 核心特性{#core-components-core-features}

核心组件具有以下特性：

|  |  |
|--- |--- |
| 可以预先配置 | 可以通过模板定义页面作者如何使用这些组件。 |
| 可以通用 | 作者使用这些组件即可创建大多数类型的内容。 |
| 易于使用 | 作者可以使用这些组件高效地创建和管理内容。 |
| 可以即刻投入使用 | 现成可用！它们强大、经过良好测试，并且性能良好。 |
| 可访问 | 它们符合 WCAG 2.0 标准，提供 ARIA 标签，并支持键盘导航。 |
| 易于设计 | 这些组件实施“样式系统”，且标记遵循 BEM CSS 命名规范。 |
| SEO 友好 | HTML 输出是语义的，并提供 schema.org 微数据注解。 |
| 可用于 PWA/SPA/应用程序 | 它们精简的 JSON 输出也可以用作客户端渲染。 |
| 可扩展 | 可满足自定义需求并且不需要从零开始，任何东西都可以扩展。 |
| 开源 | 如果某些组件的效果不如预期，还可在 GitHub（Apache 许可）上提出相关改进。 |
| 版本控制 | 我们对核心组件进行改进时，即使改进的组件可能对您有所影响，也不会破坏您的站点。 |
| [本地化](get-started/localization.md) | 智能参考分辨率允许某些组件自动查找和呈现相应的本地化内容 |

## 可用组件 {#available-components}

当前版本的核心组件具有以下组件。

* [折叠](components/accordion.md)
* [痕迹导航](components/breadcrumb.md)
* [按钮](components/button.md)
* [容器](components/container.md)
* [轮播](components/carousel.md)
* [内容片段](components/content-fragment-component.md)
* [内容片段列表](components/content-fragment-list.md)
* [下载](components/download.md)
* [嵌入](components/embed.md)
* [体验片段](components/experience-fragment.md)
* [表单按钮](components/forms/form-button.md)
* [表单容器](components/forms/form-container.md)
* [隐藏的表单](components/forms/form-hidden.md)
* [表单选项](components/forms/form-options.md)
* [表单文本](components/forms/form-text.md)
* [图像](components/image.md)
* [语言导航](components/language-navigation.md)
* [列表](components/list.md)
* [导航](components/navigation.md)
* [页面](components/page.md)
* [快速搜索](components/quick-search.md)
* [分隔符](components/separator.md)
* [社交媒体共享](components/sharing.md)
* [选项卡](components/tabs.md)
* [文本](components/text.md)
* [标题](components/title.md)

>[!NOTE]
>
>核心组件不可直接供作者使用，[开发团队必须先将它们集成到您的环境中](get-started/using.md)。Once integrated, they may be made available and pre-configured via the [template editor](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html).

>[!CAUTION]
>
>个别核心组件的某些版本可能仅与特定版本的 AEM 兼容。
>
>有关兼容性信息，请参阅特定组件对应的帮助页面（可在上文中的列表中点击相应链接），或参考[核心组件版本](versions.md)文档以了解更多信息。

## 何时使用核心组件 {#when-to-use-core-components}

由于核心组件是全新的，并且具备多种优势，因此建议新的 AEM 项目使用这些组件。对于现有项目，可以考虑在进行更大型项目工作期间进行迁移，例如在重新品牌化或整体重构工作期间。

有关具体的使用建议，请参阅[开发核心组件](developing/overview.md)文档中的[何时使用核心组件？](developing/overview.md#when-to-use-the-core-components)

## Gems 教程概述 {#gems-session-overview}

关于核心组件、组件提供的功能以及它们在 AEM 中的使用方式，请参阅 AEM Gems 教程 [AEM 核心组件。](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/AEM-Core-Components.html)

[Adobe Experience Manager上的Gems](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/aem-index.html) ，是Adobe专家提供的一系列技术深入介绍。 此系列是对产品文档和所有其他技术渠道的补充，使开发人员能够相互交流并深入讨论特定主题。

## 使用核心组件进行开发 {#developing-core-components}

核心组件提供强大且可扩展的基本组件，这些组件实现了多种可轻松自定义的模式，从简单的样式设计到高级功能重用。 有关详细信息， [请参阅核心组件开发文档](developing/overview.md) 。

按照WKND教程开始使用核心组件开 [发AEM Sites。](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)

别忘了启动您自己的AEM项目，利用 [AEM项目原型](developing/archetype/overview.md) ，内置最新的核心组件！

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
