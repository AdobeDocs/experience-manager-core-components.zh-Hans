---
title: 自适应表单核心组件 - 表单容器
description: 将自适应表单添加到网页。
role: Architect, Developer, Admin, User
exl-id: 03c4cf7c-51d6-4850-a566-1c0514d52dab
source-git-commit: 6725784bd4c94d433c91d6bd65d14d03cbefd954
workflow-type: tm+mt
source-wordcount: '1524'
ht-degree: 97%

---


# 表单容器 {#form-container-adaptive-forms-core-component}

<span class="preview">本文将讨论&#x200B;**草稿** <!--and **Hamburger Menu Support** --> 功能，这是一个预发行功能。该预发行功能仅可通过我们的[预发行渠道](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/release-notes/prerelease.html?lang=zh-Hans#new-features)访问。</span>

通过表单，网站访客可与网站交互，提供宝贵的信息，这样即可提高参与度和用户满意度。利用 Adobe Experience Manager (AEM) Sites 中的自适应表单容器，网站所有者可以轻松地将表单添加到其页面。这样通过一种简化的方式供访客提供反馈、进行查询和完成其他操作，有助于促进网站访客与网站所有者或组织之间的交流

{{traditional-aem}}

## 用途 {#reasons-to-use-forms-container}

有若干原因可将表单添加到网站：
- **数据收集**：表单可用于从网站访客收集数据作各种用途，如市场调查、用户行为分析等。

- **商机开发**：表单可用于从潜在客户收集姓名和电子邮件地址等信息，以便为销售和营销工作开发商机。

- **电子商务**：表单可用于在线购物，使客户可通过网站下订单和付款。

- **联系方式**：通过联系方式表单，网站访客可轻松地与网站所有者或组织取得联系。

- **调查和投票**：表单可用于通过调查和投票收集网站访客的反馈和意见。

- **活动注册**：表单可用于活动注册，从而使网站访客能够注册活动或网络研讨会。

- **订阅**：表单可用于网站订阅，从而使访客能够注册新闻稿或其他定期通讯。

- **用户身份验证**：表单可用于用户身份验证，从而使网站访客能够创建帐户并登录以访问专有内容或功能。

- **提高转化率**：设计良好的表单可让用户轻松完成所需操作（例如，购买产品或注册服务），从而提高转化率。

## 版本和兼容性 {#version-and-compatibility}

自适应的Forms折叠核心组件于2023年2月发布，作为Cloud Service核心组件2.0.4以及AEM 6.5.16.0 Forms或更高版本的核心组件1.1.12的一部分。 下表显示所有支持的版本、AEM 兼容性以及相应文档的链接：

| 组件版本 | AEM as a Cloud Service | AEM 6.5.16.0 Forms 或更高版本 |
|---|---|---|
| v1 | 与<br>[版本 2.0.4](/help/adaptive-forms/version.md) 和更高版本兼容 | 与<br>[版本 1.1.12](/help/adaptive-forms/version.md) 和更高版本兼容，但低于版本 2.0.0。 |

有关核心组件版本的信息，请参阅[核心组件版本](/help/adaptive-forms/version.md)文档。
<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion_cn). -->

## 技术详细信息 {#technical-details}

可在 [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/container/v1/container) 上的技术文档中获得关于自适应表单容器核心组件的最新信息。有关开发核心组件的更多信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## “配置”对话框 {#configure-dialog}

通过“配置”对话框，可轻松地自定义您为访客提供的表单容器体验。还可轻松地定义表单容器选项，从而营造一种无缝的用户体验。

### “基本”选项卡 {#basic-tab}

![“基本”选项卡](/help/adaptive-forms/assets/formcontainer_basictab1.png)

- **标题** - 通过组件的标题，可轻松地标识表单中的组件，默认情况下，标题显示在该组件的顶部。如果不添加标题，则显示该组件的名称而非标题文本。

