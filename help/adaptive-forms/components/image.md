---
title: 自适应Forms核心组件 — 图像
description: 使用或自定义自适应Forms图像核心组件。
role: Architect, Developer, Admin, User
source-git-commit: 1e6460d318f4f9a5dfdcbb81723da01b51b72f3f
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 2%

---


# 图像 {#image-adaptive-forms-core-component}

自适应表单中的图像组件是一种在表单中包含图像的方式。 这些图像可用于增强表单的整体设计、提供其他信息或用作视觉帮助，以帮助用户了解表单的用途。 图像组件可用于在表单中添加徽标、照片或图形。

对于辅助功能，请务必指定 **替换文本** 为图像提供一个简短的描述性替换文本，可向看不到该图像的用户描述该图像。


**示例**

![](/help/adaptive-forms/assets/image.png)


## 用途 {#reasons-to-use-image-in-a-form}

在自适应表单中包含图像组件有益的原因有以下几种：

* **品牌策略**:图像可用于显示创建表单的组织的徽标或名称，从而帮助建立品牌认可和信誉。

* **视觉辅助**:图像可以作为视觉辅助工具，帮助用户了解表单的用途，从而帮助为用户提供额外级别的信息。

* **装饰**:图像可用于增强表单的整体设计，并使其更具视觉吸引力。

* **用户体验**:通过为用户提供一种清晰直观的方式来访问和填写表单字段，图像可用于使表单更加用户友好。

## 版本和兼容性 {#version-and-compatibility}

自适应Forms图像核心组件作为核心组件2.0.4的一部分于2023年2月发布。此处有一个表格，其中显示了所有受支持的版本、AEM兼容性以及指向相应文档的链接：

| 组件版本 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | 兼容 with<br>[版本2.0.4](/help/versions.md) 及更高版本 | 兼容 | 兼容 |

有关核心组件版本和版本的信息，请参阅 [核心组件版本](/help/versions.md) 文档。


<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技术详细信息 {#technical-details}

在以下位置的技术文档中，获取有关自适应Forms图像核心组件的最新信息 [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/image/v1/image). 有关开发核心组件的更多信息，请参阅 [核心组件开发人员文档](/help/developing/overview.md).


## “配置”对话框 {#configure-dialog}

您可以使用配置对话框轻松自定义访客的图像体验。 您还可以轻松定义图像选项，以提供无缝的用户体验。

![“属性”选项卡](/help/adaptive-forms/assets/image_properties.png)

* **名称**  — 您可以在表单和规则编辑器中使用表单组件的唯一名称轻松识别表单组件，但名称不得包含空格或特殊字符。

* **标题**  — 通过其标题，您可以轻松地在表单中识别组件，默认情况下，标题会显示在组件顶部。 如果不添加标题，则会显示组件的名称，而不是标题文本。

* **记录绑定引用文档**  — 此选项用于将自适应表单字段与记录文档字段关联。 当用户在自适应表单的链接字段中输入任何值时，该值也会显示在相应记录文档的链接字段中。 例如，记录文档绑定引用可用于根据在表单中输入的客户ID在记录文档中显示客户的名称和地址。 这样，AEM Forms就能让您生成记录文档，并为收集和管理数据提供无缝的用户体验。

* **描述**  — 描述是一个简短的文本说明，提供有关特定图像用途的其他信息或说明。

* **将资产拖放到此处或浏览要上传的文件**  — 利用此选项，可通过鼠标拖放来拖放资产（如图像）。 您还可以使用 **浏览** 按钮。 添加图像后，图像底部会显示三个按钮：
   * **编辑**  — 点按或单击 **编辑** 以在资产编辑器中管理资产的演绎版。
   * **清除**  — 点按或单击 **清除** ，以取消选择当前选定的图像。
   * **挑选**  — 点按或单击 **挑选**  选项，以从Assets文件夹中选择其他图像。

* **替换文本**  — 此选项用于输入文本，该文本为图像提供了简短的描述性替换文本，用于向视觉障碍用户描述图像。

* **隐藏组件**  — 选择选项以在表单中隐藏组件。 该组件仍可用于其他目的，例如在规则编辑器中将其用于计算。 当您需要存储用户无需查看或直接更改的信息时，此功能非常有用。

* **只读**  — 选择选项以使组件不可编辑。 用户可以查看字段的值，但无法对其进行修改。 该组件仍可用于其他目的，例如在规则编辑器中将其用于计算。

## “设计”对话框 {#design-dialog}

“设计”对话框用于定义和管理图像组件的CSS样式。

### 样式选项卡 {#styles-tab}

“设计”对话框用于定义和管理组件的CSS样式。 自适应Forms图像核心组件支持AEM [样式系统](/help/get-started/authoring.md#component-styling).

**默认CSS类**:您可以为自适应Forms图像核心组件提供默认CSS类。

**允许的样式**:您可以通过提供名称和表示样式的CSS类来定义样式。 例如，您可以创建名为“粗体文本”的样式，并提供CSS类“font-weight:粗体”。 您可以在自适应Forms编辑器中将这些样式用于自适应表单或将其应用于自适应表单。 要应用样式，请在自适应Forms编辑器中，选择要应用该样式的组件，导航到属性对话框，然后从 **样式** 下拉列表。 如果需要更新或修改样式，只需返回到“设计”对话框，更新“样式”选项卡中的样式，然后保存更改即可。