---
title: 自适应表单核心组件 - 文本输入（文本框）
description: 使用或自定义自适应表单文本输入核心组件。
role: Architect, Developer, Admin, User
exl-id: 49d9fe69-0578-4489-beaa-a18cdb14add7
source-git-commit: 0bebc248ee2b708f7677950d90356abd5bc70a98
workflow-type: tm+mt
source-wordcount: '1822'
ht-degree: 100%

---

# 文本输入（文本框） {#text-input-adaptive-forms-core-component}

文本输入（文本框）组件可让用户输入和编辑单行或多行文本，具体取决于输入元素的类型属性。文本输入组件可放置在表单中，并且通常标有易于标识其用途的有用文本。这些是任意表单的基本元素，广泛用于从用户处收集不同类型的数据，它们简单、灵活且可配置为验证输入，并提高数据收集的准确性。


**示例**

![](/help/adaptive-forms/assets/text-input.png)


## 用途 {#reasons-to-use-text-input-field}

有若干原因要在自适应表单中使用文本输入组件：

* **数据收集**：文本输入字段是最常见的表单元素之一，这些元素用于从用户处收集各种信息，例如姓名、电子邮件地址、电话号码和其他类型的文本数据。

* **用户友好**：文本输入字段简单易用，使用户能够轻松输入和编辑文本。

* **灵活性**：文本输入字段可用于收集一系列广泛的信息，从较短的单行文本条目到较长的多行文本条目。

## 版本和兼容性 {#version-and-compatibility}

作为 Cloud Service 核心组件 2.0.4 和 AEM 6.5.16.0 Forms 或更高版本核心组件 1.1.12 的一部分，自适应表单折叠面板核心组件于 2023 年 2 月发布。下表显示所有支持的版本、AEM 兼容性以及相应文档的链接：

| 组件版本 | AEM as a Cloud Service | AEM 6.5.16.0 Forms 或更高版本 |
|---|---|---|
| v1 | 兼容<br>[版本 2.0.4](/help/adaptive-forms/version.md) 和更高版本 | 兼容<br>[版本 1.1.12](/help/adaptive-forms/version.md) 及更高但低于 2.0.0 的版本。 |

