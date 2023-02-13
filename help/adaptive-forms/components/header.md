---
title: 自适应Forms核心组件 — 标题
description: 使用或自定义自适应Forms标头核心组件。
role: Architect, Developer, Admin, User
source-git-commit: b378fbd5695f82b8fc9de3a2d53a8387099ae33b
workflow-type: tm+mt
source-wordcount: '654'
ht-degree: 7%

---


# 标题 {#header-adaptive-forms-core-component}

自适应表单中的标题组件是表单顶部的一个部分，通常包括表单的标题、徽标或名称。 标题还可以包含其他信息，如表单用途的简要描述、创建表单的组织的名称，或与表单相关的帮助联系信息。 标题用于为用户提供表单的概述，并提供要填写的信息的上下文。 它用于帮助用户了解表单的用途以及如何正确填写表单。

**示例**

![](/help/adaptive-forms/assets/header.png)

## 用途 {#reasons-to-use-header}

* **品牌策略**:标题可用于显示创建表单的组织的徽标或名称，从而帮助建立品牌认可和信誉。

* **上下文**:标题可以提供表单用途的简要描述，帮助用户了解使用表单的上下文。

* **导航**:标题可以包括允许用户导航到网站或应用程序其他部分的链接或按钮。

* **信息**:标题可以包含联系信息或帮助资源的链接，从而更便于用户在需要时获得帮助。

* **用户体验**:标题可为用户提供一种清晰直观的方式来访问和填写表单字段，从而使表单更加用户友好。

## 版本和兼容性 {#version-and-compatibility}

自适应Forms标头核心组件作为核心组件2.0.4的一部分于2023年2月发布。下面是一个表格，其中显示了所有受支持的版本、AEM兼容性以及指向相应文档的链接：

|  |  |
|---|---|
| 组件版本 | AEM as a Cloud Service |
| --- | --- |
| v1 | 兼容 with<br>[版本2.0.4](/help/versions.md) 及更高版本 | 兼容 | 兼容 |
有关核心组件版本和版本的信息，请参阅 [核心组件版本](/help/versions.md) 文档。


<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->


## 技术详细信息 {#technical-details}

在 [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/pageheader/v1/pageheader). 有关开发核心组件的更多信息，请参阅 [核心组件开发人员文档](/help/developing/overview.md).

## “配置”对话框 {#configure-dialog}

您可以使用配置对话框轻松自定义访客的页眉体验。 您还可以轻松定义标题选项，以提供无缝的用户体验。

### “图像”选项卡 {#image-tab}

标题的这一部分包含标题和图像。

![Imagetab](/help/adaptive-forms/assets/header_image.png)

* **图像资产**  — 利用此选项，可通过鼠标拖放来拖放资产（如图像）。 您还可以使用 **浏览** 按钮。 添加图像后，图像底部会显示三个按钮。 添加图像后，图像底部会显示三个按钮：
   * **编辑**  — 点按或单击 **编辑** 以在资产编辑器中管理资产的演绎版。
   * **清除**  — 点按或单击 **清除** ，以取消选择当前选定的图像。
   * **挑选**  — 点按或单击 **挑选**  选项，以从Assets文件夹中选择其他图像。

* **标题**  — 此选项用于将标题添加到标题中。 该预定义文本包含在对话框中，用户可以修改该文本。
* **链接到**  — 您可以使用 **浏览** 图标。
* **描述**  — 描述是一个简短的文本说明，提供有关特定图像用途的其他信息或说明。
* **大小(px)**  — 通过增加或减少像素，有助于调整图像的长度和宽度。

![accessibilitytab](/help/adaptive-forms/assets/header_accessibility.png)

* **替换文本**  — 此选项用于输入文本，该文本为图像提供了简短的描述性替换文本，用于向视觉障碍用户描述图像。

* **图像是装饰性的** – 检查图像是否应被辅助技术忽略，因此不需要替换文本。这仅适用于装饰性图像。

### “文本”选项卡 {#text-tab}

此部分允许输入要包含在标题中的文本。



