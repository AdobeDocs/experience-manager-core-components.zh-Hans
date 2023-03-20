---
title: 自适应表单核心组件 - 面板容器
description: 使用或自定义自适应表单面板容器核心组件。
role: Architect, Developer, Admin, User
exl-id: 104836fe-8325-47de-978d-1ff2d6a9dd15
source-git-commit: d2a6108f17f6e0c6b91bec84893d64a8bd48effd
workflow-type: tm+mt
source-wordcount: '1696'
ht-degree: 73%

---

# 面板容器 {#panel-container-adaptive-forms-core-component}

在自适应表单中，面板是用于对相关表单元素进行分组的容器元素。 它可让您以一种符合逻辑且有意义的方式对不同的表单元素进行分组和整理。这有助于改善表单的整体结构和可读性，使用户能够更轻松地理解和导航。

面板可用于创建可折叠的部分，这些部分可用于隐藏复杂或不太常用的表单字段，从而保持表单简单且易于使用。 它还允许您包含其他组件，如文本、复选框、按钮。

它还可用于设置不同的基于规则的操作，例如提交表单、打开网站、显示/隐藏组件或添加面板的实例。

**示例**

![](/help/adaptive-forms/assets/panel-container.png)

## 用途 {#reasons-to-use-panel-container}

有若干原因要在表单中使用面板，这些原因包括：

* **整理表单元素**：面板可用于将相关的表单元素组合起来，使用户能够更轻松地理解和浏览表单。

* **改善表单结构**：通过将表单元素分组到面板中，可以改善表单的整体结构和可读性，使其更易于理解。

* **创建可折叠部分**：面板可用于创建可折叠部分，这对于隐藏复杂或不常用的表单字段来说很有用，可以使表单简单易用。

* **增强可用性**：通过使用面板整理表单元素，可使得表单变得更方便用户使用，从而提高完成率。

## 版本和兼容性 {#version-and-compatibility}

自适应Forms折叠核心组件是作为适用于AEM 6.5.16.0 Forms或更高版本的核心组件2.0.4的一部分于2023年2月发布的，该组件适用于Cloud Service和核心组件1.1.12或更高版本。 下表显示了所有受支持的版本、AEM兼容性以及指向相应文档的链接：

| 组件版本 | AEM as a Cloud Service | AEM 6.5.16.0 Forms或更高版本 |
|---|---|---|
| v1 | 兼容<br>[版本 2.0.4](/help/adaptive-forms/version.md) 和更高版本 | 与兼容<br>[版本1.1.12](/help/adaptive-forms/version.md) 但低于2.0.0。 |

