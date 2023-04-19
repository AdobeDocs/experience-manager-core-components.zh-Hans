---
title: 电子邮件按钮组件
description: 利用电子邮件按钮组件，可在您的内容中配置和显示按钮项。
role: Architect, Developer, Admin, User
exl-id: b144e8d1-1097-475d-b2eb-3353c176afb9
source-git-commit: 3abc29e0c186a84f079d5938b8b716f4c7378d65
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 100%

---


# 电子邮件按钮组件 {#email-button-component}

利用电子邮件按钮组件，可在您的内容中配置和显示按钮项。

## 用途 {#usage}

电子邮件按钮组件允许在您的内容中包含一个按钮，内容阅读器可以点击该按钮，链接到其他资源。

* 可在[“配置”对话框](#configure-dialog)中选择按钮的属性。
* 电子邮件按钮组件的样式可在[“设计”对话框](#design-dialog)中定义。

## 版本和兼容性 {#version-and-compatibility}

电子邮件按钮组件的当前版本是 v1，此版本随 2022 年 10 月的电子邮件核心组件发行版本 X 的发布引入，具体说明见本文档。

下表详细说明了该组件的所有受支持版本、与该组件的版本兼容的 AEM 版本以及指向早期版本文档的链接。

| 组件版本 | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | 兼容 | - |

有关核心组件版本的更多信息，请参阅文档[电子邮件核心组件版本。](/help/email/versions.md)

## 技术详细信息 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_email_button_v1_cn)有关电子邮件按钮组件的最新技术文档。

在[核心组件开发人员文档](/help/developing/overview.md)中可找到有关开发核心组件的其他详细信息。

## “配置”对话框 {#configure-dialog}

利用“配置”对话框，内容作者可以定义按钮，以及按钮行为方式和对内容读者的显示方式。

### “属性”选项卡 {#properties-tab}

![按钮组件“编辑”对话框的“属性”选项卡](/help/email/assets/email-button-edit-properties.png)

* **文本** - 在按钮上显示的文本
   * 单击 Campaign 图标，打开[选择 Adobe Campaign 变量](/help/email/campaign-variables.md)对话框并插入来自 Adobe Campaign 的动态内容。
* **链接** - 与 AEM 中的内容页面、外部资源或锚点的链接。
   * 使用&#x200B;**“选择”对话框**&#x200B;可在 AEM 中选择路径。
   * 单击 Campaign 图标，打开[选择 Adobe Campaign 变量](/help/email/campaign-variables.md)对话框并插入来自 Adobe Campaign 的动态内容。
* **图标** – 在按钮中显示图标的标识符
* **ID** – 利用此选项，可以控制 HTML 中组件的唯一标识符。
   * 如果留空，系统会自动为您生成一个唯一 ID，可以通过检查结果内容找到该 ID。
   * 如果指定一个 ID，作者有责任确保它是唯一的。
   * 更改 ID 会对 CSS 产生影响。
* **在新标签页中打开链接** – 如果选中，将在一个新的浏览器标签页中打开链接。

### “辅助功能”选项卡 {#accessibility-tab}

![按钮组件“编辑”对话框的“辅助功能”选项卡](/help/email/assets/email-button-edit-accessibility.png)

在&#x200B;**辅助功能**&#x200B;选项卡上，可以为组件的 [ARIA 辅助功能](https://www.w3.org/WAI/standards-guidelines/aria/)标签设置值。

* **标签** - 组件的 ARIA 标签属性的值

### “样式”选项卡 {#styles-tab-edit}

电子邮件按钮组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。

使用下拉菜单选择要应用于该组件的样式。在“编辑”对话框中所做的选择与从组件工具栏中选择的操作效果相同。

必须在[“设计”对话框](#design-dialog)中为此组件配置样式，以便选项卡可用。

## “设计”对话框 {#design-dialog}

### “样式”选项卡 {#styles-tab}

电子邮件按钮组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。
