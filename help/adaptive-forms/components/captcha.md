---
title: 自适应表单核心组件 - 表单容器
description: 将自适应表单添加到网页。
role: Architect, Developer, Admin, User
hide: true
hidefromtoc: true
exl-id: 1e413ef3-7a6f-41fc-825d-dbe09ebaffe9
source-git-commit: e843ccf5c030cd4f1015e3290347b5799828537a
workflow-type: ht
source-wordcount: '869'
ht-degree: 100%

---

# Google reCAPTCHA {#google-recaptcha}

CAPTCHA（区分计算机和人类的完全自动化公共图灵测试）是一种在线交易中常用的程序，用于区分人类和自动化程序或机器人。它提出了一个挑战，并评估用户响应以确定是人还是机器人与网站交互。如果测试失败，它会阻止用户继续操作，并通过阻止机器人发布垃圾邮件或恶意目的来帮助确保在线交易的安全。

AEM Forms as a Cloud Service 支持自适应表单中的 Google reCAPTCHA v2。您可以使用它在表单提交时提出验证码挑战

## 用途 {#reasons-to-use-google-recaptcha}

- **垃圾邮件和机器人程序预防**：使用 reCAPTCHA 的主要原因之一是防止垃圾邮件提交和恶意机器人淹没您的表单。reCAPTCHA 的高级算法可以检测提交表单的自动尝试，从而确保只有合法用户才能与之交互。

- **增强安全性**：通过实施 reCAPTCHA，您可以为自适应表单添加额外的安全层。这有助于保护敏感信息并防止恶意用户利用漏洞。

- **用户体验**：虽然验证码有时会被视为不便，但 reCAPTCHA 的自适应方法意味着大多数用户都会获得简化的、用户友好的体验，并且需要最少的交互。这可以帮助保持积极的用户体验，同时仍然阻止机器人。

- **适应性**：reCAPTCHA 的自适应机制分析用户行为和交互，以确定他们是否是人类。这意味着向用户呈现的挑战级别可能会根据他们是机器人的可能性而有所不同。这种适应性减少了真正用户的摩擦，同时保持了强大的安全性。

- **减少手动审核**：通过显着减少垃圾邮件提交和机器人生成内容的数量，reCAPTCHA 可以节省用于手动审核和清理的时间和资源。

## 版本和兼容性 {#version-and-compatibility}

自适应表单 Google reCAPTCHA 核心组件于 2023 年 8 月发布，作为核心组件“版本”的一部分。下表显示所有支持的版本、AEM 兼容性以及相应文档的链接：


|  |  |
|---|---|
| 组件版本 | AEM as a Cloud Service |
| --- | --- |
| v1 | 与<br>[版本 2.0.4](/help/versions.md) 和更高版本兼容 | 兼容 | 兼容 |

有关核心组件版本的信息，请参阅[核心组件版本](/help/versions.md)文档。

## 技术详细信息 {#technical-details}

可在 [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/recaptcha/v1/recaptcha) 上的技术文档中获得关于自适应表单 Google reCAPTCHA 核心组件的最新信息。有关开发核心组件的更多信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## “配置”对话框 {#configure-dialog}

通过“配置”对话框，可轻松地自定义您为访客提供的 Google reCAPTCHA 体验。还可轻松地定义 Google reCAPTCHA 选项，从而营造一种无缝的用户体验。

### “基本”选项卡 {#basic-tab}

- **名称** - 可在表单和规则编辑器中通过唯一名称轻松地标识表单组件，但该名称不得包含空格或特殊字符。

- **标题** - 通过组件的标题，可轻松地标识表单中的组件，默认情况下，标题显示在该组件的顶部。如果不添加标题，则显示该组件的名称而非标题文本。

- **隐藏标题** - 选中此选项可隐藏该组件的标题。

- **配置** -

- **类型** -

- **隐藏组件** - 选中此选项以从表单中隐藏该组件。仍可访问该组件作其他用途，如在规则编辑器中使用它进行计算。当需要存储用户无需看到或直接更改的信息时，此项很有用。

- **禁用组件** - 选中此选项以禁用该组件。被禁用的组件不再活跃或最终用户无法编辑它。禁用组件的数据未提交用户可以看到该字段的值，但无法修改。仍可访问该组件作其他用途，如在规则编辑器中使用它进行计算。

- **只读** - 选中此选项以使组件不可编辑。用户可看到但无法修改字段的值。仍可访问该组件作其他用途，如在规则编辑器中使用它进行计算。

### “验证”选项卡 {#validation-tab}

- **错误消息** - 通过此选项，可输入如果选中了&#x200B;**必需**&#x200B;复选框并将表单字段留空，所显示的消息。

## 另请参阅 {#see-also}

- [创建 AEM 自适应表单](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html)
- [将 AEM 自适应表单添加到 AEM Sites 页面](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html)
- [将主题应用于 AEM 自适应表单](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/using-themes-in-core-components.html)
- [将组件添加到 AEM 自适应表单](/help/adaptive-forms/introduction.md#adaptive-forms-core-components-components)
- [以 AEM 自适应表单的形式使用 reCAPTCHA](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/add-components-to-an-adaptive-form/captcha-adaptive-forms.html)
- [生成 AEM 自适应表单的 PDF 版本 (DoR)](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/generate-document-of-record-core-components.html)
- [翻译 AEM 自适应表单](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/using-aem-translation-workflow-to-localize-adaptive-forms-core-components.html)
- [为自适应表单启用 Adobe Analytics 以跟踪表单使用情况](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/integrate/services/enable-adobe-analytics-adaptive-form-using-experience-cloud-setup-automation.html)
- [将自适应表单连接到 Microsoft SharePoint](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components.html#create-sharepoint-configuration)
- [将自适应表单连接到 Microsoft Power Automate](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components.html#microsoft-power-automate)
- [将自适应表单连接到 Microsoft OneDrive](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components.html#submit-to-onedrive)
- [将自适应表单连接到 Microsoft Azure Blob 存储](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components.html#submit-to-azure-blob-storage)
- [将自适应表单连接到 Salesforce](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/integrate/use-form-data-model/oauth2-client-credentials-flow-for-server-to-server-integration.html)
- [在 AEM 自适应表单中使用 Adobe Sign](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/use-adobe-sign/working-with-adobe-sign.html)
- [为自适应表单添加新区域设置](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/supporting-new-language-localization-core-components.html)
- [将自适应表单数据发送到数据库](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/integrate/use-form-data-model/data-integration.html)
- [将自适应表单数据发送到 REST 端点](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components.html#submit-to-rest-endpoint)
- [将自适应表单数据发送到 AEM 工作流](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components.html#invoke-an-aem-workflow)
- [使用 Forms 门户在 AEM 网站上列出 AEM 自适应表单](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/configure-forms-portal.html)

