---
title: 电子邮件分段组件
description: 电子邮件分段组件
role: Architect, Developer, Admin, User
hidefromtoc: true
index: false
source-git-commit: 8bebe3ca036557f3f7c6b8ec0e65d6d104d5ffae
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 电子邮件分段组件 {#email-segmentation-component}

电子邮件分段组件使用Adobe Campaign中的变量来根据内容的收件人显示和隐藏内容。

## 用途 {#usage}

电子邮件分段组件允许内容作者根据变量满足的关于Adobe Campaign提供的收件人的条件来隐藏和显示内容。 这样，内容的收件人便可以根据其分段查看内容。

* 模板作者可以使用 [设计对话框](#design-dialog) 以定义可添加为区段的组件。
* 内容作者可以使用 [配置对话框](#configure-dialog) 可将组件添加为区段，并根据Adobe Campaign变量配置显示哪些区段。

作为使用配置对话框的替代方法，内容作者将电子邮件分段组件添加到内容页面后，内容作者可以将其他组件拖放到电子邮件分段组件上以创建新区段。

## 版本和兼容性 {#version-and-compatibility}

电子邮件分段组件的当前版本为v1，该版本于2022年10月随电子邮件核心组件第x版引入，在本文档中进行了描述。

下表详细说明了该组件的所有受支持版本、与该组件的版本兼容的 AEM 版本以及指向早期版本文档的链接。

| 组件版本 | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | 兼容 | 兼容 |

## 示例组件输出 {#sample-component-output}

要体验电子邮件分段组件并查看其配置选项以及HTML和JSON输出的示例，请访问 [组件库。](https://adobe.com/go/aem_cmp_library_email_segmentation)

### 技术详细信息 {#technical-details}

有关Email Teaser组件的最新技术文档 [可在GitHub上找到。](https://adobe.com/go/aem_cmp_tech_email_segmentation_v1)

有关开发核心组件的更多详细信息，请参阅 [核心组件开发人员文档。](/help/developing/overview.md)

## “配置”对话框 {#configure-dialog}

通过“配置”对话框，内容作者可以创建、重命名和重新排列区段，以及定义活动区段。 在电子邮件分段组件中，区段只是另一个根据内容收件人满足的条件隐藏或显示的组件。 您可以将其与 [核心组件选项卡组件、](/help/components/tabs.md) 但是在分段组件中，只显示满足条件的选项卡的内容。

### “项”选项卡 {#items-tab}

![电子邮件分段组件的“配置”对话框项目选项卡](/help/email/assets/email-segmentation-configure-items.png)

使用 **添加区段** 按钮以打开组件选择器，以选择要添加为区段的组件。 添加后，会将一个条目添加到列表中，该列表包含以下元素：

* **图标**  — 区段的组件类型图标，以便在列表中轻松识别。 将鼠标悬停在上面时将显示完整的组件名称作为工具提示。
* **条件**  — 要向内容的收件人显示此区段，必须满足的条件。
   * 可用条件在 [“设计”对话框。](#design-dialog)
   * **默认**  — 定义默认区段，以在不满足其他条件时显示
   * **自定义**  — 允许作者定义条件
      * 条件基于Adobe Campaign个性化变量
      * [请参阅此处获取Adobe Campaign Standard个性化资源。](https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/personalization.html?)
      * [请参阅此处获取Adobe Campaign Classic个性化资源。](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/personalizing-deliveries/personalization-fields.html)
* **删除**  — 点按或单击以从电子邮件分段组件中删除区段。
* **重新排列**  — 点按或单击并拖动以重新排列区段。

>[!TIP]
>
>如果缩小了内容的视区，使编辑对话框变为全屏，则 **添加** 按钮。 组件仍可以通过 [从组件浏览器中拖放到内容编辑器中的电子邮件分段组件。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#inserting-a-component)

### “属性”选项卡 {#properties-tab}

![电子邮件分段组件的“配置”对话框属性选项卡](/help/email/assets/email-segmentation-configure-properties.png)

* **ID**  — 此选项允许控制组件在HTML中的唯一标识符。
   * 如果留空，则会自动为您生成唯一ID，并且可以通过检查生成的内容来找到该ID。
   * 如果指定一个 ID，作者有责任确保它是唯一的。
   * 更改ID可能会对CSS产生影响。

### “辅助功能”选项卡 {#accessibility-tab}

![电子邮件分段组件的“配置”对话框辅助功能选项卡](/help/email/assets/email-segmentation-configure-accessibility.png)

在&#x200B;**辅助功能**&#x200B;选项卡上，可以为组件的 [ARIA 辅助功能](https://www.w3.org/WAI/standards-guidelines/aria/)标签设置值。

* **标签** - 组件的 ARIA 标签属性的值

### “样式”选项卡 {#styles-tab-edit}

电子邮件分段组件支持AEM [样式系统。](/help/get-started/authoring.md#component-styling)

使用下拉菜单选择要应用于该组件的样式。在“编辑”对话框中所做的选择与从组件工具栏中选择的操作效果相同。

必须在 [设计对话框](#design-dialog) 以使选项卡可用。

## 选择面板 {#select-panel}

内容作者可以使用 **选择面板** 选项，以更改为其他区段进行编辑，并轻松重新排列区段。

![选择面板图标](/help/email/assets/select-panel-icon.png)

选择 **选择面板** 选项时，配置的区段将显示为下拉列表。

* 列表按区段的分配排列排序，并反映在编号中。
* 首先显示区段的组件类型，然后以较浅字体显示区段的描述。

![“选择面板”弹出框](/help/email/assets/select-panel-popover.png)

* 点按或单击下拉菜单中的条目，即会将编辑器中的视图切换到该区段。
* 可使用拖动手柄就地重新排列区段。

>[!NOTE]
>
>区段在页面编辑器中以选项卡的形式呈现，以显示最终内容的多个选项。 作者在页面编辑器中无法选择这些选项卡。 使用“选择”面板可在显示的区段之间切换。

## “设计”对话框 {#design-dialog}

设计对话框允许模板作者定义哪些组件可作为区段添加到电子邮件分段组件，以及定义哪些自定义样式可供内容作者使用。

### “允许的组件”选项卡 {#allowed-components-tab}

的 **允许的组件** 选项卡，用于定义内容作者可以将哪些组件作为区段添加到电子邮件分段组件。

的 **允许的组件** 选项卡函数，与 [在模板编辑器中定义布局容器的策略和属性。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)

### 样式选项卡 {#styles-tab}

电子邮件分段组件支持AEM [样式系统。](/help/get-started/authoring.md#component-styling)

### “定义的条件”选项卡 {#defined-conditions}

使用 **定义的条件** 选项卡中，模板编辑器可以定义内容作者在创建区段时可以选择的条件。

![“设计”对话框“定义的条件”选项卡](/help/email/assets/email-segmentation-design-defined-conditions.png)

点按或单击 **添加** 按钮以创建新条件。

* **区段条件名称**  — 条件描述
* **区段条件**  — 根据Adobe Campaign个性化变量，必须满足的实际条件
   * [请参阅此处获取Adobe Campaign Standard个性化资源。](https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/personalization.html?)
   * [请参阅此处获取Adobe Campaign Classic个性化资源。](https://experienceleague.adobe.com/docs/)
* **删除**  — 点按以删除条件
* **重新排列**  — 点按或单击并拖动以重新排列条件的顺序
