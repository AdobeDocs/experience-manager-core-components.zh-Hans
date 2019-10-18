---
title: 组件准则
seo-title: 组件准则
description: 核心组件遵循与基础组件截然不同的现代实施模式。
seo-description: 核心组件遵循与基础组件截然不同的现代实施模式。
uuid: b1dea89-da3c-454f-8ab5-d75a19412954
contentOwner: 用户
content-type: 参考
topic-tags: 开发
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-new
discoiquuid: 170dba8f-a2ed-442e-a56e-1126b338c36e
translation-type: tm+mt
source-git-commit: 683b4f4705c226275439a408423cbf1b23bea66f

---


# 组件准则 {#component-guidelines}

核心 [](developing.md) 组件遵循与基础组件截然不同的现代实施模式。

本页介绍这些模式，以及何时使用这些模式构建您自己的可创作组件。 第一部分“ [常规组件模式](guidelines.md)[](guidelines.md) ”适用于任何类型的组件，而第二部分“可重用组件模式”则适用于计划跨站点或项目重用的组件，例如核心组件。

## 常规组件模式 {#general-component-patterns}

本节中的准则建议用于任何类型的组件，无论该组件是否特定于单个项目，或该组件是否打算在各站点或项目之间广泛重复使用。

### 可配置组件 {#configurable-components}

组件可以具有包含各种选项的对话框。 这应该被用于使组件变得灵活且可配置，并避免实施多个组件，这些组件大多是彼此不同的组件。

通常，如果线框或设计包含类似元素的变体，则这些变体不应作为不同的组件实现，而应作为一个具有在变体之间进行选择的选项的组件实现。

