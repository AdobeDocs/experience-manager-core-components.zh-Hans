---
title: 自适应表单核心组件 - 面板容器
description: 使用或自定义自适应表单面板容器核心组件。
role: Architect, Developer, Admin, User
exl-id: 104836fe-8325-47de-978d-1ff2d6a9dd15
source-git-commit: 4c510b8fe59f4be6e1b329ee4257ab1b780fbf22
workflow-type: tm+mt
source-wordcount: '2225'
ht-degree: 98%

---

# 面板组件{#panel-container-adaptive-forms-core-component}

在自适应表单中，面板是一个容器元素，可用于将相关表单元素组合在一起。它可让您以一种符合逻辑且有意义的方式对不同的表单元素进行分组和整理。这有助于改善表单的整体结构和可读性，使用户能够更轻松地理解和导航。

面板也可用于创建可可折叠项部分，这对于隐藏复杂或不常用的表单字段来说很有用，可以使表单简单易用。它还可让您包含其他组件，如文本、复选框、按钮等。

它还可用于设置各种基于规则的操作，如提交表单、打开网站、显示/隐藏组件或添加面板实例。

**示例**

![示例](/help/adaptive-forms/assets/panel-container.png)

## 用途 {#reasons-to-use-panel-container}

有若干原因要在表单中使用面板，这些原因包括：

- **整理表单元素**：面板可用于将相关的表单元素组合起来，使用户能够更轻松地理解和浏览表单。

- **改善表单结构**：通过将表单元素分组到面板中，可以改善表单的整体结构和可读性，使其更易于理解。

- **创建可可折叠项部分**：面板可用于创建可可折叠项部分，这对于隐藏复杂或不常用的表单字段来说很有用，可以使表单简单易用。

- **增强可用性**：通过使用面板整理表单元素，可使得表单变得更方便用户使用，从而提高完成率。

## 版本和兼容性 {#version-and-compatibility}

2023 年 2 月，作为核心组件 2.0.4 的一部分发布了自适应表单面板容器核心组件。下表展示所有支持的版本、AEM 兼容性和相应文档的链接：

|  |  |
|---|---|
| 组件版本 | AEM as a Cloud Service |
| --- | --- |
| v1 | 与<br>[版本 2.0.4](/help/adaptive-forms/version.md) 和更高版本兼容 | 兼容 | 兼容 |

