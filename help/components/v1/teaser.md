---
title: Teaser 组件 (v1)
description: Teaser 组件可以显示图像、标题、富文本并可以选择链接到更多内容。
role: Architect, Developer, Admin, User
exl-id: 48e56938-660a-43e7-9e62-8069283ae73f
source-git-commit: 84e09fa64b3a7ae40ff3ff1a04ea1c7504db29d2
workflow-type: tm+mt
source-wordcount: '722'
ht-degree: 100%

---

# Teaser 组件 (v1) {#teaser-component}

核心组件 Teaser 组件可以显示图像、标题、富文本并可以选择链接到更多内容。

## 用途 {#usage}

使用 Teaser 组件，内容作者可以轻松地创建 Teaser，以便让更多内容使用图像、标题或富文本，并将其链接到更多内容或其他操作。

模板作者可以使用[“设计”对话框](#design-dialog)定义创建行动号召和添加链接的选项是否可用，以及禁用各种显示选项。内容作者可以使用[“配置”对话框](#configure-dialog)来设置图像、定义 CTA、设置标题和描述，以及配置指向个别 Teaser 的链接。可以访问[图像组件](image-v1.md)的[“编辑”对话框](image-v1.md#edit-dialog)来修改 Teaser 图像。

## 版本和兼容性 {#version-and-compatibility}

本文档介绍了 Teaser 组件 v1，此版本随 2018 年 7 月的核心组件发行版本 2.1.0 的发布引入。

>[!CAUTION]
>
>本文档介绍了 Teaser 组件 v1。
>
>有关当前版本的 Teaser 组件的详细信息，请参阅 [Teaser 组件](/help/components/teaser.md)文档。

## 示例组件输出 {#sample-component-output}

要体验 Teaser 组件并查看其配置选项示例以及 HTML 和 JSON 输出，请访问[组件库](https://adobe.com/go/aem_cmp_library_teaser_cn)。

### 技术详细信息 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_teaser_v1_cn)有关 Teaser 组件的最新技术文档。

在[核心组件开发人员文档](/help/developing/overview.md)中可找到有关开发核心组件的其他详细信息。

## “配置”对话框 {#configure-dialog}

内容作者可以使用“配置”对话框定义个别 Teaser 的属性。在选中时，还有[“编辑”对话框](#edit-dialog)可修改 Teaser 图像。

### 图像 {#image}

![Teaser 组件的“编辑”对话框中的“图像”选项卡](/help/assets/teaser-edit-image.png)

* **图像资源**
   * 通过[资源浏览器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html?lang=zh-Hans)拖放资源或点击&#x200B;**浏览**&#x200B;选项，以从本地文件系统上传。
   * 点按或单击&#x200B;**“清除”**&#x200B;以取消选择当前选定的图像。
   * 点击或单击&#x200B;**“编辑”**&#x200B;可在资源编辑器中[管理资源的再现](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html?lang=zh-Hans)。

>[!NOTE]
>
>[Dynamic Media 功能](image-v1.md#dynamic-media)当前在 Teaser 组件中不可用。

### 文本 {#text}

![Teaser 组件的“编辑”对话框中的“文本”选项卡](/help/assets/teaser-edit-text.png)

* **前标题** - 前标题显示在 Teaser 的标题之前。
* **标题** - 定义显示为 Teaser 大标题的标题。
   * **从链接的页面获取标题** - 在选中时，使用链接页面的标题填充标题。
* **描述** - 定义显示为 Teaser 子标题的描述。
   * **从链接的页面获取描述** - 在选中时，使用链接页面的描述填充描述。
* **ID** - 利用此选项，可以控制 HTML 和 [Data Layer](/help/developing/data-layer/overview.md) 中的组件的唯一标识符。
   * 如果留空，系统会自动为您生成一个唯一 ID，可以通过检查结果页面找到该 ID。
   * 如果指定一个 ID，作者有责任确保它是唯一的。
   * 更改此 ID 会对 CSS、JS 和 Data Layer 跟踪产生影响。

### 链接和操作 {#links-actions}

![Teaser 组件的“编辑”对话框中的“链接”选项卡](/help/assets/teaser-edit-link.png)

* **链接** - 应用到 Teaser 的链接。使用路径浏览器选择链接目标。
* **启用行动号召** - 选中时，启用行动号召的定义。列表中的第一个行动号召链接用作其他 Teaser 元素的链接。

## “编辑”对话框 {#edit-dialog}

Teaser 组件将图像渲染委派给[图像组件](image-v1.md)。因此，内容作者可以使用图像组件的[“编辑”对话框](image-v1.md#edit-dialog)来处理 Teaser 图像。

## “设计”对话框 {#design-dialog}

利用“设计”对话框，模板作者可以定义内容作者在使用此组件时具有的 Teaser 选项。

### “Teaser”选项卡 {#teaser-tab}

![Teaser 组件的“设计”对话框](/help/assets/teaser-design.png)

* **行动号召**
   * **禁用行动号召** - 对内容作者隐藏&#x200B;**行动号召**&#x200B;选项
* **元素**
   * **隐藏前标题** - 对内容作者隐藏&#x200B;**前标题**&#x200B;选项
   * **隐藏标题** - 对内容作者隐藏&#x200B;**标题**&#x200B;选项
      * 在选中时，将隐藏&#x200B;**标题类型**
   * **隐藏描述** - 对内容作者隐藏&#x200B;**描述**&#x200B;选项
* **标题类型** - 定义由 Teaser 的标题使用的 H 标记。
* **链接**
   * **不链接图像** - 在选中时，不链接 Teaser 图像
   * **不链接标题** - 在选中时，不链接 Teaser 标题
* **图像委派** - 信息性显示，指示 Teaser 将图像处理委派到的组件。

### “样式”选项卡 {#styles-tab}

Teaser 组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。

## Adobe Client Data Layer {#data-layer}

Teaser 组件支持 [Adobe Client Data Layer](/help/developing/data-layer/overview.md)。