有关核心组件版本的信息，请参阅[核心组件版本](/help/adaptive-forms/version.md)文档。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技术详细信息 {#technical-details}

可在 [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/textinput/v1/textinput) 上的技术文档中获得关于自适应表单顶部选项卡核心组件的最新信息。有关开发核心组件的更多信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## “配置”对话框 {#configure-dialog}

通过“配置”对话框，可轻松地自定义您为访客提供的文本输入体验。还可轻松地定义文本输入选项，从而营造一种无缝的用户体验。

![“基本”选项卡](/help/adaptive-forms/assets/textinput_basictab.png)

* **名称** - 可在表单和规则编辑器中通过唯一名称轻松地标识表单组件，但该名称不得包含空格或特殊字符。

* **标题** - 通过组件的标题，可轻松地标识表单中的组件，默认情况下，标题显示在该组件的顶部。如果不添加标题，则显示该组件的名称而非标题文本。

* **隐藏标题** - 选中此选项以隐藏该组件的标题。

* **占位符文本** - 表单组件中的占位符文本是指在输入字段中显示的短标签或提示，用于提示用户需要在该字段中输入什么类型的信息。当用户开始向该字段中键入时，占位符文本消失，如果将该字段留空，则占位符文本重新出现。它为用户提供视觉提示，但不充当该字段的永久标签或值。

* **绑定引用** - 绑定引用是对存储在外部数据源中并在表单中使用的数据元素的引用。通过绑定引用，可动态地将数据绑定到表单字段，以使表单可显示来自数据源的最新数据。例如，可使用绑定引用，根据输入到表单中的客户 ID，在该表单中显示该客户的姓名和地址。还可使用绑定引用，通过输入到表单中的数据更新数据源。这样通过 AEM Forms 即可创建与外部数据源交互的表单，从而为收集和管理数据提供一种无缝的用户体验。

* **隐藏组件** - 选中此选项以从表单中隐藏该组件。仍可访问该组件作其他用途，如在规则编辑器中使用它进行计算。当需要存储用户无需看到或直接更改的信息时，此项很有用。

* **禁用组件** - 选中此选项以禁用该组件。被禁用的组件不再活跃或最终用户无法编辑它。用户可看到但无法修改字段的值。仍可访问该组件作其他用途，如在规则编辑器中使用它进行计算。

* **只读** - 选中此选项以使组件不可编辑。用户可看到但无法修改字段的值。仍可访问该组件作其他用途，如在规则编辑器中使用它进行计算。

* **默认值** - 通过此选项，可在表单字段中添加默认值。当用户开始在字段中键入时，文本将消失。如果选中了&#x200B;**已禁用的组件**&#x200B;或&#x200B;**只读组件**，则在屏幕上显示默认值。如果用户未在表单字段中输入值，则在提交表单时提交此值。

* **允许多行** - 此选项可让用户在表单字段中输入多个行。

* **允许富文本** -“编辑”对话框提供了标准富文本格式化工具，可让用户设置文本的格式。

* **自动填充属性** -“自动填充”选项将根据模式或之前输入的文本填充表单字段。当用户开始在表单字段中键入文本时，下拉列表中将显示可从中选择适当选项的建议。

### “验证”选项卡 {#validation-tab}

![“验证”选项卡](/help/adaptive-forms/assets/textinput_validationtab.png)

* **必需** - 如果要在自适应表单中显示该组件，请选中此选项。选中此选项后，无法在&#x200B;**基本**&#x200B;选项卡中选择&#x200B;**隐藏组件**&#x200B;或&#x200B;**禁用组件**。

* **错误消息** - 通过此选项，可输入如果选中了&#x200B;**必需**&#x200B;复选框并将字段留空，所显示的消息。

* **脚本验证消息** - 通过此选项，可输入如果脚本验证失败，所显示的消息。

* **最大字符数** - 此选项可让您指定组件中允许的最大字符数。如果您输入的字符数大于在&#x200B;**最大字符数**&#x200B;中指定的值，则屏幕上显示一条错误消息。通过&#x200B;**最大字符数错误消息**&#x200B;对话框，可添加自定义错误消息。

* **最大字符数错误消息** - 通过&#x200B;**最大字符数错误消息**&#x200B;对话框，可添加如果您输入的字符数大于在&#x200B;**最大字符数**&#x200B;选项中指定的值，所显示的自定义错误消息。

* **最小字符数** - 通过此选项，可指定字段中允许的最小字符数。如果您输入的字符数小于在&#x200B;**最小字符数**&#x200B;中指定的值，则屏幕上显示一条错误消息。通过&#x200B;**最小字符数错误消息**&#x200B;对话框，可添加自定义错误消息。

* **最小字符数错误消息** - 如果您输入的字符数小于在&#x200B;**最小字符数**&#x200B;选项中指定的值，**最小字符数错误消息**&#x200B;对话框允许您添加自定义错误消息。

**验证模式**&#x200B;选项允许您输入一个模式来验证输入的文本。如果文本与&#x200B;**模式**&#x200B;选项中输入的值不一致，则屏幕上会显示错误消息。

* **模式** - 此选项可让您输入允许使用的文本验证模式。也可以使用正则表达式。

*  **错误消息** - 如果输入的文本与&#x200B;**模式**&#x200B;选项中输入的值不一致，则您可以通过该选项输入显示在屏幕上的消息

### “帮助内容”选项卡 {#help-content-tab}

![“帮助内容”选项卡](/help/adaptive-forms/assets/textinput_helptab.png)

* **简短描述** - 简短描述是一段简短的文字说明，其中提供关于特定表单字段的用途的其他信息或阐述。它帮助用户了解应将什么类型的数据输入到字段中，并可提供准则或示例以帮助确保所输入的信息有效且符合预期的标准。默认情况下，简短描述保持隐藏状态。启用&#x200B;**始终显示简短描述**&#x200B;选项以在组件下方显示它。

* **始终显示简短描述** - 启用该选项以在组件下方显示简短描述。

* **帮助文本** - 帮助文本是指提供给用户以帮助其正确填写表单字段的其他信息或指导。当用户单击组件旁的“帮助”图标 (i) 时显示它。帮助文本提供比表单字段的标签或占位符文本更详细的信息，旨在帮助用户了解该字段的要求或限制。它还可提供建议或示例，以使填写表单更轻松且更准确。

### “辅助功能”选项卡 {#accessibility-tab}

![“辅助功能”选项卡](/help/adaptive-forms/assets/textinput_accessibiltytab.png)

**屏幕阅读器文本** - 屏幕阅读器文本是指专供由视障人士使用的屏幕阅读器等辅助技术读取的附加文本。此文本提供表单字段用途的音频描述，并可包括关于字段的标题、描述、名称和任何相关消息（自定义文本）的信息。屏幕阅读器文本帮助确保包括视障用户在内的所有用户均可访问表单，并使其完整地了解表单字段及其要求。

## “设计”对话框 {#design-dialog}

“设计”对话框用于定义和管理文本框组件的 CSS 样式。

### “样式”选项卡 {#styles-tab}

该选项卡用于定义和管理组件的 CSS 样式。自适应表单文本框核心组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。

![“设计”对话框](/help/adaptive-forms/assets/telephoneinput_designdialog.png)

* **默认 CSS 类**：可为自适应表单文本框核心组件提供默认 CSS 类。

* **允许使用的样式**：可通过提供名称和表示样式的 CSS 类而定义样式。例如，您可以创建一个名为“bold text”的样式，并提供 CSS 类“font-weight: bold”。可使用这些样式或将其应用于自适应表单编辑器中的自适应表单。要应用样式，请在自适应表单编辑器中选择要将样式应用于的组件，导航到“属性”对话框，然后从&#x200B;**样式**&#x200B;下拉列表中选择所需的样式。如果您需要更新或修改样式，只需返回“设计”对话框，在“样式”选项卡中更新样式，然后保存更改。

### “格式”选项卡 {#format-tab}

通过“格式”选项卡，可指定默认和自定义数字格式。

![“格式”选项卡](/help/adaptive-forms/assets/telephoneinput_format.png)


## 相关文章 {#related-article}

* [在 AEM Sites 页面或体验片段中创建自适应表单](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html)

* [创建独立的自适应表单](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html)


>[!MORELIKETHIS]
>
>* [折叠](/help/adaptive-forms/components/accordion.md)
>* [按钮](/help/adaptive-forms/components/button.md)
>* [复选框组](/help/adaptive-forms/components/checkbox-group.md)
>* [日期选取器](/help/adaptive-forms/components/date-picker.md)
>* [下拉列表](/help/adaptive-forms/components/drop-down.md)
>* [电子邮件输入](/help/adaptive-forms/components/email-input.md)
>* [表单容器](/help/adaptive-forms/components/form-container.md)
>* [文件附件](/help/adaptive-forms/components/file-attachment.md)
>* [页脚](/help/adaptive-forms/components/footer.md)
>* [页眉](/help/adaptive-forms/components/header.md)
>* [水平选项卡](/help/adaptive-forms/components/horizontal-tabs.md)
>* [图像](/help/adaptive-forms/components/image.md)
>* [数值输入](/help/adaptive-forms/components/number-input.md)
>* [面板容器](/help/adaptive-forms/components/panel-container.md)
>* [单选按钮](/help/adaptive-forms/components/radio-button.md)
>* [“重置”按钮](/help/adaptive-forms/components/reset-button.md)
>* [“提交”按钮](/help/adaptive-forms/components/submit-button.md)
>* [电话号码输入](/help/adaptive-forms/components/telephone-input.md)
>* [文本](/help/adaptive-forms/components/text.md)
>* [标题](/help/adaptive-forms/components/title.md)
>* [向导](/help/adaptive-forms/components/wizard.md)

## 另请参阅 {#see-also}

{{see-also}}