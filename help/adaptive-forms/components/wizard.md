---
title: 自适应表单核心组件 - 向导
description: 使用或自定义自适应表单向导核心组件。
role: Architect, Developer, Admin, User
exl-id: fd785cd2-5ed6-4efb-997f-ce9056ed113d
source-git-commit: 8bba79956a04020647d5d04f9fe6fa674affedf1
workflow-type: ht
source-wordcount: '2186'
ht-degree: 100%

---

# 向导组件{#wizard-adaptive-forms-core-component}

自适应表单中的向导布局是指表单被分成多个步骤或页面，用户通过这些步骤或页面完成整个表单（一次一个步骤）。此布局称作“向导”，因为它将引导用户逐步完成表单。

向导的每个步骤通常包含一组相关的表单字段和一个用于在步骤之间移动的导航机制，例如“下一步”和“后退”按钮。用户只有在完成当前步骤并填写所有必填字段后，才能继续下一步。

向导布局对于包含大量字段或需要收集的信息的表单很有用，因为它将表单拆分成多个更小且更易于管理的部分。它还帮助用户一次专注于一组字段，这可以简化表单填写过程。

不过，它也会增加表单的复杂性，因为用户必须浏览多个页面才能完成表单。因此，在决定使用向导布局之前，必须评估表单要求和用户需求。
您可以在自适应表单中使用向导布局核心组件来创建向导布局。

**示例**

![示例](/help/adaptive-forms/assets/wizard.png)

## 用途 {#reasons-to-use-wizard-in-an-adaptive-form}

有若干原因使得在自适应表单中使用向导布局可能有益：

- **简单性**：通过将表单拆分成多个步骤，使用户能够更轻松地了解和完成表单，因为他们能够一次专注于一组字段。

- **编排**：向导布局可以帮助按主题或用途编排表单，它还可以将相关字段组合在一起，从而使表单填写过程更加合理和高效。

- **验证**：向导布局允许分步验证，这可以帮助用户随时识别和纠正错误，而不是等到表单结束。

- **进度指示器**：向导布局可以显示表单的进度，这有助于用户了解尚未填写的表单部分。

- **长表单**：如果表单具有大量字段，则用户一次查看所有字段可能会感到不知所措，因此，将它们拆分成更小、更易于管理的部分可以使其不那么令人生畏。

- **避免放弃**：向导布局还可以帮助减少表单放弃，因为用户在能够查看进度并了解剩余工作的情况下会更有可能完成表单。

- **移动体验**：向导布局也有利于在移动设备上访问表单，因为它允许加载速度更快且更易于导航的较小页面。

总的来说，向导布局可以使用户的表单填写过程更易管理和高效，但在决定使用此类布局之前，请务必先考虑表单的复杂性和用户需求。

## 版本和兼容性 {#version-and-compatibility}

2023 年 2 月，作为核心组件 2.0.4 的一部分发布了自适应表单向导布局核心组件。下表展示所有支持的版本、AEM 兼容性和相应文档的链接：

|  |  |
|---|---|
| 组件版本 | AEM as a Cloud Service |
| --- | --- |
| v1 | 与<br>[版本 2.0.4](/help/adaptive-forms/version.md) 和更高版本兼容 | 兼容 | 兼容 |

