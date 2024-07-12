---
title: 自适应表单核心组件：Google reCAPTCHA
description: 使用 AEM Forms 轻松通过 Google reCAPTCHA 服务增强表单安全性。解释自适应表单 reCaptcha 的属性
role: Architect, Developer, Admin, User
exl-id: 2d986b90-e596-4e8f-9a32-0ebced5461c8
source-git-commit: b97687e7f7437af57e2a8b9f442d4e0c8322a3d2
workflow-type: tm+mt
source-wordcount: '1325'
ht-degree: 100%

---

# 自适应表单 reCAPTCHA {#google-recaptcha}

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


| 组件版本 | AEM as a Cloud Service |
|--- |--- |
| v1 | 与<br>[版本 2.0.4](/help/versions.md) 和更高版本兼容 | 兼容 | 兼容 |

有关核心组件版本的信息，请参阅[核心组件版本](/help/versions.md)文档。

## 技术详细信息 {#technical-details}

可在 [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/recaptcha/v1/recaptcha) 上的技术文档中获得关于自适应表单 Google reCAPTCHA 核心组件的最新信息。有关开发核心组件的更多信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## “配置”对话框 {#configure-dialog}

通过“配置”对话框，可轻松地自定义您为访客提供的 Google reCAPTCHA 体验。还可轻松地定义 Google reCAPTCHA 选项，从而营造一种无缝的用户体验。

### “基本”选项卡 {#basic-tab}

![“基本”选项卡](/help/adaptive-forms/assets/recaptcha-basictab.png)

- **名称** - 可在表单和规则编辑器中通过唯一名称轻松地标识表单组件，但该名称不得包含空格或特殊字符。

- **标题** - 通过组件的标题，可轻松地标识表单中的组件，默认情况下，标题显示在该组件的顶部。如果不添加标题，则显示该组件的名称而非标题文本。

- **允许标题为富文本**：此功能使用户能够格式化纯文本标题，结合粗体、斜体、下划线文本、各种字体、字体大小、颜色和附加选项等功能，以增强视觉呈现和定制效果。它提供了更大的灵活性以及对创作的控制度，使标题在文档、网站或应用程序中脱颖而出。\
  选中**允许标题为富文本复选框后，可以看到格式化选项，用于设置组件标题的样式。要访问所有可用的格式选项，您可以点击![全屏图标](/help/adaptive-forms/assets/fullscreen-icon.png)选项卡。

  ![富文本支持](/help/adaptive-forms/assets/richtext-support-title.png)

- **隐藏标题** - 选中此选项可隐藏该组件的标题。
- **标记为未绑定表单元素**：选择此选项可配置未链接到任何架构的表单字段。利用此选项，您可以保存数据而不更新数据源。它还可让您以一种独立于标准数据库集成的自定义方式处理数据。
- **配置设置**：选择包含云配置的配置容器，该配置通过 Google 将 AEM Forms 与 reCAPTCHA 服务连接起来。

  >[!NOTE]
  >
  > 请参阅[在基于核心组件的 AEM 自适应表单中使用 Google reCAPTCHA](https://experienceleague.adobe.com/zh-hans/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/captcha-adaptive-forms-core-components) 的文章，了解如何为您的环境创建和配置 Google reCAPTCHA。

- **类型**：选择此选项可选择 reCAPTCHA 的大小。
   - **正常**：指的是标准、更大版本的 reCAPTCHA 构件，它可能更加明显且更易于用户交互，尤其是在屏幕更大的设备上。
   - **精简**：指的是 reCAPTCHA 构件的较小版本。此选项适用于空间有限的情况，例如移动设备或网页紧凑的布局。

- **隐藏组件** - 选中此选项以从表单中隐藏该组件。仍可访问该组件作其他用途，如在规则编辑器中使用它进行计算。当需要存储用户无需看到或直接更改的信息时，此项很有用。

- **禁用组件** - 选中此选项以禁用该组件。被禁用的组件不再活跃或最终用户无法编辑它。禁用组件的数据未提交用户可以看到该字段的值，但无法修改。仍可访问该组件作其他用途，如在规则编辑器中使用它进行计算。

- **只读** - 选中此选项以使组件不可编辑。用户可看到但无法修改字段的值。仍可访问该组件作其他用途，如在规则编辑器中使用它进行计算。

### “验证”选项卡 {#validation-tab}

![“验证”选项卡](/help/adaptive-forms/assets/recaptcha-validationtab.png)

- **错误消息** - 通过此选项，可输入如果选中了&#x200B;**必需**&#x200B;复选框并将表单字段留空，所显示的消息。

- **脚本验证消息** - 通过此选项，可输入如果脚本验证失败，所显示的消息。

## “设计”对话框 {#design-dialog}

“设计”对话框用于定义和管理 reCAPTCHA 组件的 CSS 样式。

### “样式”选项卡 {#styles-design-tab}

自适应表单 reCAPTCHA 核心组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。

![“设计”对话框](/help/adaptive-forms/assets/checkbox-style.png)

- **默认 CSS 类**：可为自适应表单 reCAPTCHA 核心组件提供默认 CSS 类。

- **允许使用的样式**：可通过提供名称和表示样式的 CSS 类而定义样式。例如，您可以创建一个名为“bold text”的样式，并提供 CSS 类“font-weight: bold”。可使用这些样式或将其应用于自适应表单编辑器中的自适应表单。要应用样式，请在自适应表单编辑器中选择要将样式应用于的组件，导航到“属性”对话框，然后从&#x200B;**样式**&#x200B;下拉列表中选择所需的样式。如果您需要更新或修改样式，只需返回“设计”对话框，在“样式”选项卡中更新样式，然后保存更改。

### 自定义属性

![“自定义属性”对话框](/help/adaptive-forms/assets/checkbox-customproperties.png)

通过自定义属性，您可使用表单模板将自定义属性（键值对）关联到自适应表单核心组件。自定义属性反映在组件 Headless 演绎版的属性部分中。它可让您创建根据自定义属性值进行调整的动态表单行为。例如，开发人员可以为移动、桌面或 Web 平台设计 Headless 表单组件的各种演绎版，从而大大提升各种设备上的用户体验。
- **组名称**：您可以提供名称来标识自定义属性组。您可以添加、删除或重新排列多个自定义属性组。添加自定义属性组后，可看到以下选项：

   - **键值对**：您可以通过单击“**添加**”按钮，为每个自定义属性组添加多个自定义属性名称和自定义属性值。

   - **删除**：点按或单击此项可删除自定义属性名称和自定义属性值。

   - **重新排列**：点按或单击并拖动可重新排列自定义属性名称和自定义属性值。


## 相关文章 {#related-articles}

{{more-like-this}}

## 另请参阅 {#see-also}

{{see-also}}
