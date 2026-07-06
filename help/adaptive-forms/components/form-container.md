---
title: 自适应表单核心组件 - 表单容器
description: 将自适应表单添加到网页。
role: Developer, Admin, User
exl-id: 03c4cf7c-51d6-4850-a566-1c0514d52dab
TQID: https://experienceleague.adobe.com/kMG6SKHisAUmKhOh9AFLI8NG6w0vH7tP4XimBKAMo-I
product_v2:
  - id: c45915cf-e157-4af7-a80d-97b905bcb3a5
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: e2c1b6d3-bb7e-4fe8-8c72-f7b403298e91
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 0af65c80f9cc58c4ba48d5b3dc7a026820bd2833
workflow-type: tm+mt
source-wordcount: 2555
ht-degree: 64%

---

# 表单容器 {#form-container-adaptive-forms-core-component}

<span class="preview">本文讨论&#x200B;**草稿**&#x200B;和&#x200B;**汉堡菜单支持**&#x200B;功能，它们是预发行版功能。 该预发行功能仅可通过我们的[预发行渠道](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/release-notes/prerelease.html#new-features)访问。</span>

通过表单，网站访客可与网站交互，提供宝贵的信息，这样即可提高参与度和用户满意度。 利用 Adobe Experience Manager (AEM) Sites 中的自适应表单容器，网站所有者可以轻松地将表单添加到其页面。 这样通过一种简化的方式供访客提供反馈、进行查询和完成其他操作，有助于促进网站访客与网站所有者或组织之间的交流

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

作为 Cloud Service 核心组件 2.0.4 和 AEM 6.5.16.0 Forms 或更高版本核心组件 1.1.12 的一部分，自适应表单手风琴核心组件于 2023 年 2 月发布。 下表显示所有支持的版本、AEM 兼容性以及相应文档的链接：

| 组件版本 | AEM as a Cloud Service | AEM 6.5.16.0 Forms 或更高版本 |
|---|---|---|
| v1 | 与<br>[版本 2.0.4](/help/adaptive-forms/version.md) 和更高版本兼容 | 与<br>[版本 1.1.12](/help/adaptive-forms/version.md) 和更高版本兼容，但低于版本 2.0.0。 |

有关核心组件版本的信息，请参阅[核心组件版本](/help/adaptive-forms/version.md)文档。
<!--
## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). 
-->

## 技术详细信息 {#technical-details}

可在 [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/container/v1/container) 上的技术文档中获得关于自适应表单容器核心组件的最新信息。 有关开发核心组件的更多信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## “配置”对话框 {#configure-dialog}

通过“配置”对话框，可轻松地自定义您为访客提供的表单容器体验。 还可轻松地定义表单容器选项，从而营造一种无缝的用户体验。

### “基本”选项卡 {#basic-tab}

![“基本”选项卡](/help/adaptive-forms/assets/formcontainer_basictab1.png)

- **标题** - 通过组件的标题，可轻松地标识表单中的组件，默认情况下，标题显示在该组件的顶部。 如果不添加标题，则显示该组件的名称而非标题文本。

