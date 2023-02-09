---
title: 自适应表单折叠面板
description: 使用可折叠面板将长形式或复杂形式拆分为更小、更易于管理的部分，从而对其进行组织和简化。
role: Architect, Developer, Admin, User
source-git-commit: 945e1793ae4e959f83960db46d2de4257916fe32
workflow-type: tm+mt
source-wordcount: '1768'
ht-degree: 4%

---

# 折叠组件 {#accordion-component-adaptive-forms-core-component}

折叠面板核心组件允许用户在自适应表单中创建可展开和可折叠的部分。 它通常用于组织和简化长或复杂的表单，方法是将表单分解为更小、更易于管理的部分。 折叠面板的每个部分通常由一个标题表示，用户可单击该标题以展开或折叠相应的内容。 内容可以是任何核心组件。

## 用途 {#usage}

在自适应表单中包含折叠面板有益的原因包括以下几点：

* **节省空间**:折叠面板允许用户展开和折叠表单的部分，从而减少一次显示所有表单字段所需的空间量。

* **导航**:可折叠面板可用于创建分层导航结构，从而更便于用户查找所需的表单字段。

* **用户体验**:可折叠面板可以为用户提供一种清晰直观的方式来访问和填写表单字段，从而使表单更加用户友好。

* **龙Forms**:折叠面板是处理长表单的理想组件，因为它允许用户一次只关注一个部分，而不是尝试一次处理大量信息。

您可以使用：

