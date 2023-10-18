---
title: 自适应表单核心组件 - 复选框组
description: 使用或自定义自适应表单复选框组核心组件。
role: Architect, Developer, Admin, User
exl-id: 2ced0223-e664-470b-a400-b6865d3a67c9
source-git-commit: 0026734a2e43c51c7f5af2b37492d61e8f779ac7
workflow-type: tm+mt
source-wordcount: '1663'
ht-degree: 100%

---

# 复选框组 {#button-component-adaptive-forms-core-component}

自适应表单中的复选框组是一组相关的复选框，通过这组复选框，用户可从列表中选择一个或多个选项。每个复选框都由一个数据值（用于处理复选框组的项的值）和一个显示值（每个复选框项的标签，用于描述其用途）表示

**示例**

![](/help/adaptive-forms/assets/checkbox-group.png)

**“属性”对话框**

![](/help/adaptive-forms/assets/checkbox-group-properties.png)

在此示例中，使用“选项”元素将复选框分组在一起。**显示文本**&#x200B;元素用于为项提供标签，**数据值**&#x200B;用于指定提交表单时发送到服务器的值。

每个复选框选项/项都有唯一的“数据值”和“显示文本”属性。如果用户选中“Son”和“Daughter”复选框，则在提交表单时将对应的数据值发送到服务器。然后，服务器端脚本可以处理此数据以确定用户选择了哪些选项，并可使用此数据执行各种操作，例如更新表单中的其他字段或将表单数据提交给服务器端脚本进行进一步处理。

此外，可将复选框组配置为每个选项采用不同的处理值，并可使用自适应表单规则编辑器设置此项。

## 用途 {#reasons-to-use-check-box-group}

有若干原因使得在自适应表单中加入复选框组组件有益，这些原因包括：

* **多项选择**：通过复选框组，用户可从列表中选择多个选项，这在允许或要求多项选择的情况下很有用。

* **用户体验**：可使用复选框组为用户提供一种清晰而直观的方式以选择多个选项，使得表单更方便用户使用。

* **数据分析**：复选框组可用于从各种来源收集数据并进行分析，或将其用作进一步处理的输入。

* **调查**：复选框组可在调查中用于为一个问题选择多个选项。

* **用户偏好**：复选框组可用于收集用户对不同选项的偏好。

* **数据值**：复选框组也可用于处理一个复选框组的项。

## 版本和兼容性 {#version-and-compatibility}

作为 Cloud Service 核心组件 2.0.4 和 AEM 6.5.16.0 Forms 或更高版本核心组件 1.1.12 的一部分，自适应表单折叠面板核心组件于 2023 年 2 月发布。下表显示所有支持的版本、AEM 兼容性以及相应文档的链接：

| 组件版本 | AEM as a Cloud Service | AEM 6.5.16.0 Forms 或更高版本 |
|---|---|---|
| v1 | 兼容<br>[版本 2.0.4](/help/adaptive-forms/version.md) 和更高版本 | 兼容<br>[版本 1.1.12](/help/adaptive-forms/version.md) 及更高但低于 2.0.0 的版本。 |

