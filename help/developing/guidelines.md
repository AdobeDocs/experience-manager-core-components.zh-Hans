---
title: 组件准则
description: 核心组件遵循与基础组件截然不同的现代实施模式。
role: Architect, Developer, Administrator
exl-id: e8c58fa5-c991-433c-8d38-575dacfc3433
translation-type: tm+mt
source-git-commit: b5b77f21cbeaa46622cef85f3bbaa549f17f1a06
workflow-type: tm+mt
source-wordcount: '1272'
ht-degree: 2%

---

# 组件准则 {#component-guidelines}

[核心组件](overview.md)遵循与基础组件截然不同的现代实施模式。

本页介绍这些模式，以及何时使用这些模式构建您自己的可创作组件。 第一部分[常规组件模式](#general-component-patterns)适用于任何类型的组件，而第二部分[可重用组件模式](#reusable-component-patterns)适用于计划跨站点或项目（例如核心组件）重用的组件。

## 常规组件模式{#general-component-patterns}

本部分中的准则建议用于任何类型的组件，无论该组件是否特定于单个项目，或者组件是否打算在站点或项目之间广泛重复使用。

### 可配置组件{#configurable-components}

组件可以具有包含各种选项的对话框。 应利用此功能来使组件具有灵活性和可配置性，并避免实施多个组件，这些组件大多是彼此不同的组件。

通常，如果线框或设计包含相似元素的变体，则这些变体不应作为不同的组件实现，而应作为具有在这些变体之间进行选择的选项的组件。

要更进一步，如果组件在站点或项目之间重复使用，请参阅[预配置功能](#pre-configurable-capabilities)部分。

### 问题分离{#separation-of-concerns}

将组件的逻辑（或模型）与标记模板(或视图)分开通常是一个好做法。 实现这一点有几种方法，但建议使用[Sling Models](https://sling.apache.org/documentation/bundles/models.html)作为逻辑，使用[HTML模板语言](https://docs.adobe.com/content/help/zh-Hans/experience-manager-htl/using/overview.html)(HTL)作为标记，如核心组件。

Sling Models是一组Java注释，可轻松访问POJO中需要的变量，因此可优惠一种简单、强大而高效的方法来为组件实施Java逻辑。

HTL已设计为一种为AEM量度身定制的安全、简单的模板语言。 它可以调用多种形式的逻辑，使其非常灵活。

## 可重用组件模式{#reusable-component-patterns}

本节中的准则同样适用于任何类型的组件，但对于打算跨站点或项目（例如核心组件）重复使用的组件，它们最有意义。 因此，对于仅在单个站点或项目上使用的组件，可以忽略这些准则。

### 预配置功能{#pre-configurable-capabilities}

除了页面作者使用的编辑对话框外，组件还可以有一个设计对话框，供模板作者预配置它们。 [模板编辑器](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)允许设置所有这些预配置，这些预配置称为“策略”。

为了使组件尽可能地可重用，应为它们提供有意义的预配置选项。 这将允许或禁用组件功能以满足不同站点的特定需求。

### 代理组件模式{#proxy-component-pattern}

由于每个内容资源都有一个`sling:resourceType`属性，该属性引用组件以呈现它，因此通常最好将这些属性指向特定于站点的组件，而不是指向由多个站点共享的组件。 如果一个站点需要某个组件的不同行为，这将更灵活地优惠并避免内容重构，因为随后可以在特定于站点的组件上实现此自定义，而不会影响其他站点。

但是，对于不要重复任何代码的项目特定组件，它们应分别引用具有`sling:resourceSuperType`属性的共享父组件。 这些主要只引用父组件的项目特定组件称为“代理组件”。 如果代理组件完全继承了该功能，则它们可以是完全空的，或者它们可以重新定义组件的某些方面。

>[!TIP]
>
>有关如何创建代理组件的详细信息，请参阅[使用核心组件](/help/get-started/using.md#create-proxy-components)。

### 组件版本控制{#component-versioning}

随着时间的推移，组件应保持完全兼容，但有时，无法保持兼容的更改是必要的。 针对这些对立需求的一个解决方案是通过在其资源类型路径中添加数字，并在其实现的完全限定的Java类名称中添加数字来引入组件版本控制。 此版本号表示由[语义版本准则](https://semver.org/)定义的主版本，仅对不向后兼容的更改递增。

对组件的以下方面进行不兼容的更改将生成新版本：

* Sling模型（遵循语义版本准则）
* HTL脚本和模板
* HTML标记和CSS选择器
* JSON表示
* 对话框

有关更多详细信息，请参阅GitHub中的[版本控制策略](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-Policies)文档。

组件版本控制创建了一种合同形式，这种形式对于升级很重要，因为它澄清了何时可能需要重构某些内容。 另请参见[自定义的升级兼容性](customizing.md#upgrade-compatibility-of-customizations)部分，其中说明了不同形式的自定义升级需要哪些注意事项。

为避免痛苦的内容迁移，永远不要直接指向内容资源中版本化的组件非常重要。 根据经验，`sling:resourceType`的内容绝不能包含版本号，或者升级组件也需要重新构造内容。 避免这种情况的最佳方法是遵循上述[代理组件模式](#proxy-component-pattern)。

### 模型接口{#model-interfaces}

此模式与HTL的`data-sly-use`指向Java接口的指令有关，而Sling Model实现也将自身注册到组件的资源类型。

与上述[代理组件模式](#proxy-component-pattern)组合后，这种形式的多次绑定优惠会遵循好的扩展点：

1. 站点可以通过将Sling模型注册到代理组件的资源类型来重新定义其实现，而无需考虑HTL文件，HTL文件仍可指向接口。
1. 站点可以重新定义组件的HTL标记，而不必考虑它应该指向的实现逻辑。

## 将所有内容组合在一起{#putting-it-all-together}

以下是整个资源类型绑定结构的概述，以标题核心组件为例。 它说明了站点特定的代理组件如何允许解析组件版本控制，以避免内容资源包含任何版本号。 然后，它显示组件的`title.html` [HTL](https://docs.adobe.com/content/help/en/experience-manager-htl/using/overview.html)文件如何用于模型接口，而实现则通过[Sling Model](https://sling.apache.org/documentation/bundles/models.html)注释绑定到组件的特定版本。

![资源绑定概述](/help/assets/chlimage_1-32.png)

下面是另一个概述，它不显示实施POJO的详细信息，但显示关联的[模板和策略](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/components-templates/templates.html)如何被引用。

`cq:allowedTemplates`属性告诉哪些模板可用于站点， `cq:template`属性告诉每个页面关联的模板是什么。 每个模板由以下三部分组成：

* **structure**  — 包含将强制每个页面上存在的资源，以及页面作者无法删除的资源，例如，page header和footer组件。
* **initial**  — 包含创建页面时将复制到页面的初始内容。
* **策略**  — 包含每个组件的策略映射，策略是组件的预配置。此映射允许策略跨模板重用，因此可以集中管理。

![模板和策略概述](/help/assets/screen_shot_2018-12-07at093102.png)

## AEM 项目原型 {#aem-project-archetype}

[AEM Project Archety将最](/help/developing/archetype/overview.md) 小的Adobe Experience Manager项目视为您自己项目的起点，包括一个使用SlingModels的自定义HTL组件示例，用于逻辑和使用推荐的代理模式正确实施核心组件。

**阅读下一篇文章：**

* [使用核心组件](/help/get-started/using.md)  — 在您自己的项目中开始使用核心组件。
* [自定义核心组件](customizing.md)  — 了解如何设置核心组件的样式和自定义核心组件。