要更进一步，如果组件在站点或项目之间重复使用，请参阅预 [配置功能部分](#pre-configurable-capabilities) 。

### 关注事项分离 {#separation-of-concerns}

通常，将组件的逻辑（或模型）与标记模板（或视图）分开是一个好做法。 要实现此目的，有多种方法，但建议使用 [Sling Models](https://sling.apache.org/documentation/bundles/models.html) （逻辑模型）和 [](https://helpx.adobe.com/experience-manager/htl/using/overview.html) HTML模板语言(HTL)（核心组件也是如此）。

Sling Models是一组Java注释，可以从POJO中轻松访问所需的变量，因此为组件实现Java逻辑提供了一种简单、强大而高效的方法。

HTL设计为一种安全、简单的模板语言，专为AEM量身定制。 它可以调用多种形式的逻辑，这使得它非常灵活。

## 可重用的组件模式 {#reusable-component-patterns}

本节中的准则也可用于任何类型的组件，但对于打算跨站点或项目重复使用的组件（例如，核心组件），它们最有意义。 因此，对于仅用于单个站点或项目的组件，可忽略这些准则。

### 预配置功能 {#pre-configurable-capabilities}

除了页面作者使用的编辑对话框外，组件还可以有一个设计对话框，供模板作者预配置它们。 模 [板编辑器](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html) 允许设置所有这些预配置，这些预配置称为“策略”。

为使组件尽可能地可重用，应为它们提供有意义的预配置选项。 这将允许或禁用组件的功能以匹配不同站点的特定需求。

<!-- 

Comment Type: annotation
Last Modified By: ims-author-CE1E2CE451D1F0680A490D45@AdobeID
Last Modified Date: 2017-04-17T17:49:04.584-0400

Unclear how I can add my own capability toggle (for example, if i extend a component and want to toggle that extended functionality ... )

 -->

### 代理组件模式 {#proxy-component-pattern}

由于每个内容资源都有一个引用组件以呈现它的属性，因此通常最好将这些属性指向特定于站点的组件，而不是指向由多个站点共享的组件。 `sling:resourceType` 如果一个站点需要某个组件的不同行为，这将提供更大的灵活性并避免内容重构，因为随后可以在特定于站点的组件上实现此自定义，而不会影响其他站点。

但是，对于不复制任何代码的项目特定组件，它们应分别引用具有属性的共享父组 `sling:resourceSuperType` 件。 这些主要只引用父组件的项目特定组件称为“代理组件”。 如果代理组件完全继承了该功能，则它们可以是完全空的，也可以重新定义组件的某些方面。

### 组件版本控制 {#component-versioning}

随着时间的推移，组件应保持完全兼容，但有时无法保持兼容的更改是必要的。 解决这些对立需求的一个解决方案是通过在其资源类型路径和实现的完全限定的Java类名称中添加数字来引入组件版本控制。 此版本号表示由语义版本控制准则定义的主 [要版本](https://semver.org/)，该版本仅对不向后兼容的更改递增。

对组件的以下方面进行不兼容的更改将导致组件的新版本：

* Sling模型（遵循语义版本控制准则）
* HTL脚本和模板
* HTML标记和CSS选择器
* JSON表示
* 对话框

有关更多详细信息，请参 [阅GitHub中的“版本控制策略](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-Policies) ”文档。

组件版本控制创建了一种对升级很重要的合同形式，因为它阐明了何时可能需要重新分析某些内容。 另请参阅自定义 [的升级兼容性部分](customizing.md#upgrade-compatibility-of-customizations)，其中介绍了不同形式的自定义升级需要考虑哪些事项。

为避免痛苦的内容迁移，永远不要直接指向内容资源中的版本化组件非常重要。 根据经验，某个内 `sling:resourceType` 容永远不得包含版本号，或升级组件也需要重新构造内容。 避免这种情况的最佳方法是遵循上述 [代理组件模式](#proxy-component-pattern) 。

### 模型接口 {#model-interfaces}

此模式与HTL指向Java接口的指 `data-sly-use` 令有关，而Sling Model实现也将自身注册到组件的资源类型。

与上述代理组 [件模式结合使用](#proxy-component-pattern) ，这种双绑定形式提供了以下不错的扩展点：

1. 站点可以通过将Sling模型注册到代理组件的资源类型来重新定义其实现，而无需考虑HTL文件，该文件仍可指向接口。
1. 站点可以重新定义组件的HTL标记，而不必考虑它应该指向哪个实现逻辑。

## 整合 {#putting-it-all-together}

以下是整个资源类型绑定结构的概述，以标题核心组件为例。 它说明了站点特定的代理组件如何允许解析组件版本控制，以避免内容资源包含任何版本号。 然后，它显示组件的 `title.html` HTL文件如何用于模型接口，而实现则通过 [Sling Model](https://helpx.adobe.com/experience-manager/htl/using/overview.html)[](https://sling.apache.org/documentation/bundles/models.html) annotations绑定到组件的特定版本。

![资源绑定概述](assets/chlimage_1-32.png)

下面是另一个概述，它不显示实施POJO的详细信息，但显示关联的模板和策 [略的引用](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/page-templates-editable.html) 。

该属 `cq:allowedTemplates` 性告诉哪些模板可用于站点，以及每个页 `cq:template` 面的相关模板信息。 每个模板由以下三部分组成：

* **结**&#x200B;构包含资源，这些资源将强制显示在每个页面上，并且页面作者无法删除，例如页眉和页脚组件。
* **initial**&#x200B;包含创建页面时将复制到该页面的初始内容。
* **策略**&#x200B;包含每个组件的策略映射（即组件的预配置）。 此映射允许策略在模板之间重复使用，因此可以集中管理。

![模板和策略概述](assets/screen_shot_2018-12-07at093102.png)

## AEM Project Archetype {#aem-project-archetype}

[AEM Project Archetype将创建一个最小的Adobe Experience Manager项目作为您自己项目的起点，包括一个包含SlingModels的自定义HTL组件的简单示例，用于逻辑和正确实施包含推荐代理模式的核心组件。](overview.md)

**阅读下一篇文章：**

* [使用核心组件](using.md) -在您自己的项目中开始使用核心组件。
* [自定义核心组件](customizing.md) -了解如何设计核心组件的样式和自定义核心组件。
