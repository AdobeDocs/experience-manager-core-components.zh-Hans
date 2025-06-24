---
title: 自适应表单可折叠项面板
description: 使用可折叠项面板组件通过将表单拆分为更小、更易于管理的部分，从而整理和简化较长或复杂的表单。
role: Architect, Developer, Admin, User
exl-id: 0ed38eee-fc22-4708-82eb-3fb1839b1ff2
source-git-commit: 6725784bd4c94d433c91d6bd65d14d03cbefd954
workflow-type: tm+mt
source-wordcount: '2237'
ht-degree: 100%

---


# 可折叠项面板组件 {#accordion-component-adaptive-forms-core-component}

利用可折叠项面板核心组件，用户可在自适应表单中创建可展开和可可折叠项的部分。它一般用于通过将表单拆分为更小、更易于管理的部分，从而整理和简化较长或复杂的表单。一般通过标题表示可折叠项面板的每个部分，用户单击标题即可展开或可折叠项相应的内容。该内容可为任意核心组件。

![示例](/help/adaptive-forms/assets/example-accordion.png)

{{traditional-aem}}

## 用途 {#usage}

有若干原因使得在自适应表单中加入可折叠项面板组件有益，这些原因包括：

- **节省空间**：通过可折叠项面板组件，用户可展开和可折叠项表单的各部分，从而减少同时显示所有表单字段所需的空间量。

- **导航**：可使用可折叠项面板组件创建一个分层的导航结构，使得用户更容易找到所需的表单字段。

- **用户体验**：可使用可折叠项面板组件为用户提供一种清晰而直观的方式以访问和填写表单字段，使得表单更方便用户使用。

- **长表单**：可折叠项面板是一个处理长表单的理想组件，因为它使用户可集中精力一次处理一个部分，而非尝试同时处理大量信息。

您可以使用：

