---
title: 自适应表单核心组件 - 文本
description: 使用或自定义自适应表单文本核心组件。
role: Architect, Developer, Admin, User
exl-id: b8de68e4-ca0d-4ae5-9a04-104cc617f1be
source-git-commit: 6725784bd4c94d433c91d6bd65d14d03cbefd954
workflow-type: ht
source-wordcount: '996'
ht-degree: 100%

---


# 文本组件 {#text-adaptive-forms-core-component}

在自适应表单中，文本是指显示在表单上以供用户阅读的内容。这可以包括用于标记一组表单元素的文本（例如文本字段），以及提供给用户的任何附加说明或信息。

这也有助于将表单的结构划分为多个逻辑部分，以便用户更轻松地理解和填写表单。此外，它还可作为辅助功能，用于简要描述与其关联的元素。此类文本字段通常显示在表单组件附近，例如表单组件之前或之后。

{{traditional-aem}}

**示例**

![文本示例](/help/adaptive-forms/assets/text.png)

## 用途 {#reasons-to-use-text-label}

有若干原因要在表单中使用文本：

- **提供说明**：文本可用于提供有关如何填写表单或需要哪些信息的说明。

- **提供上下文**：文本可用于为表单提供上下文，例如说明表单的用途或收集信息的组织。

- **将表单划分为逻辑部分**：可以使用文本将表单划分为多个逻辑部分，以便用户更轻松地理解和填写表单。

- **品牌化和标识**：文本可用于品牌化和标识目的，例如在表单中包含组织的名称。

## 版本和兼容性 {#version-and-compatibility}

作为 Cloud Service 核心组件 2.0.4 和 AEM 6.5.16.0 Forms 或更高版本核心组件 1.1.12 的一部分，自适应表单文本核心组件于 2023 年 2 月发布。下表显示所有支持的版本、AEM 兼容性以及相应文档的链接：

| 组件版本 | AEM as a Cloud Service | AEM 6.5.16.0 Forms 或更高版本 |
|---|---|---|
| v1 | 与<br>[版本 2.0.4](/help/adaptive-forms/version.md) 和更高版本兼容 | 与<br>[版本 1.1.12](/help/adaptive-forms/version.md) 和更高版本兼容，但低于版本 2.0.0。 |

有关核心组件版本的信息，请参阅[核心组件版本](/help/adaptive-forms/version.md)文档。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion_cn). -->

## 技术详细信息 {#technical-details}

可在 [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/text/v1/text) 上的技术文档中获得关于自适应表单文本核心组件的最新信息。有关开发核心组件的更多信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## “配置”对话框 {#configure-dialog}

通过“配置”对话框，可轻松地自定义您为访客提供的文本体验。还可轻松地定义文本选项，从而营造一种无缝的用户体验。

### “基本”选项卡

![“基本”选项卡](/help/adaptive-forms/assets/text_properties.png)

- **名称** - 可在表单和规则编辑器中通过唯一名称轻松地标识表单组件，但该名称不得包含空格或特殊字符。

- **绑定引用** - 绑定引用是对存储在外部数据源中并在表单中使用的数据元素的引用。通过绑定引用，可动态地将数据绑定到表单字段，以使表单可显示来自数据源的最新数据。例如，可使用绑定引用，根据输入到表单中的客户 ID，在该表单中显示该客户的姓名和地址。还可使用绑定引用，通过输入到表单中的数据更新数据源。这样通过 AEM Forms 即可创建与外部数据源交互的表单，从而为收集和管理数据提供一种无缝的用户体验。
- **标记为未绑定表单元素**：选择此选项可配置未链接到任何架构的表单字段。利用此选项，您可以保存数据而不更新数据源。它还可让您以一种独立于标准数据库集成的自定义方式处理数据。
- **隐藏组件** - 选中此选项以从表单中隐藏该组件。仍可访问该组件作其他用途，如在规则编辑器中使用它进行计算。当需要存储用户无需看到或直接更改的信息时，此项很有用。
  <!--    **Read-only** - Select the option to make the component non-editable. The user can see the value of the field but cannot modify it. The component remains accessible for other purposes, such as using it for calculations in the Rule Editor.-->

## “设计”对话框 {#design-dialog}

“设计”对话框用于定义和管理文本组件的 CSS 样式。

### “样式”选项卡 {#styles-tab}

该选项卡用于定义和管理组件的 CSS 样式。自适应表单文本核心组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。

![“设计”对话框](/help/adaptive-forms/assets/checkbox-style.png)

- **默认 CSS 类**：可为自适应表单文本核心组件提供默认 CSS 类。

- **允许使用的样式**：可通过提供名称和表示样式的 CSS 类而定义样式。例如，您可以创建一个名为“bold text”的样式，并提供 CSS 类“font-weight: bold”。可使用这些样式或将其应用于自适应表单编辑器中的自适应表单。要应用样式，请在自适应表单编辑器中选择要将样式应用于的组件，导航到“属性”对话框，然后从&#x200B;**样式**&#x200B;下拉列表中选择所需的样式。如果您需要更新或修改样式，只需返回“设计”对话框，在“样式”选项卡中更新样式，然后保存更改。

### 自定义属性

![“自定义属性”对话框](/help/adaptive-forms/assets/checkbox-customproperties.png)

通过自定义属性，您可使用表单模板将自定义属性（键值对）关联到自适应表单核心组件。自定义属性反映在组件 Headless 演绎版的属性部分中。它可让您创建根据自定义属性值进行调整的动态表单行为。例如，开发人员可以为移动、桌面或 Web 平台设计 Headless 表单组件的各种演绎版，从而大大提升各种设备上的用户体验。

- **组名称**：您可以提供名称来标识自定义属性组。您可以添加、删除或重新排列多个自定义属性组。添加自定义属性组后，可看到以下选项：

   - **键值对**：您可以通过单击“**添加**”按钮，为每个自定义属性组添加多个自定义属性名称和自定义属性值。

   - **删除**：点击或单击此项可删除自定义属性名称和自定义属性值。

   - **重新排列**：点击或单击并拖动可重新排列自定义属性名称和自定义属性值的顺序。

## 相关文章 {#related-articles}

{{more-like-this}}

## 另请参阅 {#see-also}

{{see-also}}