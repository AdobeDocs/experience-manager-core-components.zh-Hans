---
title: 核心组件简介
seo-title: 核心组件简介
description: '引入核心组件，以提供基于最新技术和最佳做法的强大、可扩展的基本组件。 '
seo-description: '引入核心组件，以提供基于最新技术和最佳做法的强大、可扩展的基本组件。 '
uuid: b815c7d1-fbb0-4480-bd23-42606ff8 b1 eb
contentOwner: 用户
content-type: 引用
topic-tags: introduction
products: SG_ EXPERIENCE MANAGER/CORECOMMPANES-new
discoiquuid: c44bb0d7-5d91-4659-878e-a0658 fe29 aa2
translation-type: tm+mt
source-git-commit: 7130f4ae8add8c8dc3cdfcc4addd0621722b89f7

---


# Core Components Introduction{#core-components-introduction}

在 Adobe Experience Manager 中，组件是结构化的元素，用于构成所创作的页面内容。组件始终是AEM体验的基本元素，这使得页面创建变得简单而强大，并且对创作和组件开发的开发可为开发者提供灵活性和可扩展性。

引入核心组件，以提供强大、可扩展的基本组件，这些组件基于最新技术和最佳做法以及符合辅助功能指导原则并且符合WCAG2.0AA标准。核心组件使页面创作更灵活、可自定义，并且扩展它们为开发人员提供自定义功能变得很简单。

## 试用核心组件

If you want to get started straight away trying out the Core Components, head over to the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library.html). 组件库是核心组件的当前版本的在线展示，允许您与各种组件交互以及查看示例HTML和JSON输出。

[We. Retail参考站点](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html) 还说明了核心组件的使用方式。

## Core Components - Core Features {#core-components-core-features}

核心组件有：

|  |  |
|--- |--- |
| 可预配置 | 模板可以定义页面作者可以使用它们的方式。 |
| 通用拼贴 | 作者可以使用这些内容创建最类型的内容。 |
| 易于使用 | 作者可以高效地创建和管理内容。 |
| 生产就绪 | 现成可用！它们强大、可靠并且性能良好。 |
| 可访问 | 他们遵守WCAG2.0标准、提供ARI标签并支持键盘导航。 |
| 简单易用 | 组件实现样式系统，标记遵循BEM CSS命名。 |
| SEO友好 | HTML输出是语义的，并提供schema.org微数据注释。 |
| PWA/SPA/App就绪 | 其简化的JSON输出还可用于客户端渲染。 |
| 可扩展 | 为了满足自定义需求，但无需从头开始，一切都可以扩展。 |
| 开放源代码 | 如果内容不应满足要求，在GitHub(Apache许可证)上做出改进。 |
| Versioned | 改进可能影响您的内容时，核心组件不会中断您的网站。 |

## Available Components {#available-components}

核心组件的当前版本包含以下组件。

* [折叠](accordion.md)
* [痕迹导航](breadcrumb.md)
* [按钮](button.md)
* [容器](container.md)
* [传送](carousel.md)
* [内容片段](content-fragment-component.md)
* [内容片段列表](content-fragment-list.md)
* [下载](download.md)
* [表单按钮](form-button.md)
* [表单容器](form-container.md)
* [隐藏的表单](form-hidden.md)
* [表单选项](form-options.md)
* [表单文本](form-text.md)
* [图像](image.md)
* [语言导航](language-navigation.md)
* [列表](list.md)
* [导航](navigation.md)
* [页面](page.md)
* [快速搜索](quick-search.md)
* [分隔符](separator.md)
* [社交媒体共享](sharing.md)
* [选项卡](tabs.md)
* [文本](text.md)
* [标题](title.md)

>[!NOTE]
>
>Core Components are not immediately available to authors, the [development team must first integrate them to your environment](using.md). Once integrated, they may be made available and pre-configured via the [template editor](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html) or in [design mode](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/default-components-designmode.html).

>[!CAUTION]
>
>某些版本的单独核心组件只能与特定版本的AEM兼容。
>
>See the individual help page (linked to in the previous list) for the specific component for compatibility information or reference the [Core Components Versions](versions.md) document for more information.

## When to Use Core Components {#when-to-use-core-components}

由于核心组件是全新的并且提供多个优势，因此建议新AEM项目使用它们。对于现有项目，迁移应属于较大项目的一部分，例如品牌或整体重构。

For specific use recommendations, see [When to Use the Core Components?](developing.md) 开发 [核心组件](developing.md) 文档中。

## Gems Session Overview {#gems-session-overview}

For an introduction to the Core Components, the features they offer, and how they are leveraged in AEM, check out the AEM Gems Session [AEM Core Components.](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/AEM-Core-Components.html)

[Adobe Experience Manager](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/aem-index.html) 的Gems是由Adobe专家提供的一系列技术深层产品。本系列对产品文档和所有其他技术渠道进行了补充，允许开发人员接触并深入了解特定主题。

## WKND Developer Tutorial {#wknd-developer-tutorial}

Get started developing AEM Sites with Core Components by following [this step by step tutorial.](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/getting-started.html)

## Core Components Support {#core-components-support}

核心组件是AEM不可分割的一部分，按相同的条款和条件提供支持，如同它们是作为快速入门的一部分提供的一样。

与其他产品功能一样，生命结束的一般规则是：

* 在删除组件之前先宣布已弃用组件
* 最初，在发布公告之后，会从AEM版本中删除它们。

这为客户提供至少一个发布周期，以便在支持结束之前转到组件的新版本。

每个组件的版本清楚地陈述了其支持的AEM版本。当支持某个版本的AEM时，也支持该版本AEM的核心组件。

For details about the support of component customizations, see the [Customizing Core Components](customizing.md) page of the relevant Core Components Version.

## Foundation Component Support {#foundation-component-support}

由于基础组件已经作为许多版本的如此多的项目开发基础，它们将继续支持可预见的未来。

However, Adobe&#39;s development emphasis has shifted to the Core Components and new features will be added to them, whereas [nearly all Foundation Components have been deprecated with AEM 6.5](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/default-components-foundation.html) and only bug fixes will be made to the Foundation Components going forward.
