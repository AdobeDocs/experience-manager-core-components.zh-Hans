---
title: 自适应Forms核心组件 — “密码”框
description: 使用或自定义自适应Forms密码框核心组件。
role: Architect, Developer, Admin, User
hide: true
hidefromtoc: true
source-git-commit: 86a30bc396d89340106177deb08323bfc5640e0e
workflow-type: tm+mt
source-wordcount: '1916'
ht-degree: 90%

---

# 密码框组件

<span class="preview">这是一项预发布功能，可通过我们的[预发布渠道](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/release-notes/prerelease.html#new-features)访问。</span>

密码框组件允许用户输入和编辑通常为隐私而蒙版的敏感信息。 可使用各种验证规则配置密码组件以确保数据准确性。 密码字段在表单中非常简单且经常使用，可增强数据安全性。

**示例**

![密码框示例](/help/adaptive-forms/assets/password.png)

用户可以单击眼睛图标来切换输入密码文本的可见性。 它增强了安全性，同时允许用户准确地输入机密信息。

## 用途

在自适应表单中使用密码框组件有以下几个原因：

- **安全数据收集**：密码框字段用于收集敏感信息，如密码、PIN和其他机密条目，显示用于隐私的蒙版字符。

- **用户友好**：密码框字段允许用户安全地输入和编辑信息，而无需在屏幕上显示该信息。

- **灵活性**：密码框组件可以配置为符合安全要求，例如最小字符长度、特殊字符或其他自定义验证，以确保强大的数据保护能力和准确性。

<!--
## Version and Compatibility {#version-and-compatibility}

The Adaptive Forms Password box Core Component was released in Feb 2023 as part of the Core Components 2.0.4 for Cloud Service and Core Components 1.1.12 for AEM 6.5.16.0 Forms or later. Here's a table showing all supported versions, AEM compatibility, and links to corresponding documentation:

|Component Version|AEM as a Cloud Service|AEM 6.5.16.0 Forms or later|
|---|---|---|
|v1|Compatible with<br>[release 2.0.4](/help/adaptive-forms/version.md) and later| Compatible with<br>[release 1.1.12](/help/adaptive-forms/version.md) and later but less than 2.0.0.|

For information on Core Component versions and releases, refer to the [Core Components Versions](/help/adaptive-forms/version.md) document.

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技术详细信息 {#technical-details}

可在 [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/textinput/v1/textinput) 上的技术文档中获得关于自适应表单顶部选项卡核心组件的最新信息。有关开发核心组件的更多信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## “配置”对话框 {#configure-dialog}

通过“配置”对话框，可轻松地自定义您为访客提供的文本输入体验。还可轻松地定义文本输入选项，从而营造一种无缝的用户体验。

### “基本”选项卡

![“基本”选项卡](/help/adaptive-forms/assets/password-basic.png)

- **名称** - 可在表单和规则编辑器中通过唯一名称轻松地标识表单组件，但该名称不得包含空格或特殊字符。

- **标题** - 通过组件的标题，可轻松地标识表单中的组件，默认情况下，标题显示在该组件的顶部。如果不添加标题，则显示该组件的名称而非标题文本。
- **允许标题为富文本**：此功能使用户能够格式化纯文本标题，结合粗体、斜体、下划线文本、各种字体、字体大小、颜色和附加选项等功能，以增强视觉呈现和定制效果。它提供了更大的灵活性以及对创作的控制度，使标题在文档、网站或应用程序中脱颖而出。\
  选中&#x200B;**允许标题为富文本**&#x200B;复选框后，可以看到格式化选项，用于设置组件标题的样式。要访问所有可用的格式选项，您可以点击![全屏图标](/help/adaptive-forms/assets/fullscreen-icon.png)选项卡。

  ![富文本支持](/help/adaptive-forms/assets/richtext-support-title.png)

- **隐藏标题** - 选中此选项可隐藏该组件的标题。

- **占位符文本** - 表单组件中的占位符文本是指在输入字段中显示的短标签或提示，用于提示用户需要在该字段中输入什么类型的信息。当用户开始向该字段中键入时，占位符文本消失，如果将该字段留空，则占位符文本重新出现。它为用户提供视觉提示，但不充当该字段的永久标签或值。
- **绑定引用** - 绑定引用是对存储在外部数据源中并在表单中使用的数据元素的引用。通过绑定引用，可动态地将数据绑定到表单字段，以使表单可显示来自数据源的最新数据。例如，可使用绑定引用，根据输入到表单中的客户 ID，在该表单中显示该客户的姓名和地址。还可使用绑定引用，通过输入到表单中的数据更新数据源。这样通过 AEM Forms 即可创建与外部数据源交互的表单，从而为收集和管理数据提供一种无缝的用户体验。
- **标记为未绑定表单元素**：选择此选项可配置未链接到任何架构的表单字段。利用此选项，您可以保存数据而不更新数据源。它还可让您以一种独立于标准数据库集成的自定义方式处理数据。

- **隐藏组件** - 选中此选项以从表单中隐藏该组件。仍可访问该组件作其他用途，如在规则编辑器中使用它进行计算。当需要存储用户无需看到或直接更改的信息时，此项很有用。

- **禁用组件** - 选中此选项以禁用该组件。被禁用的组件不再活跃或最终用户无法编辑它。用户可看到但无法修改字段的值。仍可访问该组件作其他用途，如在规则编辑器中使用它进行计算。

- **只读** - 选中此选项以使组件不可编辑。用户可看到但无法修改字段的值。仍可访问该组件作其他用途，如在规则编辑器中使用它进行计算。

### “验证”选项卡 {#validation-tab}

![“验证”选项卡](/help/adaptive-forms/assets/password-validation.png)

- **必需** - 如果要在自适应表单中显示该组件，请选中此选项。选择此选项后，您必须先输入一个值，然后再继续提交表单。选中此选项后，无法在&#x200B;**基本**&#x200B;选项卡中选择&#x200B;**隐藏组件**&#x200B;或&#x200B;**禁用组件**。

- **错误消息** - 通过此选项，可输入如果选中了&#x200B;**必需**&#x200B;复选框并将字段留空，所显示的消息。

- **脚本验证消息** - 通过此选项，可输入如果脚本验证失败，所显示的消息。

- **最大字符数** - 此选项可让您指定组件中允许的最大字符数。如果您输入的字符数大于在&#x200B;**最大字符数**&#x200B;中指定的值，则屏幕上显示一条错误消息。通过&#x200B;**最大字符数错误消息**&#x200B;对话框，可添加自定义错误消息。

- **最大字符数错误消息** - 通过&#x200B;**最大字符数错误消息**&#x200B;对话框，可添加如果您输入的字符数大于在&#x200B;**最大字符数**&#x200B;选项中指定的值，所显示的自定义错误消息。

- **最小字符数** - 通过此选项，可指定字段中允许的最小字符数。如果您输入的字符数小于在&#x200B;**最小字符数**&#x200B;中指定的值，则屏幕上显示一条错误消息。通过&#x200B;**最小字符数错误消息**&#x200B;对话框，可添加自定义错误消息。

- **最小字符数错误消息** - 如果您输入的字符数小于在&#x200B;**最小字符数**&#x200B;选项中指定的值，**最小字符数错误消息**&#x200B;对话框允许您添加自定义错误消息。

**验证模式**&#x200B;选项允许您输入一个模式来验证输入的文本。如果文本与&#x200B;**模式**&#x200B;选项中输入的值不一致，则屏幕上会显示错误消息。

- **模式** - 此选项可让您输入允许使用的文本验证模式。也可以使用正则表达式。

-  **错误消息** - 如果输入的文本与&#x200B;**模式**&#x200B;选项中输入的值不一致，则您可以通过该选项输入显示在屏幕上的消息

### “帮助内容”选项卡 {#help-content-tab}

![“帮助内容”选项卡](/help/adaptive-forms/assets/password-help.png)

- **简短描述** - 简短描述是一段简短的文字说明，其中提供关于特定表单字段的用途的其他信息或阐述。它帮助用户了解应将什么类型的数据输入到字段中，并可提供准则或示例以帮助确保所输入的信息有效且符合预期的标准。默认情况下，简短描述保持隐藏状态。启用&#x200B;**始终显示简短描述**&#x200B;选项以在组件下方显示它。

- **始终显示简短描述** - 启用该选项以在组件下方显示简短描述。

- **帮助文本** - 帮助文本是指提供给用户以帮助其正确填写表单字段的其他信息或指导。当用户单击组件旁的“帮助”图标 (i) 时显示它。帮助文本提供比表单字段的标签或占位符文本更详细的信息，旨在帮助用户了解该字段的要求或限制。它还可提供建议或示例，以使填写表单更轻松且更准确。

### “辅助功能”选项卡 {#accessibility-tab}

![“辅助功能”选项卡](/help/adaptive-forms/assets/password-accessibilty.png)

- **屏幕阅读器文本** - 屏幕阅读器文本是指专供由视障人士使用的屏幕阅读器等辅助技术读取的附加文本。此文本提供表单字段用途的音频描述，并可包括关于字段的标题、描述、名称和任何相关消息（自定义文本）的信息。屏幕阅读器文本帮助确保包括视障用户在内的所有用户均可访问表单，并使其完整地了解表单字段及其要求。
   - **自定义文本**：选中此选项以将自定义文本用于 ARIA 辅助功能标签。选中此选项将显示“自定义文本”对话框。可在“自定义文本”对话框中添加相关信息。
   - **描述**：选中此选项以将描述用于 ARIA 辅助功能标签。
   - **标题**：选中此选项以将标题用于 ARIA 辅助功能标签。
   - **名称**：选中此选项以将名称用于 ARIA 辅助功能标签。
   - **无**：如果不想为 ARIA 辅助功能标签添加任何内容，请选中此选项。

## “设计”对话框 {#design-dialog}

“设计”对话框用于定义和管理文本框组件的 CSS 样式。

### “样式”选项卡 {#styles-tab}

该选项卡用于定义和管理组件的 CSS 样式。自适应表单文本框核心组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。

![“样式”选项卡](/help/adaptive-forms/assets/datepicker_styletab.png)

- **默认 CSS 类**：可为自适应表单文本框核心组件提供默认 CSS 类。

- **允许使用的样式**：可通过提供名称和表示样式的 CSS 类而定义样式。例如，您可以创建一个名为“bold text”的样式，并提供 CSS 类“font-weight: bold”。可使用这些样式或将其应用于自适应表单编辑器中的自适应表单。要应用样式，请在自适应表单编辑器中选择要将样式应用于的组件，导航到“属性”对话框，然后从&#x200B;**样式**&#x200B;下拉列表中选择所需的样式。如果您需要更新或修改样式，只需返回“设计”对话框，在“样式”选项卡中更新样式，然后保存更改。

### 自定义属性

![“自定义属性”对话框](/help/adaptive-forms/assets/datepicker_customproperties.png)

通过自定义属性，您可使用表单模板将自定义属性（键值对）关联到自适应表单核心组件。自定义属性反映在组件 Headless 演绎版的属性部分中。它可让您创建根据自定义属性值进行调整的动态表单行为。例如，开发人员可以为移动、桌面或 Web 平台设计 Headless 表单组件的各种演绎版，从而大大提升各种设备上的用户体验。

- **组名称**：您可以提供名称来标识自定义属性组。您可以添加、删除或重新排列多个自定义属性组。添加自定义属性组后，可看到以下选项：

   - **键值对**：您可以通过单击“**添加**”按钮，为每个自定义属性组添加多个自定义属性名称和自定义属性值。

   - **删除**：点按或单击此项可删除自定义属性名称和自定义属性值。

   - **重新排列**：点按或单击并拖动可重新排列自定义属性名称和自定义属性值的顺序。

### “格式”选项卡 {#formats-tab}

通过“格式”选项卡，可指定默认和自定义日期格式。

![“格式”选项卡](/help/adaptive-forms/assets/emailinput_formattab.png)

<!--

## Related article {#related-article}

* [Create a standalone Adaptive Form](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html)

-->

## 相关文章 {#related-articles}

{{more-like-this}}

## 另请参阅 {#see-also}

{{see-also}}