---
title: AEM 自适应表单核心组件简介
description: 借助自适应表单核心组件的灵活性创建引人入胜的注册体验（表单），并利用 Adobe Experience Manager 的强大功能进行交付。
role: Architect, Developer, Admin, User
source-git-commit: ae81102adafef131b013425465ad56af41f604bf
workflow-type: tm+mt
source-wordcount: '2229'
ht-degree: 99%

---

# 自适应表单核心组件  {#adaptive-forms-core-components-introduction}

借助 Adob&#x200B;&#x200B;e Experience Manager 中的自适应表单核心组件可以创建引人注目的注册体验。

## 核心组件 {#overview}

在 Adobe Experience Manager (AEM) 中，组件是用于创建页面和表单的构建基块。它们使作者能够通过一种简单而强大的方式创建和管理内容，并为开发人员提供了创建自定义组件所需的灵活性和可扩展性。它们旨在加快开发时间并降低网站和表单的维护成本，其操作灵活并且可以轻松定制，以满足网站和表单的特定需求。

此外，核心组件经过设计，具有响应能力并支持一系列广泛的设备，包括台式机、平板电脑和智能手机。它们还遵循最新的 Web 标准和最佳实践，这使其成为用于创建 Web 内容的强大且可靠的解决方案。

总的来说，核心组件是用于在 AEM 中创建和管理 Web 内容的重要工具，它提供了强大而灵活的解决方案，可帮助减少开发时间和维护成本，同时还为网站访客提供出色的用户体验。

## 自适应表单核心组件

自适应表单核心组件是一组（29 个）开源且与 BEM 兼容的组件，它们基于 Adobe Experience Manager WCM 核心组件而构建。它们专门设计用于创建自适应表单，后者是能够适应用户的设备、浏览器和屏幕大小的表单。

利用这些组件，可提供一系列广泛的表单字段选项（包括文本字段、复选框、下拉菜单等）来创建卓越的数据捕获和注册体验。它们还包括验证、条件逻辑和响应式设计等功能，可用于创建用户友好且易用的表单。

此外，由于这些组件是开源的，因此，开发人员能够轻松定制和扩展组件以满足其组织的特定需求。而且，这些组件基于 BEM 方法而构建，这确保了它们可扩展且可维护。

![自适应表单图像](assets/sample-adaptive-form.png)

## 功能 {#features}

