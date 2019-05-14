---
title: 组件指南
seo-title: 组件指南
description: 核心组件遵循与基础组件截然不同的现代实施模式。
seo-description: 核心组件遵循与基础组件截然不同的现代实施模式。
uuid: b1daex89-da3 c-454f-8ab5-d75 a19412954
contentOwner: 用户
content-type: 引用
topic-tags: developing
products: SG_ EXPERIENCE MANAGER/CORECOMMPANES-new
discoiquuid: 170dba8f-a2 ed-442e-a56 e-116b338 c36 e
translation-type: tm+mt
source-git-commit: 62643e5bd49ab006230f65004bb9374822dcc017

---


# 组件指南 {#component-guidelines}

[核心组件](developing.md) 遵循与基础组件截然不同的现代实施模式。

本页介绍这些模式，以及如何使用它们构建您自己的可授权组件。第一部分 [常规组件模式](guidelines.md) 适用于任何类型的组件，而第二部分 [可重用组件模式](guidelines.md) 适用于要跨站点或项目重用的组件(例如核心组件)。

## 常规组件模式 {#general-component-patterns}

此部分中的指导方针适用于任何类型的组件，无论组件是特定于单个项目还是组件是否要跨站点或项目重用。

### 可配置组件 {#configurable-components}

组件可具有各种选项。应利用这种方法来使组件灵活、可配置，并避免实施多个组件，它们大多是彼此变化的组件。

通常，如果线框或设计包含类似元素的变体，则这些变体不应作为不同的组件实现，而是作为一个组件来实现，可选择不同的变体。

要进一步执行此步骤，如果在站点或项目中重复使用了组件，请参阅“ [预配置功能](#pre-configurable-capabilities) ”部分。

### 分离疑虑 {#separation-of-concerns}

将组件的逻辑(或模型)与标记模板(或视图)分开通常是一个不错的做法。实现这一点的方法有若干种，但是推荐的一种方法是将 [逻辑的sling模型](https://sling.apache.org/documentation/bundles/models.html) 用于逻辑和 [HTML模板语言](https://helpx.adobe.com/experience-manager/htl/using/overview.html) (HTL)，如核心组件。

Sling Model是一组Java注释，可从Pojos轻松访问所需的变量，因此提供一种简单、功能强大且简单的方法来实现组件的Java逻辑。

HTL已被设计为为AEM量身定制的安全、简单的模板语言。它可以调用许多形式的逻辑，这使它非常灵活。

## 可重用的组件模式 {#reusable-component-patterns}

此部分中的指导方针也可用于任何类型的组件，但对于希望跨站点或项目重用的组件(例如核心组件)，它们最有意义。因此，对于只在单个站点或项目上使用的组件，可以忽略这些准则。

### 可预配置的功能 {#pre-configurable-capabilities}

除了页面作者使用的编辑对话框之外，组件还可以为模板作者提供一个设计对话框来预配置它们。[模板编辑器](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html) 允许设置所有这些预配置(称为“策略”)。

为了使组件尽可能地重复使用，应为它们提供有意义的预配置选项。这将允许启用或禁用组件的功能以满足不同站点的特定需求。

<!-- 

Comment Type: annotation
Last Modified By: ims-author-CE1E2CE451D1F0680A490D45@AdobeID
Last Modified Date: 2017-04-17T17:49:04.584-0400

Unclear how I can add my own capability toggle (for example, if i extend a component and want to toggle that extended functionality ... )

 -->

### 代理组件模式 {#proxy-component-pattern}

由于每个内容资源都有一个 `sling:resourceType` 引用该组件的属性，因此通常很好地将这些属性指向站点特定的组件，而不是指向由多个站点共享的组件。如果一个站点需要一个组件的不同行为，这将提供更大的灵活性并避免内容重构，因为随后可以在特定于站点的组件上实现这一自定义，而且不会影响其他站点。

但是，要使特定于项目的组件不复制任何代码，它们应使用该 `sling:resourceSuperType` 属性引用共享父组件。这些特定于父组件的项目特定组件称为“代理组件”。如果代理组件完全继承了该功能，则它们可以完全为空，也可以重新定义组件的某些方面。

### 组件版本控制 {#component-versioning}

组件应随时间保持完全兼容，但有时无法保持兼容的更改是必需的。这些相反的需求之一是通过在资源类型路径中添加一个数字，以及在完全限定的Java类名称中添加一个数字来引入组件版本控制。此版本号表示 [语义版本控制准则所定义的主要版本](https://semver.org/)，该准则仅对不向后兼容的更改递增。

对组件的下列方面的不兼容更改将导致新版本的组件：

* Sling Model(遵循语义版本指导准则)
* HTL脚本和模板
* HTML标记和CSS选择器
* JSON表示法
* 对话框

有关详细信息，请参阅GitHub中 [的版本控制策略](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-Policies) 文档。

组件版本控制创建一种合同形式，因为当可能需要重构某些内容时，这一形式非常重要。另请参阅自定义 [](customizing.md#upgrade-compatibility-of-customizations)的升级兼容性部分，该部分解释了进行升级所需的不同形式的自定义自定义。

为避免痛苦的内容迁移，务必从不直接指向来自内容资源的版本组件。作为缩略图规则，内容中 `sling:resourceType` 的某个内容中绝不一定有版本号，升级组件也需要重构内容。避免这种情况的最佳方法是遵循上述 [代理组件模式](#proxy-component-pattern) 。

### 模型界面 {#model-interfaces}

此模式与HTL `data-sly-use` 的说明有关，指向Java界面，而Sling Model实施也将它注册到组件的资源类型。

当与上述 [代理组件模式](#proxy-component-pattern) 相结合时，此形式的双重绑定提供了以下良好的扩展点：

1. 站点可以通过将Sling Model的实施注册到代理组件的资源类型来重新定义Sling Model的实施，无需考虑HTL文件，该文件仍可指向该界面。
1. 站点可以重新定义组件的HTL标记，而不必考虑它应指向的实施逻辑。

## 将一切整合在一起 {#putting-it-all-together}

以下是整个资源类型绑定结构的概述，以标题核心组件为例。它说明了站点特定代理组件如何允许解析组件版本控制，以避免内容资源包含任何版本号。然后，它显示组件 `title.html`[的HTL](https://helpx.adobe.com/experience-manager/htl/using/overview.html) 文件如何使用模型界面，而实施绑定到组件的特定版本通过 [Sling Model](https://sling.apache.org/documentation/bundles/models.html) 注释。

![资源绑定概述](assets/chlimage_1-32.png)

下面是另一个概述，它不显示实施POJO的详细信息，但显示相关 [模板和策略](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/page-templates-editable.html) 的引用方式。

`cq:allowedTemplates` 该属性告诉您可用于站点的模板，并告知 `cq:template` 每个页面相关模板的用途。每个模板由以下三部分构成：

* **结构**包含将在每个页面上强制显示的资源，并且页面作者无法删除，例如页面页眉和页脚组件。
* **初始**包含在创建页面时将复制到页面的初始内容。
* **策略**为每个组件添加映射到策略，该策略是组件的预配置。此映射允许跨模板重用策略，从而集中管理策略。

![模板和策略概述](assets/screen_shot_2018-12-07at093102.png)

**阅读下一步：**

* [使用核心组件](using.md) -在您自己的项目中与核心组件快速入门。
* [自定义核心组件](customizing.md) -了解如何样式和自定义核心组件。
