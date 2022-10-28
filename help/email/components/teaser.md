---
title: 电子邮件Teaser组件
description: 电子邮件Teaser组件可显示图像、标题、富文本以及指向其他内容的可选链接。
role: Architect, Developer, Admin, User
hidefromtoc: true
index: false
source-git-commit: 8bebe3ca036557f3f7c6b8ec0e65d6d104d5ffae
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 电子邮件Teaser组件 {#email-teaser-component}

电子邮件Teaser组件可显示图像、标题、富文本以及指向其他内容的可选链接。

## 用途 {#usage}

Email Teaser组件允许内容作者使用图像、标题或富文本轻松创建Teaser，并链接到其他内容或其他操作。

* 模板作者可以使用[“设计”对话框](#design-dialog)定义创建行动号召和添加链接的选项是否可用，以及禁用各种显示选项。
* 内容作者可以使用[“配置”对话框](#configure-dialog)来设置图像、定义 CTA、设置标题和描述，以及配置指向个别 Teaser 的链接。
* 的 [编辑对话框](image.md#edit-dialog) 的 [电子邮件图像组件](image.md) 可访问以修改teaser图像。

## 版本和兼容性 {#version-and-compatibility}

电子邮件Teaser组件的当前版本为v1，该版本于2022年10月随电子邮件核心组件第x版引入，在本文档中进行了描述。

下表详细说明了该组件的所有受支持版本、与该组件的版本兼容的 AEM 版本以及指向早期版本文档的链接。

| 组件版本 | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | 兼容 | 兼容 |

## 示例组件输出 {#sample-component-output}

要体验Email Teaser组件并查看其配置选项以及HTML和JSON输出的示例，请访问 [组件库。](https://adobe.com/go/aem_cmp_library_email_teaser)

### 技术详细信息 {#technical-details}

有关Email Teaser组件的最新技术文档 [可在GitHub上找到。](https://adobe.com/go/aem_cmp_tech_email_teaser_v1)

有关开发核心组件的更多详细信息，请参阅 [核心组件开发人员文档。](/help/developing/overview.md)

## “配置”对话框 {#configure-dialog}

内容作者可以使用“配置”对话框定义个别 Teaser 的属性。在选中时，还有[“编辑”对话框](#edit-dialog)可修改 Teaser 图像。

### “链接”选项卡 {#links-tab}

![Email Teaser组件的编辑对话框链接选项卡](/help/email/assets/email-teaser-edit-links.png)

Teaser标题、描述和图像可以从链接的内容中继承，也可以从第一个行动动员中链接的内容继承。 如果既未指定链接，也未指定行动动员，则标题、描述和图像将从当前内容中继承。

* **链接**  — 此文件链接到内容、外部URL或锚点。
   * 单击Campaign图标以打开 [选择Adobe Campaign变量](/help/email/campaign-variables.md) 对话框，以从Adobe Campaign插入动态内容。
* **行动号召** - 此选项允许链接到多个目标。
   * 在继承 Teaser 标题、描述或图像时使用第一个行动号召中链接的页面。
   * 单击Campaign图标以打开 [选择Adobe Campaign变量](/help/email/campaign-variables.md) 对话框，以从Adobe Campaign插入动态内容。

### “文本”选项卡 {#text-tab}

![Email Teaser组件的编辑对话框文本选项卡](/help/email/assets/email-teaser-edit-text.png)

* **前标题** - 前标题显示在 Teaser 的标题之前。
* **标题** - 定义显示为 Teaser 大标题的标题。
   * 单击Campaign图标以打开 [选择Adobe Campaign变量](/help/email/campaign-variables.md) 对话框，以从Adobe Campaign插入动态内容。
   * **从链接的页面获取标题** - 在选中时，使用链接页面的标题填充标题。
* **描述** - 定义显示为 Teaser 子标题的描述。
   * 单击 **选择Adobe Campaign变量** 图标以打开 [选择Adobe Campaign变量](/help/email/campaign-variables.md) 对话框，以从Adobe Campaign插入动态内容。
   * **从链接的页面获取描述** - 在选中时，使用链接页面的描述填充描述。
* **ID**  — 此选项允许控制组件在HTML中的唯一标识符。
   * 如果留空，则会自动为您生成唯一ID，并且可以通过检查生成的内容来找到该ID。
   * 如果指定一个 ID，作者有责任确保它是唯一的。
   * 更改ID可能会对CSS产生影响。

### “资源”选项卡 {#asset-tab}

![Email Teaser组件的编辑对话框图像选项卡](/help/email/assets/email-teaser-edit-image.png)

* **从页面继承精选图像** - 使用链接页面的页面属性中定义的图像，如果没有找到，则使用当前页面。
* **图像资源** - 在[资源浏览器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html)中放置资源或点击&#x200B;**浏览**&#x200B;选项以从本地文件系统上传。
   * 点按或单击&#x200B;**“清除”**&#x200B;以取消选择当前选定的图像。
   * 点按或单击 **编辑** to [管理资产的演绎版](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html) 在资产编辑器中。
* **用于辅助功能的替换文本** – 此字段允许您为视障用户定义图像的描述。
   * **从页面继承替换文本** - 此选项使用 DAM 中 `dc:description` 元数据的链接资源值的替代描述或当前页面的替代描述（如果未链接资源）。
* **不提供替换文本** - 此选项将图像标记为被屏幕阅读器等辅助技术忽略，以用于图像纯粹起装饰作用或不向页面传达额外信息的情况。

>[!NOTE]
>
>[Dynamic Media 功能](image.md#dynamic-media)当前在 Teaser 组件中不可用。

### “样式”选项卡 {#styles-tab-edit}

Email Teaser组件支持AEM [样式系统。](/help/get-started/authoring.md#component-styling)

使用下拉菜单选择要应用于该组件的样式。在“编辑”对话框中所做的选择与从组件工具栏中选择的操作效果相同。

必须在 [设计对话框](#design-dialog) 以使选项卡可用。

## “编辑”对话框 {#edit-dialog}

Email Teaser组件将图像渲染委派给 [图像组件](image.md). 因此，内容作者可以使用图像组件的[“编辑”对话框](image.md#edit-dialog)来处理 Teaser 图像。

## “设计”对话框 {#design-dialog}

利用“设计”对话框，模板作者可以定义内容作者在使用此组件时具有的 Teaser 选项。

### “Teaser”选项卡 {#teaser-tab}

![电子邮件Teaser组件的设计对话框](/help/email/assets/email-teaser-design.png)

* **允许的标题元素**  — 使用下拉列表定义作者可为Teaser的标题类型选择的标题HTML元素。
* **标题的默认标题元素**  — 用于Teaser标题类型的默认标题HTML元素
* **行动号召**
   * **禁用行动号召** - 对内容作者隐藏&#x200B;**行动号召**&#x200B;选项
* **元素**
   * **隐藏前标题** - 对内容作者隐藏&#x200B;**前标题**&#x200B;选项
   * **隐藏标题** - 对内容作者隐藏&#x200B;**标题**&#x200B;选项
      * 在选中时，将隐藏&#x200B;**标题类型**
   * **显示标题类型**
   * **隐藏描述** - 对内容作者隐藏&#x200B;**描述**&#x200B;选项
* **图像委派**  — 信息性显示，指示Email Teaser将图像处理委托给哪个组件。

### 样式选项卡 {#styles-tab}

Email Teaser组件支持AEM [样式系统。](/help/get-started/authoring.md#component-styling)
