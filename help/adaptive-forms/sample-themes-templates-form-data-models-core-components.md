---
title: 如何获取 AEM Forms 核心组件的示例主题和模板？
description: AEM Forms 核心组件提供自适应表单主题、模板和表单数据模型的示例。
solution: Experience Manager Forms
topic: Administration
role: Admin, User
level: Intermediate
exl-id: aef6e88b-dcae-4777-9893-9257d7702f43
source-git-commit: 6725784bd4c94d433c91d6bd65d14d03cbefd954
workflow-type: tm+mt
source-wordcount: '1239'
ht-degree: 100%

---

# 主题、模板和表单数据模型的示例 {#sample-themes-templates-and-data-models}

[!DNL AEM Forms] 核心组件提供主题、模板和表单数据模型的即用型示例以快速地创建多用途的自适应表单。这些组件还帮助表单作者了解[自适应表单核心组件](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/adaptive-forms/introduction.html?lang=zh-Hans)的可扩展性、适应性和响应能力，从而立即创建简单表单并在与数据库无缝连接的同时轻松创建复杂表单。

参考内容包中包含的示例主题、模板和表单数据模型为：

| 模板 | 主题 | 表单数据模型 |
---------|----------|---------
| [空白](#Blank) | [画布](#Canvas) | Microsoft® Dynamics 365 |
| [联系我们](#Contact-Us) | [WKND](#WKND) | Salesforce |
| [联系详细信息更新](#Contact-Details-Update) | [画架](#Easel) |   |
| [同意表单](#Consent-Form) | [FSI](#FSI) |  |
| [日志服务请求](#Log-Service-Request) | [医疗保健](#Healthcare) |  |
| [提供反馈](#Give-Feedback) |  |  |
| [福利登记](#Benefits-Enrollment) |  |   |
| [员工福利摘要](#Employee-Benefits-Summary) |   |   |
| [索取帐户对账单](#Request-for-Account-Statement) |   |   |
| [安全检查表](#Safety-Inspection) |   |   |
| [质量控制检验](#Quality-Control-Inspection) |   |   |
| [购买请求](#Purchase-Request) |  |  |

{{traditional-aem}}

## 示例主题 {#Sample-Themes}

参考示例主题帮助作者使用表单、定义表单和自定义其样式，作者只需大致了解 CSS 即可根据要求自定义主题。

**如何获取这些主题？**
按照下方为 **AEM as a Cloud Service** 环境给出的以下步骤获取这些主题：

1. [启用自适应表单核心组件](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/setup-configure-migrate/enable-adaptive-forms-core-components.html?lang=zh-Hans)
1. [将 AEM Archetype 47 项目或更高版本部署到您的环境](https://github.com/adobe/aem-project-archetype)


在部署 AEM Archetype 时，您只能在表单中使用 OOTB 主题。要根据您的要求自定义这些主题，请[使用前端管道](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/using-themes-in-core-components.html?lang=zh-Hans)部署这些主题。

>[!NOTE]
>
> * 对于 **AEM 6.5** 环境无这些主题可用。

<!--

1. **AEM 6.5**

    1. [Enable Adaptive Form Core Components](https://experienceleague.adobe.com/docs/experience-manager-65/forms/adaptive-forms-core-components/enable-adaptive-forms-core-components.html?lang=zh-Hans)
    1. [Deploy an AEM Archetype 47 or later project to your environment](https://github.com/adobe/aem-project-archetype)


    When you deploy an AEM Archetype, you can only use the OOTB themes in your forms, To customize the themes as per your requirements, [Use the front-end pipeline](https://experienceleague.adobe.com/docs/experience-manager-65/forms/adaptive-forms-core-components/create-or-customize-themes-for-adaptive-forms-core-components.html?lang=zh-Hans) to deploy the themes.

-->


<!--

### Deploying an AEM Archetype 47 or later project to your environment {#using-archetype-to-deploy-themes}

You can get these themes by deploying an [AEM Archetype 47 or later](https://github.com/adobe/aem-project-archetype) to your **AEM Forms as a Cloud Service** or **AEM 6.5** Forms environment.

### Enable core components and use front-end pipeline to deploy themes {#use-front-end-pipeline-to-deploy-themes}

1. To get these themes on **Forms as a Cloud Service** environment, [enable Adaptive Forms Core Components](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/setup-configure-migrate/enable-adaptive-forms-core-components.html?lang=zh-Hans) and use the [front-end pipeline](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/using-themes-in-core-components.html?lang=zh-Hans) to deploy these themes.
    
1. To get these themes on **AEM 6.5 Forms** environment, [enable Adaptive Forms Core Components](https://experienceleague.adobe.com/docs/experience-manager-65/forms/adaptive-forms-core-components/enable-adaptive-forms-core-components.html?lang=zh-Hans) and use the [Package Manager](https://experienceleague.adobe.com/docs/experience-manager-65/forms/adaptive-forms-core-components/create-or-customize-themes-for-adaptive-forms-core-components.html?lang=zh-Hans) to deploy these themes.

[Learn to use and customize themes in AEM Forms as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/using-themes-in-core-components.html?lang=zh-Hans). 

[Learn to use and customize themes in AEM 6.5](https://experienceleague.adobe.com/docs/experience-manager-65/forms/adaptive-forms-core-components/create-or-customize-themes-for-adaptive-forms-core-components.html?lang=zh-Hans).

-->

**现成的**[自适应表单核心组件](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/adaptive-forms/introduction.html?lang=zh-Hans)主题为：

![OOTB 主题](/help/adaptive-forms/assets/archetype-45-themes-1.png)

### 画布 {#Canvas}

画布主题是表单的默认主题，它突出对基本颜色、透明度和扁平图标的使用。在下面的屏幕快照中，您可以看到画布主题的外观。

![画布主题](/help/adaptive-forms/assets/Safety-Inspection-Theme-Canvas.png)

### WKND {#WKND}

WKND 主题体现了生动、富有想象力和引人入胜的设计，为您的表单展示了时尚的外观。该主题基于 [WKND 站点](https://wknd.site/us/en.html)的外观和样式，后者是一个基于 [Adobe Experience Manager 核心组件](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/adaptive-forms/introduction.html?lang=zh-Hans)构建的旅游和冒险网站。

![WKND 主题](/help/adaptive-forms/assets/Safety-Inspection-Form-Theme.png)


### 画架 {#Easel}

画架主题可帮助创建有吸引力且易于设置的表单外观，可自定义此外观以实现简单性和用户友好性。画架主题以画家在创作其画作时使用便携式支架支撑画布的概念为基础。

![画架主题](/help/adaptive-forms/assets/Safety-Inspection-Theme-Easel.png)

### FSI（金融服务和保险） {#FSI}

FSI 主题强调让您的表单看起来简洁实用。在应用 FSI 主题时将淡蓝色应用于您的表单，如您可在图中看到的那样。

![FSI 主题](/help/adaptive-forms/assets/fsi-theme-new1.png)


### 医疗保健 {#Healthcare}

医疗保健主题使用丰富、翠绿的色调突出表单中的选项卡、面板、文本框和按钮等元素。

![医疗保健主题](/help/adaptive-forms/assets/healthcare-new-theme.png)


## 示例模板 {#Sample-templates}

模板定义初始表单结构、内容和要在表单中重复执行的操作，或使用与表单类似的模板结构，例如同意表单、福利登记表单等。

**如何获取这些模板？**

通过将 [AEM Archetype 47 或更高版本](https://github.com/adobe/aem-project-archetype)部署到您的 **AEM Forms as a Cloud Service** 环境或 **AEM 6.5 Forms** 环境即可获取这些模板。

<!--

>[!NOTE]
>
> * If you have [enabled core components and used front-end pipeline to deploy themes](#use-front-end-pipeline-to-deploy-themes), you need not to deploy an AEM Archetype.
> * You can find list of all OOTB templates when you create a form.

-->


**现成的**[自适应表单核心组件](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/adaptive-forms/introduction.html?lang=zh-Hans)模板为：

![参考模板](/help/adaptive-forms/assets/reference-templates-core-components.png)

<!--

### Basic {#Basic}

A basic template helps you quickly create an enrollment experience form. You can also use it to preview the functionality of [Adaptive Forms Core Components](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/adaptive-forms/introduction.html?lang=zh-Hans). It provides a wizard layout for section-by-section presentation of data.

![Basic Template](/help/adaptive-forms/assets/Basic-template-desktop-view.png)

-->

### 空白 {#Blank}

可使用空白画布模板从头开始创建自适应表单结构、内容和规则。空白模板中未预集成任何表单组件。

![空白模板](/help/adaptive-forms/assets/Blank-temp-desktop-view.png)

### 联系我们 {#Contact-Us}

可使用“联系我们”表单模板创建表单，以促进网站访客和表单管理员之间的通信。用户可以通过此表单提交查询、反馈或支持请求。

![“联系我们”模板](/help/adaptive-forms/assets/Contact-us-desktop-view.png)

### 联系详细信息更新 {#Contact-Details-Update}

“联系详细信息更新”模板可帮助作者创建用于更新客户地址和联系详细信息的表单。该表单还可帮助客户更新与订阅或福利相关的个人信息，确保无缝通信和不间断地获取服务或福利。

![Contact-details-update](/help/adaptive-forms/assets/Contact-details-update.png)

### 同意表单 {#Consent-Form}

同意表单模板用于创建表单以从某些参与者获取法律文件，这些参与者参与特定活动、调查研究、医疗过程或任何可能涉及其个人信息或权利的情况。此表单可确保透明度，保护参与者的权利，并清楚地理解个人同意的内容。

![同意表单](/help/adaptive-forms/assets/Consent-form-desktop-view.png)

### 日志服务请求 {#Log-Service-Request}

“日志服务请求”模板可帮助创建一个表单，向服务提供商请求特定于日志的日志服务。该表单充当一个正式请求，其中请求为用于监视或跟踪状态的事件、活动或数据日志创建票证。

![“日志服务请求”模板](/help/adaptive-forms/assets/Log-service-request-desktop-view.png)


### 提供反馈 {#Give-Feedback}

“提供反馈”表单模板可帮助构建一个表单，向其他人员或团队提供建设性反馈。该表单有助于确保反馈明确、具体且可行动，从而促进开放的沟通和改进。

![“提供反馈”模板](/help/adaptive-forms/assets/Give-feedback-desktop-view.png)


### 福利登记 {#Benefits-Enrollment}

可使用“福利登记”表单模板创建一个表单，从员工处收集有关其首选福利和保险范围选项的基本信息。它通常附带了年度福利登记期。

![“福利登记”模板](/help/adaptive-forms/assets/Benefits-enrollment-form-template.png)


### 员工福利摘要 {#Employee-Benefits-Summary}

可使用“员工福利摘要”表单模板创建一个表单来收集有关个人福利的基本详细信息。它有助于快速准确地评估保险范围，并提供有效的帮助和支持的全面概述。
![员工福利摘要](/help/adaptive-forms/assets/Employee-benefits-summary.png)


### 索取帐户对账单 {#Request-for-Account-Statement}

“索取帐户对账单”模板有助于创建一个表单，该表单发起获取准确且最新的客户对账单的过程。该对账单提供了有关使用此表单的客户的金融交易、活动或其他相关信息的详细记录。

![Request-for-account-statment](/help/adaptive-forms/assets/Request-for-account-statment.png)

### 安全检查 {#Safety-Inspection}

可使用“安全检查”表单模板创建一个表单来输入安全工作环境的详细信息。通过使用此表单进行定期检查，可以识别潜在的危险。此表单涵盖了紧急出口、消防安全、电气安全、危险材料、个人防护设备、工作站人体工程学等各个方面，以保障员工、访客和客户的安全和福祉。

![安全检查表](/help/adaptive-forms/assets/Safety-inspection-form.png)

### 质量控制检验 {#Quality-Control-Inspection}

可使用“质量控制检验”表单模板创建一个表单，评估和记录产品或项目的外观、尺寸、功能、文档、测试结果和整体质量。它有助于识别缺陷、不符合项和必要的纠正措施，确保遵守质量标准。

![质量控制检验](/help/adaptive-forms/assets/Quality-Control-Inspection.png)


### 购买请求 {#Purchase-Request}

可使用“购买请求”表单模板构建一个表单来启动采购流程，并让员工正式请求购买其工作所需的商品或服务。此表单包含重要的详细信息，例如物品描述、数量、首选供应商（如果适用）、预算分配、购买理由、交付信息和必需的批准。

![purchase-request-form](/help/adaptive-forms/assets/Purchase-request-form.png)

## 参考表单数据模型 {#reference-models}

在创建基于[核心组件](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/adaptive-forms/introduction.html?lang=zh-Hans)的自适应表单后，可以将表单与数据库 Microsoft® Dynamics 365 和 Salesforce 服务器连接以启用业务工作流。例如：

* 提交自适应表单时，在 Microsoft® Dynamics 365 和 Salesforce 中写入数据。
* 通过表单数据模型中定义的自定义实体在 Microsoft® Dynamics 365 和 Salesforce 中写入数据，反之亦然。
* 查询 Microsoft® Dynamics 365 和 Salesforce 服务器中的数据并预填充自适应表单。
* 读取 Microsoft® Dynamics 365 和 Salesforce 服务器中的数据。

您可以通过安装[参考内容包](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-forms-reference-content.ui.content-2.1.0.zip)来获取以下表单数据模型：

* Microsoft® Dynamics 365
* Salesforce

有关如何使用这些模型的信息，请参阅[配置 Microsoft® Dynamics 365 和 Salesforce 云服务](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/integrate/use-form-data-model/configure-msdynamics-salesforce.html?lang=zh-Hans#configure-dynamics-cloud-service)