有关核心组件版本的信息，请参阅[核心组件版本](/help/adaptive-forms/version.md)文档。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技术详细信息 {#technical-details}

可在 [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/panelcontainer/v1/panelcontainer) 上的技术文档中获得关于自适应表单面板容器核心组件的最新信息。有关开发核心组件的更多信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## “配置”对话框 {#configure-dialog}

通过“配置”对话框，可轻松地自定义您为访客提供的面板容器体验。还可轻松地定义面板容器选项，从而营造一种无缝的用户体验。

### “基本”选项卡 {#basic-tab}

![“基本”选项卡](/help/adaptive-forms/assets/panelcontainer_basictab.png)

* **名称** - 可在表单和规则编辑器中通过唯一名称轻松地标识表单组件，但该名称不得包含空格或特殊字符。

* **标题** - 通过组件的标题，可轻松地标识表单中的组件，默认情况下，标题显示在该组件的顶部。如果不添加标题，则显示该组件的名称而非标题文本。

* **隐藏标题** - 选中此选项以隐藏该组件的标题。

* **将数据包装到对象中** - 选中“将数据包装到对象中”以将向导中的字段数据放入 JSON 对象。如果不选中此项，则提交数据 JSON 对于向导的字段采用扁平结构。

* **布局** - 可为向导采用固定布局（“简单”）或灵活布局（“响应式网格”）。“简单”布局将所有内容固定在原位，而通过“响应式网格”，可调整组件的位置以满足您的需要。例如，使用响应式网格将表单中的“名字”、“中间名”和“姓氏”排成一行。

* **绑定引用** - 绑定引用是对存储在外部数据源中并在表单中使用的数据元素的引用。通过绑定引用，可动态地将数据绑定到表单字段，以使表单可显示来自数据源的最新数据。例如，可使用绑定引用，根据输入到表单中的客户 ID，在该表单中显示该客户的姓名和地址。还可使用绑定引用，通过输入到表单中的数据更新数据源。这样通过 AEM Forms 即可创建与外部数据源交互的表单，从而为收集和管理数据提供一种无缝的用户体验。
* **隐藏组件** - 选中此选项以从表单中隐藏该组件。仍可访问该组件作其他用途，如在规则编辑器中使用它进行计算。当需要存储用户无需看到或直接更改的信息时，此项很有用。
* **禁用组件** - 选中此选项以禁用该组件。被禁用的组件不再活跃或最终用户无法编辑它。用户可看到但无法修改字段的值。仍可访问该组件作其他用途，如在规则编辑器中使用它进行计算。

### “帮助内容”选项卡 {#help-content}

![“帮助内容”选项卡](/help/adaptive-forms/assets/panelcontainer_helptab.png)

* **简短描述** - 简短描述是一段简短的文字说明，其中提供关于特定表单字段的用途的其他信息或阐述。它帮助用户了解应将什么类型的数据输入到字段中，并可提供准则或示例以帮助确保所输入的信息有效且符合预期的标准。默认情况下，简短描述保持隐藏状态。启用&#x200B;**始终显示简短描述**&#x200B;选项以在组件下方显示它。

* **始终显示简短描述** - 启用该选项以在组件下方显示简短描述。

* **帮助文本** - 帮助文本是指提供给用户以帮助其正确填写表单字段的其他信息或指导。当用户单击组件旁的“帮助”图标 (i) 时显示它。帮助文本提供比表单字段的标签或占位符文本更详细的信息，旨在帮助用户了解该字段的要求或限制。它还可提供建议或示例，以使填写表单更轻松且更准确。

### “辅助功能”选项卡 {#accessibility}

![“辅助功能”选项卡](/help/adaptive-forms/assets/panelcontainer_accessibilitytab.png)

* **屏幕阅读器的文本**  — 屏幕阅读器的文本是指视觉障碍人士使用的辅助技术（如屏幕阅读器）用来阅读的其他文本。 此文本提供表单字段用途的音频描述，并可包括关于字段的标题、描述、名称和任何相关消息（自定义文本）的信息。屏幕阅读器文本帮助确保包括视障用户在内的所有用户均可访问表单，并使其完整地了解表单字段及其要求。

* **用于读出内容的屏幕阅读器的 HTML 角色** - HTML 角色是一个属性，用于向屏幕阅读器等辅助技术指定 HTML 元素的用途。角色属性用于为元素提供额外的上下文和语义，使屏幕阅读器更容易向用户解释和读出内容。例如，在 AEM Forms 中，表单字段的标签可能具有“标签”的作用，其输入字段可能具有“文本框”的作用。这有助于屏幕阅读器理解标签和输入字段之间的关系，并正确地向用户读出内容。

## “设计”对话框 {#design-dialog}

“设计”对话框用于定义和管理面板容器组件的CSS样式。

### “允许使用的组件”选项卡 {#allowed-components-tab}

![允许的组件选项卡](/help/adaptive-forms/assets/panel_allowedcomponent.png)

的 **允许的组件** 选项卡允许模板编辑器设置可作为项目添加到自适应Forms编辑器中面板容器组件的面板中的组件。

### “默认组件”选项卡 {#default-component-tab}

此选项卡允许模板编辑器将可作为项目添加的组件映射到自适应Forms编辑器中面板容器组件中的面板。

![面板默认组件](/help/adaptive-forms/assets/panel_defaultcomponent.png)

### 响应设置 {#responsive-settings}

利用此选项卡，模板编辑器可设置要在响应式网格中显示的列数。

![响应式网格](/help/adaptive-forms/assets/panel_responsivesettings.png)

### 容器设置选项卡 {#container-setting-tab}

容器设置选项卡允许在自适应Forms编辑器中设置组件的位置。

![容器设置](/help/adaptive-forms/assets/panel_settings.png)

* **布局**:简单布局可将所有内容固定在原位置，而响应式网格允许您更改组件的位置以满足您的需求。
* **禁用布局**:您还可以通过选择 **禁用布局** 复选框。
* **启用背景图像**:利用此选项卡，可在模板编辑器中设置背景图像和颜色。
* **启用背景颜色**:利用此选项卡，可在模板编辑器中设置背景颜色。

### “样式”选项卡 {#styles-tab}

选项卡用于定义和管理组件的CSS样式。 自适应Forms面板容器核心组件支持AEM [样式系统](/help/get-started/authoring.md#component-styling).

![样式选项卡](/help/adaptive-forms/assets/panel_style.png)

* **默认CSS类**:您可以为自适应Forms核心组件提供默认CSS类。

* **允许使用的样式**：可通过提供名称和表示样式的 CSS 类而定义样式。例如，您可以创建一个名为“bold text”的样式，并提供 CSS 类“font-weight: bold”。您可以在自适应Forms中将这些样式用于自适应表单或将其应用于自适应表单。 要应用样式，请在自适应Forms编辑器中，选择要将样式应用到的组件，导航到属性对话框，然后从 **样式** 下拉列表。 如果您需要更新或修改样式，只需返回“设计”对话框，在“样式”选项卡中更新样式，然后保存更改。

* **用于读出内容的屏幕阅读器的 HTML 角色** - HTML 角色是一个属性，用于向屏幕阅读器等辅助技术指定 HTML 元素的用途。角色属性用于为元素提供额外的上下文和语义，使屏幕阅读器更容易向用户解释和读出内容。例如，在 AEM Forms 中，表单字段的标签可能具有“标签”的作用，其输入字段可能具有“文本框”的作用。这有助于屏幕阅读器理解标签和输入字段之间的关系，并正确地向用户读出内容。

