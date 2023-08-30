---
title: 自适应表单核心组件 -“重置”按钮
description: 使用或自定义自适应表单重置按钮核心组件。
role: Architect, Developer, Admin, User
exl-id: e5aa9d89-aece-491e-80a1-7fb9ea6c4b60
source-git-commit: ad3e3bca5cb46f14e864e4704c90ac3b62779794
workflow-type: ht
source-wordcount: '1266'
ht-degree: 100%

---

# 重置 {#reset-button}

自适应表单中的“重置”按钮可让用户清除所有表单字段或将其重置为其默认值。单击“重置”按钮时，已在表单字段中输入的所有数据将被删除，字段将恢复到原始状态。“重置”按钮通常用作提交按钮的替代项，如果用户在表单中输入了错误的或不需要的数据，可使用此按钮重新开始。


## 用途 {#reasons-to-use-reset-button}

在自适应表单中使用“重置”按钮的原因是：

* **方便用户**：利用“重置”按钮，用户可快速而轻松地清空表单并重新开始填写，而无需手动删除每个字段。

* **改进了可用性**：“重置”按钮可让用户轻松地纠正错误或更改其输入，从而改善用户体验。

* **错误预防**：通过使用“重置”按钮，用户可以避免意外提交错误数据，从而导致错误或需要处理问题。

* **一致性**：在表单中包含“重置”按钮可提供用户体验的一致性，因为“重置”按钮是表单的一项常见功能。

* **更好的数据管理**：通过使用“重置”按钮，表单数据可以保持条理和准确，因为用户不太可能提交不一致或不正确的数据。

## 版本和兼容性 {#version-and-compatibility}

作为 Cloud Service 核心组件 2.0.4 和 AEM 6.5.16.0 Forms 或更高版本核心组件 1.1.12 的一部分，自适应表单折叠面板核心组件于 2023 年 2 月发布。下表显示所有支持的版本、AEM 兼容性以及相应文档的链接：

| 组件版本 | AEM as a Cloud Service | AEM 6.5.16.0 Forms 或更高版本 |
|---|---|---|
| v1 | 兼容<br>[版本 2.0.4](/help/adaptive-forms/version.md) 和更高版本 | 兼容<br>[版本 1.1.12](/help/adaptive-forms/version.md) 及更高但低于 2.0.0 的版本。 |

