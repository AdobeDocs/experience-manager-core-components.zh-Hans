---
title: 自适应表单核心组件 - 表单容器
description: 将自适应表单添加到网页。
role: Architect, Developer, Admin, User
source-git-commit: 945e1793ae4e959f83960db46d2de4257916fe32
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 100%

---


# 表单容器 {#form-container-adaptive-forms-core-component}

通过表单，网站访客可与网站交互，提供宝贵的信息，这样即可提高参与度和用户满意度。利用 Adobe Experience Manager (AEM) Sites 中的自适应表单容器，网站所有者可以轻松地将表单添加到其页面。这样通过一种简化的方式供访客提供反馈、进行查询和完成其他操作，有助于促进网站访客与网站所有者或组织之间的交流

## 用途 {#reasons-to-use-forms-container}

有若干原因可将表单添加到网站：

* **数据收集**：表单可用于从网站访客收集数据作各种用途，如市场调查、用户行为分析等。

* **商机开发**：表单可用于从潜在客户收集姓名和电子邮件地址等信息，以便为销售和营销工作开发商机。

* **电子商务**：表单可用于在线购物，使客户可通过网站下订单和付款。

* **联系方式**：通过联系方式表单，网站访客可轻松地与网站所有者或组织取得联系。

* **调查和投票**：表单可用于通过调查和投票收集网站访客的反馈和意见。

* **活动注册**：表单可用于活动注册，从而使网站访客能够注册活动或网络研讨会。

* **订阅**：表单可用于网站订阅，从而使访客能够注册新闻稿或其他定期通讯。

* **用户身份验证**：表单可用于用户身份验证，从而使网站访客能够创建帐户并登录以访问专有内容或功能。

* **提高转化率**：设计良好的表单可让用户轻松完成所需操作（例如，购买产品或注册服务），从而提高转化率。


## 版本和兼容性 {#version-and-compatibility}

2023 年 2 月，作为核心组件 2.0.4 的一部分发布了自适应表单容器核心组件。下表展示所有支持的版本、AEM 兼容性和相应文档的链接：

|  |  |
|---|---|
| 组件版本 | AEM as a Cloud Service |
| --- | --- |
| v1 | 兼容<br>[版本 2.0.4](/help/versions.md) 和更高版本 | 兼容 | 兼容 |

有关核心组件版本的信息，请参阅[核心组件版本](/help/versions.md)文档。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技术详细信息 {#technical-details}

可在 [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/container/v1/container) 上的技术文档中获得关于自适应表单容器核心组件的最新信息。有关开发核心组件的更多信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## “配置”对话框 {#configure-dialog}

通过“配置”对话框，可轻松地自定义您为访客提供的表单容器体验。还可轻松地定义表单容器选项，从而营造一种无缝的用户体验。

### “基本”选项卡 {#basic-tab}

![“基本”选项卡](/help/adaptive-forms/assets/formcontainer_basictab.png)

* **预填充服务** - 通过此选项，用户可选择一项预填充服务以供在呈现自适应表单时检索数据。详细了解[如何创建和配置预填充服务](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/prepopulate-adaptive-form-fields.html?lang=zh-Hans#aem-forms-custom-prefill-service)。

* **客户端库类别** - 用户可以为每个自适应表单配置自定义 JavaScript 库。建议只保留库中可重用的函数，这些函数依赖 jquery 和 underscore.js 第三方库。

### “提交”选项卡 {#submission-tab}

![“提交”选项卡](/help/adaptive-forms/assets/formcontainer_submissiontab.png)

用户可以为自适应表单提交配置不同的操作。

* **重定向 URL/路径** - 通过此选项，用户可为每个表单配置一个页面，表单用户在提交自适应表单后将被重定向到该页面。单击此处以详细了解[如何配置重定向页面](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-redirect-page.html)。

![“显示消息”选项卡](/help/adaptive-forms/assets/formconatiner_showmessage.png)

* **显示消息** - 通过此选项，用户可添加在成功提交自适应表单时显示的消息。对话框中包括预定义的文本，并且用户可修改这些文本。“显示消息”对话框支持富文本格式化工具，通过这些功能，用户可为所添加的文本设置格式。

* **提交操作** - 当用户单击自适应表单上的“提交”按钮时将触发提交操作。用户可以从下拉列表中选择受支持的现有提交操作。了解如何[在“提交”选项卡中配置提交操作](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html#supporting-custom-functions-in-validation-expressions-br)。




