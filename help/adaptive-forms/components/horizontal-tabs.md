---
title: 自适应表单核心组件 - 水平选项卡
description: 使用或自定义自适应表单水平选项卡核心组件。
role: Architect, Developer, Admin, User
exl-id: fbdf330b-3b85-4f94-9dab-eea8465fba67
source-git-commit: 7888cfa0f1358ce8018fc1e3cc3b19eb66a82b9d
workflow-type: tm+mt
source-wordcount: '1769'
ht-degree: 98%

---

# 水平选项卡 {#horizontal-tabs-adaptive-forms-core-component}

自适应表单中的水平选项卡是指一种设计模式，其中表单的多个部分组合在一起并显示为水平对齐的单独选项卡。用户可以在各个选项卡之间切换来访问表单的不同部分。每个选项卡均充当显示和隐藏相关表单内容的触发器。水平选项卡可帮助将较长的表单整理成可管理的部分并改善用户体验。选项卡使残障用户能够更轻松地访问表单，因为他们可以使用键盘导航在各个部分之间切换。

选项卡通常作为一系列链接或按钮创建，每个链接或按钮均对应表单的一个部分。当用户单击选项卡时，表单内容会动态更新以显示相应部分。

## 用途 {#reasons-to-use-horizontal-tabs}

在自适应表单中使用水平选项卡的常见原因是：

* **改进了可用性**：水平选项卡使用户能够更轻松地浏览表单，尤其是在表单具有多个部分或大量字段时。

* **空间管理**：水平选项卡可将相关的表单部分分组到选项卡中，并一次只显示一个部分，从而帮助节省屏幕空间。

* **更好的组织结构**：选项卡为表单提供了清晰有序的组织结构，使用户更容易理解和填写表单。

* **提高了用户参与度**：水平选项卡可以使表单具有更吸引人的外观并吸引用户，从而提高表单完成率。

## 版本和兼容性 {#version-and-compatibility}

2023 年 2 月，作为核心组件 2.0.4 的一部分发布了自适应表单水平选项卡核心组件。下表展示所有支持的版本、AEM 兼容性和相应文档的链接：

|  |  |
|---|---|
| 组件版本 | AEM as a Cloud Service |
| --- | --- |
| v1 | 兼容<br>[版本 2.0.4](/help/versions.md) 和更高版本 | 兼容 | 兼容 |

有关核心组件版本的信息，请参阅[核心组件版本](/help/versions.md)文档。


<!-- ## Sample Component Output {#sample-component-output}

To experience the Horizontal-tabs  Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_Horizontal-tabs ). -->


## 技术详细信息 {#technical-details}

可在 [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/pageHorizontal tabs/v1/pageHorizontal tabs) 上的技术文档中获得关于自适应表单水平选项卡核心组件的最新信息。有关开发核心组件的更多信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## “配置”对话框 {#configure-dialog}

通过“配置”对话框，可轻松地自定义您为访客提供的水平选项卡体验。还可轻松地定义水平选项卡选项，从而营造一种无缝的用户体验。

### “基本”选项卡 {#basic-tab}

![“基本”选项卡](/help/adaptive-forms/assets/tabs-on-top-basic.png)

* **名称** - 可在表单和规则编辑器中通过唯一名称轻松地标识表单组件，但该名称不得包含空格或特殊字符。

* **标题** - 通过组件的标题，可轻松地标识表单中的组件，默认情况下，标题显示在该组件的顶部。如果不添加标题，则显示该组件的名称而非标题文本。

* **隐藏标题** - 选中此选项以隐藏该组件的标题。

* **将数据包装到对象中** - 选中“将数据包装到对象中”以将向导中的字段数据放入 JSON 对象。如果不选中此项，则提交数据 JSON 对于向导的字段采用扁平结构。

* **布局** - 可为向导采用固定布局（“简单”）或灵活布局（“响应式网格”）。“简单”布局将所有内容固定在原位，而通过“响应式网格”，可调整组件的位置以满足您的需要。例如，使用响应式网格将表单中的“名字”、“中间名”和“姓氏”排成一行。

* **绑定引用** - 绑定引用是对存储在外部数据源中并在表单中使用的数据元素的引用。通过绑定引用，可动态地将数据绑定到表单字段，以使表单可显示来自数据源的最新数据。例如，可使用绑定引用，根据输入到表单中的客户 ID，在该表单中显示该客户的姓名和地址。还可使用绑定引用，通过输入到表单中的数据更新数据源。这样通过 AEM Forms 即可创建与外部数据源交互的表单，从而为收集和管理数据提供一种无缝的用户体验。
* **隐藏组件** - 选中此选项以从表单中隐藏该组件。仍可访问该组件作其他用途，如在规则编辑器中使用它进行计算。当需要存储用户无需看到或直接更改的信息时，此项很有用。
* **禁用组件** - 选中此选项以禁用该组件。被禁用的组件不再活跃或最终用户无法编辑它。用户可看到但无法修改字段的值。仍可访问该组件作其他用途，如在规则编辑器中使用它进行计算。

### 重复顶部选项卡 {#repeat-tabs-on-top}

![“辅助功能”选项卡](/help/adaptive-forms/assets/repeat-tabsontop.png)

