---
title: AEM 自适应表单 hCaptcha
description: 使用 hCaptcha 服务轻松增强表单安全性。里面有分步指南！
feature-set: Experience Manager Sites, Experience Manager Forms
feature: Adaptive Forms, Core Components
role: Architect, Developer, Admin, User
exl-id: eecb38d5-711e-4dc5-bc19-498e003f37e7
source-git-commit: 6725784bd4c94d433c91d6bd65d14d03cbefd954
workflow-type: ht
source-wordcount: '583'
ht-degree: 100%

---


# hCaptcha 组件{#hCaptcha-component-adaptive-forms-core-component}

<span class="preview"> 此功能属于 Early Adopter 计划。您可以使用官方电子邮件 ID 写信给 aem-forms-ea@adobe.com，加入早期采用者计划并申请使用该功能。</span>

hCaptcha® 服务项目可保护您的表单免受机器人、垃圾邮件和自动滥用的侵害。它提出一个复选框小组件挑战，并评估用户响应以确定与表单交互的是人还是机器人。如果测试失败，它会阻止用户继续操作，并通过阻止机器人发布垃圾邮件或恶意活动来帮助确保在线交易的安全。

![hCaptcha®](/help/adaptive-forms/assets/hCaptcha-challenge.png)

{{traditional-aem}}

## 用途 {#usage}

在表单提交过程中加入 hCaptcha 挑战有以下几个好处：

- **防范机器人**：它确保表单由人工提交，减少垃圾邮件和自动提交。

- **安全性**：它增加了一层额外的安全性，验证每个表单提交的合法性并防止恶意攻击。

- **数据完整性**：通过防止重复或欺诈性提交，它有助于维护通过表单收集的数据的完整性和准确性。

- **用户验证**：验证提交表单的用户身份，确保只有经过身份验证的用户才能完成敏感交易。

- **负载管理**：它通过控制表单提交的速率来帮助管理服务器负载，防止在高流量期间系统过载。

## 技术详细信息 {#technical-details}

可在 [GitHub](https://github.com/adobe/aem-core-forms-components/blob/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/hCaptcha/v1/hCaptcha/README.md) 上的技术文档中获得关于 hCaptcha 组件的最新信息。有关开发核心组件的更多信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

通过使用[配置对话框](#configure-dialog)指定 hCaptcha 组件的属性。配置对话框是核心组件的一部分，旨在简化表单的创作，并提供一种创建复杂表单的有效方法。

## 版本和兼容性 {#version-and-compatibility}


自适应表单 hCaptcha 组件于 2024 年 5 月作为[核心组件 3.0.20](https://github.com/adobe/aem-core-forms-components/commit/a4cb97131ffad47137a8f5f173401128a1cf3491) 的一部分发布。下表显示所有支持的版本、AEM 兼容性以及相应文档的链接：

|  |  |
|---|---|
| 组件版本 | AEM as a Cloud Service |
| --- | --- |
| v1 | 与<br>[版本 2.0.4](/help/adaptive-forms/version.md) 和更高版本兼容 | 兼容 | 兼容 |

有关核心组件版本的信息，请参阅[核心组件版本](/help/adaptive-forms/version.md)文档。

## “配置”对话框 {#configure-dialog}

您可以使用具有“基本”选项卡和“验证”选项卡的配置对话框轻松自定义 hCaptcha 组件的属性，以自定义各种属性。

### “基本”选项卡 {#basic-tab}

- **[!UICONTROL 名称]：** 指定您的 hCaptcha 组件的名称，您可以在表单和规则编辑器中使用其唯一名称轻松识别表单组件。
- **[!UICONTROL 标题]：** 指定您的 hCaptcha 组件的标题。
- **[!UICONTROL 配置设置]：** 选择为 hCaptcha® 配置的云配置。
- **验证码大小：** 您可以选择 hCaptcha® 验证对话框的显示大小。使用 **[!UICONTROL 紧凑]**&#x200B;选项显示小尺寸，使用 **[!UICONTROL 正常]**&#x200B;选项显示相对大尺寸的 hCaptcha® 挑战对话框。<!-- or **[!UICONTROL Invisible]** to validate hCaptcha&reg; without explicitly rendering the checkbox widget on the user interface. -->

  ![hCaptcha 基本选项卡](/help/adaptive-forms/assets/hcaptcha-basic.png)

### “验证”选项卡 {#validation-tab}

- **[!UICONTROL 验证消息]：** 在表单提交时提供用于验证码的验证消息。
- **[!UICONTROL 脚本验证消息]** - 如果脚本验证失败，使用此选项输入所提示的消息。

  ![hCaptcha 验证选项卡](/help/adaptive-forms/assets/hcaptcha-validation-tab.png)

**hCaptcha® 是 Intuition Machines, Inc. 的注册商标。**

**详细了解**&#x200B;其他&#x200B;**验证码组件**&#x200B;及其服务，例如：

- [在自适应表单中使用 hCaptcha 作为核心组件](https://experienceleague.adobe.com/zh-hans/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/integrate-adaptive-forms-hcaptcha-core-components)

- [在自适应表单中使用 hCaptcha 作为 Foundation 组件](https://experienceleague.adobe.com/zh-hans/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/add-components-to-an-adaptive-form/integrate-adaptive-forms-hcaptcha)

- [在自适应表单中使用 Turnstile CAPTCHA 作为 Foundation 组件](https://experienceleague.adobe.com/zh-hans/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/add-components-to-an-adaptive-form/integrate-adaptive-forms-turnstile)

- [在自适应表单中使用 Google reCAPTCHA 作为 Foundation 组件](https://experienceleague.adobe.com/zh-hans/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/captcha-adaptive-forms-core-components)

## 相关文章 {#related-articles}

{{more-like-this}}

## 另请参阅 {#see-also}

{{see-also}}
