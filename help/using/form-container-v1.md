---
title: 表单容器组件(v1)
seo-title: 表单容器组件(v1)
description: 核心组件表单容器组件允许创建简单提交表单。
seo-description: 核心组件表单容器组件允许创建简单提交表单。
uuid: 075d83ed-de40-414e-a18 f-46b3 a857 acba
content-type: 引用
products: SG_ EXPERIENCE MANAGER/CORECOMMPANES-new
discoiquuid: 800c064e-2ad5-41f3-9cf-b025 a555 efd9
index: n
translation-type: tm+mt
source-git-commit: 4e74f10e2a4119484a597178dc4577b399833dbf

---


# 表单容器组件(v1){#form-container-component-v}

核心组件表单容器组件允许创建简单提交表单。

## 使用情况 {#usage}

表单容器组件通过支持简单的WCM表单并使用嵌套结构允许更多表单组件，从而支持构建简单的信息提交表单和功能。

通过使用 [设置对话框，](form-container-v1.md#main-pars_title) 内容编辑器可以定义提交触发器的类型、提交的内容应存储在何处以及是否应触发工作流。模板作者可以使用 [设计对话框](form-container-v1.md#main-pars_title_1995166862) 定义允许组件及其映射的映射，这些组件与模板编辑器中 [标准布局容器的设计对话框类似](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/templates.html#main-pars_title_1754153843)。

## 版本和兼容性 {#version-and-compatibility}

本文档描述了表单容器组件的v1，该组件最初随AEM6.3的核心组件版本1.0.0一起引入。

下表列出了表单容器组件的v兼容性。

| AEM 版本 | 表单容器组件v1 |
|--- |--- |
| 6.3 | 兼容 |
| 6.4 | 兼容 |

>[!CAUTION]
>
>本文档描述表单容器组件的v1。
>
>有关表单容器组件的当前版本的详细信息，请参阅 [表单容器组件](form-container.md) 文档。

## 设置对话框 {#settings-dialog}

设置对话框允许内容作者定义提交组件时采取的操作。

![](assets/chlimage_1.png)

根据所选 **的操作类型**，容器中的可用选项将会更改。可用的操作类型有：

* [邮件](form-container-v1.md#main-pars_title_966511656)
* [存储内容](form-container-v1.md#main-pars_title_2065985840)
* [提交订单](form-container-v1.md#main-pars_title_686874527)
* [更新订单](form-container-v1.md#main-pars_title_410109286)

无论类型如何，都有适用于每个操作的 [通用设置](form-container-v1.md#main-pars_title_375403046) 。

### 邮件 {#mail}

提交表单后，邮件操作类型将发送电子邮件给指定收件人。

![](assets/chlimage_1-1.png)

* **主题** -将在表单提交时发送的电子邮件主题
* **发件人** -将在表单提交时发送的电子邮件地址
* **收件人** -在表单提交时将收到电子邮件的收件人的地址
   * 点按或单击 **添加** 按钮以添加其他地址
   * 点按或单击 **删除** 按钮以删除电子邮件地址
* **CC** -将收到表单提交时发送的电子邮件的收件人地址的地址
   * 点按或单击 **添加** 按钮以添加其他地址
   * 点按或单击 **删除** 按钮以删除电子邮件地址

### 存储内容 {#store-content}

提交表单后，表单的内容将存储在指定的存储库位置。

![](assets/chlimage_1-2.png)

* **内容路径** -存储提交内容的内容存储库路径
* **查看数据** -点按或单击以查看将已提交的提交数据视为JSON
* **启动工作流** -配置为在表单提交时使用存储的内容作为有效负荷启动工作流

### 提交订单 {#submit-order}

提交表单后，将提交订单。

![](assets/chlimage_1-3.png)

### 更新订单 {#update-order}

提交表单后，订单将更新。

![](assets/chlimage_1-4.png)

### 常规设置 {#general-settings}

无论选择了何种操作类型，都可以始终定义感谢页面。

![](assets/chlimage_1-5.png)

表单提交完成后，用户将被重定向到指定页面。

* 使用选择对话框在AEM中选择一个资源。
* 如果感谢页面未在AEM中，请指定绝对URL。非绝对URL将相对于AEM进行解释。
* 留空可在提交后重新显示表单。

## 设计对话框 {#design-dialog}

设计对话框允许模板作者为容器定义允许的组件及其映射，该容器类似于模板编辑器中 [标准布局容器的设计对话框](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/templates.html#main-pars_title_1754153843)。

## 技术详细信息 {#technical-details}

有关表单容器组件 [的最新技术文档，请参阅GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/container/v1/container)。

可以从GitHub下载整个核心组件项目。

有关开发核心组件的更多详细信息，请参阅 [核心组件开发人员文档](developing.md)。