您可以使用重复选项来复制“水平”选项卡组件及其子组件，定义最小和最大重复计数，并促进在表单内复制类似部分。当与“水平”选项卡组件交互并访问其设置时，会出现以下选项：

* **使“水平”选项卡可重复**：切换功能，允许用户启用或禁用重复功能。
* **最少重复次数**：确定“水平”选项卡组件面板可以重复的最小次数。值为零表示“水平”选项卡组件不重复；默认值为零。
* **最多重复次数**：设置“水平”选项卡组件面板可以重复的最大次数。默认情况下，此值无限制。

要有效管理“水平”选项卡中的可重复部分，请按照[创建具有可重复部分的表单](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/create-forms-repeatable-sections.html)文章。

### “项”选项卡 {#items-tab}

![“项”选项卡](/help/adaptive-forms/assets/items-tabs-on-top.png)

通过&#x200B;**添加**&#x200B;按钮，可从组件选择窗口中选择要作为面板添加的组件。添加该组件后，可看到以下选项：

* **图标** - 图标在列表中标识面板的组件。将光标悬停在图标上，即可看到作为工具提示的完整组件名称。
* **描述** - 用作面板文本的描述。默认情况下，为面板选择组件的名称。
* **删除** – 点按或单击，即可从“水平”选项卡组件中删除该面板。
* **重新排列** - 点击或单击并拖动以重新排列面板的顺序。

### “帮助内容”选项卡 {#help-content}

![“帮助内容”选项卡](/help/adaptive-forms/assets/helpcontent-tabs-on-top.png)

* **简短描述** - 简短描述是一段简短的文字说明，其中提供关于特定表单字段的用途的其他信息或阐述。它帮助用户了解应将什么类型的数据输入到字段中，并可提供准则或示例以帮助确保所输入的信息有效且符合预期的标准。默认情况下，简短描述保持隐藏状态。启用&#x200B;**始终显示简短描述**&#x200B;选项以在组件下方显示它。

* **始终显示简短描述** - 启用该选项以在组件下方显示简短描述。

* **帮助文本** - 帮助文本是指提供给用户以帮助其正确填写表单字段的其他信息或指导。当用户单击组件旁的“帮助”图标 (i) 时显示它。帮助文本提供比表单字段的标签或占位符文本更详细的信息，旨在帮助用户了解该字段的要求或限制。它还可提供建议或示例，以使填写表单更轻松且更准确。

### “辅助功能”选项卡 {#accessibility}

![“辅助功能”选项卡](/help/adaptive-forms/assets/accessibilty-tabs-on-top.png)

* **屏幕阅读器文本** - 屏幕阅读器文本是指专供由视障人士使用的屏幕阅读器等辅助技术读取的附加文本。此文本提供表单字段用途的音频描述，并可包括关于字段的标题、描述、名称和任何相关消息（自定义文本）的信息。屏幕阅读器文本帮助确保包括视障用户在内的所有用户均可访问表单，并使其完整地了解表单字段及其要求。

* **用于读出内容的屏幕阅读器的 HTML 角色** - HTML 角色是一个属性，用于向屏幕阅读器等辅助技术指定 HTML 元素的用途。角色属性用于为元素提供额外的上下文和语义，使屏幕阅读器更容易向用户解释和读出内容。例如，在 AEM Forms 中，表单字段的标签可能具有“标签”的作用，其输入字段可能具有“文本框”的作用。这有助于屏幕阅读器理解标签和输入字段之间的关系，并正确地向用户读出内容。

## “设计”对话框 {#design-dialog}

通过“设计”对话框，模板创建者可控制在默认情况下如何显示各种内容。对于自适应表单“水平”选项卡组件，可设置以下各项：

* 表单创建者可添加到自适应表单编辑器中的“水平”选项卡的核心组件
* 可在自适应表单编辑器的“水平”选项卡组件的“属性”对话框中应用的样式（CSS 类）的简单名称。

这有助于使创建和自定义表单的过程更加简便和高效。

### “允许使用的组件”选项卡 {#allowed-components-tab}

通过&#x200B;**允许使用的组件**&#x200B;选项卡，模板编辑者可设置可作为项添加到自适应表单编辑器中的水平选项卡组件面板的组件。

### “样式”选项卡 {#styles-tab}

“设计”对话框用于定义和管理组件的 CSS 样式。自适应表单水平选项卡核心组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。

**默认 CSS 类**：可为自适应表单水平选项卡核心组件提供默认 CSS 类。

* **允许使用的样式**：可通过提供名称和表示样式的 CSS 类而定义样式。例如，您可以创建一个名为“bold text”的样式，并提供 CSS 类“font-weight: bold”。可使用这些样式或将其应用于自适应表单编辑器中的自适应表单。要应用样式，请在自适应表单编辑器中选择要将样式应用于的组件，导航到“属性”对话框，然后从&#x200B;**样式**&#x200B;下拉列表中选择所需的样式。如果您需要更新或修改样式，只需返回“设计”对话框，在“样式”选项卡中更新样式，然后保存更改。

## 相关文章 {#related-article}

* [在AEM Sites页面或体验片段中创建自适应表单](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html)

* [创建独立的自适应表单](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html)