有关核心组件版本的信息，请参阅[核心组件版本](/help/adaptive-forms/version.md)文档。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技术详细信息 {#technical-details}

可在 [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/wizard/v1/wizard) 上的技术文档中获得关于自适应表单标题核心组件的最新信息。有关开发核心组件的更多信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## “配置”对话框 {#configure-dialog}

通过“配置”对话框，可轻松地自定义您为访客提供的向导体验。还可轻松地定义向导选项，从而营造一种无缝的用户体验。

### “基本”选项卡 {#basic-tab}

![“基本”选项卡](/help/adaptive-forms/assets/wizard-basic.png)

- **名称** - 可在表单和规则编辑器中通过唯一名称轻松地标识表单组件，但该名称不得包含空格或特殊字符。

- **标题** - 通过组件的标题，可轻松地标识表单中的组件，默认情况下，标题显示在该组件的顶部。

- **隐藏标题** - 选中此选项可隐藏该组件的标题。

- **表单提交时对子组件的数据进行分组（将数据包装在对象中）** - 选择该选项后，子组件中的数据将嵌套在父组件的 JSON 对象中。但是，如果未选择该选项，则提交的 JSON 数据具有扁平结构，没有父组件的对象。例如：

   - 选择该选项后，子组件中的数据（例如，街道、城市和邮政编码）将作为 JSON 对象嵌套在父组件（地址）中。这将创建一个层次结构，并且数据组织在父组件下。

     提交数据的结构：

     ```JSON
     { "Address":
     
     { "Street": "123 Main Street", "City": "New York", "Zip Code": "12345" }
     
     }
     ```

   - 当未选择该选项时，提交的 JSON 数据具有扁平结构，没有父组件（地址）的对象。所有数据都处于同一级别，没有任何层级组织。


     提交数据的结构：

     ```JSON
        { "Street": "123 Main Street", "City": "New York", "Zip Code": "12345" }
     ```

<!--   **Wrap data in an object** - Choose "Wrap data in an object" to put the field data from the Wizard inside a JSON object. If not chosen, the submit data JSON has a flat structure for the Wizard's fields.

-   **Layout** - You can have either a fixed layout (Simple) or a flexible layout (Responsive Grid) for your wizard. The Simple layout keeps everything fixed in the place, while the Responsive Grid allows you to adjust the position of components to suit your needs. For example, use Responsive Grid to align "First Name", "Middle Name" and "Last Name" in a form in a single row.  -->

- **绑定引用** - 绑定引用是对存储在外部数据源中并在表单中使用的数据元素的引用。通过绑定引用，可动态地将数据绑定到表单字段，以使表单可显示来自数据源的最新数据。例如，可使用绑定引用，根据输入到表单中的客户 ID，在该表单中显示该客户的姓名和地址。还可使用绑定引用，通过输入到表单中的数据更新数据源。这样通过 AEM Forms 即可创建与外部数据源交互的表单，从而为收集和管理数据提供一种无缝的用户体验。

- **隐藏组件** - 选中此选项以从表单中隐藏该组件。仍可访问该组件作其他用途，如在规则编辑器中使用它进行计算。当需要存储用户无需看到或直接更改的信息时，此项很有用。

- **禁用组件** - 选中此选项以禁用该组件。被禁用的组件不再活跃或最终用户无法编辑它。用户可看到但无法修改字段的值。仍可访问该组件作其他用途，如在规则编辑器中使用它进行计算。

- **只读** - 选中此选项以使组件不可编辑。用户可看到但无法修改字段的值。仍可访问该组件作其他用途，如在规则编辑器中使用它进行计算。

### “重复向导”选项卡 {#repeat-wizard-tab}

![重复向导](/help/adaptive-forms/assets/wizard-repeat.png)

您可以使用重复选项来复制向导及其子组件，定义最小和最大重复计数，并促进在表单内复制类似部分。当与向导组件交互并访问其设置时，会出现以下选项：

- **使向导可重复**：切换功能，允许用户启用或禁用重复功能。
- **最少重复次数**：确定向导面板可以重复的最小次数。值为零表示向导面板不重复；默认值为零。
- **最多重复次数**：设置向导面板可以重复的最多次数。默认情况下，此值无限制。

要有效管理向导中的可重复部分，请按照[创建具有可重复部分的表单](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/create-forms-repeatable-sections.html)文章。

### “项”选项卡 {#items-tab}

![“项”选项卡](/help/adaptive-forms/assets/wizard_itemstab.png)

利用此选项，可以单击“添加”按钮来添加自适应表单组件，在编辑模式下添加向导时，此按钮默认出现。

### “帮助”选项卡 {#help-tab}

![“帮助”选项卡](/help/adaptive-forms/assets/wizard_helptab.png)

- **简短描述** - 简短描述是一段简短的文字说明，其中提供关于特定表单字段的用途的其他信息或阐述。它帮助用户了解应将什么类型的数据输入到字段中，并可提供准则或示例以帮助确保所输入的信息有效且符合预期的标准。默认情况下，简短描述保持隐藏状态。启用&#x200B;**始终显示简短描述**&#x200B;选项以在组件下方显示它。

- **始终显示简短描述** - 启用该选项以在组件下方显示简短描述。

- **帮助文本** - 帮助文本是指提供给用户以帮助其正确填写表单字段的其他信息或指导。当用户单击组件旁的“帮助”图标 (i) 时显示它。帮助文本提供比表单字段的标签或占位符文本更详细的信息，旨在帮助用户了解该字段的要求或限制。它还可提供建议或示例，以使填写表单更轻松且更准确。


### “辅助功能”选项卡 {#accessibility}

![“辅助功能”选项卡](/help/adaptive-forms/assets/wizard_accessibiltytab.png)

- **屏幕阅读器文本** - 屏幕阅读器文本是指专供由视障人士使用的屏幕阅读器等辅助技术读取的附加文本。此文本提供表单字段用途的音频描述，并可包括关于字段的标题、描述、名称和任何相关消息（自定义文本）的信息。屏幕阅读器文本帮助确保包括视障用户在内的所有用户均可访问表单，并使其完整地了解表单字段及其要求。
   - **自定义文本**：选中此选项以将自定义文本用于 ARIA 辅助功能标签。选中此选项将显示“自定义文本”对话框。可在“自定义文本”对话框中添加相关信息。
   - **描述**：选中此选项以将描述用于 ARIA 辅助功能标签。
   - **标题**：选中此选项以将标题用于 ARIA 辅助功能标签。
   - **名称**：选中此选项以将名称用于 ARIA 辅助功能标签。
   - **无**：如果不想为 ARIA 辅助功能标签添加任何内容，请选中此选项。

- **用于读出内容的屏幕阅读器的 HTML 角色** - HTML 角色是一个属性，用于向屏幕阅读器等辅助技术指定 HTML 元素的用途。角色属性用于为元素提供额外的上下文和语义，使屏幕阅读器更容易向用户解释和读出内容。例如，在 AEM Forms 中，表单字段的标签可能具有“标签”的作用，其输入字段可能具有“文本框”的作用。这有助于屏幕阅读器理解标签和输入字段之间的关系，并正确地向用户读出内容。


## “设计”对话框 {#design-dialog}

通过“设计”对话框，模板创建者可控制在默认情况下如何显示各种内容。对于自适应表单向导组件，您可以进行以下设置：

- 表单创建者可以在自适应表单编辑器中添加到向导中的核心组件
- 可在自适应表单编辑器的向导组件的“属性”对话框中应用的样式（CSS 类）的简单名称。

这有助于使创建和自定义表单的过程更加简便和高效。

### “允许使用的组件”选项卡 {#allowed-components-tab}

![“允许使用的组件”选项卡](/help/adaptive-forms/assets/tabs-allowed-component.png)

通过&#x200B;**允许使用的组件**&#x200B;选项卡，模板编辑器可设置组件，这些组件可作为项添加到自适应表单编辑器的向导组件中的面板。

### “样式”选项卡 {#styles-tab}

“设计”对话框用于定义和管理组件的 CSS 样式。自适应表单向导核心组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。

![“样式”选项卡](/help/adaptive-forms/assets/tabs-styles-tab.png)

- **默认 CSS 类**：可为自适应表单向导核心组件提供默认 CSS 类。

- **允许使用的样式**：可通过提供名称和表示样式的 CSS 类而定义样式。例如，您可以创建一个名为“bold text”的样式，并提供 CSS 类“font-weight: bold”。可使用这些样式或将其应用于自适应表单编辑器中的自适应表单。要应用样式，请在自适应表单编辑器中选择要将样式应用于的组件，导航到“属性”对话框，然后从&#x200B;**样式**&#x200B;下拉列表中选择所需的样式。如果您需要更新或修改样式，只需返回“设计”对话框，在“样式”选项卡中更新样式，然后保存更改。

### “自定义属性”选项卡

![“自定义属性”选项卡](/help/adaptive-forms/assets/tabs-custom-properties.png)

通过自定义属性，您可使用表单模板将自定义属性（键值对）关联到自适应表单核心组件。自定义属性反映在组件 Headless 演绎版的属性部分中。它可让您创建根据自定义属性值进行调整的动态表单行为。例如，开发人员可以为移动、桌面或 Web 平台设计 Headless 表单组件的各种演绎版，从而大大提升各种设备上的用户体验。

- **组名称**：您可以提供名称来标识自定义属性组。您可以添加、删除或重新排列多个自定义属性组。添加自定义属性组后，可看到以下选项：

   - **键值对**：您可以通过单击“**添加**”按钮，为每个自定义属性组添加多个自定义属性名称和自定义属性值。

   - **删除**：点按或单击此项可删除自定义属性名称和自定义属性值。

   - **重新排列**：点按或单击并拖动可重新排列自定义属性名称和自定义属性值的顺序。

## 相关文章 {#related-articles}

{{more-like-this}}

## 另请参阅 {#see-also}

{{see-also}}