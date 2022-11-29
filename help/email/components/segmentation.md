---
title: 电子邮件分段组件
description: 电子邮件分段组件
role: Architect, Developer, Admin, User
exl-id: 6c88b8c5-189a-40c0-ab28-04d37dc5fbac
source-git-commit: 33976c0e745ad091a142109f70541f01a31edc5b
workflow-type: tm+mt
source-wordcount: '1171'
ht-degree: 100%

---


# 电子邮件分段组件 {#email-segmentation-component}

电子邮件分段组件使用 Adobe Campaign 中的变量来根据内容的收件人显示和隐藏内容。

## 用途 {#usage}

电子邮件分段组件允许内容作者根据 Adobe Campaign 提供的有关收件人的变量所满足的条件隐藏和显示内容。 通过这种方式，内容的接收者可以看到基于他们的分段的内容。

* 模板作者可以使用[设计对话框](#design-dialog)定义哪些组件可以添加为段。
* 内容作者可以使用[配置对话框](#configure-dialog)将组件添加为分段并根据 Adobe Campaign 变量配置显示哪些分段。

作为使用配置对话框的替代方法，一旦内容作者将电子邮件分段组件添加到内容页面，内容作者就可以将其他组件拖放到电子邮件分段组件上创建新分段。

## 版本和兼容性 {#version-and-compatibility}

电子邮件分段组件的当前版本是 v1，此版本随 2022 年 10 月的电子邮件核心组件发行版本 X 的发布引入，具体说明见本文档。

下表详细说明了该组件的所有受支持版本、与该组件的版本兼容的 AEM 版本以及指向早期版本文档的链接。

| 组件版本 | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | 兼容 | 兼容 |

## 示例组件输出 {#sample-component-output}

要体验电子邮件分段组件并查看其配置选项示例以及 HTML 和 JSON 输出，请访问[组件库](https://adobe.com/go/aem_cmp_library_email_segmentation_cn)。

### 技术详细信息 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_email_segmentation_v1_cn)有关电子邮件 Teaser 组件的最新技术文档。

在[核心组件开发人员文档](/help/developing/overview.md)中可找到有关开发核心组件的其他详细信息。

## “配置”对话框 {#configure-dialog}

配置对话框允许内容作者创建、重命名和重新排列段以及定义活动段。 在电子邮件分段组件中，分段只是根据内容接收者满足的条件隐藏或显示的另一个组件。 您可以将其与[核心组件选项卡组件，](/help/components/tabs.md)进行比较，但在分段组件中，仅显示满足条件的选项卡的内容。

### “项”选项卡 {#items-tab}

![电子邮件分段组件的配置对话框项选项卡](/help/email/assets/email-segmentation-configure-items.png)

使用&#x200B;**“添加区段”**&#x200B;按钮可打开组件选择器，来选择要作为区段添加的组件。在添加之后，一个条目将添加到列表中，包含以下元素：

* **图标** – 区段的组件类型的图标，用于方便在列表中识别。将鼠标悬停在上面时将显示完整的组件名称作为工具提示。
* **条件** – 该段必须满足的条件才能显示给内容的接收者。
   * 可用的条件定义在[设计对话框。](#design-dialog)
   * **默认** – 定义默认段以显示是否不满足其他条件
   * **自定义** – 允许作者定义条件
      * 条件基于 Adobe Campaign 个性化变量
      * [有关 Adobe Campaign Standard 个性化资源的信息，请参阅此处。](https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/personalization.html?)
      * [有关 Adobe Campaign Classic 个性化资源的信息，请参阅此处。](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-fields.html)
* **删除** – 点击或单击以从电子邮件分段组件中删除区段。
* **重新排列** - 点击或单击并拖动以重新排列区段。

>[!TIP]
>
>如果减小内容视区以便全屏显示“编辑”对话框，则将隐藏&#x200B;**添加**&#x200B;按钮。 组件仍可以通过[从组件浏览器拖动并放置在内容编辑器的电子邮件分段组件上](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#inserting-a-component)来添加到电子邮件分段组件中。

### “属性”选项卡 {#properties-tab}

![电子邮件分段组件的配置对话框属性选项卡](/help/email/assets/email-segmentation-configure-properties.png)

* **ID** – 此选项允许控制 HTML 中组件的唯一标识符。
   * 如果留空，系统会自动为您生成一个唯一 ID，可以通过检查结果内容找到该 ID。
   * 如果指定一个 ID，作者有责任确保它是唯一的。
   * 更改 ID 会对 CSS 产生影响。

### “辅助功能”选项卡 {#accessibility-tab}

![电子邮件分段组件的配置对话框可访问性选项卡](/help/email/assets/email-segmentation-configure-accessibility.png)

在&#x200B;**辅助功能**&#x200B;选项卡上，可以为组件的 [ARIA 辅助功能](https://www.w3.org/WAI/standards-guidelines/aria/)标签设置值。

* **标签** - 组件的 ARIA 标签属性的值

### 样式选项卡 {#styles-tab-edit}

电子邮件分段组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。

使用下拉菜单选择要应用于该组件的样式。在“编辑”对话框中所做的选择与从组件工具栏中选择的操作效果相同。

必须在[“设计”对话框](#design-dialog)中为此组件配置样式，以便选项卡可用。

## 选择面板 {#select-panel}

内容作者可以使用组件工具栏上的&#x200B;**选择面板**&#x200B;选项，更改到不同的区段进行编辑，以及轻松地重新排列区段。

![选择面板图标](/help/email/assets/select-panel-icon.png)

在组件工具栏中选择了&#x200B;**选择面板**&#x200B;选项之后，配置的区段将显示为下拉列表。

* 下拉列表按照向区段分配的顺序排列，并体现在编号中。
* 首先显示区段的组件类型，然后是较细字体的区段描述。

![“选择面板”弹出框](/help/email/assets/select-panel-popover.png)

* 在下拉列表中点击或单击某个条目，会在编辑器中将视图切换到该区段。
* 可以使用拖动手柄就地重新排列区段。

>[!NOTE]
>
>区段在页面编辑器中呈现为选项卡，以显示最终内容有多个选项。 作者在页面编辑器中无法选择这些选项卡。 使用选择面板在显示的区段之间切换。

## “设计”对话框 {#design-dialog}

使用“设计”对话框，模板作者可以定义哪些组件可以作为区段添加到电子邮件区段组件中，并定义哪些自定义样式可供内容作者使用。

### “允许的组件”选项卡 {#allowed-components-tab}

**“允许的组件”**&#x200B;选项卡用于定义哪些组件可由内容作者作为区段添加到电子邮件分段组件。

**“允许的组件”**&#x200B;选项卡的功能，与[在模板编辑器的布局容器中定义策略和属性时的同名选项卡的功能相同。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)

### 样式选项卡 {#styles-tab}

电子邮件分段组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。

### 定义条件选项卡 {#defined-conditions}

通过&#x200B;**定义条件**&#x200B;选项卡，模板编辑器可以定义内容作者在创建区段时可以选择哪些条件。

![设计对话框定义条件选项卡](/help/email/assets/email-segmentation-design-defined-conditions.png)

点击或单击&#x200B;**添加**&#x200B;按钮可创建新条件。

* **区段条件名称** – 条件描述
* **区段条件** – 必须满足的实际条件，基于 Adobe Campaign 个性化变量
   * [有关 Adobe Campaign Standard 个性化资源的信息，请参阅此处。](https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/personalization.html?)
   * [有关 Adobe Campaign Classic 个性化资源的信息，请参阅此处。]（https://experienceleague.adobe.com/docs/
* **移除** – 点击以移除条件
* **重新排列** – 点击或单击并拖动以重新排列条件。