- **预填充服务** - 通过此选项，用户可选择一项预填充服务以供在呈现自适应表单时检索数据。 详细了解[如何创建和配置预填充服务](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/prepopulate-adaptive-form-fields.html?lang=zh-Hans#aem-forms-custom-prefill-service)。

- **角色**：角色是一个 HTML 属性，用于向屏幕阅读器等辅助技术指定 HTML 元素的用途。 角色属性用于为元素提供额外的上下文和语义，使屏幕阅读器更容易向用户解释和读出内容。 例如，在 AEM Forms 中，表单字段的标签可能具有“标签”的作用，其输入字段可能具有“文本框”的作用。 这有助于屏幕阅读器理解标签和输入字段之间的关系，并正确地向用户读出内容。

- **客户端库类别** - 用户可以为每个自适应表单配置自定义 JavaScript 库。 建议只保留库中可重用的函数，这些函数依赖 jquery 和 underscore.js 第三方库。有时，如果存在&#x200B;**复杂的验证规则**，则准确的验证脚本驻留在自定义函数中，并且用户从字段验证表达式中调用这些自定义函数。 要在执行服务器端验证时使此自定义函数库已知并可用，表单用户可以在自适应表单容器属性的&#x200B;**[!UICONTROL “基本”]**&#x200B;选项卡下配置 AEM 客户端库的名称。用户可以为每个自适应表单配置自定义 JavaScript 库。 该库中只保留可重用的函数，这些函数依赖 jquery 和 underscore.js 第三方库。

- **启用移动设备视图的汉堡菜单** — 选中此复选框可将汉堡菜单集成到移动设备视图的表单中。 此菜单由垂直栈叠的三条水平线表示，可为小型设备（特别是移动设备）上的面板提供清晰而整齐的显示。 有关汉堡菜单的更多信息，请参阅[了解有关汉堡菜单的更多信息](#learn-more-about-the-hamburger-menu)部分。


### “数据模型”选项卡 {#data-model-tab}

![数据模型选项卡](/help/adaptive-forms/assets/formcontainer_fdmtab.png)

您可以使用表单数据模型将表单连接到数据源，以根据用户操作来发送和接收数据。 您还可以将表单连接到 JSON 架构，以接收预定义格式的提交数据。 根据要求，将表单连接到 JSON 架构或表单数据模型：
- **无** — 不要将表单与数据模型关联。
- **架构** — 将表单连接到上载到您环境的JSON架构。
- **表单数据模型** — 将表单连接到表单数据模型以与外部数据源集成。
- **连接器** — 将表单连接到基于连接器的数据源。
- **表单模板** — 将表单与表单模板关联。

### “草稿”选项卡 {#drafts-tab}

![草稿选项卡](/help/adaptive-forms/assets/formcontainer_autosavetab.png)

- **自动保存草稿**：选择&#x200B;**自动保存草稿**&#x200B;复选框可将表单保存为草稿。
- **保存偏好设置**：将&#x200B;**保存偏好设置**&#x200B;配置为&#x200B;**定期保存草稿**，以在特定时间间隔后自动保存表单。
  **保存间隔频率（秒）**：指定时间间隔（以秒为单位），以设置按照定义的间隔触发表单自动保存的持续时间。

### “提交”选项卡 {#submission-tab}

用户可以为自适应表单提交配置不同的操作。

- **在提交时** — 选择&#x200B;**重定向到URL**&#x200B;以在提交后将表单用户发送到配置的页面，或选择&#x200B;**显示消息**&#x200B;以在表单上显示确认消息。

- **重定向 URL/路径** - 通过此选项，用户可为每个表单配置一个页面，表单用户在提交自适应表单后将被重定向到该页面。 单击此处以详细了解[如何配置重定向页面](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-redirect-page.html?lang=zh-Hans)。

![“提交”选项卡](/help/adaptive-forms/assets/formcontainer_submissiontab.png)

- **显示消息** - 通过此选项，用户可添加在成功提交自适应表单时显示的消息。 对话框中包括预定义的文本，并且用户可修改这些文本。 “显示消息”对话框支持富文本格式化工具，通过这些功能，用户可为所添加的文本设置格式。

![“显示消息”选项卡](/help/adaptive-forms/assets/formconatiner_showmessage.png)

- **提交操作** - 当用户单击自适应表单上的“提交”按钮时将触发提交操作。 用户可以从下拉列表中选择受支持的现有提交操作。 了解如何[在“提交”选项卡中配置提交操作](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/create-an-adaptive-form/configure-submit-actions-and-metadata-submission/configuring-submit-actions.html?lang=zh-Hans#supporting-custom-functions-in-validation-expressions-br)。

- **操作配置** — 配置映射以将字段值作为感谢页面请求参数进行传递。

- **启用POST请求** — 选择此选项可使用HTTP POST请求提交表单数据。

### 记录文档选项卡 {#document-of-record-tab}

![记录文档选项卡](/help/adaptive-forms/assets/formcontainer_dortab.png)

[记录文档(DoR)](https://experienceleague.adobe.com/zh-hans/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/generate-document-of-record-core-components)是通过表单提交的数据的正式可打印表示形式。 使用&#x200B;**记录文档**&#x200B;选项卡配置在用户提交表单时如何生成DoR：

- **无** — 不为表单生成记录文档。
- **将表单模板关联为记录文档模板** — 使用现有表单模板作为DoR模板。
- **生成记录文档** — 根据提交的表单数据自动生成记录文档。
- **从记录文档排除文件附件** — 选择此选项可从生成的DoR中忽略文件附件。

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

- **允许使用的样式**：可通过提供名称和表示样式的 CSS 类而定义样式。 例如，您可以创建一个名为“bold text”的样式，并提供 CSS 类“font-weight: bold”。 可使用这些样式或将其应用于自适应表单编辑器中的自适应表单。 要应用样式，请在自适应表单编辑器中选择要将样式应用于的组件，导航到“属性”对话框，然后从&#x200B;**样式**&#x200B;下拉列表中选择所需的样式。 如果您需要更新或修改样式，只需返回“设计”对话框，在“样式”选项卡中更新样式，然后保存更改。

### “自定义属性”选项卡

![“自定义属性”对话框](/help/adaptive-forms/assets/formcontainer-custompropertiestab.png)

通过自定义属性，您可使用表单模板将自定义属性（键值对）关联到自适应表单核心组件。 自定义属性反映在组件 Headless 演绎版的属性部分中。 它可让您创建根据自定义属性值进行调整的动态表单行为。 例如，开发人员可以为移动、桌面或 Web 平台设计 Headless 表单组件的各种演绎版，从而大大提升各种设备上的用户体验。

- **组名称**：您可以提供名称来标识自定义属性组。 您可以添加、删除或重新排列多个自定义属性组。 添加自定义属性组后，可看到以下选项：

   - **键值对**：您可以通过单击“**添加**”按钮，为每个自定义属性组添加多个自定义属性名称和自定义属性值。

   - **删除**：点击或单击此项可删除自定义属性名称和自定义属性值。

   - **重新排列**：点击或单击并拖动可重新排列自定义属性名称和自定义属性值的顺序。

## 了解有关汉堡菜单的更多信息 {#learn-more-about-the-hamburger-menu}

汉堡菜单（通常称为移动菜单或导航抽屉）是移动用户界面中常用的设计元素。 它有三条垂直栈叠的水平线，像一个汉堡包。 该设计通过隐藏辅助导航选项直到需要它们时有效地节省屏幕空间，尤其是在较小的设备（如移动设备）上。 AEM表单可以在汉堡菜单中进行有效组织，使用户能够访问表单中的各种面板，而不会在主界面中占据。

考虑一个方案，金融机构提供在线贷款申请表，要求用户在多个面板中提供详细信息，如个人详细信息、财务信息、贷款偏好设置和支持文档。 该表单包含多个面板和选项，可能会使界面（尤其是在移动设备上）变得杂乱。 用户需要一种有条理的方式来浏览这些面板，而不会感到不知所措。 实施汉堡菜单以增强移动设备的用户体验。

### 汉堡菜单组件

![汉堡菜单](/help/adaptive-forms/assets/hamburger-menu.png){width=50%, align=center}

**A。汉堡菜单**：汉堡菜单具有导航面板，单击或点按汉堡图标时该面板会滑出或下降。 菜单会显示面板标题，选择面板会将焦点移至该面板。 它允许用户在不同的面板之间轻松导航。

![汉堡菜单](/help/adaptive-forms/assets/hamburger-menu-icon.png){width=50%}

**B。痕迹导航**：痕迹导航指示用户在表单中的当前位置。 它们提供分层跟踪，可显示用户的导航路径并帮助用户了解他们在表单中的位置。

**C。活动面板**：活动面板引用了当前显示的部分或表单部分。 当用户从汉堡菜单选择选项时，相应的面板将成为活动面板，显示该部分的相关字段和信息。

### 使用汉堡菜单时要考虑的点

- 汉堡菜单仅显示面板的名称。 以下不同情形说明了面板名称如何根据面板的配置属性显示在汉堡菜单的导航窗格中：

   - 如果将面板的属性设置为隐藏，则面板的名称不会出现在汉堡菜单的导航窗格中。 例如，如果将`Financial Information`面板的属性配置为`hidden`，则面板名称不会出现在汉堡菜单的导航窗格中。

     ![隐藏面板](/help/adaptive-forms/assets/hidden-panel.png){width=50%}

   - 如果将面板的属性设置为`disabled`，则其名称会显示在汉堡菜单的导航窗格中，但无法选择或编辑它。 例如，如果将`Financial Information`面板的属性配置为`disabled`，则面板名称会显示在导航窗格中，但无法选择或编辑它。

     ![已禁用面板](/help/adaptive-forms/assets/disabled-panel.png){width=50%}

   - 如果隐藏面板的标题，则它不会出现在汉堡菜单的导航窗格中。 此时将显示一个空格，但您可以通过单击该空格来导航至面板的字段。 例如，如果隐藏`Financial Information`面板的标题，则空白会出现在汉堡菜单导航窗格中的相应位置。 您可以通过单击空格来导航到面板的字段。

     ![隐藏的标题面板](/help/adaptive-forms/assets/hidden-title-panel.png){width=50%}

- 默认情况下，痕迹导航组件中的导航窗格最多支持三个级别的导航。 但是，使用自定义组件，您可以配置导航层次结构以根据需要容纳尽可能多的级别。
- 使用汉堡菜单时，用户可以使用箭头在面板之间导航。 但是，一旦选择了面板，菜单就会自动关闭，并且焦点会转移到所选面板内的字段。

<!--
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

![Basic tab](/help/adaptive-forms/assets/formcontainer_basictab1.png)
-->

## 相关文章 {#related-articles}

{{more-like-this}}

## 另请参阅 {#see-also}

{{see-also}}