有关核心组件版本的信息，请参阅[核心组件版本](/help/adaptive-forms/version.md)文档。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技术详细信息 {#technical-details}

可在 [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/checkboxgroup/v1/checkboxgroup) 上的技术文档中获得关于自适应表单复选框组核心组件的最新信息。有关开发核心组件的更多信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## “配置”对话框 {#configure-dialog}

通过“配置”对话框，可轻松地自定义您为访客提供的复选框体验。还可轻松地定义复选框选项，从而营造一种无缝的用户体验。


### “基本”选项卡 {#basic-tab}

![“基本”选项卡](/help/adaptive-forms/assets/checkbox_basictab.png)

* **名称** - 名称在规则编辑器中唯一标识组件。名称字符串中不允许使用特殊字符和空格。

* **标题** - 通过组件的标题，可轻松地标识表单中的组件，默认情况下，标题显示在该组件的顶部。如果不添加标题，则显示该组件的名称而非标题文本。

* **隐藏标题** - 选中此选项以隐藏该组件的标题。

* **选项** - 您可以使用&#x200B;**添加**&#x200B;按钮添加数据值和显示文本对。添加新选项后，可以执行以下操作：

   * **数据值** - 通过此选项，可输入在选择某个选项时要提交的内容。
   * **显示文本** - 通过此选项，可输入要在自适应表单中显示的内容。
   * **删除** - 点击或单击以删除复选框的选项。
   * **重新排列** - 点击或单击并拖动以重新排列面板的顺序。

* **绑定引用** - 绑定引用是对存储在外部数据源中并在表单中使用的数据元素的引用。通过绑定引用，可动态地将数据绑定到表单字段，以使表单可显示来自数据源的最新数据。例如，可使用绑定引用，根据输入到表单中的客户 ID，在该表单中显示该客户的姓名和地址。还可使用绑定引用，通过输入到表单中的数据更新数据源。这样通过 AEM Forms 即可创建与外部数据源交互的表单，从而为收集和管理数据提供一种无缝的用户体验。

* **提交的值的数据类型** - 此选项指定在选择任何选项时发送的值的数据类型。如果将&#x200B;**提交的值的数据类型**&#x200B;设置为 `Number`，而您在&#x200B;**选项**&#x200B;选项卡上将字符串数据添加到&#x200B;**数据值**，&#x200B;则屏幕显示一条 `Value type mismatch` 错误消息。

* **显示选项** - 此选项用于设置自适应表单中复选框的视觉对齐方式。支持的两个选项为：
   * **水平** - 选择此选项后，在自适应表单中从左到右显示复选框。
   * **垂直** - 选择此选项后，在自适应表单中从上到下显示复选框。

* **默认选项** - 通过此选项，可添加在表单加载时预先选择的默认值。使用“删除”图标删除已添加的选项。如果将&#x200B;**提交的值的数据类型**&#x200B;设置为 `Number`，而您将字符串数据添加到&#x200B;**默认选项**，则屏幕显示一条 `Value type mismatch` 错误消息。
* **隐藏组件** - 选中此选项以从表单中隐藏该组件。仍可访问该组件作其他用途，如在规则编辑器中使用它进行计算。当需要存储用户无需看到或直接更改的信息时，此项很有用。
* **禁用组件** - 选中此选项以禁用该组件。被禁用的组件不再活跃或最终用户无法编辑它。用户可看到但无法修改字段的值。仍可访问该组件作其他用途，如在规则编辑器中使用它进行计算。
* **只读** - 选中此选项以使组件不可编辑。用户可看到但无法修改字段的值。仍可访问该组件作其他用途，如在规则编辑器中使用它进行计算。

### “验证”选项卡 {#validation-tab}

![“验证”选项卡](/help/adaptive-forms/assets/checkbox_validationtab.png)

* **必需** - 如果要在自适应表单中显示该组件，请选中此选项。选中此选项后，无法在&#x200B;**基本**&#x200B;选项卡中选择&#x200B;**隐藏组件**&#x200B;或&#x200B;**禁用组件**。

* **错误消息** - 通过此选项，可输入如果选中了&#x200B;**必需**&#x200B;复选框并将表单字段留空，所显示的消息。

* **脚本验证消息** - 通过此选项，可输入如果脚本验证失败，所显示的消息。

### “帮助内容”选项卡 {#helpcontent-tab}

![“帮助内容”选项卡](/help/adaptive-forms/assets/checkbox_helptab.png)

* **简短描述** - 简短描述是一段简短的文字说明，其中提供关于特定表单字段的用途的其他信息或阐述。它帮助用户了解应将什么类型的数据输入到字段中，并可提供准则或示例以帮助确保所输入的信息有效且符合预期的标准。默认情况下，简短描述保持隐藏状态。启用&#x200B;**始终显示简短描述**&#x200B;选项以在组件下方显示它。

* **始终显示简短描述** - 启用该选项以在组件下方显示简短描述。

* **帮助文本** - 帮助文本是指提供给用户以帮助其正确填写表单字段的其他信息或指导。当用户单击组件旁的“帮助”图标 (i) 时显示它。帮助文本提供比表单字段的标签或占位符文本更详细的信息，旨在帮助用户了解该字段的要求或限制。它还可提供建议或示例，以使填写表单更轻松且更准确。

### “辅助功能”选项卡 {#accessibility-tab}

![“辅助功能”选项卡](/help/adaptive-forms/assets/checkbox_accessibility.png)

**屏幕阅读器文本** - 屏幕阅读器文本是指专供由视障人士使用的屏幕阅读器等辅助技术读取的附加文本。此文本提供表单字段用途的音频描述，并可包括关于字段的标题、描述、名称和任何相关消息（自定义文本）的信息。屏幕阅读器文本帮助确保包括视障用户在内的所有用户均可访问表单，并使其完整地了解表单字段及其要求。

    ##“设计”对话框 {#design-dialog}

“设计”对话框用于定义和管理复选框组组件的 CSS 样式。

### “样式”选项卡 {#styles-tab}

自适应表单复选框组核心组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。

![“设计”对话框](/help/adaptive-forms/assets/checkbox_designdialog.png)

* **默认 CSS 类**：可为自适应表单复选框组核心组件提供默认 CSS 类。

* **允许使用的样式**：可通过提供名称和表示样式的 CSS 类而定义样式。例如，您可以创建一个名为“bold text”的样式，并提供 CSS 类“font-weight: bold”。可使用这些样式或将其应用于自适应表单编辑器中的自适应表单。要应用样式，请在自适应表单编辑器中选择要将样式应用于的组件，导航到“属性”对话框，然后从&#x200B;**样式**&#x200B;下拉列表中选择所需的样式。如果您需要更新或修改样式，只需返回“设计”对话框，在“样式”选项卡中更新样式，然后保存更改。

<!--

## Related article {#related-article}

* [Create a standalone Adaptive Form](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html)

-->

>[!MORELIKETHIS]
>
>* [折叠](/help/adaptive-forms/components/accordion.md)
>* [按钮](/help/adaptive-forms/components/button.md)
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
>* [文本输入](/help/adaptive-forms/components/text-input.md)
>* [文本](/help/adaptive-forms/components/text.md)
>* [标题](/help/adaptive-forms/components/title.md)
>* [向导](/help/adaptive-forms/components/wizard.md)

## 另请参阅 {#see-also}

{{see-also}}