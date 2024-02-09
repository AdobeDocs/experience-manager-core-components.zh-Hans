---
title: 自适应表单核心组件 - 开关组件
description: 使用或自定义自适应表单开关核心组件。
role: Architect, Developer, Admin, User
hide: true
hidefromToC: true
source-git-commit: d172e019c5621d950a94cbdd8d27e4834dbabe3b
workflow-type: tm+mt
source-wordcount: '1689'
ht-degree: 100%

---


# 开关组件{#switch-adaptive-forms-core-component}

开关组件是表单中使用的图形用户界面，允许用户在两个选项之间进行选择。它通常是两种状态开关，使用户能够在两种状态之间进行选择，从而启用或禁用特性、设置或功能。开关组件旨在直观地表示当前状态并显示特定功能是处于启用还是禁用状态。

开关组件是一个布尔值控制元素，它可将值设置为 true 或 false。例如，它用于打开或关闭某项功能，例如静音或取消静音，或者启用或禁用蓝牙或 WiFi。

![开关组件示例](/help/adaptive-forms/assets/switch-example.png)

## 用途 {#reasons-to-use-switch}

在自适应表单中使用开关的常见原因是：

- **用户交互**：用户可以通过单击或点按开关组件来与之交互。

- **状态**：开关组件有两种状态：ON 和 OFF。开关组件的初始状态取决于默认设置或它控制的功能的当前状态。

- **可视表示形式**：开关组件通过更改颜色或位置来直观地反映其当前状态。

- **控制功能**：开关组件用于启用或禁用 AEM 表单中的特定功能。例如，它允许用户打开或关闭某项功能。

## 版本和兼容性 {#version-and-compatibility}

作为核心组件 2.0.64 的一部分发布了自适应表单开关核心组件。下表展示了所有支持的版本、AEM 兼容性和相应文档的链接：

|  |  |
|---|---|
| 组件版本 | AEM as a Cloud Service |
| --- | --- |
| v1 | 与<br>[版本 2.0.64](/help/adaptive-forms/version.md) 和更高版本兼容 | 兼容 | 兼容 |

有关核心组件版本的信息，请参阅[核心组件版本](/help/adaptive-forms/version.md)文档。

## 技术详细信息 {#technical-details}

可在 [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/switch/v1/switch) 上的技术文档中获得关于自适应表单开关核心组件的最新信息。有关开发核心组件的更多信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## “配置”对话框 {#configure-dialog}

通过“配置”对话框，可轻松地自定义您为访客提供的开关组件体验。还可轻松地定义开关组件选项，从而营造一种无缝的用户体验。

### “基本”选项卡

![“基本”选项卡](/help/adaptive-forms/assets/switch-basic.png)

- **名称** - 可在表单和规则编辑器中通过唯一名称轻松地标识表单组件，但该名称不得包含空格或特殊字符。

- **标题** - 通过组件的标题，可轻松地标识表单中的组件，默认情况下，标题显示在该组件的旁边。如果不添加标题，则不会显示该组件。

- **隐藏标题** - 选中此选项可隐藏该组件的标题。

- **保留“取消选中”状态值** - 选中此选项可让您指定未选择开关组件时要返回的值。
- **选项** - 指定每个选项的数据值和显示文本。
   - **启用时的数据值** - 指定在自适应表单中启用开关时要提交的值。
   - **启用时的显示文本** - 指定在自适应表单中启用开关时要显示为标签的文本。
   - **禁用时的数据值** - 指定未在自适应表单中启用开关时要提交的值。此选项仅在启用&#x200B;**保留“取消选中”状态值**&#x200B;开关时可见。
   - **禁用时的显示文本** - 指定未在自适应表单中启用开关时要显示为标签的文本。此选项仅在启用&#x200B;**保留“取消选中”状态值**&#x200B;开关时可见。

- **绑定引用** - 绑定引用是对存储在外部数据源中并在表单中使用的数据元素的引用。通过绑定引用，可动态地将数据绑定到表单字段，以使表单可显示来自数据源的最新数据。例如，可使用绑定引用，根据输入到表单中的客户 ID，在该表单中显示该客户的姓名和地址。还可使用绑定引用，通过输入到表单中的数据更新数据源。这样通过 AEM Forms 即可创建与外部数据源交互的表单，从而为收集和管理数据提供一种无缝的用户体验。
- **标记为未绑定表单元素**：选择此选项可配置未链接到任何架构的表单字段。利用此选项，您可以保存数据而不更新数据源。它还可让您以一种独立于标准数据库集成的自定义方式处理数据。

- **提交的值的数据类型**：此选项指定在选择任何选项时发送的值的数据类型。如果将&#x200B;**提交的值的数据类型**&#x200B;设置为 `Number`，而您在&#x200B;**选项**&#x200B;选项卡上将字符串数据添加到&#x200B;**数据值**，则屏幕显示一条 `Value type mismatch` 错误消息。
- **隐藏组件** - 选中此选项以从表单中隐藏该组件。仍可访问该组件作其他用途，如在规则编辑器中使用它进行计算。当需要存储用户无需看到或直接更改的信息时，此项很有用。

