---
title: 表单容器组件 (v1)
description: 利用核心组件表单容器组件，可以创建简单提交表单。
index: n
role: Architect, Developer, Admin, User
exl-id: 1e34219f-fa82-494e-82e2-1b4d63d37fea
source-git-commit: 92a3ec273a5be6751c1503835b9c2e5cbd61bb9e
workflow-type: ht
source-wordcount: '609'
ht-degree: 100%

---


# 表单容器组件 (v1) {#form-container-component-v1}

利用核心组件表单容器组件，可以创建简单提交表单。

## 用途 {#usage}

利用表单容器组件，可支持简单的 WCM 表单并使用嵌套结构来允许其他表单组件，从而构建简单信息提交表单和功能。

通过使用[“设置”对话框](#settings-dialog)，内容编辑者可以定义由表单提交触发的操作的类型、提交的内容的存储位置以及是否应触发工作流。模板作者可使用[“设计”对话框](#design-dialog)定义允许的组件及其映射，这与[模板编辑器中的标准布局容器](https://helpx.adobe.com/cn/experience-manager/6-4/sites/authoring/using/templates.html)的“设计”对话框类似。

## 版本和兼容性 {#version-and-compatibility}

本文档介绍了表单容器组件 (v1)，它最初随带 AEM 6.3 的核心组件 1.0.0 版引入。

下表列出了表单容器组件 (v1) 的兼容性。

| AEM 版本 | 表单容器组件 v1 |
|--- |--- |
| 6.3 | 兼容 |
| 6.4 | 兼容 |

>[!CAUTION]
>
>本文档介绍了表单容器组件 (v1)。
>
>有关当前版本的表单容器组件的详细信息，请参阅[表单容器组件](/help/components/forms/form-container.md)文档。

## “设置”对话框 {#settings-dialog}

利用“设置”对话框，内容作者可以定义在提交组件时执行的操作。

![](/help/assets/chlimage_1.png)

容器中的可用选项因选定的&#x200B;**操作类型**&#x200B;而异。可用的操作类型为：

* [邮件](#mail)
* [存储内容](#store-content)
* [提交订单](#submit-order)
* [更新订单](#update-order)

不管类型如何，都有适用于每种操作的[常规设置](#general-settings)。

### 邮件 {#mail}

在提交表单时，邮件操作类型将向指定收件人发送电子邮件。

![](/help/assets/chlimage_1-1.png)

* **主题** - 在提交表单时将发送的电子邮件的主题
* **发件人** - 在提交表单时将发送的电子邮件的发件人电子邮件地址
* **收件人** - 在提交表单时将接收电子邮件的收件人的电子邮件地址
   * 点击或单击&#x200B;**“添加”**&#x200B;按钮可添加其他地址
   * 点击或单击&#x200B;**“删除”**&#x200B;按钮可删除电子邮件地址
* **抄送** - 将接收在提交表单时发送的电子邮件的副本的收件人地址
   * 点击或单击&#x200B;**“添加”**&#x200B;按钮可添加其他地址
   * 点击或单击&#x200B;**“删除”**&#x200B;按钮可删除电子邮件地址

### 存储内容 {#store-content}

在提交表单时，表单内容将存储在指定的存储库位置。

![](/help/assets/chlimage_1-2.png)

* **内容路径** - 用于存储所提交内容的内容存储库路径
* **查看数据** - 点击或单击此项可查看以 JSON 格式存储的已提交数据
* **启动工作流** - 配置此项可在提交表单时启动工作流并将存储的内容作为有效负载

### 提交订单 {#submit-order}

在提交表单时，将提交订单。

![](/help/assets/chlimage_1-3.png)

### 更新订单 {#update-order}

在提交表单时，将更新订单。

![](/help/assets/chlimage_1-4.png)

### 常规设置 {#general-settings}

无论选择的操作类型如何，始终能定义感谢页面。

![](/help/assets/chlimage_1-5.png)

在提交完表单后，用户将被重定向到指定的页面。

* 使用“选择”对话框可在 AEM 中选择资源。
* 如果感谢页面未在 AEM 中，请指定绝对 URL。非绝对 URL 将解释为相对于 AEM。
* 留空可在提交后重新显示表单。

## “设计”对话框 {#design-dialog}

利用“设计”对话框，模板作者可为容器定义允许的组件及其映射，这与[模板编辑器中的标准布局容器](https://helpx.adobe.com/cn/experience-manager/6-4/sites/authoring/using/templates.html#main-pars_title_1754153843)的“设计”对话框类似。

## 技术详细信息 {#technical-details}

[在 GitHub 上可找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/container/v1/container)有关表单容器组件的最新技术文档。

从 GitHub 可下载整个核心组件项目。

在[核心组件开发人员文档](/help/developing/overview.md)中可找到有关开发核心组件的其他详细信息。
