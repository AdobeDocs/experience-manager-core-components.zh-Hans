---
title: 表单容器组件
description: 核心组件表单容器组件允许创建简单的提交表单。
translation-type: tm+mt
source-git-commit: c186e9ec3944d785ab0376769cf7f2307049a809
workflow-type: tm+mt
source-wordcount: '805'
ht-degree: 3%

---


# 表单容器组件 {#form-container-component}

核心组件表单容器组件允许创建简单的提交表单。

## 使用 {#usage}

表单容器组件支持简单的WCM表单，并使用嵌套结构允许其他表单组件，从而支持构建简单的信息提交表单和功能。

通过使用 [配置对话框](#configure-dialog) ，内容编辑器可以定义由表单提交触发的操作、应在何处存储提交的内容以及是否应触发工作流。 模板作者可以使用设 [计对话框](#design-dialog) ，定义允许的组件及其映射，这与模板编辑器中标准布 [局容器的设计对话框类似](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)。

>[!NOTE]
>
>表单容器组件的核心组件仅支持使用核心组件表单组件（按钮、文本、隐藏等）。 不支持 [在核心组件](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/siteandpage/default-components-foundation.html) （反之亦然）中使用基础组件表单组件。

## 版本和兼容性 {#version-and-compatibility}

表单容器组件的当前版本为v2,2018年1月随核心组件版本2.0.0一起推出，本文档对此进行了说明。

下表详细列出了组件的所有受支持版本、与组件版本兼容的AEM版本以及指向先前版本文档的链接。

| 组件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM 云服务 |
|--- |--- |--- |--- |---|
| v2 | - | 兼容 | 兼容 | 兼容 |
| [v1](/help/components/v1/form-container-v1.md) | 兼容 | 兼容 | 兼容 | - |

有关核心组件版本和版本的详细信息，请参阅文档 [核心组件版本](/help/versions.md)。

## 示例组件输出 {#sample-component-output}

要体验表单容器组件，并查看其配置选项以及HTML和JSON输出的示例，请访问组件 [库](https://adobe.com/go/aem_cmp_library_form_container)。

## 技术详细信息 {#technical-details}

有关表单容器组件的最 [新技术文档可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_form_container_v2)。

有关开发核心组件的更多详细信息，请参阅核 [心组件开发人员文档](/help/developing/overview.md)。

## 配置对话框 {#configure-dialog}

配置对话框允许内容作者定义提交组件时要执行的操作。

根据所选的操 **作类型**,容器中的可用选项将发生变化。 可用的操作类型有：

* [邮件](#mail)
* [存储内容](#store-content)

无论类型如何，都有适 [用于每](#general-settings) 个操作的常规设置。

### 邮件 {#mail}

提交表单后，邮件操作类型将向指定收件人发送电子邮件。

![表单容器组件编辑对话框中的邮件选项](/help/assets/form-container-edit-mail.png)

* **主题** -提交表单时将发送的电子邮件的主题
* **发件人** -提交表单时将发送的电子邮件的发件人电子邮件地址
* **收件人** -提交表单后将收到电子邮件的收件人的地址
   * 点按或单击添 **加按** 钮以添加其他地址
   * 点按或单击删 **除按钮** ，以删除电子邮件地址
* **CC** —— 收到提交表单时发送的电子邮件的碳副本的收件人的地址
   * 点按或单击添 **加按** 钮以添加其他地址
   * 点按或单击删 **除按钮** ，以删除电子邮件地址

### 存储内容 {#store-content}

提交表单后，表单的内容将存储在指定的存储库位置。

![在表单容器的编辑对话框中存储内容选项](/help/assets/form-container-edit-store.png)

* **内容路径** -存储已提交内容的内容存储库路径
* **视图数据** -点按或单击以将存储的提交数据视图为JSON
* **开始工作流** -配置以在提交表单时将存储的内容作为有效负荷开始工作流

### 常规设置 {#general-settings}

无论选择何种操作类型，始终都可以定义感谢页面。

![表单容器组件编辑对话框中的常规选项](/help/assets/form-container-edit-general.png)

* **感谢页面** -表单提交完成后，用户将被重定向到指定页面。
   * 使用选择对话框在AEM中选择资源。
   * 如果感谢页面不在AEM中，请指定绝对URL。 非绝对URL将解释为相对于AEM。
   * 留空可在提交后重新显示表单。
* **ID** —— 此选项允许控制HTML和数据层中组件的唯一标 [识符](/help/developing/data-layer/overview.md)。
   * 如果留空，则会自动为您生成唯一ID，并可通过检查生成的页面找到该ID。
   * 如果指定了ID，则作者有责任确保它是唯一的。
   * 更改ID可能会影响CSS、JS和数据层跟踪。

## 设计对话框 {#design-dialog}

设计对话框允许模板作者为容器定义允许的组件及其映射，这与模板编辑器中标准布局容器的 [设计对话框类似](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)。

### 样式选项卡 {#styles-tab}

表单容器组件支持AEM [样式系统](/help/get-started/authoring.md#component-styling)。
