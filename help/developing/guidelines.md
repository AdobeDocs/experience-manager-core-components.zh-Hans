---
title: 组件准则
description: 核心组件遵循的是与基础组件截然不同的现代实施模式。
role: Architect, Developer, Admin
exl-id: e8c58fa5-c991-433c-8d38-575dacfc3433
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '1272'
ht-degree: 2%

---

# 组件准则 {#component-guidelines}

[核心组件](overview.md)遵循与基础组件截然不同的现代实施模式。

本页介绍了这些模式，以及何时使用这些模式构建您自己的可创作组件。 第一部分[常规组件模式](#general-component-patterns)适用于任何类型的组件，而第二部分[可重用组件模式](#reusable-component-patterns)适用于打算在站点或项目中重复使用的组件，例如核心组件。

## 常规组件模式 {#general-component-patterns}

无论组件是否特定于单个项目，或者组件是否打算在站点或项目中广泛重复使用，都建议对任何类型的组件使用此部分中的准则。

### 可配置组件 {#configurable-components}

组件可以具有包含各种选项的对话框。 应利用此功能，使组件变得灵活且可配置，并避免实施多个组件，这些组件大多是彼此不同的组件。

通常，如果线框或设计包含相似元素的变体，则这些变体不应作为不同的组件实施，而应作为一个组件实施，该组件具有可在这些变体之间进行选择的选项。

要进一步说明，如果组件在站点或项目之间重复使用，请参阅[预配置功能](#pre-configurable-capabilities)部分。

### 关注事项分离 {#separation-of-concerns}

将组件的逻辑（或模型）与标记模板（或视图）分开通常是一种好做法。 实现此目的的方法有多种，但建议的方法是对逻辑使用[Sling模型](https://sling.apache.org/documentation/bundles/models.html)，对标记使用[HTML模板语言](https://docs.adobe.com/content/help/zh-Hans/experience-manager-htl/using/overview.html)(HTL)，如核心组件也使用。

Sling模型是一组Java批注，用于轻松访问来自POJO的所需变量，因此为组件实施Java逻辑提供了一种简单、功能强大且高效的方法。

HTL旨在作为一种安全而简单的模板语言，专为AEM量身定制。 它可以调用多种形式的逻辑，这使得它非常灵活。

## 可重用组件模式 {#reusable-component-patterns}

此部分中的准则也可用于任何类型的组件，但对于打算在站点或项目（例如核心组件）中重复使用的组件而言，这些准则非常有意义。 因此，对于仅在单个站点或项目上使用的组件，可以忽略这些准则。

### 可预配置的功能 {#pre-configurable-capabilities}

除了页面作者使用的编辑对话框之外，组件还可以具有一个模板作者用于预配置组件的设计对话框。 [模板编辑器](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)允许设置所有这些预配置，称为“Policies”。

为了使组件尽可能可重复使用，应为它们提供用于预配置的有意义选项。 这将允许或禁用组件的功能，以匹配不同站点的特定需求。

### 代理组件模式 {#proxy-component-pattern}

由于每个内容资源都有一个`sling:resourceType`属性，该属性引用组件进行呈现，因此通常最好将这些属性指向特定于站点的组件，而不是指向由多个站点共享的组件。 如果一个站点需要组件的不同行为，这将提供更大的灵活性并避免内容重构，因为随后可以在特定于站点的组件上实现此自定义，而不会影响其他站点。

但是，对于不复制任何代码的项目特定组件，它们应该各自引用具有`sling:resourceSuperType`属性的共享父组件。 这些特定于项目的组件通常只称为父组件，称为“代理组件”。 如果代理组件完全继承功能，则它们可以是完全空的，或者它们可以重新定义组件的某些方面。

>[!TIP]
>
>有关如何创建代理组件的详细信息，请参阅[使用核心组件](/help/get-started/using.md#create-proxy-components)。

### 组件版本控制 {#component-versioning}

随着时间的推移，组件应保持完全兼容，但有时需要进行无法保持兼容的更改。 解决这些对立需求的一个解决方案是，通过在其资源类型路径中以及其实施的完全限定的Java类名称中添加数字来引入组件版本控制。 此版本号表示由[语义版本控制准则](https://semver.org/)定义的主要版本，该版本号仅针对不向后兼容的更改递增。

对组件的以下方面进行不兼容的更改将导致新版本的组件：

* Sling模型（遵循语义版本控制准则）
* HTL脚本和模板
* HTML标记和CSS选择器
* JSON表示法
* 对话框

有关更多详细信息，请参阅GitHub中的[版本控制策略](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-Policies)文档。

组件版本控制创建了一种合同形式，这种合同形式对于升级非常重要，因为它澄清了何时可能需要重构某些内容。 另请参阅[Upgrade Compatibility of Customizations](customizing.md#upgrade-compatibility-of-customizations)部分，其中说明了不同形式的自定义升级需要考虑哪些事项。

为避免痛苦的内容迁移，切勿直接从内容资源中指向版本控制的组件。 根据经验，`sling:resourceType`的内容永远不得包含版本号，否则升级组件将要求对内容进行重构。 避免这种情况的最佳方法是遵循上述[代理组件模式](#proxy-component-pattern)。

### 模型接口 {#model-interfaces}

此模式与HTL的`data-sly-use`指令相关，指向Java接口，而Sling Model实施也将其自身注册到组件的资源类型中。

如果与上述[代理组件模式](#proxy-component-pattern)结合使用，这种双绑定形式提供了以下不错的扩展点：

1. 站点可以通过将Sling模型注册到代理组件的资源类型来重新定义其实现，而无需考虑HTL文件，该文件仍可指向接口。
1. 站点可以重新定义组件的HTL标记，而不必考虑它应该指向哪个实施逻辑。

## 把它们整合起来 {#putting-it-all-together}

以下是整个资源类型绑定结构的概述，以标题核心组件为例。 它说明了特定于站点的代理组件如何允许解析组件版本控制，以避免内容资源包含任何版本号。 然后，它会显示组件的`title.html` [HTL](https://docs.adobe.com/content/help/en/experience-manager-htl/using/overview.html)文件如何用于模型界面，而实施则通过[Sling Model](https://sling.apache.org/documentation/bundles/models.html)注释绑定到组件的特定版本。

![资源绑定概述](/help/assets/chlimage_1-32.png)

下面是另一个概述，它不显示实施POJO的详细信息，但显示了关联的[模板和策略](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/components-templates/templates.html)如何引用。

`cq:allowedTemplates`属性用于告知哪些模板可用于站点，而`cq:template`属性用于告知每个页面关联的模板。 每个模板由以下三部分组成：

* **结构**  — 包含将强制在每个页面上显示的资源，以及页面作者将无法删除的资源，例如页眉和页脚组件。
* **initial**  — 包含创建页面时将复制到该页面的初始内容。
* **策略**  — 包含每个组件的策略映射（即组件的预配置）。此映射允许策略在模板之间重复使用，因此可以集中管理。

![模板和策略概述](/help/assets/screen_shot_2018-12-07at093102.png)

## AEM 项目原型 {#aem-project-archetype}

[AEM项目原](/help/developing/archetype/overview.md) 型将最小的Adobe Experience Manager项目视为您自己项目的起点，包括一个使用SlingModels的自定义HTL组件示例，该示例用于逻辑和使用推荐的代理模式正确实施核心组件。

**阅读下一篇文章：**

* [使用核心组件](/help/get-started/using.md)  — 在您自己的项目中开始使用核心组件并运行。
* [自定义核心组件](customizing.md)  — 了解如何设置核心组件的样式和自定义核心组件。
