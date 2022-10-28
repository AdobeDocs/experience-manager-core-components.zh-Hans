---
title: 电子邮件按钮组件
description: 电子邮件按钮组件允许在内容中配置和显示按钮项目。
role: Architect, Developer, Admin, User
hidefromtoc: true
index: false
source-git-commit: 8bebe3ca036557f3f7c6b8ec0e65d6d104d5ffae
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 电子邮件按钮组件 {#email-button-component}

电子邮件按钮组件允许在内容中配置和显示按钮项目。

## 用途 {#usage}

电子邮件按钮组件允许在内容中包含按钮，内容阅读器可单击，并将其链接到其他资源。

* 可以在 [配置对话框。](#configure-dialog)
* 可以在 [“设计”对话框。](#design-dialog)

## 版本和兼容性 {#version-and-compatibility}

电子邮件按钮组件的当前版本为v1，该版本于2022年10月随电子邮件核心组件第x版引入，在本文档中进行了描述。

下表详细说明了该组件的所有受支持版本、与该组件的版本兼容的 AEM 版本以及指向早期版本文档的链接。

| 组件版本 | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | 兼容 | 兼容 |

有关核心组件版本和版本的更多信息，请参阅此文档 [电子邮件核心组件版本。](/help/email/versions.md)

## 示例组件输出 {#sample-component-output}

要体验电子邮件按钮组件并查看其配置选项以及HTML和JSON输出的示例，请访问 [组件库。](https://adobe.com/go/aem_cmp_library_email_button)

## 技术详细信息 {#technical-details}

有关电子邮件按钮组件的最新技术文档 [可在GitHub上找到。](https://adobe.com/go/aem_cmp_tech_email_button_v1)

有关开发核心组件的更多详细信息，请参阅 [核心组件开发人员文档。](/help/developing/overview.md)

## “配置”对话框 {#configure-dialog}

“配置”对话框允许内容作者定义按钮及其行为和向内容读者显示的方式。

### “属性”选项卡 {#properties-tab}

![按钮组件“编辑”对话框的“属性”选项卡](/help/email/assets/email-button-edit-properties.png)

* **文本** - 在按钮上显示的文本
   * 单击Campaign图标以打开 [选择Adobe Campaign变量](/help/email/campaign-variables.md) 对话框，以从Adobe Campaign插入动态内容。
* **链接** - 与 AEM 中的内容页面、外部资源或锚点的链接。
   * 使用&#x200B;**“选择”对话框**&#x200B;可在 AEM 中选择路径。
   * 单击Campaign图标以打开 [选择Adobe Campaign变量](/help/email/campaign-variables.md) 对话框，以从Adobe Campaign插入动态内容。
* **图标** - 在按钮中显示图标的标识符
* **ID**  — 此选项允许控制组件在HTML中的唯一标识符。
   * 如果留空，则会自动为您生成唯一ID，并且可以通过检查生成的内容来找到该ID。
   * 如果指定一个 ID，作者有责任确保它是唯一的。
   * 更改ID可能会对CSS产生影响。
* **在新标签页中打开链接** - 在选中时，将在一个新的浏览器标签页中打开链接。

### “辅助功能”选项卡 {#accessibility-tab}

![按钮组件“编辑”对话框的“辅助功能”选项卡](/help/email/assets/email-button-edit-accessibility.png)

在&#x200B;**辅助功能**&#x200B;选项卡上，可以为组件的 [ARIA 辅助功能](https://www.w3.org/WAI/standards-guidelines/aria/)标签设置值。

* **标签** - 组件的 ARIA 标签属性的值

### “样式”选项卡 {#styles-tab-edit}

电子邮件按钮组件支持AEM [样式系统。](/help/get-started/authoring.md#component-styling).

使用下拉菜单选择要应用于该组件的样式。在“编辑”对话框中所做的选择与从组件工具栏中选择的操作效果相同。

必须在 [设计对话框](#design-dialog) 以使选项卡可用。

## “设计”对话框 {#design-dialog}

### “样式”选项卡 {#styles-tab}

电子邮件按钮组件支持AEM [样式系统](/help/get-started/authoring.md#component-styling).
