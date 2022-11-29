---
title: 电子邮件容器组件
description: 使用电子邮件容器组件，可在您的电子邮件内容上为多个其他组件创建容器。
role: Architect, Developer, Admin, User
exl-id: 3b271e95-0093-4cb1-bb83-8446ba12a821
source-git-commit: 33976c0e745ad091a142109f70541f01a31edc5b
workflow-type: tm+mt
source-wordcount: '835'
ht-degree: 100%

---


# 电子邮件容器组件 {#email-container-component}

使用电子邮件容器组件，可在您的电子邮件内容上为多个其他组件创建容器。

## 用途 {#usage}

使用电子邮件容器组件，可在您的电子邮件内容上为多个其他组件创建容器，并可用于分组其他组件以及应用通用样式或布局。

* 在[“配置”对话框](#configure-dialog)中可选择容器的属性。
* 将电子邮件容器组件添加到页面时的默认值可以在[“设计”对话框](#design-dialog)中定义。

将电子邮件容器组件添加到页面后，内容作者可以将其他组件拖放到其中。

## 版本和兼容性 {#version-and-compatibility}

电子邮件容器组件的当前版本是 v1，此版本随 2022 年 10 月的电子邮件核心组件发行版本 X 的发布引入，具体说明见本文档。

下表详细说明了该组件的所有受支持版本、与该组件的版本兼容的 AEM 版本以及指向早期版本文档的链接。

| 组件版本 | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | 兼容 | 兼容 |

有关电子邮件核心组件版本的更多信息，请参阅文档[电子邮件核心组件版本。](/help/email/versions.md)

## 示例组件输出 {#sample-component-output}

要体验电子邮件容器组件并查看其配置选项示例以及 HTML 和 JSON 输出，请访问[组件库。](https://adobe.com/go/aem_cmp_library_email_container_cn)

## 技术详细信息 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_email_container_v1_cn)有关容器组件的最新技术文档。

在[核心组件开发人员文档](/help/developing/overview.md)中可找到有关开发核心组件的其他详细信息。

## “配置”对话框 {#configure-dialog}

配置对话框允许内容作者定义容器项以及它在您的内容中的行为和显示方式。

![电子邮件容器组件的“编辑”对话框](/help/email/assets/email-container-configure.png)

* **布局** - 此选项定义电子邮件容器组件的行为或布局行为。
   * **完整宽度**
   * **一半|一半**
   * **三分之一|三分之二**
   * **三分之二|三分之一**
   * **三分之一|三分之一|三分之一**
* **背景颜色** - 定义为自由格式的 RGB 值，或者使用拾色器，[具体取决于配置](#container-settings-tab)
* **背景图像** – 定义容器的背景图像，[具体取决于配置](#container-settings-tab)
* **ID** – 此选项允许控制 HTML 中组件的唯一标识符。
   * 如果留空，系统会自动为您生成一个唯一 ID，可以通过检查结果内容找到该 ID。
   * 如果指定一个 ID，作者有责任确保它是唯一的。
   * 更改 ID 会对 CSS 产生影响。

### 样式选项卡 {#styles-tab-edit}

电子邮件容器组件支持 AEM [样式系统。](/help/get-started/authoring.md#component-styling)

使用下拉菜单选择要应用于该组件的样式。在“编辑”对话框中所做的选择与从组件工具栏中选择的操作效果相同。

必须在[“设计”对话框](#design-dialog)中为此组件配置样式，以便选项卡可用。

## “设计”对话框 {#design-dialog}

使用“设计”对话框，模板作者可以定义哪些选项可供使用电子邮件容器组件的内容作者使用。

### “允许的组件”选项卡 {#allowed-components-tab}

**“允许的组件”**&#x200B;选项卡用于定义哪些组件可由内容作者作为项目添加到电子邮件容器组件。

**“允许的组件”**&#x200B;选项卡的功能，与[在模板编辑器的布局容器中定义策略和属性时的同名选项卡的功能相同。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)

### “默认组件”选项卡 {#default-components-tab}

**“默认组件”**&#x200B;选项卡用于定义在特定资源类型放到容器上时，要向组件中添加哪些组件，类似于[如何在页面模板上定义默认组件。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)

### 容器设置选项卡 {#container-settings-tab}

**容器设置**&#x200B;选项卡定义作者是否可以定义背景图像或颜色。

![电子邮件容器组件的“设计”对话框的“容器设置”选项卡](/help/email/assets/email-container-design-container-settings.png)

* **背景图像**
   * **启用背景图像** - 选择此选项可允许内容作者定义容器的背景图像。
* **背景颜色**
   * **启用背景颜色** - 选择此选项可允许内容作者定义容器的背景颜色。
   * **仅色板** - 选择此选项可仅允许内容作者从预定义的色板中选择容器的背景颜色。
      * 仅在选择了&#x200B;**“启用背景颜色”**&#x200B;时可用
* **允许的色板** - 定义内容作者可从中选择容器背景颜色的预定义颜色
   * 使用&#x200B;**“添加”**&#x200B;按钮可添加预定义的色板。在添加之后，一个条目将添加到列表中，包含以下列：
   * **值** - 通过 RGB 值手动定义颜色
      * 点击或单击拾色器，以通过调整单独的 RGB 值或定义十六进制值，更轻松地选择颜色。
   * **删除** - 点击或单击以删除色板。
   * **重新排列** – 点击或单击并拖动以重新排列色板。

### 样式选项卡 {#styles-tab}

电子邮件容器组件支持 AEM [样式系统。](/help/get-started/authoring.md#component-styling)