有关核心组件版本的信息，请参阅[核心组件版本](/help/adaptive-forms/version.md)文档。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技术详细信息 {#technical-details}

可在 [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/panelcontainer/v1/panelcontainer) 上的技术文档中获得关于自适应表单面板容器核心组件的最新信息。有关开发核心组件的更多信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## “配置”对话框 {#configure-dialog}

通过“配置”对话框，可轻松地自定义您为访客提供的面板容器体验。还可轻松地定义面板容器选项，从而营造一种无缝的用户体验。

### “基本”选项卡 {#basic-tab}

![“基本”选项卡](/help/adaptive-forms/assets/basic-panel.png)

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

- **绑定引用** - 绑定引用是对存储在外部数据源中并在表单中使用的数据元素的引用。通过绑定引用，可动态地将数据绑定到表单字段，以使表单可显示来自数据源的最新数据。例如，可使用绑定引用，根据输入到表单中的客户 ID，在该表单中显示该客户的姓名和地址。还可使用绑定引用，通过输入到表单中的数据更新数据源。这样通过 AEM Forms 即可创建与外部数据源交互的表单，从而为收集和管理数据提供一种无缝的用户体验。
- **隐藏组件** - 选中此选项以从表单中隐藏该组件。仍可访问该组件作其他用途，如在规则编辑器中使用它进行计算。当需要存储用户无需看到或直接更改的信息时，此项很有用。
- **禁用组件** - 选中此选项以禁用该组件。被禁用的组件不再活跃或最终用户无法编辑它。用户可看到但无法修改字段的值。仍可访问该组件作其他用途，如在规则编辑器中使用它进行计算。
- **只读** - 选中此选项以使组件不可编辑。用户可看到但无法修改字段的值。仍可访问该组件作其他用途，如在规则编辑器中使用它进行计算。

### 重复面板选项卡 {#repeat-panel}

![重复选项卡](/help/adaptive-forms/assets/repeat-panel.png)

您可以使用重复选项来复制面板容器及其子组件，定义最小和最大重复计数，并促进在表单内复制类似部分。当与面板容器组件交互并访问其设置时，会出现以下选项：

- **使面板可重复**：切换功能，允许用户启用或禁用重复功能。
- **最少重复次数**：确定面板容器可以重复的最小次数。值为零表示向导面板不重复；默认值为零。
- **最多重复次数**：设置面板容器可以重复的最多次数。默认情况下，此值无限制。

要有效管理面板容器中的可重复部分，请按照[创建具有可重复部分的表单](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/create-forms-repeatable-sections.html)文章。

### “帮助内容”选项卡 {#help-content}

![“帮助内容”选项卡](/help/adaptive-forms/assets/helpcontent-panel.png)

- **简短描述** - 简短描述是一段简短的文字说明，其中提供关于特定表单字段的用途的其他信息或阐述。它帮助用户了解应将什么类型的数据输入到字段中，并可提供准则或示例以帮助确保所输入的信息有效且符合预期的标准。默认情况下，简短描述保持隐藏状态。启用&#x200B;**始终显示简短描述**&#x200B;选项以在组件下方显示它。

- **始终显示简短描述** - 启用该选项以在组件下方显示简短描述。

- **帮助文本** - 帮助文本是指提供给用户以帮助其正确填写表单字段的其他信息或指导。当用户单击组件旁的“帮助”图标 (i) 时显示它。帮助文本提供比表单字段的标签或占位符文本更详细的信息，旨在帮助用户了解该字段的要求或限制。它还可提供建议或示例，以使填写表单更轻松且更准确。

### “辅助功能”选项卡 {#accessibility}

![“辅助功能”选项卡](/help/adaptive-forms/assets/accessibilty-panel.png)


- **屏幕阅读器文本** - 屏幕阅读器文本是指专供由视障人士使用的屏幕阅读器等辅助技术读取的附加文本。此文本提供表单字段用途的音频描述，并可包括关于字段的标题、描述、名称和任何相关消息（自定义文本）的信息。屏幕阅读器文本帮助确保包括视障用户在内的所有用户均可访问表单，并使其完整地了解表单字段及其要求。
   - **自定义文本**：选中此选项以将自定义文本用于 ARIA 辅助功能标签。选中此选项将显示“自定义文本”对话框。可在“自定义文本”对话框中添加相关信息。
   - **描述**：选中此选项以将描述用于 ARIA 辅助功能标签。
   - **标题**：选中此选项以将标题用于 ARIA 辅助功能标签。
   - **名称**：选中此选项以将名称用于 ARIA 辅助功能标签。
   - **无**：如果不想为 ARIA 辅助功能标签添加任何内容，请选中此选项。

- **用于读出内容的屏幕阅读器的 HTML 角色** - HTML 角色是一个属性，用于向屏幕阅读器等辅助技术指定 HTML 元素的用途。角色属性用于为元素提供额外的上下文和语义，使屏幕阅读器更容易向用户解释和读出内容。例如，在 AEM Forms 中，表单字段的标签可能具有“标签”的作用，其输入字段可能具有“文本框”的作用。这有助于屏幕阅读器理解标签和输入字段之间的关系，并正确地向用户读出内容。

## “设计”对话框 {#design-dialog}

“设计”对话框用于定义和管理面板组件的CSS样式。

### “允许使用的组件”选项卡 {#allowed-components-tab}

![“设计”对话框允许使用的组件选项卡](/help/adaptive-forms/assets/panel-container-allowed-component.png)

此 **允许的组件** 选项卡允许模板编辑器设置组件，这些组件可以在自适应Forms编辑器中作为项添加到组件中的面板。

### “默认组件”选项卡 {#default-components-tab}

![“设计”对话框默认组件选项卡](/help/adaptive-forms/assets/panel-container-default-component.png)

通过&#x200B;**默认组件**&#x200B;选项卡，模板编辑器可指定默认情况下作为项显示在自适应表单编辑器中的表单容器组件中的组件。

### “响应式设置”选项卡 {#responsive-tab}

![“设计”对话框响应式设置选项卡](/help/adaptive-forms/assets/panel-container-responsive-style-tab.png)

通过&#x200B;**响应式设置**&#x200B;选项卡，模板编辑器可指定自适应表单编辑器中的表单容器组件内的网格列数。

### “容器设置”选项卡

![“容器设置”选项卡](/help/adaptive-forms/assets/panel-container-container-settings.png)

- **布局** - 可为向导采用固定布局（“简单”）或灵活布局（“响应式网格”）。“简单”布局将所有内容固定在原位，而通过“响应式网格”，可调整组件的位置以满足您的需要。例如，使用响应式网格将表单中的“名字”、“中间名”和“姓氏”排成一行。

- **禁用布局**：选中此选项可禁用组件编辑对话框中的布局选择。

- **启用背景图像**：利用此选项，用户可以配置面板设置以包括可视化背景来增大视觉吸引力。

- **启用背景颜色**：利用此选项，您可以设置或更改面板的背景颜色。此功能通常在用户界面设计中用于自定义较大界面中的面板外观。在选中&#x200B;**启用背景颜色**&#x200B;选项时，将显示&#x200B;**仅色板**&#x200B;选项。利用&#x200B;**仅色板**&#x200B;选项，可使用&#x200B;**添加**&#x200B;按钮来指定或选择面板内的背景、文本或其他可视元素的颜色

### “样式”选项卡 {#styles-tab}

自适应表单文件附件核心组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。

![“设计”对话框](/help/adaptive-forms/assets/panel-container-styles-tab.png)

- **默认 CSS 类**：可为自适应表单面板容器核心组件提供默认 CSS 类。

- **允许使用的样式**：可通过提供名称和表示样式的 CSS 类而定义样式。例如，您可以创建一个名为“bold text”的样式，并提供 CSS 类“font-weight: bold”。可使用这些样式或将其应用于自适应表单编辑器中的自适应表单。要应用样式，请在自适应表单编辑器中选择要将样式应用于的组件，导航到“属性”对话框，然后从&#x200B;**样式**&#x200B;下拉列表中选择所需的样式。如果您需要更新或修改样式，只需返回“设计”对话框，在“样式”选项卡中更新样式，然后保存更改。

### “自定义属性”选项卡

![“自定义属性”对话框](/help/adaptive-forms/assets/panel-container-custom-properties.png)

通过自定义属性，您可使用表单模板将自定义属性（键值对）关联到自适应表单核心组件。自定义属性反映在组件 Headless 演绎版的属性部分中。它可让您创建根据自定义属性值进行调整的动态表单行为。例如，开发人员可以为移动、桌面或 Web 平台设计 Headless 表单组件的各种演绎版，从而大大提升各种设备上的用户体验。

- **组名称**：您可以提供名称来标识自定义属性组。您可以添加、删除或重新排列多个自定义属性组。添加自定义属性组后，可看到以下选项：

   - **键值对**：您可以通过单击“**添加**”按钮，为每个自定义属性组添加多个自定义属性名称和自定义属性值。

   - **删除**：点按或单击此项可删除自定义属性名称和自定义属性值。

   - **重新排列**：点按或单击并拖动可重新排列自定义属性名称和自定义属性值的顺序。

<!--

## Related article {#related-article}

* [Create a standalone Adaptive Form](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html)

-->

## 相关文章 {#related-articles}

{{more-like-this}}

## 另请参阅 {#see-also}

{{see-also}}