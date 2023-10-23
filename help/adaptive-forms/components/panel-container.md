---
title: 自适应表单核心组件 - 面板容器
description: 使用或自定义自适应表单面板容器核心组件。
role: Architect, Developer, Admin, User
exl-id: 104836fe-8325-47de-978d-1ff2d6a9dd15
source-git-commit: 37ac7d3a9ae8c88d4c9be8129cfbd1eb4a7cccd1
workflow-type: tm+mt
source-wordcount: '1828'
ht-degree: 90%

---

# 面板容器 {#panel-container-adaptive-forms-core-component}

在自适应表单中，面板是一个容器元素，可用于将相关表单元素组合在一起。它可让您以一种符合逻辑且有意义的方式对不同的表单元素进行分组和整理。这有助于改善表单的整体结构和可读性，使用户能够更轻松地理解和导航。

面板也可用于创建可可折叠项部分，这对于隐藏复杂或不常用的表单字段来说很有用，可以使表单简单易用。它还可让您包含其他组件，如文本、复选框、按钮等。

它还可用于设置各种基于规则的操作，如提交表单、打开网站、显示/隐藏组件或添加面板实例。

**示例**

![](/help/adaptive-forms/assets/panel-container.png)

## 用途 {#reasons-to-use-panel-container}

有若干原因要在表单中使用面板，这些原因包括：

- **整理表单元素**：面板可用于将相关的表单元素组合起来，使用户能够更轻松地理解和浏览表单。

- **改善表单结构**：通过将表单元素分组到面板中，可以改善表单的整体结构和可读性，使其更易于理解。

- **创建可可折叠项部分**：面板可用于创建可可折叠项部分，这对于隐藏复杂或不常用的表单字段来说很有用，可以使表单简单易用。

- **增强可用性**：通过使用面板整理表单元素，可使得表单变得更方便用户使用，从而提高完成率。

## 版本和兼容性 {#version-and-compatibility}

2023 年 2 月，作为核心组件 2.0.4 的一部分发布了自适应表单面板容器核心组件。下表展示所有支持的版本、AEM 兼容性和相应文档的链接：

|  |  |
|---|---|
| 组件版本 | AEM as a Cloud Service |
| --- | --- |
| v1 | 兼容<br>[版本 2.0.4](/help/versions.md) 和更高版本 | 兼容 | 兼容 |

