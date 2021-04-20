---
title: 表单容器组件(v1)
description: 核心组件表单容器组件允许创建简单的提交表单。
index: n
role: Architect, Developer, Administrator, Business Practitioner
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '643'
ht-degree: 3%

---


# 表单容器组件(v1){#form-container-component-v1}

核心组件表单容器组件允许创建简单的提交表单。

## 使用 {#usage}

表单容器组件支持简单的WCM表单，并使用嵌套结构允许其他表单组件，从而支持构建简单的信息提交表单和功能。

通过使用[设置对话框](#settings-dialog)，内容编辑器可以定义触发何种类型的操作表单提交、在何处存储提交的内容以及是否应触发工作流。 模板作者可以使用[设计对话框](#design-dialog)定义允许组件及其映射，该对话框类似于模板编辑器](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/templates.html)中[标准布局容器的设计对话框。

## 版本和兼容性{#version-and-compatibility}

本文档描述了表单容器组件的v1，该组件最初随AEM 6.3的核心组件版本1.0.0引入。

下表列表了表单容器组件v1的兼容性。

| AEM 版本 | 表单容器组件v1 |
|--- |--- |
| 6.3 | 兼容 |
| 6.4 | 兼容 |

>[!CAUTION]
>
>本文档描述了表单容器组件的v1。
>
>有关表单容器组件当前版本的详细信息，请参阅[表单容器组件](/help/components/forms/form-container.md)文档。

## 设置对话框{#settings-dialog}

设置对话框允许内容作者定义提交组件时要执行的操作。

![](/help/assets/chlimage_1.png)

根据所选&#x200B;**操作类型**,容器中的可用选项将发生更改。 可用的操作类型有：

* [邮件](#mail)
* [存储内容](#store-content)
* [提交订单](#submit-order)
* [更新订单](#update-order)

无论类型如何，都有[常规设置](#general-settings)适用于每个操作。

### 邮件 {#mail}

提交表单后，邮件操作类型将向指定的收件人发送电子邮件。

![](/help/assets/chlimage_1-1.png)

* **主题**  — 提交表单时将发送的电子邮件的主题
* **发件人**  — 在提交表单时将发送的电子邮件的发件人电子邮件地址
* **收件人**  — 提交表单后将收到电子邮件的收件人的地址
   * 点按或单击&#x200B;**添加**&#x200B;按钮以添加其他地址
   * 点按或单击&#x200B;**删除**&#x200B;按钮以删除电子邮件地址
* **CC**  — 收到提交表单时发送的电子邮件的碳副本的收件人地址
   * 点按或单击&#x200B;**添加**&#x200B;按钮以添加其他地址
   * 点按或单击&#x200B;**删除**&#x200B;按钮以删除电子邮件地址

### 存储内容 {#store-content}

提交表单后，表单的内容将存储在指定的存储库位置。

![](/help/assets/chlimage_1-2.png)

* **内容路径**  — 存储已提交内容的内容存储库路径
* **视图数据**  — 点按或单击可将存储的已提交数据视图为JSON
* **开始工作流**  — 配置以在表单提交时将存储内容作为有效负荷开始工作流

### 提交订单 {#submit-order}

提交表单后，将提交订单。

![](/help/assets/chlimage_1-3.png)

### 更新订单 {#update-order}

提交表单后，订单将更新。

![](/help/assets/chlimage_1-4.png)

### 常规设置 {#general-settings}

无论选择何种操作类型，始终都可以定义感谢页面。

![](/help/assets/chlimage_1-5.png)

在表单提交完成后，用户将被重定向到指定页面。

* 使用选择对话框在AEM中选择资源。
* 如果感谢页面不在AEM中，请指定绝对URL。 非绝对URL将解释为相对于AEM。
* 留空可在提交后重新显示表单。

## 设计对话框{#design-dialog}

设计对话框允许模板作者为容器定义允许的组件及其映射，这与模板编辑器](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/templates.html#main-pars_title_1754153843)中[标准布局容器的设计对话框类似。

## 技术详细信息{#technical-details}

有关表单容器组件[的最新技术文档可在GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/container/v1/container)上找到。

整个核心组件项目可从GitHub下载。

有关开发核心组件的更多详细信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。
