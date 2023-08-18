---
title: 自适应表单核心组件 - 表单容器
description: 将自适应表单添加到网页。
role: Architect, Developer, Admin, User
hide: true
hidefromtoc: true
source-git-commit: 8db061f3d6f1041336c379b34f3b6b7f03083560
workflow-type: tm+mt
source-wordcount: '723'
ht-degree: 44%

---


# Google reCPATCHA {#google-recaptcha}

CAPTCHA（完全自动化公共图灵测试，用于区分计算机和人类）是一种在线交易中常用的程序，用于区分人类和自动化程序或机器人。 它会提出挑战，并评估用户响应以确定是人类还是机器人与网站交互。 它可防止用户在测试失败时继续操作，并通过防止机器人发送垃圾邮件或恶意目的而确保在线交易的安全。

AEM Formsas a Cloud Service支持自适应Forms中的Google reCAPTCHA v2。 您可以用它来对表单提交提出验证码质询

## 用途 {#reasons-to-use-google-recaptcha}


- **垃圾邮件和机器人预防**：使用reCAPTCHA的主要原因之一是防止垃圾邮件提交和恶意机器人泛滥您的表单。 reCAPTCHA的高级算法可以检测自动提交表单的尝试，从而确保只有合法用户才能与表单进行交互。

- **增强的安全性**：通过实施reCAPTCHA，可为自适应表单添加额外的安全层。 这有助于保护敏感信息并防止恶意用户利用漏洞。

- **用户体验**：虽然CAPTCHA有时被视为不便，但reCAPTCHA的自适应方法意味着大多数用户可获得简化的、用户友好的体验，并且只需很少的交互。 这有助于在仍然阻止机器人的同时保持积极的用户体验。

- **适应性**： reCAPTCHA的自适应机制分析用户行为和交互以确定他们是否为人类。 这意味着根据用户成为机器人的可能性，他们所面临的挑战可能会有所不同。 这种适应性在保持强大安全性的同时，减少了真实用户的摩擦力。

- **减少手动审核**：通过显着减少垃圾邮件提交和机器人生成内容的数量，reCAPTCHA可以节省原本用于手动审核和清理的时间和资源。

## 版本和兼容性 {#version-and-compatibility}

自适应Forms Google reCAPTCHA核心组件作为核心组件“版本”的一部分于2023年8月发布。 下表显示所有支持的版本、AEM 兼容性以及相应文档的链接：

|  |  |
|---|---|
| 组件版本 | AEM as a Cloud Service |
| --- | --- |
| v1 | 兼容<br>[版本 2.0.4](/help/versions.md) 和更高版本 | 兼容 | 兼容 |

有关核心组件版本的信息，请参阅[核心组件版本](/help/versions.md)文档。

## 技术详细信息 {#technical-details}

在以下位置的技术文档中获取有关自适应Forms Google reCAPTCHA核心组件的最新信息： [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/recaptcha/v1/recaptcha). 有关开发核心组件的更多信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## “配置”对话框 {#configure-dialog}

通过“配置”对话框，您可以轻松自定义访客的Google reCAPTCHA体验。 您还可以轻松地定义Google reCAPTCHA选项，以实现无缝用户体验。

### “基本”选项卡 {#basic-tab}

- **名称** - 可在表单和规则编辑器中通过唯一名称轻松地标识表单组件，但该名称不得包含空格或特殊字符。

- **标题** - 通过组件的标题，可轻松地标识表单中的组件，默认情况下，标题显示在该组件的顶部。如果不添加标题，则显示该组件的名称而非标题文本。

- **隐藏标题** - 选中此选项以隐藏该组件的标题。

- **配置** -

- **类型** -

- **隐藏组件** - 选中此选项以从表单中隐藏该组件。仍可访问该组件作其他用途，如在规则编辑器中使用它进行计算。当需要存储用户无需看到或直接更改的信息时，此项很有用。

- **禁用组件** - 选中此选项以禁用该组件。被禁用的组件不再活跃或最终用户无法编辑它。未提交禁用组件的数据。用户可以看到字段的值，但无法修改它。 仍可访问该组件作其他用途，如在规则编辑器中使用它进行计算。

- **只读** - 选中此选项以使组件不可编辑。用户可看到但无法修改字段的值。仍可访问该组件作其他用途，如在规则编辑器中使用它进行计算。

### “验证”选项卡 {#validation-tab}

- **错误消息** - 通过此选项，可输入如果选中了&#x200B;**必需**&#x200B;复选框并将表单字段留空，所显示的消息。

