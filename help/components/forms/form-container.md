---
title: 表单容器组件
description: 利用核心组件表单容器组件，可以创建简单提交表单。
role: Architect, Developer, Admin, User
exl-id: 552f9dd5-6a3a-42d9-9969-e62a1f36e811
source-git-commit: 9767a3a10cb9a77f385edc0ac3fb00096c0087af
workflow-type: ht
source-wordcount: '954'
ht-degree: 100%

---

# 表单容器组件 {#form-container-component}

利用核心组件表单容器组件，可以创建简单提交表单。

## 用途 {#usage}

利用表单容器组件，可支持简单的 WCM 表单并使用嵌套结构来允许其他表单组件，从而构建简单信息提交表单和功能。

通过使用[“配置”对话框](#configure-dialog)，内容编辑者可以定义由表单提交触发的操作、将处理提交的 URl 以及是否应触发工作流。模板作者可使用[“设计”对话框](#design-dialog)定义允许的组件及其映射，这与[模板编辑器中的标准布局容器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)的“设计”对话框类似。

>[!NOTE]
>
>核心组件表单容器组件仅支持使用核心组件表单组件（按钮、文本、隐藏等）。不支持使用核心组件表单容器中的[基础组件](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/siteandpage/default-components-foundation.html)表单组件，反之亦然。

## 版本和兼容性 {#version-and-compatibility}

表单容器组件的当前版本是 v2，此版本随 2018 年 1 月的核心组件 2.0.0 版的发布引入，具体说明见本文。

下表详细说明了该组件的所有受支持版本、与该组件的版本兼容的 AEM 版本以及指向早期版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v2 | 兼容<br>[版本 2.17.4](/help/versions.md) 和更低版本 | 兼容 | 兼容 |
| [v1](/help/components/v1/form-container-v1.md) | 兼容 | 兼容 | - |

有关核心组件版本的更多信息，请参阅文档[核心组件版本](/help/versions.md)。

## 示例组件输出 {#sample-component-output}

要体验表单容器组件并查看其配置选项示例以及 HTML 和 JSON 输出，请访问[组件库](https://adobe.com/go/aem_cmp_library_form_container_cn)。

## 技术详细信息 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_form_container_v2_cn)有关表单容器组件的最新技术文档。

在[核心组件开发人员文档](/help/developing/overview.md)中可找到有关开发核心组件的其他详细信息。

## “配置”对话框 {#configure-dialog}

利用“配置”对话框，内容作者可以定义在提交组件时执行的操作。

容器中的可用选项因选定的&#x200B;**操作类型**&#x200B;而异。可用的操作类型为：

* [发布表单数据](#post-data)
* [邮件](#mail)
* [存储内容](#store-content)

不管类型如何，都有适用于每种操作的[常规设置](#general-settings)。

### 发布表单数据 {#post-data}

在提交表单时，发布表单数据操作类型会将提交的数据作为 JSON 传递给第三方以供处理。

![表单容器组件的“编辑”对话框中的发布表单数据选项](/help/assets/form-container-edit-post.png)

* **端点** - 将处理数据的完全限定的 HTTPS 服务
* **错误消息** - 提交失败时显示的消息

>[!TIP]
>提供了一些额外的超时选项，系统管理员可以调整这些选项来处理转发的表单数据。[有关更多信息，请参阅 GitHub 上的技术文档。](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/actions/rpc)

### 邮件 {#mail}

在提交表单时，邮件操作类型将向指定收件人发送电子邮件。

![表单容器组件的“编辑”对话框中的邮件选项](/help/assets/form-container-edit-mail.png)

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

![表单容器的“编辑”对话框中的存储内容选项](/help/assets/form-container-edit-store.png)

* **内容路径** - 用于存储所提交内容的内容存储库路径
* **查看数据** - 点击或单击此项可查看以 JSON 格式存储的已提交数据
* **启动工作流** - 配置此项可在提交表单时启动工作流并将存储的内容作为有效负载

>[!NOTE]
>
>为了进一步简化用户数据的管理和强制实施关注分离，通常建议不要将用户生成的内容存储在存储库中。
>
>改用[发布表单数据](#post-data)操作类型将用户内容传递给专用服务提供程序。

### 常规设置 {#general-settings}

无论选择的操作类型如何，始终能定义感谢页面。

![表单容器组件的“编辑”对话框中的常规选项](/help/assets/form-container-edit-general.png)

* **感谢页面** - 在提交完表单后，用户将被重定向到指定的页面。
   * 使用“选择”对话框可在 AEM 中选择资源。
   * 如果感谢页面未在 AEM 中，请指定绝对 URL。非绝对 URL 将解释为相对于 AEM。
   * 留空可在提交后重新显示表单。
* **ID** - 利用此选项，可以控制 HTML 和[ Data Layer ](/help/developing/data-layer/overview.md)中的组件的唯一标识符。
   * 如果留空，系统会自动为您生成一个唯一 ID，可以通过检查结果页面找到该 ID。
   * 如果指定一个 ID，作者有责任确保它是唯一的。
   * 更改此 ID 会对 CSS、JS 和 Data Layer 跟踪产生影响。

## “设计”对话框 {#design-dialog}

利用“设计”对话框，模板作者可为容器定义允许的组件及其映射，这与[模板编辑器中的标准布局容器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)的“设计”对话框类似。

### “样式”选项卡 {#styles-tab}

表单容器组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。