|  |  |
|---|---|
| 可以即刻投入使用 | 自适应表单核心组件是 24 个功能强大的 WCM 组件。 |
| 云就绪 | 适用于 [AEM Forms as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/home.html)。 |
| 可以通用 | 这些组件代表了表单作者可用来设计几乎任何布局的通用概念。 |
| 可配置 | 模板级[内容策略](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/full-stack/components-templates/templates.html#content-policies)定义了可以使用或无法使用的功能。 |
| 可访问 | 它们提供 ARIA 标签，支持键盘导航以及用于屏幕阅读器等辅助技术的文本。 |
| 可主题化 | 这些组件实施[样式系统](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/features/style-system.html)，且标记遵循 [BEM CSS 约定](https://getbem.com/)。 |
| 可自定义 | 可利用几种模式来轻松进行自定义设置（从调整 HTML 到高级功能重用）。 |
| 版本控制 | [版本控制策略](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-policies)可确保核心组件在改进可能影响您的内容时不会中断您的网站。 |
| 开源 | 如果有出错的地方，请做出您的改进。 |

<!-- comply with [WCAG 2.1 standard](https://www.w3.org/TR/WCAG21/), -->


## 好处 {#benefits}

数据捕获体验对于商机开发和注册至关重要，自适应表单核心组件提供了功能强大的解决方案来创建针对数据捕获优化的表单。使用核心组件在基础组件上创建这些体验的一些益处包括：

* **[在 GitHub 上可用](https://github.com/adobe/aem-core-forms-components)**：AEM 自适应表单核心组件是开源的，可在 GitHub 上使用，并提供全面的文档。这使开发人员能够更容易理解相关组件及其工作方式，并为其开发做出贡献。[Aemcomponents.dev](https://www.aemcomponents.dev/) 网站也是一项宝贵的资源，开发人员可以在其中查看正在运行的组件并访问详细的文档。

* **[样式的 BEM 模型](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/using-themes-in-core-components)**：核心组件遵循 BEM（块元素修饰符）样式模型，这是一种行之有效且广泛使用的 CSS 组织方法。这使开发人员更容易理解相关样式的组织方式，以及如何修改它们，以满足其特定需求。

* **不依赖第三方库**：核心组件的优势之一是它们不依赖于第三方 JavaScript 库，包括 JQuery 和 Underscore。这使得组件能够更快、更轻巧，并且更容易集成到现有的 AEM 实施中。

* **专注于性能和可访问性**：核心组件在构建时考虑到了性能和可访问性，这反映在其较高的 Google Lighthouse 和 Web Vitals 得分中。这使开发人员可以更轻松地创建可访问且高性能的网页，而这在当今的数字环境中越来越重要。

* **Sites 30 模板和主题中的表单组件**：核心组件为 Sites 30 模板和主题中的表单组件提供支持，使开发人员可以更轻松地在 AEM 中创建和自定义表单。

* **[更容易设计样式](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/using-themes-in-core-components)**：与对应的基础组件相比，核心组件更容易设计样式。 主题创建过程类似于 Sites，并且能够从父 Sites 页面继承相同的主题/CSS。此外，用于样式的 BEM 模型使理解和修改各个样式变得更加容易。

* **辅助功能**：自适应表单核心组件支持辅助功能标准和指南，以确保残障人士（包括那些使用屏幕阅读器等辅助技术的人员）能够使用表单。

* **[版本控制](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/add-comments-annotations-versioning-adaptive-form-core-components)**：您可以创建并管理基于核心组件的自适应表单的多个版本，通过评论参与协作讨论，并将注释附加到特定表单组件中，从而增强整体表单构建体验。

## 可用组件：按组件类型细分

AEM Forms 的当前版本具有以下核心组件、[基础组件](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/create-an-adaptive-form-on-forms-cs/introduction-forms-authoring#component-toolbar)和[表单块组件 (Edge Delivery Services)](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/edge-delivery/build-forms/forms-references/form-components)。

| 组件 | Foundation 组件  | 核心组件 | 表单块组件 | 附加信息 |
|------------|:---------------------:|:---------------:|:---------------------:|-----------------------|
| Adobe Sign Block | ✔️ | | | [Adobe Sign 集成](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/integrate/services/adobe-sign-integration-adaptive-forms#adobe-acrobat-sign-for-government)仅适用于基础组件。 |
| 可折叠项 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/accordion.md)</span> | | 对于基础组件，您可以在[面板组件属性](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/configure-layout-of-an-adaptive-form/layout-capabilities-adaptive-forms#panel-layout)中配置可折叠项版面。 |
| 自适应表单片段 | ✔️ | ✔️ | | 对于基础组件，您可以从资产浏览器中[添加片段](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/forms/adaptive-forms-basic-authoring/adaptive-form-fragments#insert-a-fragment-in-an-adaptive-form)。 |
| 自适应表单 reCAPTCHA | ✔️ | ✔️ | ✔️ | 对于基础组件，使用验证码组件[将 Google reCaptcha 添加到表单中](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/add-components-to-an-adaptive-form/captcha-adaptive-forms#google-reCAPTCHA)。 |
| 按钮 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/button.md)</span> | ✔️ | |
| 验证码 | ✔️ |  |  | 对于基础组件，使用验证码组件[将 Google reCaptcha 添加到表单中](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/add-components-to-an-adaptive-form/captcha-adaptive-forms#google-reCAPTCHA)。 |
| 图表 | ✔️ | | | |
| 复选框 | ✔️ | ✔️ | | |
| 复选框组 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/checkbox-group.md)</span> | ✔️ | 对于基础组件，使用复选框组件添加多个复选框 |
| 数据输入字段 | ✔️ | | | 对于核心组件，使用[日期选择器](/help/adaptive-forms/components/date-picker.md)组件。您还可以添加单独的[文本框](/help/adaptive-forms/components/text-box.md)或[数字框](/help/adaptive-forms/components/numeric-box.md)组件来捕获日期、月份和年份等信息。 |
| 日期选取器 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/date-picker.md)</span> | ✔️ | |
| 下拉列表 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/drop-down-list.md)</span> | ✔️ | |
| 电子邮件 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/email-input.md)</span> | ✔️ | |
| 文件附件 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/file-attachment.md)</span> | ✔️ | |
| 文件附件列表 | ✔️ | | | |
| 页脚 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/footer.md)</span> | ✔️ | |
| 脚注占位符 | ✔️ | | | |
| 表单容器 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/form-container.md)</span> | ✔️ | 对于基础组件，使用[根面板组件](https://experienceleague.adobe.com/en/docs/experience-manager-learn/cloud-service/forms/create-first-af/configure-root-panel)。 |
| 表单标题 | ✔️ | ✔️ | | 对于基础组件，使用标题组件。 |
| hCaptcha | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/hcaptcha.md)</span> |  | |
| 页眉 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/header.md)</span> | ✔️ | |
| 水平选项卡 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/horizontal-tabs.md)</span> | | 对于基础组件，您可以在面板组件属性中配置[顶部选项卡（水平选项卡）布局](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/configure-layout-of-an-adaptive-form/layout-capabilities-adaptive-forms#panel-layout)。 |
| 图像 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/image.md)</span> | ✔️ | |
| 图像选择 | ✔️ | | | |
| “下一个”按钮 | ✔️ | ✔️ | | 使用[向导组件](/help/adaptive-forms/components/wizard.md) 的下一个和上一个按钮在多个面板之间移动。 |
| 数值框 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/numeric-box.md)</span> | ✔️ | |
| 数值步进器 | ✔️ | | | |
| 面板 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/panel.md)</span> | ✔️ | |
| 密码框 | ✔️ | | ✔️ | |
| 电话 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/telephone-input.md)</span> | ✔️ | |
| “上一个”按钮 | ✔️ | | | 使用[向导组件](/help/adaptive-forms/components/wizard.md) 的下一个和上一个按钮在多个面板之间移动。 |
| 单选按钮 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/radio-button.md)</span> | | |
| 单选按钮群组 | | | ✔️ | |
| “重置”按钮 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/reset-button.md)</span> | ✔️ | |
| 潦草签名 | ✔️ | | | |
| 分隔符 | ✔️ | | | |
| “提交”按钮 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/submit-button.md)</span> | ✔️ | |
| 摘要步骤 | ✔️ | | | |
| 开关 | ✔️ | <span style="color:blue"> [✔️](/help/adaptive-forms/components/switch.md) | | |
| 表 | ✔️ | | | |
| 条款和条件 | ✔️ | ✔️ | | |
| 文本 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/text.md)</span> | ✔️ | |
| 文本框 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/text-box.md)</span> | ✔️ | |
| 标题 | ✔️ | | | 对于核心组件，使用[表单标题](/help/adaptive-forms/components/title.md)组件。 |
| Turnstile验证码 | ✔️ | | | [Turnstile验证码](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/add-components-to-an-adaptive-form/integrate-adaptive-forms-turnstile) 仅适用于Foundation组件。 |
| 垂直选项卡 | ✔️ | ✔️ | | 对于基础组件，您可以在面板组件属性中配置[左侧选项卡（垂直选项卡）布局](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/configure-layout-of-an-adaptive-form/layout-capabilities-adaptive-forms#panel-layout) |
| 向导 | ✔️ | <span style="color:blue">[✔️](/help/adaptive-forms/components/wizard.md)</span> | ✔️ | 对于基础组件，您可以在面板组件属性中配置[向导版面](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/configure-layout-of-an-adaptive-form/layout-capabilities-adaptive-forms#panel-layout)。 |




>[!NOTE]
>
>
> * 除了上面列出的组件之外，Forms 块还支持所有有效的 [HTML5 输入类型](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#input_types)和[文本区域](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea)作为组件。
> * 需要上面未列出的组件？请通过您的官方地址向 aem-forms-ea@adobe.com 发送电子邮件进行请求。


<!-- >
* [Accordion](/help/adaptive-forms/components/accordion.md)
* [Button](/help/adaptive-forms/components/button.md)
* [Check Box Group](/help/adaptive-forms/components/checkbox-group.md)
* [Date Picker](/help/adaptive-forms/components/date-picker.md)
* [Drop-down list](/help/adaptive-forms/components/drop-down-list.md)
* [Email-input](/help/adaptive-forms/components/email-input.md)
* [Form Container](/help/adaptive-forms/components/form-container.md)
* [File Attachment](/help/adaptive-forms/components/file-attachment.md)
* [Footer](/help/adaptive-forms/components/footer.md)
* [Header](/help/adaptive-forms/components/header.md)
* [Horizontal Tabs](/help/adaptive-forms/components/horizontal-tabs.md)
* [Image](/help/adaptive-forms/components/image.md)
* [Numeric Box](/help/adaptive-forms/components/numeric-box.md)
* [Panel](/help/adaptive-forms/components/panel.md)
* [Radio Button](/help/adaptive-forms/components/radio-button.md)
* [Reset Button](/help/adaptive-forms/components/reset-button.md)
* [Submit Button](/help/adaptive-forms/components/submit-button.md)
* [Telephone input](/help/adaptive-forms/components/telephone-input.md)
* [Text Box](/help/adaptive-forms/components/text-box.md)
* [Text](/help/adaptive-forms/components/text.md)
* [Title](/help/adaptive-forms/components/title.md)
* [Wizard](/help/adaptive-forms/components/wizard.md)

-->

## 易于使用的表单编辑器

基于核心组件的自适应表单的编辑器与您用于创建 AEM Sites 页面的编辑器类似。您将会获得以下内容：


* **熟悉的 UI 元素和设置**：在配置表单组件的属性时，您会看到一个属性对话框，它看起来就像您用于 WCM 核心组件的对话框一样。这可以让您更快地找到所需的选项。与 WCM 核心组件一样，对于表单组件，属性对话框会出现在编辑器的中心，并带有清晰的选项卡，其中会将基本选项和高级选项、帮助文本和可访问性信息分开。所有这些都采用选项卡格式，以便于导航。

* **[规则编辑器](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/rule-editor-core-components)**：您无需编写代码即可向表单添加逻辑和动态功能。您可以使用内置规则编辑器来：
   * 根据用户选择显示或隐藏字段
   * 启用或禁用对象
   * 为对象设置值
   * 执行计算
   * 设置对象的属性
   * 验证数据输入
   * 调用服务（调用外部功能）
   * 使用内置函数（用于常见任务的预定义函数）
   * 使用自定义函数（您自己的满足特定需求的代码）
   * 验证字段和面板（确保数据符合要求）
   * 验证某个对象的值
   * 通过执行函数来计算对象的值
   * 调用表单数据模型 (FDM) 服务并执行操作
   * 动态添加样式（根据条件改变外观）
   * 创建其他规则（连锁操作和逻辑）
   * 等等！

  规则编辑器没有代码编辑器。您可以使用[自定义函数](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/create-and-use-custom-functions)向规则编辑器添加您自己的代码，以满足特定需求。



* **预填表格**：当用户打开表格时，您可以使用现有数据自动填充表格中的某些字段。由于无需手动输入可能已经存在的信息，这有助于用户节省时间和精力。核心组件编辑器提供 OOTB 预填充服务，以借助表单数据模型填充表单字段。您还可以为更复杂的场景创建自定义预填充服务。

* **[记录文档 (DoR)](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/generate-document-of-record-core-components)**：记录文档 (DoR) 是指通过表单提交的数据的正式、可打印的表示形式。它作为用户输入信息的永久记录，以易于使用的格式（通常是 PDF 文档）提供所提交数据的快照。您可以使用编辑器轻松配置自定义模板或使用 OOTB 模板生成 DoR。

* **[表单数据模型](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/integrate/use-form-data-model/using-form-data-model)**：自适应表单数据模型 (FDM) 充当自适应表单和数据源之间的桥梁。它本质上定义了表单收集和交互的数据的结构和组织。您可以使用编辑器轻松地将表单与表单数据模型 (FDM) 联系起来。

* **[表单提交](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components#:~:text=Adaptive%20Form%20Submit%20Action&amp;text=Adobe%20recommends%20using%20Core%20Components,to%20create%20standalone%20Adaptive%20Forms.&amp;text=A%20Submit%20Action%20lets%20you,button%20on%20an%20Adaptive%20Form)**：表单提交是指用户填写并发送已填表格的过程。这会触发表单配置中定义的一系列操作，最终会存储或处理提交的数据。自适应表单编辑器提供了多种用于配置表单提交的选项。一些常见的提交操作包括：

   * [发送电子邮件](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components#:~:text=Adaptive%20Form%20Submit%20Action&amp;text=Adobe%20recommends%20using%20Core%20Components,to%20create%20standalone%20Adaptive%20Forms.&amp;text=A%20Submit%20Action%20lets%20you,button%20on%20an%20Adaptive%20Form.)
   * [调用 Power Automate 流](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/integrate/services/forms-microsoft-power-automate-integration)
   * [提交到 SharePoint](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-action-sharepoint)
   * [调用 Workfront Fusion](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components#:~:text=Invoke%20a%20Workfront%20Fusion)
   * [使用表单数据模型提交 (FDM)](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/integrate/use-form-data-model/using-form-data-model)
   * [提交到 Azure Blob 存储](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components#:~:text=Submit%20to%20Azure%20Blob%20Storage)
   * [提交到 REST 端点](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-action-restpoint)
   * [提交到 OneDrive](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components#:~:text=to%20REST%20endpoint-,Submit%20to%20OneDrive,-Invoke%20an%20AEM)
   * [调用 AEM 工作流](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components#:~:text=Invoke%20an%20AEM%20Workflow)


* [Sites 页面编辑器中的自适应表单核心组件](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page)：您可以在 AEM 页面编辑器和 AEM 体验片段中启用和使用自适应表单核心组件，以直接创建数据捕获体验以及构建 Sites 页面。

  >[!VIDEO](https://video.tv.adobe.com/v/3419284?quality=12&learn=on)


<!-- 
* **Preview Forms**: You can use the editor to  simulates how the form would appear on various devices like desktops, tablets, and smartphones.
-->



## 启用自适应表单核心组件

通过在 AEM Forms as a Cloud Service 上启用自适应表单核心组件，您可以使用 AEM Forms Cloud Service 实例为多个渠道创建、发布和投放基于核心组件的自适应表单和 Headless 表单。有关启用自适应表单核心组件的详细说明，请参阅[在 AEM Forms as a Cloud Service 和本地开发环境上启用自适应表单核心组件](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/setup-configure-migrate/enable-adaptive-forms-core-components.html)。

自适应表单核心组件具有以下要求。

| AEM 版本 | AEM Forms 附加组件 | 自适应表单核心组件 |
|---|---|---|
| AEM as a Cloud Service | 表单 - 数字注册 | [版本 2.0.10](version.md) 以上 |
| AEM 6.5 | Forms 附加组件 | [版本 1.1.12](version.md) 以上 |

如果您的 AEM Cloud Service SDK 版本低于 2023.02.0，请[确保在您的环境上启用 `prerelease` 标志](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/release-notes/prerelease.html?lang=zh-Hans#new-features)，因为自适应表单核心组件是低于 2023.02.0 版本的预发行版本的一部分。


## 创建基于核心组件的自适应表单

您可以在 AEM Forms as a Cloud Service 或 AEM 6.5 Forms 环境中执行以下操作：

| 操作 | AEM Forms 版本 |
|--------|------------------|
| 创建独立的自适应表单 | [AEM Forms as Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html) |
| 在 AEM Sites 页面中创建自适应表单 | [AEM 6.5 Forms](https://experienceleague.adobe.com/docs/experience-manager-65/forms/adaptive-forms-basic-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html?lang=zh-Hans#create-an-adaptive-form-in-sites-editor-or-experience-fragment)、[AEM Forms as Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html#create-an-adaptive-form-in-sites-editor-or-experience-fragment) |
| 在 AEM 体验片段中创建自适应表单 | [AEM 6.5 Forms](https://experienceleague.adobe.com/docs/experience-manager-65/forms/adaptive-forms-basic-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html?lang=zh-Hans#create-an-adaptive-form-in-experience-fragment)、[AEM Forms as Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html#create-an-adaptive-form-in-experience-fragment) |
| 将自适应表单转换为体验片段 | [AEM 6.5 Forms](https://experienceleague.adobe.com/docs/experience-manager-65/forms/adaptive-forms-basic-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html?lang=zh-Hans#convert-an-adaptive-form-in-sites-page-to-an-experience-fragment)、[AEM Forms as Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html#convert-an-adaptive-form-in-sites-page-to-an-experience-fragment) |





<!-- >, such as  [WCAG 2.1 standard](https://www.w3.org/TR/WCAG21/), to ensure that forms can be used by people with disabilities, including those using assistive technologies such as screen readers.

*   **Alignment with AEM Sites**: The Core Components are designed to be more aligned with AEM Sites, making it easier for Sites users to adopt and use them without having to learn anything new. The components use the same front-end pipeline as Sites, making it easier to style and modify their appearance. 

<!-- Additionally, the following points further illustrate this alignment:

    *   **Authoring experience inline with Page editor**: The Core Components have an authoring experience that is inline with the Sites editor, with dialogs and other experiences similar to the Page editor. This makes it easier for Sites users to create and manage forms within the familiar context of the Sites editor.

    *   **Inline form editing in Sites editor**: The Core Components allow  inline form editing within the Sites editor, avoiding the need to switch back and forth between editors. This streamlines the authoring experience and makes it easier to create and manage forms.

    *   **Inheriting Sites features in Forms**: Forms authored within a Sites page inherit the same features as Sites. This provides a seamless and integrated experience for creating and managing forms within the context of AEM Sites 
    
    <!--including Multi Site Manager, the ability to use Sites components within a form for static content, support for scheduled publish/unpublish, form translation aligned with Sites translation, versioning, and targeting -->

## 另请参阅 {#see-also}

{{see-also}}