- [“配置”对话框](#configure-dialog)指定可折叠项面板组件的属性。

- [“选择面板”弹出框](#select-panel-popover)定义可折叠项面板组件中各个面板的顺序。这样，作者即可将面板排列为其应出现的顺序。

- [“设计”对话框](#design-dialog)中的选项以使表单作者启用或禁用某些功能。例如，作者可以选择禁用表单的某些字段或部分。通过这些选项，作者可更精确地控制表单的设计和功能，从而更轻松地创建为组织的特定需求量身定制的表单。

“配置”对话框、“选择面板”弹出框和“设计”对话框都是核心组件的一部分，它们旨在简化表单创作，并提供一种创建复杂表单的高效方法。

## 版本和兼容性 {#version-and-compatibility}


2023 年 2 月，作为核心组件 2.0.4 的一部分发布了自适应表单可折叠项面板核心组件。下表展示所有支持的版本、AEM 兼容性和相应文档的链接：

|  |  |
|---|---|
| 组件版本 | AEM as a Cloud Service |
| --- | --- |
| v1 | 与<br>[版本 2.0.4](/help/adaptive-forms/version.md) 和更高版本兼容 | 兼容 | 兼容 |

有关核心组件版本的信息，请参阅[核心组件版本](/help/adaptive-forms/version.md)文档。


<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion_cn). -->

## 技术详细信息 {#technical-details}

可在 [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/accordion/v1/accordion) 上的技术文档中获得关于可折叠项面板组件的最新信息。有关开发核心组件的更多信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## “配置”对话框 {#configure-dialog}

通过“配置”对话框，可轻松地自定义您为访客提供的可折叠项面板体验。还可轻松地定义可折叠项面板项、面板、行为和外观，从而营造一种无缝的用户体验。

### “基本”选项卡 {#basic-tab}

![“基本”选项卡](/help/adaptive-forms/assets/acc-basic.png)

- **名称** - 可在表单和规则编辑器中通过唯一名称轻松地标识表单组件，但该名称不得包含空格或特殊字符。

- **标题** - 通过组件的标题，可轻松地标识表单中的组件，默认情况下，标题显示在该组件的顶部。如果不添加标题，则显示该组件的名称而非标题文本。

- **允许标题为富文本**：此功能使用户能够格式化纯文本标题，结合粗体、斜体、下划线文本、各种字体、字体大小、颜色和附加选项等功能，以增强视觉呈现和定制效果。它提供了更大的灵活性以及对创作的控制度，使标题在文档、网站或应用程序中脱颖而出。\
  选中&#x200B;**允许标题为富文本**&#x200B;复选框后，可以看到格式化选项，用于设置组件标题的样式。要访问所有可用的格式选项，您可以点击![全屏图标](/help/adaptive-forms/assets/fullscreen-icon.png)选项卡。

  ![富文本支持](/help/adaptive-forms/assets/richtext-support-title.png)

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

<!--  **Layout** - You can have either a fixed layout (Simple) or a flexible layout (Responsive Grid) for your wizard. The Simple layout keeps everything fixed in the place, while the Responsive Grid allows you to adjust the position of components to suit your needs. For example, use Responsive Grid to align "First Name", "Middle Name" and "Last Name" in a form in a single row. -->

- **绑定引用** - 绑定引用是对存储在外部数据源中并在表单中使用的数据元素的引用。通过绑定引用，可动态地将数据绑定到表单字段，以使表单可显示来自数据源的最新数据。例如，可使用绑定引用，根据输入到表单中的客户 ID，在该表单中显示该客户的姓名和地址。还可使用绑定引用，通过输入到表单中的数据更新数据源。这样通过 AEM Forms 即可创建与外部数据源交互的表单，从而为收集和管理数据提供一种无缝的用户体验。

- **隐藏组件** - 选中此选项以从表单中隐藏该组件。仍可访问该组件作其他用途，如在规则编辑器中使用它进行计算。当需要存储用户无需看到或直接更改的信息时，此项很有用。

- **禁用组件** - 选中此选项以禁用该组件。被禁用的组件不再活跃或最终用户无法编辑它。用户可看到但无法修改字段的值。仍可访问该组件作其他用途，如在规则编辑器中使用它进行计算。

- **只读** - 选中此选项以使组件不可编辑。用户可看到但无法修改字段的值。仍可访问该组件作其他用途，如在规则编辑器中使用它进行计算。

### 重复可折叠项 {#repeat-accordion}

![重复可折叠项](/help/adaptive-forms/assets/repeat-accordion.png)

您可以使用重复选项来复制可折叠项面板及其子组件，定义最小和最大重复计数，并促进在表单内复制类似部分。当与可折叠项组件交互并访问其设置时，会出现以下选项：

- **使可折叠项可重复**：切换功能，允许用户启用或禁用重复功能。
- **最少重复次数**：确定可折叠项面板可以重复的最小次数。值为零表示可折叠项面板不重复；默认值为零。
- **最多重复次数**：设置可折叠项面板可以重复的最多次数。默认情况下，此值无限制。

要有效管理可折叠项中的可重复部分，请按照[创建具有可重复部分的表单](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/create-forms-repeatable-sections.html?lang=zh-Hans)文章。

### “项”选项卡 {#items-tab}

![“项”选项卡](/help/adaptive-forms/assets/acc-items.png)

通过“添加”按钮，可从组件选择窗口中选择要作为面板添加的组件。添加该组件后，可看到以下选项：

- **图标** - 图标在列表中标识面板的组件。将光标悬停在图标上，即可看到作为工具提示的完整组件名称。
- **描述** - 用作面板文本的描述。默认情况下，为面板选择该组件的名称。
- **删除** - 点按或单击可从可折叠项组件中删除面板。
- **重新排列** - 点击或单击并拖动以重新排列面板的顺序。

### “帮助内容”选项卡 {#help-content}

![“帮助内容”选项卡](/help/adaptive-forms/assets/acc-helpcontent.png)

- **简短描述** - 简短描述是一段简短的文字说明，其中提供关于特定表单字段的用途的其他信息或阐述。它帮助用户了解应将什么类型的数据输入到字段中，并可提供准则或示例以帮助确保所输入的信息有效且符合预期的标准。默认情况下，简短描述保持隐藏状态。启用&#x200B;**始终显示简短描述**&#x200B;选项以在组件下方显示它。

- **始终显示简短描述** - 启用该选项以在组件下方显示简短描述。

- **帮助文本** - 帮助文本是指提供给用户以帮助其正确填写表单字段的其他信息或指导。当用户单击组件旁的“帮助”图标 (i) 时显示它。帮助文本提供比表单字段的标签或占位符文本更详细的信息，旨在帮助用户了解该字段的要求或限制。它还可提供建议或示例，以使填写表单更轻松且更准确。

### “辅助功能”选项卡 {#accessibility}

![“辅助功能”选项卡](/help/adaptive-forms/assets/acc-accessisbilty.png)

在&#x200B;**辅助功能**&#x200B;选项卡上，为组件的 [ARIA 辅助功能](https://www.w3.org/WAI/standards-guidelines/aria/)标签设置值。使用屏幕阅读器文本时有多个选项：

- **屏幕阅读器文本** - 屏幕阅读器文本是指专供由视障人士使用的屏幕阅读器等辅助技术读取的附加文本。此文本提供表单字段用途的音频描述，并可包括关于字段的标题、描述、名称和任何相关消息（自定义文本）的信息。屏幕阅读器文本帮助确保包括视障用户在内的所有用户均可访问表单，并使其完整地了解表单字段及其要求。

   - **自定义文本**：选中此选项以将自定义文本用于 ARIA 辅助功能标签。选中此选项将显示“自定义文本”对话框。可在“自定义文本”对话框中添加相关信息。
   - **描述**：选中此选项以将描述用于 ARIA 辅助功能标签。
   - **标题**：选中此选项以将标题用于 ARIA 辅助功能标签。
   - **名称**：选中此选项以将名称用于 ARIA 辅助功能标签。
   - **无**：如果不想为 ARIA 辅助功能标签添加任何内容，请选中此选项。

<!--

### Properties Tab {#properties-tab}

![Properties tab of the edit dialog of the Accordion Component](/help/assets/accordion-edit-properties.png)

*   **Single item expansion** - When selected, this option forces a single accordion item to be expanded at a time. Expanding one item will then collapse all others.
*   **Expanded items** - This option defines the items that are expanded by default when the page is loaded.
    * When **Single item expansion** is selected, one panel must be selected. By default the first panel is selected.
    * When **Single item expansion** is not selected, this option is a multi-select and is optional.
*   **ID** - This option allows to control the unique identifier of the component in the HTML and in the [Data Layer](/help/developing/data-layer/overview.md).
    * If left blank, a unique ID is automatically generated for you and can be found by inspecting the resulting page.
    * If an ID is specified, it is the responsibility of the author to make sure that it is unique.
    * Changing the ID can have an impact on CSS, JS and Data Layer tracking.

## Select Panel Popover {#select-panel-popover}

The **Select Panel** option (![Select panel icon](/help/assets/select-panel-icon.png)) on the component toolbar enables content authors to modify the panels in an accordion with ease. By selecting this option, the author can switch to a different panel for editing and rearrange the order of the panels in the accordion. The configured panels will be displayed in a drop-down menu for the author to choose from. This feature optimizes the editing process and makes it user-friendly for content authors.

![Select panel popover](/help/assets/select-panel-popover.png)


* The panels are displayed in a numbered list, reflecting the assigned arrangement.
* Each panel is listed with its component type in bold, followed by a brief description in lighter font.
* By clicking or tapping on a panel in the drop-down, you can easily switch the view in the editor to that specific panel.
* To rearrange the panels, simply use the drag handles to move them into the desired order. -->

## “设计”对话框 {#design-dialog}

通过“设计”对话框，模板创建者可控制在默认情况下如何显示各种内容。对于自适应表单可折叠项面板组件，可设置以下各项：

- 允许使用并设置为默认值的 HTML 标题元素的类型（如 H1、H2、H3 等）
- 表单创建者可添加到自适应表单编辑器中的可折叠项面板的核心组件
- 可在自适应表单编辑器的可折叠项面板组件的“属性”对话框中应用的样式（CSS 类）的简单名称。

这有助于使创建和自定义表单的过程更加简便和高效。

### “属性”选项卡 {#properties-tab-design}

通过“属性”选项卡，模板作者可为表单作者设置默认和允许使用的 HTML 标题元素：

![“设计”对话框“属性”选项卡](/help//adaptive-forms/assets/accordion-design-properties.png)

- **允许使用的标题元素**：一个下拉列表，其中含有多个选项，通过它，模板作者可选择表单作者可将哪些标题元素用于可折叠项面板组件。

- **默认标题元素** - 一个下拉列表，它设置可折叠项面板组件的默认标题元素。

### “允许使用的组件”选项卡 {#allowed-components-tab}

![“设计”对话框允许使用的组件选项卡](/help//adaptive-forms/assets/accordion-allowed-components.png)

通过&#x200B;**允许使用的组件**&#x200B;选项卡，模板编辑者可设置可作为项添加到自适应表单编辑器的可折叠项面板组件中的面板的组件。

### “样式”选项卡 {#styles-tab}

![“设计”对话框样式选项卡](/help/adaptive-forms/assets/accordion-styles-tab.png)

“设计”对话框用于定义和管理组件的 CSS 样式。自适应表单可折叠项面板核心组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。

- **默认 CSS 类**：可为可折叠项面板组件提供默认 CSS 类。

- **允许使用的样式**：可通过提供名称和表示样式的 CSS 类而定义样式。例如，您可以创建一个名为“bold text”的样式，并提供 CSS 类“font-weight: bold”。可使用这些样式或将其应用于自适应表单编辑器中的自适应表单。要应用样式，请在自适应表单编辑器中选择要将样式应用于的组件，导航到“属性”对话框，然后从&#x200B;**样式**&#x200B;下拉列表中选择所需的样式。如果您需要更新或修改样式，只需返回“设计”对话框，在“样式”选项卡中更新样式，然后保存更改。

### 自定义属性

![accordion-custom-properties-tab](/help/adaptive-forms/assets/accordion-custom-properties-tab.png)
通过自定义属性，您可使用表单模板将自定义属性（键值对）关联到自适应表单核心组件。自定义属性反映在组件 Headless 演绎版的属性部分中。它可让您创建根据自定义属性值进行调整的动态表单行为。例如，开发人员可以为移动、桌面或 Web 平台设计 Headless 表单组件的各种演绎版，从而大大提升各种设备上的用户体验。

- **组名称**：您可以提供名称来标识自定义属性组。您可以添加、删除或重新排列多个自定义属性组。添加自定义属性组后，可看到以下选项：

   - **键值对**：您可以通过单击“**添加**”按钮，为每个自定义属性组添加多个自定义属性名称和自定义属性值。

   - **删除**：点按或单击此项可删除自定义属性名称和自定义属性值。

   - **重新排列**：点按或单击并拖动可重新排列自定义属性名称和自定义属性值的顺序。

## 相关文章 {#related-articles}

{{more-like-this}}

## 另请参阅 {#see-also}

{{see-also}}