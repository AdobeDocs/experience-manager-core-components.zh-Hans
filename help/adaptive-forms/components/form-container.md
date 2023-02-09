---
title: 自适应Forms核心组件 — 表单容器
description: 向网页中添加自适应表单。
role: Architect, Developer, Admin, User
source-git-commit: 7f680eac1da61b55f9d90db6c0842421d03ac1dc
workflow-type: tm+mt
source-wordcount: '700'
ht-degree: 3%

---


# 表单容器 {#form-container-adaptive-forms-core-component}

Forms允许网站访客通过提供有价值的信息与网站进行交互，从而提高参与度和用户满意度。 Adobe Experience Manager(AEM)站点中的自适应表单容器使网站所有者能够轻松地将表单添加到其页面。 这有助于简化网站访客与网站所有者或组织之间的通信，方法是为访客提供反馈、查询和完成其他操作的简化方式

## 用途 {#reasons-to-use-forms-container}

可以将表单添加到网站的原因有多种：

* **数据收集**:Forms可用于从网站访客收集各种数据，例如市场研究、用户行为分析等。

* **商机拓展**:表单可用于收集潜在客户的信息（如姓名和电子邮件地址），以生成销售和营销工作的潜在客户。

* **电子商务**:Forms可用于在线购物，让客户通过网站下订单和付款。

* **联系人**:通过联系表，网站访客可以轻松联系网站所有者或组织。

* **调查和投票**:Forms可用于通过调查和投票收集网站访客的反馈和意见。

* **事件注册**:Forms可用于活动注册，从而允许网站访客注册活动或网络研讨会。

* **订阅**:Forms可用于网站订阅，允许访客注册新闻稿或其他常规通信。

* **用户身份验证**:Forms可用于用户身份验证，从而允许网站访客创建帐户并登录以访问专有内容或功能。

* **提高转化率**:精心设计的表单可以提高转化率，它使用户能够轻松完成所需的操作，如购买产品或注册服务。


## 版本和兼容性 {#version-and-compatibility}

自适应Forms容器核心组件作为核心组件2.0.4的一部分于2023年2月发布。下面是一个表格，其中显示了所有受支持的版本、AEM兼容性以及指向相应文档的链接：

| 组件版本 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | 兼容 with<br>[版本2.0.4](/help/versions.md) 及更高版本 | 兼容 | 兼容 |

有关核心组件版本和版本的信息，请参阅 [核心组件版本](/help/versions.md) 文档。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技术详细信息 {#technical-details}

在 [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/container/v1/container). 有关开发核心组件的更多信息，请参阅 [核心组件开发人员文档](/help/developing/overview.md).

## “配置”对话框 {#configure-dialog}

您可以使用配置对话框轻松自定义访客的表单容器体验。 您还可以轻松定义表单容器选项，以提供无缝的用户体验。

### 基本选项卡 {#basic-tab}

![“基本”选项卡](/help/adaptive-forms/assets/formcontainer_basictab.png)

* **预填充服务**  — 此选项允许用户在呈现自适应表单时选择用于检索数据的预填充服务。 详细了解 [如何创建和配置预填充服务](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/prepopulate-adaptive-form-fields.html?lang=en#aem-forms-custom-prefill-service).

* **客户端库类别**  — 用户可以根据自适应表单配置自定义JavaScript库。 建议仅保留库中可重用函数，这些函数依赖于jquery和undersore.js第三方库。

### “提交”选项卡 {#submission-tab}

![“提交”选项卡](/help/adaptive-forms/assets/formcontainer_submissiontab.png)

用户可以为自适应表单提交配置不同的操作。
* **重定向URL/路径**  — 此选项允许用户为每个表单配置一个页面，在提交自适应表单后，表单用户将被重定向到该页面。 单击此处了解有关 [如何配置重定向页面](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-redirect-page.html).

![“显示消息”选项卡](/help/adaptive-forms/assets/formconatiner_showmessage.png)

* **显示消息**  — 此选项允许用户添加在自适应表单成功提交时显示的消息。 该预定义文本包含在对话框中，用户可以修改该文本。 “显示消息”对话框支持富文本格式工具，允许用户对添加的文本进行格式设置。

* **提交操作**  — 当用户单击自适应表单上的“提交”按钮时，会触发“提交操作”。 用户可以从支持的下拉列表中选择提交操作。 了解如何 [在“提交”选项卡中配置提交操作](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#supporting-custom-functions-in-validation-expressions-br).

## “设计”对话框 {#design-dialog}



