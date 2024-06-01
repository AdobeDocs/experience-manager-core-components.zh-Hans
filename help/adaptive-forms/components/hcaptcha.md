---
title: AEM自适应Forms中的验证码
description: 使用hCaptcha&reg；服务轻松增强表单安全性。 内部分步指南！
feature-set: Experience Manager Sites, Experience Manager Forms
feature: Adaptive Forms, Core Components
role: Architect, Developer, Admin, User
source-git-commit: ddfd55259f84443e6add3ced09fd319bcd9c1677
workflow-type: tm+mt
source-wordcount: '583'
ht-degree: 12%

---

# Captcha组件{#hCaptcha-component-adaptive-forms-core-component}

<span class="preview"> 此功能在早期采用者计划项下。 您可以从官方电子邮件ID写信到aem-forms-ea@adobe.com ，加入率先采用者计划并请求获取该功能的访问权限。 </span>

hCaptcha®服务可保护您的表单免遭机器人、垃圾邮件和自动滥用。 它会发起复选框构件质询并评估用户响应，以确定是人类还是机器人与表单交互。 它可防止用户在测试失败时继续操作，并通过阻止机器人发送垃圾邮件或恶意活动来帮助确保在线交易的安全。

![验证码®](/help/adaptive-forms/assets/hCaptcha-challenge.png)

## 用途 {#usage}

在表单提交过程中包含hCaptcha挑战有多种好处，包括：

- **机器人预防**：它确保表单由人工提交，减少垃圾邮件和自动提交。

- **安全性**：它添加了一个额外的安全层，验证每个表单提交的合法性并防御恶意攻击。

- **数据完整性**：通过阻止多次或欺诈性提交，它有助于维护通过表单收集的数据的完整性和准确性。

- **用户验证**：验证提交表单的用户的身份，确保只有经过身份验证的用户才能完成敏感交易。

- **负载管理**：它有助于通过控制表单提交速率来管理服务器负载，从而防止高流量期间系统过载。

## 技术详细信息 {#technical-details}

在以下位置的技术文档中获取有关验证码组件的最新信息： [GitHub](https://github.com/adobe/aem-core-forms-components/blob/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/hCaptcha/v1/hCaptcha/README.md). 有关开发核心组件的更多信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

使用指定验证码组件的属性 [配置对话框](#configure-dialog). “配置”对话框是核心组件的一部分，构建该对话框是为了使表单创作更容易，并提供创建复杂表单的有效方式。

## 版本和兼容性 {#version-and-compatibility}


自适应Forms hCaptcha组件于2024年5月发布，作为 [核心组件3.0.20](https://github.com/adobe/aem-core-forms-components/commit/a4cb97131ffad47137a8f5f173401128a1cf3491). 下表显示所有支持的版本、AEM 兼容性以及相应文档的链接：

|  |  |
|---|---|
| 组件版本 | AEM as a Cloud Service |
| --- | --- |
| v1 | 与<br>[版本 2.0.4](/help/adaptive-forms/version.md) 和更高版本兼容 | 兼容 | 兼容 |

有关核心组件版本的信息，请参阅[核心组件版本](/help/adaptive-forms/version.md)文档。

## “配置”对话框 {#configure-dialog}

您可以使用配置对话框轻松自定义验证码组件的属性，该对话框具有用于自定义各种属性的基本选项卡和验证选项卡。

### “基本”选项卡 {#basic-tab}

- **[!UICONTROL 名称]：** 为hCaptcha组件指定名称，您可以在表单和规则编辑器中使用表单组件的唯一名称轻松识别表单组件。
- **[!UICONTROL 标题]：** 指定hCaptcha组件的标题。
- **[!UICONTROL 配置设置]：** 选择为Captcha®配置的云配置。
- **验证码大小：** 您可以选择hCaptcha®质询对话框的显示大小。 使用 **[!UICONTROL 紧凑]** 用于显示小尺寸和 **[!UICONTROL 普通]** 用于显示相对较大的hCaptcha®挑战对话框的选项。<!-- or **[!UICONTROL Invisible]** to validate hCaptcha&reg; without explicitly rendering the checkbox widget on the user interface. -->

  ![验证码基本选项卡](/help/adaptive-forms/assets/hcaptcha-basic.png)

### “验证”选项卡 {#validation-tab}

- **[!UICONTROL 验证消息]：** 在提交表单时提供验证码验证消息。
- **[!UICONTROL 脚本验证消息]**  — 如果脚本验证失败，使用此选项输入提示消息。

  ![验证码验证选项卡](/help/adaptive-forms/assets/hcaptcha-validation-tab.png)

**hCaptcha®是Intuition Machines， Inc.的注册商标。**

**了解更多信息** 关于其他 **验证码组件** 以及他们的服务，例如：

- [在核心组件的自适应表单中使用Captcha](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/integrate-adaptive-forms-hCaptcha-core-components)

- [在适用于Foundation组件的自适应表单中使用Captcha](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/add-components-to-an-adaptive-form/integrate-adaptive-forms-hcaptcha)

- [在适用于Foundation组件的自适应表单中使用Turnstile CAPTCHA](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/add-components-to-an-adaptive-form/integrate-adaptive-forms-turnstile)

- [在适用于Foundation组件的自适应表单中使用Google reCAPTCHA](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/captcha-adaptive-forms-core-components)

## 相关文章 {#related-articles}

{{more-like-this}}

## 另请参阅 {#see-also}

{{see-also}}
