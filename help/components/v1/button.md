---
title: 按钮组件 (v1)
description: 利用核心组件按钮组件，可创建和显示按钮。
role: Architect, Developer, Admin, User
exl-id: 63af16e4-dd4d-426d-88ef-769ecd1b3175
index: n
source-git-commit: 92a3ec273a5be6751c1503835b9c2e5cbd61bb9e
workflow-type: ht
source-wordcount: '397'
ht-degree: 100%

---


# 按钮组件 (v1) {#button-component}

利用核心组件按钮组件，可在页面上配置和显示按钮。

## 用途 {#usage}

利用核心组件按钮组件，可在页面上包含按钮。

* 可在[“配置”对话框](#configure-dialog)中选择按钮的属性。
* 按钮组件的样式可在[“设计”对话框](#design-dialog)中定义。

## 版本和兼容性 {#version-and-compatibility}

本文档介绍了按钮组件 v1，此版本随 2019 年 6 月的核心组件发行版本 2.5.0 的发布引入。

>[!CAUTION]
>
>本文档介绍了按钮组件 v1。
>
>有关当前版本的按钮组件的详细信息，请参阅[按钮组件](/help/components/button.md)文档。

## 示例组件输出 {#sample-component-output}

要体验按钮组件并查看其配置选项示例以及 HTML 和 JSON 输出，请访问[组件库](https://adobe.com/go/aem_cmp_library_button_cn)。

## 技术详细信息 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_button_v1_cn)有关按钮组件的最新技术文档。

在[核心组件开发人员文档](/help/developing/overview.md)中可找到有关开发核心组件的其他详细信息。

## “配置”对话框 {#configure-dialog}

利用“配置”对话框，内容作者可以定义按钮，以及对于页面的访客它会如何表现和显示。

### “属性”选项卡 {#properties-tab}

![按钮组件“编辑”对话框的“属性”选项卡](/help/assets/button-edit-properties.png)

* **文本** - 在按钮上显示的文本
* **链接** - 与 AEM 中的内容页面、外部资源或锚点的链接。
   * 使用&#x200B;**“选择”对话框**&#x200B;可在 AEM 中选择路径。
* **图标** - 在按钮中显示图标的标识符
* **ID** - 利用此选项，可以控制 HTML 和 [Data Layer](/help/developing/data-layer/overview.md) 中的组件的唯一标识符。
   * 如果留空，系统会自动为您生成一个唯一 ID，可以通过检查结果页面找到该 ID。
   * 如果指定一个 ID，作者有责任确保它是唯一的。
   * 更改此 ID 会对 CSS、JS 和 Data Layer 跟踪产生影响。

### “辅助功能”选项卡 {#accessibility-tab}

![按钮组件“编辑”对话框的“辅助功能”选项卡](/help/assets/button-edit-accessibility.png)

在&#x200B;**辅助功能**&#x200B;选项卡上，可以为组件的 [ARIA 辅助功能](https://www.w3.org/WAI/standards-guidelines/aria/)标签设置值。

* **标签** - 组件的 ARIA 标签属性的值

## “设计”对话框 {#design-dialog}

### “样式”选项卡 {#styles-tab}

按钮组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。

## Adobe Client Data Layer {#data-layer}

按钮组件支持 [Adobe Client Data Layer](/help/developing/data-layer/overview.md)。
