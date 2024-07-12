---
title: 电子邮件标题组件
description: 电子邮件标题组件是您的电子邮件的分区标题组件，具有就地编辑功能。
role: Architect, Developer, Admin, User
exl-id: f65b6973-bb36-406f-bbea-f85a23f5340b
source-git-commit: 3abc29e0c186a84f079d5938b8b716f4c7378d65
workflow-type: tm+mt
source-wordcount: '593'
ht-degree: 100%

---


# 电子邮件标题组件 {#email-title-component}

电子邮件标题组件是您的电子邮件的分区标题组件，具有就地编辑功能。

## 用途 {#usage}

电子邮件标题组件旨在用作电子邮件分区的标题。

* 可用的标题级别可由模板作者在[“设计”对话框](#design-dialog)中定义。
* 内容作者可以在[“编辑”对话框](#edit-dialog)中从可用标题级别选择。

为了增加便利性，可以简单地就地编辑标题文本。

## 版本和兼容性 {#version-and-compatibility}

电子邮件标题组件的当前版本是 v1，此版本随 2022 年 10 月的电子邮件核心组件发行版本 X 的发布引入，具体说明见本文档。

下表详细说明了该组件的所有受支持版本、与该组件的版本兼容的 AEM 版本以及指向早期版本文档的链接。

| 组件版本 | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | 兼容 | - |

有关核心组件版本和发布的更多信息，请参阅文档[核心电子邮件组件版本](/help/versions.md)。

### 技术详细信息 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_email_title_v1_cn)有关标题组件的最新技术文档。

在[核心组件开发人员文档](/help/developing/overview.md)中可找到有关开发核心组件的其他详细信息。

## “编辑”对话框 {#edit-dialog}

内容作者可以使用“编辑”对话框定义标题文本以及选择标题级别。

* **标题** - 如果为空，则使用页面标题
   * 单击 Campaign 图标，打开[选择 Adobe Campaign 变量](/help/email/campaign-variables.md)对话框并插入来自 Adobe Campaign 的动态内容。
* **类型/大小** - 定义标题的标题级别
* **链接** - 定义标题将链接到的内容。这可以是内容页面的路径、外部 URL 或页面锚点。
   * 单击 Campaign 图标，打开[选择 Adobe Campaign 变量](/help/email/campaign-variables.md)对话框并插入来自 Adobe Campaign 的动态内容。
* **ID** – 此选项允许控制 HTML 中组件的唯一标识符。
   * 如果留空，则自动为您生成一个唯一 ID，通过检查所得页面即可找到该 ID。
   * 如果指定一个 ID，作者有责任确保它是唯一的。
   * 更改 ID 会对 CSS 产生影响。

![电子邮件标题组件的“编辑”对话框](/help/email/assets/email-title-edit.png)

就地编辑器也可以用于编辑标题组件的文本。

![就地编辑电子邮件标题组件](/help/email/assets/email-title-edit-inline.png)

### 样式选项卡 {#styles-tab-edit}

电子邮件标题组件支持 AEM [样式系统。](/help/get-started/authoring.md#component-styling)

使用下拉菜单选择要应用于该组件的样式。在“编辑”对话框中所做的选择与从组件工具栏中选择的操作效果相同。

必须在[“设计”对话框](#design-dialog)中为此组件配置样式，以便下拉菜单可用。

![标题组件“编辑”对话框的“样式”选项卡](/help/email/assets/email-title-edit-styles.png)

## “设计”对话框 {#design-dialog}

模板作者可以使用“设计”对话框定义内容作者在创建标题组件时具有的默认标题级别。

### “大小”选项卡 {#sizes-tab}

![标题组件的“设计”对话框](/help/email/assets/email-title-design.png)

* **为作者允许的类型/大小** – 启用或禁用内容作者在使用电子邮件标题组件时可用的标题类型。
* **默认类型/大小** – 定义内容作者在将电子邮件标题组件添加到页面时，将自动分配的标题类型。
* **禁用链接** – 禁用电子邮件标题组件中对链接的支持，从而不允许内容作者从标题进行链接。

### 样式选项卡 {#styles-tab}

电子邮件标题组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。
