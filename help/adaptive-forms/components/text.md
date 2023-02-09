---
title: 自适应Forms核心组件 — 文本
description: 使用或自定义自适应Forms文本核心组件。
role: Architect, Developer, Admin, User
source-git-commit: 1e6460d318f4f9a5dfdcbb81723da01b51b72f3f
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 3%

---


# 文本 {#text-adaptive-forms-core-component}

在自适应表单中，文本是指在表单上显示以供用户阅读的内容。 这可以包括用于标记一组表单元素（如文本字段）的文本，以及提供给用户的任何其他说明或信息。

这也有助于将表单的结构划分为逻辑部分，从而让用户更容易理解和完成表单。 此外，还可将其用于辅助功能，以简要描述与之关联的元素。 此类文本字段通常显示在表单组件附近，如表单组件之前或之后。

**示例**

![](/help/adaptive-forms/assets/text.png)

## 用途 {#reasons-to-use-text-label}

在表单中使用文本的原因有多种：

* **提供说明**:文本可用于提供有关如何填写表单或需要哪些信息的说明。

* **提供上下文**:文本可用于提供表单的上下文，例如说明表单或收集信息的组织的用途。

* **将表单划分为逻辑部分**:文本可用于将表单划分为逻辑部分，从而让用户更容易理解和完成表单。

* **品牌和身份**:文本可用于品牌和身份目的，例如在表单中包含组织的名称。

## 版本和兼容性 {#version-and-compatibility}

自适应Forms文本核心组件作为核心组件2.0.4的一部分于2023年2月发布。下面是一个表格，其中显示了所有受支持的版本、AEM兼容性以及指向相应文档的链接：

| 组件版本 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | 兼容 with<br>[版本2.0.4](/help/versions.md) 及更高版本 | 兼容 | 兼容 |

有关核心组件版本和版本的信息，请参阅 [核心组件版本](/help/versions.md) 文档。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技术详细信息 {#technical-details}

在 [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/text/v1/text). 有关开发核心组件的更多信息，请参阅 [核心组件开发人员文档](/help/developing/overview.md).

## “配置”对话框 {#configure-dialog}

您可以使用配置对话框轻松自定义访客的文本体验。 您还可以轻松定义文本选项，以提供无缝的用户体验。

![“基本”选项卡](/help/adaptive-forms/assets/text_properties.png)

* **名称**  — 您可以在表单和规则编辑器中使用表单组件的唯一名称轻松识别表单组件，但名称不得包含空格或特殊字符。

* **绑定引用**  — 绑定引用是对存储在外部数据源中并在表单中使用的数据元素的引用。 绑定引用允许您将数据动态绑定到表单字段，以便表单可以显示来自数据源的最新数据。 例如，可以使用绑定引用根据在表单中输入的客户ID在表单中显示客户的名称和地址。 绑定引用还可用于使用输入到表单中的数据更新数据源。 通过这种方式，AEM Forms使您能够创建与外部数据源交互的表单，从而为数据收集和管理提供无缝的用户体验。
* **隐藏组件**  — 选择选项以在表单中隐藏组件。 该组件仍可用于其他目的，例如在规则编辑器中将其用于计算。 当您需要存储用户无需查看或直接更改的信息时，此功能非常有用。
* **只读**  — 选择选项以使组件不可编辑。 用户可以查看字段的值，但无法对其进行修改。 该组件仍可用于其他目的，例如在规则编辑器中将其用于计算。


## “设计”对话框 {#design-dialog}

“设计”对话框用于定义和管理文本组件的CSS样式。


### 样式选项卡 {#styles-tab}

“设计”对话框用于定义和管理组件的CSS样式。 自适应Forms文本核心组件支持AEM [样式系统](/help/get-started/authoring.md#component-styling).

**默认CSS类**:您可以为自适应Forms文本核心组件提供默认CSS类。

**允许的样式**:您可以通过提供名称和表示样式的CSS类来定义样式。 例如，您可以创建名为“粗体文本”的样式，并提供CSS类“font-weight:粗体”。 您可以在自适应Forms编辑器中将这些样式用于自适应表单或将其应用于自适应表单。 要应用样式，请在自适应Forms编辑器中，选择要应用该样式的组件，导航到属性对话框，然后从 **样式** 下拉列表。 如果需要更新或修改样式，只需返回到“设计”对话框，更新“样式”选项卡中的样式，然后保存更改即可。
