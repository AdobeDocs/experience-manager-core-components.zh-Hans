---
title: 表单容器组件
description: 核心组件表单容器组件允许创建简单的提交表单。
role: Architect, Developer, Administrator, Business Practitioner
exl-id: 552f9dd5-6a3a-42d9-9969-e62a1f36e811
source-git-commit: 8ff36ca143af9496f988b1ca65475497181def1d
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 2%

---

# 表单容器组件{#form-container-component}

核心组件表单容器组件允许创建简单的提交表单。

## 使用 {#usage}

表单容器组件支持简单的WCM表单，并使用嵌套结构允许其他表单组件，从而构建简单信息提交表单和功能。

通过使用[配置对话框](#configure-dialog)，内容编辑器可以定义由表单提交触发的操作、应处理提交的URL以及是否应触发工作流。 模板作者可以使用[设计对话框](#design-dialog)定义允许的组件及其映射，这与模板编辑器](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)中[标准布局容器的设计对话框类似。

>[!NOTE]
>
>表单容器组件的核心组件仅支持使用核心组件表单组件（按钮、文本、隐藏等）。 不支持在核心组件表单容器内使用[基础组件](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/siteandpage/default-components-foundation.html)表单组件（反之亦然）。

## 版本和兼容性{#version-and-compatibility}

表单容器组件的当前版本为v2,2018年1月核心组件2.0.0版中引入了v2，本文档对此进行了描述。

下表详细列出了组件的所有受支持版本、组件版本与之兼容的AEM版本，以及指向以前版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v2 | 兼容 | 兼容 | 兼容 |
| [v1](/help/components/v1/form-container-v1.md) | 兼容 | 兼容 | - |

有关核心组件版本和版本的更多信息，请参阅文档[核心组件版本](/help/versions.md)。

## 组件输出示例{#sample-component-output}

要体验表单容器组件以及其配置选项以及HTML和JSON输出的示例，请访问[组件库](https://adobe.com/go/aem_cmp_library_form_container)。

## 技术详细信息{#technical-details}

有关表单容器组件[的最新技术文档，请参阅GitHub](https://adobe.com/go/aem_cmp_tech_form_container_v2)。

有关开发核心组件的更多详细信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## 配置对话框{#configure-dialog}

配置对话框允许内容作者定义在提交组件时执行的操作。

根据所选的&#x200B;**操作类型**，容器中的可用选项将发生更改。 可用的操作类型包括：

* [帖子表单数据](#post-data)
* [邮件](#mail)
* [存储内容](#store-content)

无论类型如何，都有[常规设置](#general-settings)适用于每个操作。

### 表单数据{#post-data}

提交表单后，帖子表单数据操作类型会将提交的数据作为JSON传递给第三方以进行处理。

![表单容器组件的编辑对话框中的“表单后数据”选项](/help/assets/form-container-edit-post.png)

* **端点**  — 将处理数据的完全限定的HTTPS服务
* **错误消息**  — 在提交失败时显示的消息

>[!TIP]
>系统管理员可以调整其他超时选项以处理转发的表单数据。 [有关更多信息，请参阅GitHub技术文档。](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/actions/rpc)

### 邮件 {#mail}

提交表单后，邮件操作类型将向指定收件人发送电子邮件。

![表单容器组件的编辑对话框中的邮件选项](/help/assets/form-container-edit-mail.png)

* **主题**  — 在提交表单时发送的电子邮件的主题
* **发件人**  — 将在表单提交时发送的电子邮件的发件人电子邮件地址
* **收件人**  — 提交表单后将收到电子邮件的收件人的地址
   * 点按或单击&#x200B;**Add**&#x200B;按钮以添加其他地址
   * 点按或单击&#x200B;**Delete**&#x200B;按钮以删除电子邮件地址
* **抄送**  — 将收到表单提交时发送的电子邮件副本的收件人的地址
   * 点按或单击&#x200B;**Add**&#x200B;按钮以添加其他地址
   * 点按或单击&#x200B;**Delete**&#x200B;按钮以删除电子邮件地址

### 存储内容 {#store-content}

提交表单后，表单的内容将存储在指定的存储库位置。

![在表单容器的编辑对话框中存储内容选项](/help/assets/form-container-edit-store.png)

* **内容路径**  — 存储了已提交内容的内容存储库路径
* **查看数据**  — 点按或单击，以JSON形式查看存储的已提交数据
* **启动工作流**  — 配置以在表单提交时将存储的内容作为有效负荷来启动工作流

>[!NOTE]
>
>为了简化用户数据管理并强制区分问题，通常不建议在存储库内存储用户生成的内容。
>
>请改用[表单后数据](#post-data)操作类型将用户内容传递到专用服务提供商。

### 常规设置 {#general-settings}

无论选择何种操作类型，都始终可以定义感谢页面。

![表单容器组件的编辑对话框中的常规选项](/help/assets/form-container-edit-general.png)

* **感谢页面**  — 在表单提交完成后，用户将被重定向到指定的页面。
   * 使用选择对话框在AEM中选择资源。
   * 如果感谢页面不在AEM中，请指定绝对URL。 非绝对URL将被解释为相对于AEM。
   * 留空可在提交后重新显示表单。
* **ID**  — 利用此选项，可控制HTML和数据层中组件的唯一标识符 [的唯一标识符](/help/developing/data-layer/overview.md)。
   * 如果留为空白，则会自动为您生成唯一ID，并且可以通过检查生成的页面找到该ID。
   * 如果指定了ID，则作者有责任确保该ID是唯一的。
   * 更改ID可能会影响CSS、JS和数据层跟踪。

## 设计对话框{#design-dialog}

设计对话框允许模板作者为容器定义允许的组件及其映射，类似于模板编辑器](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)中[标准布局容器的设计对话框。

### 样式选项卡{#styles-tab}

表单容器组件支持AEM [样式系统](/help/get-started/authoring.md#component-styling)。