- **禁用组件** - 选中此选项可禁用或锁定该组件。被禁用的组件不再活跃或最终用户无法编辑它。用户可看到但无法修改字段的值。仍可访问该组件作其他用途，如在规则编辑器中使用它进行计算。

- **默认值**：通过此选项，可在表单字段中添加默认值。如果选中了&#x200B;**已禁用的组件**&#x200B;或&#x200B;**只读组件**，则在屏幕上显示默认值。如果用户未在表单字段中输入值，则在提交表单时提交此值。

### “验证”选项卡 {#validation-tab}

![“验证”选项卡](/help/adaptive-forms/assets/switch-validation.png)

- **必需** - 如果要在自适应表单中显示该组件，请选中此选项。选择此选项后，您必须先做出选择，之后才能继续提交表单。选中此选项后，无法在&#x200B;**基本**&#x200B;选项卡中选择&#x200B;**隐藏组件**&#x200B;或&#x200B;**禁用组件**。

- **错误消息** - 通过此选项，可输入如果选中了&#x200B;**必需**&#x200B;复选框并将表单字段留空，所显示的消息。

- **脚本验证消息** - 通过此选项，可输入如果脚本验证失败，所显示的消息。

### “帮助内容”选项卡 {#helpcontent-tab}

![“帮助内容”选项卡](/help/adaptive-forms/assets/switch-help.png)

- **简短描述** - 简短描述是一段简短的文字说明，其中提供关于特定表单字段的用途的其他信息或阐述。它帮助用户了解应将什么类型的数据输入到字段中，并可提供准则或示例以帮助确保所输入的信息有效且符合预期的标准。默认情况下，简短描述保持隐藏状态。启用&#x200B;**始终显示简短描述**&#x200B;选项以在组件下方显示它。

- **始终显示简短描述** - 启用该选项以在组件下方显示简短描述。

- **帮助文本** - 帮助文本是指提供给用户以帮助其正确填写表单字段的其他信息或指导。当用户单击组件旁的“帮助”图标 (i) 时显示它。帮助文本提供比表单字段的标签或占位符文本更详细的信息，旨在帮助用户了解该字段的要求或限制。它还可提供建议或示例，以使填写表单更轻松且更准确。

### “辅助功能”选项卡 {#accessibility-tab}

![“辅助功能”选项卡](/help/adaptive-forms/assets/switch-accessibility.png)

**屏幕阅读器文本** - 屏幕阅读器文本是指供由视障人士使用的屏幕阅读器等辅助技术读取的附加文本。此文本提供表单字段用途的音频描述，并可包括关于字段的标题、描述、名称和任何相关消息（自定义文本）的信息。屏幕阅读器文本帮助确保包括视障用户在内的所有用户均可访问表单，并使其完整地了解表单字段及其要求。

### “样式”选项卡 {#styles-tab}

![“样式”选项卡](/help/adaptive-forms/assets/switch-styles.png)

- **隐藏标签** - 选中此选项可隐藏开关组件的标签。

- **显示标签** - 选中此选项可显示开关组件的标签。

## “设计”对话框 {#design-dialog}

“设计”对话框用于定义和管理开关组件的 CSS 样式。

### “样式”选项卡 {#styles-design-tab}

自适应表单开关核心组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。

![“设计”对话框](/help/adaptive-forms/assets/checkbox-style.png)

- **默认 CSS 类**：可为自适应表单开关组核心组件提供默认 CSS 类。

- **允许使用的样式**：可通过提供名称和表示样式的 CSS 类而定义样式。例如，您可以创建一个名为“bold text”的样式，并提供 CSS 类“font-weight: bold”。可使用这些样式或将其应用于自适应表单编辑器中的自适应表单。要应用样式，请在自适应表单编辑器中选择要将样式应用于的组件，导航到“属性”对话框，然后从&#x200B;**样式**&#x200B;下拉列表中选择所需的样式。如果您需要更新或修改样式，只需返回“设计”对话框，在“样式”选项卡中更新样式，然后保存更改。

### 自定义属性

![“自定义属性”对话框](/help/adaptive-forms/assets/checkbox-customproperties.png)

通过自定义属性，您可使用表单模板将自定义属性（键值对）关联到自适应表单核心组件。自定义属性反映在组件 Headless 演绎版的属性部分中。它可让您创建根据自定义属性值进行调整的动态表单行为。例如，开发人员可以为移动、桌面或 Web 平台设计 Headless 表单组件的各种演绎版，从而大大提升各种设备上的用户体验。

- **组名称**：您可以提供名称来标识自定义属性组。您可以添加、删除或重新排列多个自定义属性组。添加自定义属性组后，可看到以下选项：

   - **键值对**：您可以通过单击“**添加**”按钮，为每个自定义属性组添加多个自定义属性名称和自定义属性值。

   - **删除**：点按或单击此项可删除自定义属性名称和自定义属性值。

   - **重新排列**：点按或单击并拖动可重新排列自定义属性名称和自定义属性值。

## 相关文章 {#related-articles}

{{more-like-this}}

## 另请参阅 {#see-also}

{{see-also}}








