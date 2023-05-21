---
title: 组件准则
description: 核心组件遵循的现代实施模式与基础组件大为不同。
role: Architect, Developer, Admin
exl-id: e8c58fa5-c991-433c-8d38-575dacfc3433
source-git-commit: ee18626280f74a51a799f16d6bf3f5b0be9cd6b9
workflow-type: tm+mt
source-wordcount: '1267'
ht-degree: 100%

---

# 组件准则 {#component-guidelines}

[核心组件](overview.md)遵循的现代实施模式与基础组件大为不同。

此页面说明了这些模式，以及何时使用这些模式来构建自己的可创作组件。第一部分[常规组件模式](#general-component-patterns)适用于任何类型的组件，第二部分[可重用组件模式](#reusable-component-patterns)适用于要跨网站或项目重用的组件，例如核心组件。

## 常规组件模式 {#general-component-patterns}

此部分中的指南推荐用于任何类型的组件，不论该组件是否特定于单个项目，或者该组件是否要跨网站或项目广泛地重用。

### 可配置组件 {#configurable-components}

组件的对话框可以有各种选项。应该利用这一特点让组件灵活且可配置，并且避免实施的多个组件主要是彼此的变体。

通常，如果线框或设计包含类似元素的变体，这些变体不应作为不同的组件实施，而应作为一个组件，并通过选项在变体之间选择。

要更进一步跨网站或项目重用组件，请参阅[可预配置的功能](#pre-configurable-capabilities)部分。

### 分离关注点 {#separation-of-concerns}

通常，将组件的逻辑（或模型）与标记模板（或视图）分离开是一种好的做法。有多种方法可以做到这一点，但是，建议的方法是为逻辑使用 [Sling 模型](https://sling.apache.org/documentation/bundles/models.html)，为标记使用 [HTML 模板语言](https://experienceleague.adobe.com/docs/experience-manager-htl/using/overview.html) (HTL)，就像核心组件这样。

Sling 模型是一组 Java 注释，可从 POJO 轻松地访问所需的变量，因此这种模型提供了简单、强大且高效的方法为组件实施 Java 逻辑。

HTL 设计作为针对 AEM 定制的简单安全的模板语言。它可以调用多种形式的逻辑，使其非常灵活。

## 可重用组件模式 {#reusable-component-patterns}

此部分中的指南也可用于任何类型的组件，但最适合用于要跨网站或项目重用的组件，例如针对实例的核心组件。因此，对于仅用于单个网站或项目的组件，可以忽略这些指南。

### 可预配置功能 {#pre-configurable-capabilities}

除了由页面作者使用的“编辑”对话框之外，组件还有“设计”对话框，供模板作者预配置组件。使用[模板编辑器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)可以设置这些称为“策略”的预配置。

要使组件尽可能地可重用，应该向它们提供有意义的选项来预配置。这将允许启用或禁用组件的功能，以匹配不同网站的特定需求。

### 代理组件模式 {#proxy-component-pattern}

由于每个内容资源都有一个 `sling:resourceType` 属性来引用渲染它的组件，通常好的做法是让这样的属性指向网站特定的组件，而不是指向由多个网站共享的组件。这样可以实现更好的灵活性，并且当一个网站需要某个组件的不同行为时能够避免内容重构，因为此自定义设置可以在网站特定的组件中实现，而不会影响其他网站。

但是，对于项目特定的组件，不要复制任何代码，它们均应该使用 `sling:resourceSuperType` 属性引用共享的父组件。通常只是引用父组件的这些项目特定组件称为“代理组件”。如果代理组件完全继承了父组件的功能，代理组件也可以完全为空，或者可以重新定义它的一些方面。

>[!TIP]
>
>有关如何创建代理组件的详细信息，请参阅[使用核心组件](/help/get-started/using.md#create-proxy-components)。

### 组件版本控制 {#component-versioning}

组件应随时间推移保持完全的兼容性，而有时候则必须进行无法保持兼容的更改。要解决这些矛盾的需求，一种解决方案是引入组件版本控制，方法是在其资源类型路径中，以及在其实施的完全限定 Java 类名中添加编号。此编号表示版本号，是[语义版本控制指南](https://semver.org/)所定义的主要版本，只有进行了不向后兼容的更改时才增加版本。

对组件的以下方面进行不兼容更改将导致组件产生新版本：

* Sling 模型（遵循语义版本控制指南）
* HTL 脚本和模板
* HTML 标记和 CSS 选择器
* JSON 呈现
* 对话框

有关更多详细信息，请参阅 GitHub 中的[版本控制策略](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-Policies)文档。

组件版本控制创建了一种对升级很重要的合同形式，因为它说明了某些内容什么时候可能需要重构。另请参阅[升级自定义设置的兼容性](customizing.md#upgrade-compatibility-of-customizations)部分，其中说明了不同自定义设置在升级时需要考虑的注意事项。

为了避免麻烦的内容迁移，不要从内容资源直接指向版本控制的组件，这一点非常重要。根据经验，内容的 `sling:resourceType` 中永远不应有版本号，否则升级组件时也会要求重构内容。避免这种情况的最佳方式是遵循前文所述的[代理组件模式](#proxy-component-pattern)。

### 模型接口 {#model-interfaces}

此模式关系到指向 Java 接口的 HTL 的 `data-sly-use` 指令，而 Sling 模型实施同样将自己注册到组件的资源类型。

在与前文所述的[代理组件模式](#proxy-component-pattern)结合起来后，这种形式的双重绑定提供了以下很好的扩展点：

1. 网站可以重新定义 Sling 模型的实施，方法是将其注册到代理组件的资源类型，而无需考虑 HTL 文件，该文件仍可指向接口。
1. 网站可以重新定义组件的 HTL 标记，而无需考虑它应指向的实施逻辑。

## 融于一起 {#putting-it-all-together}

下文以标题核心组件为例，概述了完整资源类型绑定结构。它说明了网站特定的代理组件如何允许解析组件版本控制，以避免内容资源包含任何版本号。然后，它显示了当实施通过 [Sling 模型](https://sling.apache.org/documentation/bundles/models.html)注释绑定到组件的特定版本时，组件的 `title.html` [HTL](https://experienceleague.adobe.com/docs/experience-manager-htl/using/overview.html) 文件如何使用模型接口。

![资源绑定概览](/help/assets/chlimage_1-32.png)

下面是其他概述，其中并未显示实施 POJO 的详细信息，而是揭示了如何引用关联的[模板和策略](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/full-stack/components-templates/templates.html)。

`cq:allowedTemplates` 属性说明哪些模板可以用于网站，`cq:template` 说明关联模板的对应页面。每个模板由以下三个部分组成：

* **结构** - 包含将在要呈现的每个页面上强制实施而页面作者无法删除的资源，例如页眉和页脚组件。
* **初始** - 包含初始内容，在创建页面时这些内容复制到页面。
* **策略** - 包含每个组件到策略的映射，这是组件的预配置。通过此映射，策略可以跨模板重用，因此可以集中管理。

![模板和策略概述](/help/assets/screen_shot_2018-12-07at093102.png)

## AEM 项目原型 {#aem-project-archetype}

[AEM 项目原型](/help/developing/archetype/overview.md)创建一个规模最小的 Adobe Experience Manager 项目作为您项目的起点，包括一个带 SlingModel 的自定义 HTL 组件示例，可用于带建议的代理模式的核心组件的逻辑和正确实施。

**阅读下一篇文章：**

* [使用核心组件](/help/get-started/using.md) - 在您自己的项目中启动并运行核心组件。
* [自定义核心组件](customizing.md) - 了解如何样式化和自定义核心组件。