有关核心组件版本的信息，请参阅[核心组件版本](/help/versions.md)文档。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技术详细信息 {#technical-details}

可在 [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/panelcontainer/v1/panelcontainer) 上的技术文档中获得关于自适应表单面板容器核心组件的最新信息。有关开发核心组件的更多信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## “配置”对话框 {#configure-dialog}

通过“配置”对话框，可轻松地自定义您为访客提供的面板容器体验。还可轻松地定义面板容器选项，从而营造一种无缝的用户体验。

### “基本”选项卡 {#basic-tab}

![“基本”选项卡](/help/adaptive-forms/assets/basic-panel.png)

- **名称** - 可在表单和规则编辑器中通过唯一名称轻松地标识表单组件，但该名称不得包含空格或特殊字符。

- **标题** - 通过组件的标题，可轻松地标识表单中的组件，默认情况下，标题显示在该组件的顶部。如果不添加标题，则显示该组件的名称而非标题文本。

- **隐藏标题** - 选中此选项以隐藏该组件的标题。

- **表单提交时对子组件的数据进行分组（将数据包装在对象中）** - 选择该选项后，子组件中的数据将嵌套在父组件的 JSON 对象中。但是，如果未选择该选项，则提交的 JSON 数据具有扁平结构，没有父组件的对象。例如：

   - 选择该选项后，子组件中的数据（例如，街道、城市和邮政编码）将作为 JSON 对象嵌套在父组件（地址）中。这将创建一个层次结构，并且数据组织在父组件下。

     提交数据的结构：

     ```JSON
     { "Address":
     
     { "Street": "123 Main Street", "City": "New York", "Zip Code": "12345" }
     
     }
     ```

   - 当未选择该选项时，提交的 JSON 数据具有扁平结构，没有父组件（地址）的对象。所有数据都处于同一级别，没有任何层级组织。


     提交数据的结构：

     ```JSON
        { "Street": "123 Main Street", "City": "New York", "Zip Code": "12345" }
     ```

- **布局** - 可为向导采用固定布局（“简单”）或灵活布局（“响应式网格”）。“简单”布局将所有内容固定在原位，而通过“响应式网格”，可调整组件的位置以满足您的需要。例如，使用响应式网格将表单中的“名字”、“中间名”和“姓氏”排成一行。

- **绑定引用** - 绑定引用是对存储在外部数据源中并在表单中使用的数据元素的引用。通过绑定引用，可动态地将数据绑定到表单字段，以使表单可显示来自数据源的最新数据。例如，可使用绑定引用，根据输入到表单中的客户 ID，在该表单中显示该客户的姓名和地址。还可使用绑定引用，通过输入到表单中的数据更新数据源。这样通过 AEM Forms 即可创建与外部数据源交互的表单，从而为收集和管理数据提供一种无缝的用户体验。
- **隐藏组件** - 选中此选项以从表单中隐藏该组件。仍可访问该组件作其他用途，如在规则编辑器中使用它进行计算。当需要存储用户无需看到或直接更改的信息时，此项很有用。
- **禁用组件** - 选中此选项以禁用该组件。被禁用的组件不再活跃或最终用户无法编辑它。用户可看到但无法修改字段的值。仍可访问该组件作其他用途，如在规则编辑器中使用它进行计算。

### 重复面板选项卡 {#repeat-panel}

![重复选项卡](/help/adaptive-forms/assets/repeat-panel.png)

您可以使用重复选项来复制面板容器及其子组件，定义最小和最大重复计数，并促进在表单内复制类似部分。当与面板容器组件交互并访问其设置时，会出现以下选项：

- **使向导可重复**：切换功能，允许用户启用或禁用重复功能。
- **最少重复次数**：确定面板容器可以重复的最小次数。值为零表示向导面板不重复；默认值为零。
- **最多重复次数**：设置面板容器可以重复的最多次数。默认情况下，此值无限制。

要有效管理面板容器中的可重复部分，请按照[创建具有可重复部分的表单](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/create-forms-repeatable-sections.html)文章。

### “帮助内容”选项卡 {#help-content}

![“帮助内容”选项卡](/help/adaptive-forms/assets/helpcontent-panel.png)


- **简短描述** - 简短描述是一段简短的文字说明，其中提供关于特定表单字段的用途的其他信息或阐述。它帮助用户了解应将什么类型的数据输入到字段中，并可提供准则或示例以帮助确保所输入的信息有效且符合预期的标准。默认情况下，简短描述保持隐藏状态。启用&#x200B;**始终显示简短描述**&#x200B;选项以在组件下方显示它。

- **始终显示简短描述** - 启用该选项以在组件下方显示简短描述。

- **帮助文本** - 帮助文本是指提供给用户以帮助其正确填写表单字段的其他信息或指导。当用户单击组件旁的“帮助”图标 (i) 时显示它。帮助文本提供比表单字段的标签或占位符文本更详细的信息，旨在帮助用户了解该字段的要求或限制。它还可提供建议或示例，以使填写表单更轻松且更准确。

### “辅助功能”选项卡 {#accessibility}

![“辅助功能”选项卡](/help/adaptive-forms/assets/accessibilty-panel.png)


- **屏幕阅读器文本** - 屏幕阅读器文本是指专供由视障人士使用的屏幕阅读器等辅助技术读取的附加文本。此文本提供表单字段用途的音频描述，并可包括关于字段的标题、描述、名称和任何相关消息（自定义文本）的信息。屏幕阅读器文本帮助确保包括视障用户在内的所有用户均可访问表单，并使其完整地了解表单字段及其要求。

- **用于读出内容的屏幕阅读器的 HTML 角色** - HTML 角色是一个属性，用于向屏幕阅读器等辅助技术指定 HTML 元素的用途。角色属性用于为元素提供额外的上下文和语义，使屏幕阅读器更容易向用户解释和读出内容。例如，在 AEM Forms 中，表单字段的标签可能具有“标签”的作用，其输入字段可能具有“文本框”的作用。这有助于屏幕阅读器理解标签和输入字段之间的关系，并正确地向用户读出内容。

## 相关文章 {#related-articles}

- [可折叠项](/help/adaptive-forms/components/accordion.md)
- [按钮](/help/adaptive-forms/components/button.md)
- [复选框组](/help/adaptive-forms/components/checkbox-group.md)
- [日期选取器](/help/adaptive-forms/components/date-picker.md)
- [下拉列表](/help/adaptive-forms/components/drop-down.md)
- [电子邮件输入](/help/adaptive-forms/components/email-input.md)
- [表单容器](/help/adaptive-forms/components/form-container.md)
- [文件附件](/help/adaptive-forms/components/file-attachment.md)
- [页脚](/help/adaptive-forms/components/footer.md)
- [页眉](/help/adaptive-forms/components/header.md)
- [水平选项卡](/help/adaptive-forms/components/horizontal-tabs.md)
- [图像](/help/adaptive-forms/components/image.md)
- [数字输入](/help/adaptive-forms/components/number-input.md)
- [单选按钮](/help/adaptive-forms/components/radio-button.md)
- [“重置”按钮](/help/adaptive-forms/components/reset-button.md)
- [“提交”按钮](/help/adaptive-forms/components/submit-button.md)
- [电话号码输入](/help/adaptive-forms/components/telephone-input.md)
- [文本输入](/help/adaptive-forms/components/text-input.md)
- [文本](/help/adaptive-forms/components/text.md)
- [标题](/help/adaptive-forms/components/title.md)
- [向导](/help/adaptive-forms/components/wizard.md)


## 另请参阅 {#see-also}

- [创建AEM自适应表单](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html)
- [将AEM自适应表单添加到AEM Sites页面](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html)
- [将主题应用到AEM自适应表单](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/using-themes-in-core-components.html)
- [将组件添加到AEM自适应表单](/help/adaptive-forms/introduction.md#adaptive-forms-core-components-components)
- [在AEM自适应表单中使用reCAPTCHA](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/add-components-to-an-adaptive-form/captcha-adaptive-forms.html)
- [生成AEM自适应表单的PDF版本(DoR)](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/generate-document-of-record-core-components.html)
- [翻译AEM自适应表单](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/using-aem-translation-workflow-to-localize-adaptive-forms-core-components.html)
- [为自适应表单启用Adobe Analytics以跟踪表单使用情况](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/integrate/services/enable-adobe-analytics-adaptive-form-using-experience-cloud-setup-automation.html)
- [将自适应表单连接到Microsoft SharePoint](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components.html#create-sharepoint-configuration)
- [将自适应表单连接到Microsoft Power Automate](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components.html#microsoft-power-automate)
- [将自适应表单连接到Microsoft OneDrive](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components.html#submit-to-onedrive)
- [将自适应表单连接到Microsoft Azure Blob Storage](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components.html#submit-to-azure-blob-storage)
- [将自适应表单连接到Salesforce](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/integrate/use-form-data-model/oauth2-client-credentials-flow-for-server-to-server-integration.html)
- [在AEM自适应表单中使用Adobe Sign](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/use-adobe-sign/working-with-adobe-sign.html)
- [为自适应表单添加新区域设置](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/supporting-new-language-localization-core-components.html)
- [将自适应表单数据发送到数据库](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/integrate/use-form-data-model/data-integration.html)
- [将自适应表单数据发送到REST端点](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components.html#submit-to-rest-endpoint)
- [将自适应表单数据发送到AEM Workflow](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/configure-submit-actions-core-components.html#invoke-an-aem-workflow)
- [使用Forms Portal在AEM网站上列出AEM自适应Forms](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/configure-forms-portal.html)

