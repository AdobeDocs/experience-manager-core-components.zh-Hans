---
title: 电子邮件容器组件
description: 电子邮件容器组件允许为电子邮件内容中的多个其他组件创建容器。
role: Architect, Developer, Admin, User
hidefromtoc: true
index: false
source-git-commit: 8bebe3ca036557f3f7c6b8ec0e65d6d104d5ffae
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 电子邮件容器组件 {#email-container-component}

电子邮件容器组件允许为电子邮件内容中的多个其他组件创建容器。

## 用途 {#usage}

电子邮件容器组件允许为电子邮件内容中的多个其他组件创建容器，并可用于对其他组件进行分组和应用通用样式或布局。

* 可以在 [配置对话框。](#configure-dialog)
* 将电子邮件容器组件添加到页面时，其默认值可在 [“设计”对话框。](#design-dialog)

将电子邮件容器组件添加到页面后，内容作者可以将其他组件拖放到页面中。

## 版本和兼容性 {#version-and-compatibility}

电子邮件容器组件的当前版本为v1，该版本于2022年10月随电子邮件核心组件X版引入，在本文档中进行了描述。

下表详细说明了该组件的所有受支持版本、与该组件的版本兼容的 AEM 版本以及指向早期版本文档的链接。

| 组件版本 | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | 兼容 | 兼容 |

有关电子邮件核心组件版本和版本的更多信息，请参阅此文档 [电子邮件核心组件版本。](/help/email/versions.md)

## 示例组件输出 {#sample-component-output}

要体验电子邮件容器组件，并查看其配置选项以及HTML和JSON输出的示例，请访问 [组件库。](https://adobe.com/go/aem_cmp_library_email_container)

## 技术详细信息 {#technical-details}

有关容器组件的最新技术文档 [可在GitHub上找到。](https://adobe.com/go/aem_cmp_tech_email_container_v1)

有关开发核心组件的更多详细信息，请参阅 [核心组件开发人员文档。](/help/developing/overview.md)

## “配置”对话框 {#configure-dialog}

配置对话框允许内容作者定义容器项目及其行为和在内容中的显示方式。

![电子邮件容器组件的编辑对话框](/help/email/assets/email-container-configure.png)

* **布局**  — 此选项定义电子邮件容器组件的行为或布局行为。
   * **全宽**
   * **半|半**
   * **三分之一|三分之二**
   * **三分之二|三分之一**
   * **第三|第三|第三**
* **背景颜色** - 定义为自由格式的 RGB 值，或者使用拾色器，[具体取决于配置](#container-settings-tab)
* **背景图像**  — 为容器定义背景图像， [取决于配置](#container-settings-tab)
* **ID**  — 此选项允许控制组件在HTML中的唯一标识符。
   * 如果留空，则会自动为您生成唯一ID，并且可以通过检查生成的内容来找到该ID。
   * 如果指定一个 ID，作者有责任确保它是唯一的。
   * 更改ID可能会对CSS产生影响。

### 样式选项卡 {#styles-tab-edit}

电子邮件容器组件支持AEM [样式系统。](/help/get-started/authoring.md#component-styling)

使用下拉菜单选择要应用于该组件的样式。在“编辑”对话框中所做的选择与从组件工具栏中选择的操作效果相同。

必须在 [设计对话框](#design-dialog) 以使选项卡可用。

## “设计”对话框 {#design-dialog}

设计对话框允许模板作者定义内容作者可以使用电子邮件容器组件的选项。

### “允许的组件”选项卡 {#allowed-components-tab}

的 **允许的组件** 选项卡，用于定义内容作者可以将哪些组件作为项目添加到电子邮件容器组件。

的 **允许的组件** 选项卡函数，与 [在模板编辑器中定义布局容器的策略和属性。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)

### “默认组件”选项卡 {#default-components-tab}

的 **默认组件** 选项卡用于定义在容器上放置特定资产类型时向组件添加的组件，类似于 [如何在页面模板中定义默认组件。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)

### “容器设置”选项卡 {#container-settings-tab}

的 **容器设置** 选项卡定义作者是否可以定义背景图像或颜色。

![电子邮件容器组件设计对话框的“容器设置”选项卡](/help/email/assets/email-container-design-container-settings.png)

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
   * **重新排列**  — 点按或单击并拖动以重新排序色板。

### 样式选项卡 {#styles-tab}

电子邮件容器组件支持AEM [样式系统。](/help/get-started/authoring.md#component-styling)