有关核心组件版本的信息，请参阅[核心组件版本](/help/adaptive-forms/version.md)文档。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技术详细信息 {#technical-details}

可在 [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/button/v1/button) 上的技术文档中获得关于自适应表单“重置”按钮核心组件的最新信息。有关开发核心组件的更多信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## “配置”对话框 {#configure-dialog}

通过“配置”对话框，可轻松地自定义您为访客提供的“重置”按钮体验。还可轻松地定义“重置”按钮选项，从而营造一种无缝的用户体验。

### “基本”选项卡 {#basic-tab}

![“基本”选项卡](/help/adaptive-forms/assets/button_basictab.png)

* **名称** - 可在表单和规则编辑器中通过唯一名称轻松地标识表单组件，但该名称不得包含空格或特殊字符。

* **标题** - 通过组件的标题，可轻松地标识表单中的组件，默认情况下，标题显示在该组件的顶部。如果不添加标题，则显示该组件的名称而非标题文本。

* **绑定引用** - 绑定引用是对存储在外部数据源中并在表单中使用的数据元素的引用。通过绑定引用，可动态地将数据绑定到表单字段，以使表单可显示来自数据源的最新数据。例如，可使用绑定引用，根据输入到表单中的客户 ID，在该表单中显示该客户的姓名和地址。还可使用绑定引用，通过输入到表单中的数据更新数据源。这样通过 AEM Forms 即可创建与外部数据源交互的表单，从而为收集和管理数据提供一种无缝的用户体验。

* **隐藏组件** - 选中此选项以从表单中隐藏该组件。仍可访问该组件作其他用途，如在规则编辑器中使用它进行计算。当需要存储用户无需看到或直接更改的信息时，此项很有用。
* **禁用组件** - 选中此选项以禁用该组件。被禁用的组件不再活跃或最终用户无法编辑它。用户可看到但无法修改字段的值。仍可访问该组件作其他用途，如在规则编辑器中使用它进行计算。
* **只读** - 选中此选项以使组件不可编辑。用户可看到但无法修改字段的值。仍可访问该组件作其他用途，如在规则编辑器中使用它进行计算。

### “帮助内容”选项卡 {#help-content}

![“帮助内容”选项卡](/help/adaptive-forms/assets/button_helptab.png)

* **简短描述** - 简短描述是一段简短的文字说明，其中提供关于特定表单字段的用途的其他信息或阐述。它帮助用户了解应将什么类型的数据输入到字段中，并可提供准则或示例以帮助确保所输入的信息有效且符合预期的标准。默认情况下，简短描述保持隐藏状态。启用&#x200B;**始终显示简短描述**&#x200B;选项以在组件下方显示它。

* **始终显示简短描述** - 启用该选项以在组件下方显示简短描述。

* **帮助文本** - 帮助文本是指提供给用户以帮助其正确填写表单字段的其他信息或指导。当用户单击组件旁的“帮助”图标 (i) 时显示它。帮助文本提供比表单字段的标签或占位符文本更详细的信息，旨在帮助用户了解该字段的要求或限制。它还可提供建议或示例，以使填写表单更轻松且更准确。

### 辅助功能 {#accessibility}

![“辅助功能”选项卡](/help/adaptive-forms/assets/button_accessibilitytab.png)


**屏幕阅读器文本** - 屏幕阅读器文本是指专供由视障人士使用的屏幕阅读器等辅助技术读取的附加文本。此文本提供表单字段用途的音频描述，并可包括关于字段的标题、描述、名称和任何相关消息（自定义文本）的信息。屏幕阅读器文本帮助确保包括视障用户在内的所有用户均可访问表单，并使其完整地了解表单字段及其要求。

## “设计”对话框 {#design-dialog}

“设计”对话框用于定义和管理“重置”按钮组件的 CSS 样式。


### “样式”选项卡 {#styles-tab}

该选项卡用于定义和管理组件的 CSS 样式。自适应表单“重置”按钮核心组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。

![“设计”对话框](/help/adaptive-forms/assets/reset_designdialog.png)

* **默认 CSS 类**：可为自适应表单“重置”按钮核心组件提供默认 CSS 类。

* **允许使用的样式**：可通过提供名称和表示样式的 CSS 类而定义样式。例如，您可以创建一个名为“bold text”的样式，并提供 CSS 类“font-weight: bold”。可使用这些样式或将其应用于自适应表单编辑器中的自适应表单。要应用样式，请在自适应表单编辑器中选择要将样式应用于的组件，导航到“属性”对话框，然后从&#x200B;**样式**&#x200B;下拉列表中选择所需的样式。如果您需要更新或修改样式，只需返回“设计”对话框，在“样式”选项卡中更新样式，然后保存更改。

## 相关文章 {#related-article}

* [在 AEM Sites 页面或体验片段中创建自适应表单](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html)

* [创建独立的自适应表单](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html)


## 另请参阅 {#see-also}

* [折叠](/help/adaptive-forms/components/accordion.md)
* [按钮](/help/adaptive-forms/components/button.md)
* [复选框组](/help/adaptive-forms/components/checkbox-group.md)
* [日期选取器](/help/adaptive-forms/components/date-picker.md)
* [下拉列表](/help/adaptive-forms/components/drop-down.md)
* [电子邮件输入](/help/adaptive-forms/components/email-input.md)
* [表单容器](/help/adaptive-forms/components/form-container.md)
* [文件附件](/help/adaptive-forms/components/file-attachment.md)
* [页脚](/help/adaptive-forms/components/footer.md)
* [页眉](/help/adaptive-forms/components/header.md)
* [水平选项卡](/help/adaptive-forms/components/horizontal-tabs.md)
* [图像](/help/adaptive-forms/components/image.md)
* [数值输入](/help/adaptive-forms/components/number-input.md)
* [面板容器](/help/adaptive-forms/components/panel-container.md)
* [单选按钮](/help/adaptive-forms/components/radio-button.md)
* [“提交”按钮](/help/adaptive-forms/components/submit-button.md)
* [电话号码输入](/help/adaptive-forms/components/telephone-input.md)
* [文本输入](/help/adaptive-forms/components/text-input.md)
* [文本](/help/adaptive-forms/components/text.md)
* [标题](/help/adaptive-forms/components/title.md)
* [向导](/help/adaptive-forms/components/wizard.md)