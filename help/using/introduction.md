---
title: 核心组件简介
seo-title: 核心组件简介
description: '引入核心组件是为了提供基于最新技术和最佳做法的强大、可扩展的基本组件。 '
seo-description: '引入核心组件是为了提供基于最新技术和最佳做法的强大、可扩展的基本组件。 '
uuid: b815c7d1-fbb0-4480-bd23-42606ff8b1eb
contentOwner: 用户
content-type: 引用
topic-tags: 简介
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-新
discoiquuid: c44bb0d7-5d91-4659-878e-a0658fe29aa2
translation-type: tm+mt
source-git-commit: b6fbef1cff2908533df6573cd3a92266857ba93f

---


# 核心组件简介{#core-components-introduction}

在 Adobe Experience Manager 中，组件是结构化的元素，用于构成所创作的页面内容。组件一直是AEM体验的一个基本元素，它使页面创建变得简单但功能强大，并且组件开发对于开发人员来说灵活且可扩展。

引入核心组件是为了提供健壮、可扩展的基本组件，这些基本组件构建在最新技术和最佳做法之上，并遵守辅助功能准则，并符合WCAG 2.0 AA标准。 核心组件使页面创作更灵活、可自定义，并且对开发人员来说，扩展这些组件以提供自定义功能很简单。

## 试用核心组件

如果要立即开始尝试核心组件，请转到组件 [库](http://opensource.adobe.com/aem-core-wcm-components/library.html)。 组件库是大多数核心组件当前版本的在线展示，允许您与各种组件进行交互，并查看示例HTML和JSON输出。

The [We.Retail reference site](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html) also illustrates how the core components can be used.

## 核心组件——核心功能 {#core-components-core-features}

核心组件包括：

|  |  |
|--- |--- |
| 预配置 | 模板可以定义页面作者如何使用这些模板。 |
| 通用 | 作者可以使用它们创建大多数类型的内容。 |
| 易于使用 | 作者可以高效地创建和管理内容。 |
| 生产就绪 | 现成可用！ 它们强健、经过良好测试，并且性能良好。 |
| 可访问 | 它们符合WCAG 2.0标准，提供ARIA标签，并支持键盘导航。 |
| 易于设计 | 这些组件实现样式系统，标记遵循BEM CSS命名。 |
| SEO Friendly | HTML输出是语义的，并提供schema.org微数据注释。 |
| PWA/SPA/App Ready | 他们简化的JSON输出还可用于客户端渲染。 |
| 可扩展 | 为了满足自定义需求，但无需从头开始，所有内容都可以扩展。 |
| 开放源 | 如果某些内容不应该如此，请改进GitHub（Apache许可证）。 |
| 版本控制 | 在改进可能影响您的内容时，核心组件不会破坏您的网站。 |
| [本地化](localization.md) | 智能引用解析允许某些组件自动查找和渲染相应的本地化内容 |

## 可用组件 {#available-components}

核心组件的当前版本具有以下组件。

* [折叠](accordion.md)
* [痕迹导航](breadcrumb.md)
* [按钮](button.md)
* [容器](container.md)
* [传送](carousel.md)
* [内容片段](content-fragment-component.md)
* [内容片段列表](content-fragment-list.md)
* [下载](download.md)
* [体验片段](experience-fragment.md)
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
>某些版本的单个核心组件可能仅与某些版本的AEM兼容。
>
>有关兼容性信息，请参阅特定组件的单个帮助页面（在上一列表中链接到），或参考核心组件版本文档以了解更多信息。 [](versions.md)

## 何时使用核心组件 {#when-to-use-core-components}

由于核心组件是全新的，并且提供多种优势，因此建议新AEM项目使用这些组件。 对于现有项目，迁移应该是更大项目工作的一部分，例如重新品牌化或整体重构。

有关特定用途的建议，请 [参阅何时使用核心组件？](developing.md) 开发核 [心组件文档](developing.md) 。

## Gems会话概述 {#gems-session-overview}

有关核心组件、它们提供的功能以及它们在AEM中的利用方式的介绍，请参阅AEM Gems会话 [AEM核心组件。](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/AEM-Core-Components.html)

[Adobe Experience Manager上的Gems](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/aem-index.html) ，是Adobe专家提供的一系列技术深入介绍。 此系列是对产品文档和所有其他技术渠道的补充，使开发人员能接触并深入讨论特定主题。

## WKND开发人员教程 {#wknd-developer-tutorial}

按照此分步教程，开始使用核心组 [件开发AEM Sites。](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/getting-started.html)

## 核心组件支持 {#core-components-support}

核心组件是AEM的一个组成部分，并按照与作为快速入门的一部分提供的条款和条件原样提供支持。

与其他产品功能一样，寿命终止的一般规则是：

* 组件在删除之前先宣布已弃用
* 最早会在发布后从AEM版本中删除这些组件。

这为客户提供了至少一个发布周期，以便在支持结束前移动到组件的新版本。

每个组件的版本都清楚地声明了它支持的AEM版本。 当AEM版本不再支持时，该版本AEM的核心组件也不再支持。

有关支持组件自定义的详细信息，请参 [阅相关核心组件版本的](customizing.md) “自定义核心组件”页。

## 基础组件支持 {#foundation-component-support}

由于基础组件在许多版本中都是众多项目开发的基础，因此在可预见的将来将继续支持这些组件。

但是，Adobe的开发重点已转移到核心组件上，并将为其添加新功能，而几乎所有基础组件在AEM 6.5中都已弃用 [](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/default-components-foundation.html) ，今后只会对基础组件进行错误修复。