- **预填充服务** - 通过此选项，用户可选择一项预填充服务以供在呈现自适应表单时检索数据。详细了解[如何创建和配置预填充服务](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/prepopulate-adaptive-form-fields.html?lang=zh-Hans#aem-forms-custom-prefill-service)。

- **角色**：角色是一个 HTML 属性，用于向屏幕阅读器等辅助技术指定 HTML 元素的用途。角色属性用于为元素提供额外的上下文和语义，使屏幕阅读器更容易向用户解释和读出内容。例如，在 AEM Forms 中，表单字段的标签可能具有“标签”的作用，其输入字段可能具有“文本框”的作用。这有助于屏幕阅读器理解标签和输入字段之间的关系，并正确地向用户读出内容。

- **客户端库类别** - 用户可以为每个自适应表单配置自定义 JavaScript 库。建议只保留库中可重用的函数，这些函数依赖 jquery 和 underscore.js 第三方库。
有时，如果存在&#x200B;**复杂的验证规则**，则准确的验证脚本驻留在自定义函数中，并且用户从字段验证表达式中调用这些自定义函数。要在执行服务器端验证时使此自定义函数库已知并可用，表单用户可以在自适应表单容器属性的&#x200B;**[!UICONTROL “基本”]**&#x200B;选项卡下配置 AEM 客户端库的名称。用户可以为每个自适应表单配置自定义 JavaScript 库。该库中只保留可重用的函数，这些函数依赖 jquery 和 underscore.js 第三方库。

<!--
- **Enable the hamburger menu for mobile view** - Select the checkbox to integrate a hamburger menu into your form for mobile view. Represented by three horizontal lines stacked vertically, this menu provides a clear and uncluttered display for panels on smaller devices, especially on mobile devices. For more information about the hamburger menu, refer to the [Learn more about the hamburger menu](#learn-more-about-the-hamburger-menu) section. -->


### “数据模型”选项卡 {#data-model-tab}

![“提交”选项卡](/help/adaptive-forms/assets/formcontainer_fdmtab.png)

您可以使用表单数据模型将表单连接到数据源，以根据用户操作来发送和接收数据。您还可以将表单连接到 JSON 架构，以接收预定义格式的提交数据。根据要求，将表单连接到 JSON 架构或表单数据模型：
- 创建 JSON 架构并上传到您的环境
- 创建表单数据模型

### 草稿

![“提交”选项卡](/help/adaptive-forms/assets/formcontainer_autosavetab.png)

- **自动保存草稿**：选择&#x200B;**自动保存草稿**&#x200B;复选框可将表单保存为草稿。
- **保存偏好设置**：将&#x200B;**保存偏好设置**&#x200B;配置为&#x200B;**定期保存草稿**，以在特定时间间隔后自动保存表单。
  **保存间隔频率（秒）**：指定时间间隔（以秒为单位），以设置按照定义的间隔触发表单自动保存的持续时间。

### “提交”选项卡 {#submission-tab}

用户可以为自适应表单提交配置不同的操作。

- **重定向 URL/路径** - 通过此选项，用户可为每个表单配置一个页面，表单用户在提交自适应表单后将被重定向到该页面。单击此处以详细了解[如何配置重定向页面](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-redirect-page.html?lang=zh-Hans)。

![“提交”选项卡](/help/adaptive-forms/assets/formcontainer_submissiontab.png)

- **显示消息** - 通过此选项，用户可添加在成功提交自适应表单时显示的消息。对话框中包括预定义的文本，并且用户可修改这些文本。“显示消息”对话框支持富文本格式化工具，通过这些功能，用户可为所添加的文本设置格式。

![“显示消息”选项卡](/help/adaptive-forms/assets/formconatiner_showmessage.png)

- **提交操作** - 当用户单击自适应表单上的“提交”按钮时将触发提交操作。用户可以从下拉列表中选择受支持的现有提交操作。了解如何[在“提交”选项卡中配置提交操作](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html?lang=zh-Hans#supporting-custom-functions-in-validation-expressions-br)。

## “设计”对话框 {#design-dialog}

“设计”对话框用于定义和管理表单容器组件的 CSS 样式。

### “允许使用的组件”选项卡 {#allowed-components-tab}

![“设计”对话框允许使用的组件选项卡](/help/adaptive-forms/assets/formcontainer-allowedcomponents.png)

通过&#x200B;**允许使用的组件**&#x200B;选项卡，模板编辑器可设置组件，这些组件可作为项添加到自适应表单编辑器组件中的面板。

### “默认组件”选项卡 {#default-components-tab}

![“设计”对话框默认组件选项卡](/help/adaptive-forms/assets/formcontainer-defaultcomponents.png)

通过&#x200B;**默认组件**&#x200B;选项卡，模板编辑器可指定默认情况下作为项显示在自适应表单编辑器中的表单容器组件中的组件。

### “响应式设置”选项卡 {#responsive-tab}

![“设计”对话框响应式设置选项卡](/help/adaptive-forms/assets/formcontainer-responsivestyle.png)

通过&#x200B;**响应式设置**&#x200B;选项卡，模板编辑器可指定自适应表单编辑器中的表单容器组件内的网格列数。

### “样式”选项卡 {#styles-tab}

自适应表单文件附件核心组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。

![“设计”对话框](/help/adaptive-forms/assets/formcontainer-styletab.png)

- **默认 CSS 类**：可为自适应表单表单容器核心组件提供默认 CSS 类。

- **允许使用的样式**：可通过提供名称和表示样式的 CSS 类而定义样式。例如，您可以创建一个名为“bold text”的样式，并提供 CSS 类“font-weight: bold”。可使用这些样式或将其应用于自适应表单编辑器中的自适应表单。要应用样式，请在自适应表单编辑器中选择要将样式应用于的组件，导航到“属性”对话框，然后从&#x200B;**样式**&#x200B;下拉列表中选择所需的样式。如果您需要更新或修改样式，只需返回“设计”对话框，在“样式”选项卡中更新样式，然后保存更改。

### “自定义属性”选项卡

![“自定义属性”对话框](/help/adaptive-forms/assets/formcontainer-custompropertiestab.png)

通过自定义属性，您可使用表单模板将自定义属性（键值对）关联到自适应表单核心组件。自定义属性反映在组件 Headless 演绎版的属性部分中。它可让您创建根据自定义属性值进行调整的动态表单行为。例如，开发人员可以为移动、桌面或 Web 平台设计 Headless 表单组件的各种演绎版，从而大大提升各种设备上的用户体验。

- **组名称**：您可以提供名称来标识自定义属性组。您可以添加、删除或重新排列多个自定义属性组。添加自定义属性组后，可看到以下选项：

   - **键值对**：您可以通过单击“**添加**”按钮，为每个自定义属性组添加多个自定义属性名称和自定义属性值。

   - **删除**：点按或单击此项可删除自定义属性名称和自定义属性值。

   - **重新排列**：点按或单击并拖动可重新排列自定义属性名称和自定义属性值的顺序。

<!--
## Learn more about the hamburger menu

A hamburger menu, often referred to as a mobile menu or navigation drawer, is a popular design element in mobile user interfaces. It features three horizontal lines stacked vertically, resembling a hamburger. The design efficiently conserves screen space by hiding secondary navigation options until they are needed, especially on smaller devices such as mobile. AEM forms can be efficiently organized within the hamburger menu, enabling users to access various panels within a form without overwhelming the main interface.

Consider a scenario, where a financial institution offers an online loan application form that requires users to provide detailed information across several panels, such as personal details, financial information, loan preferences, and supporting documents. The form includes multiple panels and options that can clutter the interface, especially on mobile devices. Users need an organized way to navigate through these panels without feeling overwhelmed. The hamburger menu is implemented to enhance the user experience on mobile devices.

### Components of hamburger menu

![Hamburger Menu](/help/adaptive-forms/assets/hamburger-menu.png){width=50%, align=center}

**A. Hamburger menu**: The hamburger menu features a navigation panel that slides out or drops down when the hamburger icon is clicked or tapped. The menu displays the panel headings, and selecting a panel shifts the focus to that panel. It allows users to easily navigate between different panels.

![Hamburger Menu](/help/adaptive-forms/assets/hamburger-menu-icon.png){width=50%}

**B. Breadcrumb**: Breadcrumbs indicate the user’s current location within the form. They offer a hierarchical trail that shows the user’s navigation path and helps them understand their position in the form.

**C. Active panel**: The active panel refers to the section or part of the form that is currently being displayed. When a user selects an option from the hamburger menu, the corresponding panel becomes the active panel, showing the relevant fields and information for that section.

### Points to consider while working with the hamburger menu

- The hamburger menu displays only the names of the panels. Here are different scenarios illustrating how the panel name appears in the navigation pane of the hamburger menu based on the configuration properties of the panel:  
  
  - If you set the properties of the panel to hidden, the panel's name does not appear in the navigation pane of the hamburger menu. For example, if you configure the properties of the `Financial Information` panel as `hidden`, the panel name does not appear in the navigation pane of the hamburger menu.
    
    ![Hidden panel](/help/adaptive-forms/assets/hidden-panel.png){width=50%}

  - If you set the properties of the panel to `disabled`, its name appears in the navigation pane of the hamburger menu, but you cannot select or edit it. For example, if you configure the properties of the `Financial Information` panel as `disabled`, the panel name appears in the navigation pane, but it cannot be selected or edited. 
     
    ![Disabled panel](/help/adaptive-forms/assets/disabled-panel.png){width=50%}

  - If you hide the  title of the panel, it does not appear in the navigation pane of the hamburger menu. A blank space shows up instead, but you can navigate to the fields of the panel by clicking on that space. For example, if you hide the title of the `Financial Information` panel, the blank space appears in its place in the navigation pane of the hamburger menu. You can navigate to the fields of the panel by clicking on the blank space.
    
    ![Hidden title panel](/help/adaptive-forms/assets/hidden-title-panel.png){width=50%}

- By default, the navigation pane in the breadcrumb component supports up to three levels of navigation. However, with the custom component, you can configure the navigation hierarchy to accommodate as many levels as needed.
- When using the hamburger menu, the user can navigate between panels using arrows. However, once a panel is selected, the menu automatically closes, and focus shifts to the fields within the chosen panel.

### Advantages to use hamburger menu

- **Space efficiency**: By hiding form navigation options until needed, the hamburger menu maximizes screen space, which is especially beneficial on smaller devices.

- **Clutter reduction**: It minimizes visual clutter by consolidating various form navigation links into a single, collapsible menu.

- **Improved focus**: With fewer visible navigation elements, users can concentrate on the main content of the form without being distracted by secondary options.

- **Simplified design**: It creates a more streamlined user interface, resulting in a cleaner and more organized form layout.

- **Enhanced mobile experience**: On mobile devices, where screen space is limited, the hamburger menu offers an efficient way to access all form navigation options without overwhelming the user.

### How to enable hamburger menu for your form?

To enable hamburger menu for form, perform the following steps:

1. Open form in an edit mode.
1. Open the Content browser, and select the **[!UICONTROL Guide Container]** component of your Adaptive Form. 
1. Click the Guide Container properties ![Guide properties](/help/adaptive-forms/assets/configure_icon.png) icon. The Adaptive Form Container dialog box opens. 
1. Click the  **[!UICONTROL Basic]** tab. 
1. Select the **[!UICONTROL Add hamburger menu support]** checkbox.
1. Click **[!UICONTROL Done]**.

![Basic tab](/help/adaptive-forms/assets/formcontainer_basictab.png)
-->

## 相关文章 {#related-articles}

{{more-like-this}}

## 另请参阅 {#see-also}

{{see-also}}