* 的 [配置对话框](#configure-dialog) 以指定折叠组件的属性。

* 的 [选择面板弹出窗口](#select-panel-popover)  以定义折叠面板的顺序。 这允许作者按面板的显示顺序排列面板。

* 表单作者在 [设计对话框](#design-dialog). 例如，作者可以选择禁用表单的某些字段或部分。 通过这些选项，作者可以更好地控制表单的设计和功能，从而更轻松地创建符合组织特定需求的表单。

配置对话框、选择面板弹出窗口和设计对话框都是核心组件的一部分，这些核心组件旨在简化表单创作过程，并提供创建复杂表单的有效方式。

## 版本和兼容性 {#version-and-compatibility}


自适应Forms折叠核心组件作为核心组件2.0.4的一部分于2023年2月发布。此处有一个表格，其中显示了所有受支持的版本、AEM兼容性以及指向相应文档的链接：

|  |  |
|---|---|
| 组件版本 | AEM as a Cloud Service |
| --- | --- |
| v1 | 兼容 with<br>[版本2.0.4](/help/versions.md) 及更高版本 | 兼容 | 兼容 |

有关核心组件版本和版本的信息，请参阅 [核心组件版本](/help/versions.md) 文档。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技术详细信息 {#technical-details}

在 [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/accordion/v1/accordion). 有关开发核心组件的更多信息，请参阅 [核心组件开发人员文档](/help/developing/overview.md).

## “配置”对话框 {#configure-dialog}

您可以使用配置对话框轻松地为访客自定义折叠面板体验。 您还可以轻松定义折叠项目、面板、行为和外观，以实现无缝的用户体验。

### 基本选项卡 {#basic-tab}

![“基本”选项卡](/help/adaptive-forms/assets/accordion_basictab.png)

* **名称**  — 您可以在表单和规则编辑器中使用表单组件的唯一名称轻松识别表单组件，但名称不得包含空格或特殊字符。

* **标题**  — 通过其标题，您可以轻松地在表单中识别组件，默认情况下，标题会显示在组件顶部。 如果不添加标题，则会显示组件的名称，而不是标题文本。

* **隐藏标题**  — 选择用于隐藏组件标题的选项。

* **将数据包装在对象中**  — 选择“将数据嵌套在对象中”，将向导中的字段数据放在JSON对象中。 如果未选择，则提交数据JSON具有适用于向导字段的平面结构。

* **布局**  — 您可以具有固定布局（简单）或灵活的布局（响应式网格）来向导。 简单布局可将所有内容固定在原位置，而响应式网格则允许您调整组件的位置以满足您的需求。 例如，使用响应式网格在单行表单中对齐“名字”、“中间名”和“姓氏”。

* **绑定引用**  — 绑定引用是对存储在外部数据源中并在表单中使用的数据元素的引用。 绑定引用允许您将数据动态绑定到表单字段，以便表单可以显示来自数据源的最新数据。 例如，可以使用绑定引用根据在表单中输入的客户ID在表单中显示客户的名称和地址。 绑定引用还可用于使用输入到表单中的数据更新数据源。 通过这种方式，AEM Forms使您能够创建与外部数据源交互的表单，从而为数据收集和管理提供无缝的用户体验。
* **隐藏组件**  — 选择选项以在表单中隐藏组件。 该组件仍可用于其他目的，例如在规则编辑器中将其用于计算。 当您需要存储用户无需查看或直接更改的信息时，此功能非常有用。
* **禁用组件**  — 选择选项以禁用组件。 禁用的组件不处于活动状态或最终用户无法编辑。 用户可以查看字段的值，但无法对其进行修改。 该组件仍可用于其他目的，例如在规则编辑器中将其用于计算。

### “项”选项卡 {#items-tab}

![“项目”选项卡](/help/adaptive-forms/assets/accordion_itemstab.png)

通过添加按钮，您可以从组件选择窗口中选择要添加为面板的组件。 添加组件后，您可以看到以下选项：

* **图标**  — 该图标标识列表中面板的组件。 您可以将鼠标悬停在图标上，以查看完整的组件名称作为工具提示。
* **描述**  — 用作面板文本的描述。 默认情况下，会为面板选择组件的名称。
* **删除** - 点击或单击可从折叠组件中删除面板。
* **重新排列** - 点击或单击并拖动以重新排列面板。

### 帮助内容选项卡 {#help-content}

![帮助内容选项卡](/help/adaptive-forms/assets/accordion_helpcontent.png)

* **简短描述**  — 简短的描述是一个简短的文本说明，提供有关特定表单字段用途的其他信息或说明。 它有助于用户了解应在字段中输入哪种类型的数据，并且可以提供准则或示例，以帮助确保输入的信息有效并满足所需标准。 默认情况下，短描述仍保持隐藏状态。 启用 **始终显示简短描述** 选项来将其显示在组件下方。

* **始终显示简短描述**  — 启用选项，以在组件下方显示简短说明。

* **帮助文本**  — 帮助文本是指提供给用户的其他信息或指导，以帮助用户正确填写表单字段。 当用户单击位于组件旁边的帮助图标(i)时，会显示该图标。 帮助文本提供比表单字段的标签或占位符文本更详细的信息，旨在帮助用户了解该字段的要求或限制。 它还可以提供建议或示例，以便更轻松、更准确地填写表单。

### “辅助功能”选项卡 {#accessibility}

![“辅助功能”选项卡](/help/adaptive-forms/assets/accordion_accessibility.png)

在 **辅助功能** 选项卡，为 [ARIA辅助功能](https://www.w3.org/WAI/standards-guidelines/aria/) 组件的标签。 可使用屏幕阅读器的文本选项有多种：

* **屏幕阅读器的文本**  — 屏幕阅读器的文本是指专门用于由视觉障碍个人使用的屏幕阅读器等辅助技术阅读的其他文本。 此文本提供表单字段用途的音频描述，并可包含有关字段标题、描述、名称和任何相关消息的信息（自定义文本）。 屏幕阅读器文本有助于确保所有用户（包括患有视觉障碍的用户）都可以访问表单，并为他们提供对表单字段及其要求的完整了解。


   * **自定义文本**:选择此选项可将自定义文本用于ARIA辅助功能标签。 选择此选项将显示“自定义文本”对话框。 您可以在“自定义文本”(Custom Text)对话框中添加相关信息。
   * **描述**:选择此选项可使用ARIA辅助功能标签的描述。
   * **标题**:选择此选项可使用ARIA辅助功能标签的标题。
   * **名称**:选择此选项可使用ARIA辅助功能标签的名称。
   * **无**:如果不想为ARIA辅助功能标签添加，请选择此选项。

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

“设计”(Design)对话框允许模板创建者控制默认情况下的显示方式。 对于自适应Forms折叠面板组件，您可以设置以下内容：

* 允许并设置为默认值的HTML标题元素类型（如H1、H2、H3等）
* 表单创建者可以添加到自适应Forms编辑器中折叠面板的核心组件
* 样式（CSS类）的简单名称，可在自适应Forms编辑器的折叠组件的属性对话框中应用。

这有助于使创建和自定义表单的过程更加简单和高效。

### “属性”选项卡 {#properties-tab-design}

“属性”选项卡允许模板作者为表单作者设置默认和允许的HTML标题元素：

![“设计”对话框“属性”选项卡](/help/assets/accordion-design-properties.png)

* **允许的标题元素**:一个包含多个选项的下拉列表，允许模板作者选择表单作者可以用于折叠面板的标题元素。

* **默认标题元素**:下拉列表可为折叠面板组件设置默认的标题元素。

### “允许的组件”选项卡 {#allowed-components-tab}

的 **允许的组件** 选项卡允许模板编辑器设置可作为项目添加到自适应Forms编辑器中折叠面板组件中的面板的组件。

### 样式选项卡 {#styles-tab}

“设计”对话框用于定义和管理组件的CSS样式。 自适应Forms折叠面板核心组件支持AEM [样式系统](/help/get-started/authoring.md#component-styling).

**默认CSS类**:您可以为折叠面板组件提供默认的CSS类。

**允许的样式**:您可以通过提供名称和表示样式的CSS类来定义样式。 例如，您可以创建名为“粗体文本”的样式，并提供CSS类“font-weight:粗体”。 您可以在自适应Forms编辑器中将这些样式用于自适应表单或将其应用于自适应表单。 要应用样式，请在自适应Forms编辑器中，选择要应用该样式的组件，导航到属性对话框，然后从 **样式** 下拉列表。 如果需要更新或修改样式，只需返回到“设计”对话框，更新“样式”选项卡中的样式，然后保存更改即可。


<!-- 

The design dialog allows the template author to define the options available to the content author who uses the Accordion Component and the defaults set when placing the Accordion Component.


### Properties Tab {#properties-tab-design}

![Design dialog properties tab](/help/assets/accordion-design-properties.png)

* **Allowed Heading Elements** - This multi-select drop-down defines the accordion item heading HTML elements that are allowed to be selected by an author.
* **Default Heading Element** - This drop-down defines the default accordion item heading HTML element.

### Allowed Components Tab {#allowed-components-tab}

The **Allowed Components** tab is used to define which components can be added as items to panels in the Accordion Component by the content author.

The Allowed Components tab functions in the same way as the tab of the same name when [defining the policy and properties of a Layout Container in the Template Editor.](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html#editing-a-template-layout-template-author)

### Styles Tab {#styles-tab}

The Accordion Component supports the AEM [Style System](/help/get-started/authoring.md#component-styling).

## Adobe Client Data Layer {#data-layer}

The Accordion Component supports the [Adobe Client Data Layer.](/help/developing/data-layer/overview.md)

-->




