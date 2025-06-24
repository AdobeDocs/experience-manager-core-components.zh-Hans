---
title: 电子邮件 Teaser 组件
description: 电子邮件 Teaser 组件可以显示图像、标题、富文本并可以选择链接到更多内容。
role: Architect, Developer, Admin, User
exl-id: d6123b22-7cba-406c-986d-b6f00322d135
index: false
source-git-commit: eb77567dc32cccb81a9fc131493d11fb55b7e93b
workflow-type: tm+mt
source-wordcount: '1002'
ht-degree: 100%

---


# 电子邮件 Teaser 组件 {#email-teaser-component}

电子邮件 Teaser 组件可以显示图像、标题、富文本并可以选择链接到更多内容。

## 用途 {#usage}

电子邮件 Teaser 组件允许内容作者使用图像、标题或富文本轻松创建 Teaser，并链接到更多内容或其他操作。

* 模板作者可以使用[“设计”对话框](#design-dialog)定义创建行动号召和添加链接的选项是否可用，以及禁用各种显示选项。
* 内容作者可以使用[“配置”对话框](#configure-dialog)来设置图像、定义 CTA、设置标题和描述，以及配置指向个别 Teaser 的链接。
* 可以访问[电子邮件图像组件](image.md)的[“编辑”对话框](image.md#edit-dialog)来修改 Teaser 图像。

## 版本和兼容性 {#version-and-compatibility}

电子邮件 Teaser 组件的当前版本是 v1，此版本随 2022 年 10 月的电子邮件核心组件发行版本 x 的发布引入，具体说明见本文档。

下表详细说明了该组件的所有受支持版本、与该组件的版本兼容的 AEM 版本以及指向早期版本文档的链接。

| 组件版本 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|---|---|---|---|
| v1 | 兼容 | - | - |

### 技术详细信息 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_email_teaser_v1_cn)有关电子邮件 Teaser 组件的最新技术文档。

在[核心组件开发人员文档](/help/developing/overview.md)中可找到有关开发核心组件的其他详细信息。

## “配置”对话框 {#configure-dialog}

内容作者可以使用“配置”对话框定义个别 Teaser 的属性。在选中时，还有[“编辑”对话框](#edit-dialog)可修改 Teaser 图像。

### “链接”选项卡 {#links-tab}

![电子邮件 Teaser 组件的“编辑”对话框中的“链接”选项卡](/help/email/assets/email-teaser-edit-links.png)

Teaser 标题、描述和图像可以从链接的内容或第一个号召性用语中链接的内容继承。 如果既没有指定链接也没有指定号召性用语，则标题、描述和图像将从当前内容继承。

* **链接** – 此文件链接到内容、外部 URL 或锚点。
   * 单击 Campaign 图标，打开[选择 Adobe Campaign 变量](/help/email/campaign-variables.md)对话框并插入来自 Adobe Campaign 的动态内容。
* **行动号召** - 此选项允许链接到多个目标。
   * 在继承 Teaser 标题、描述或图像时使用第一个行动号召中链接的页面。
   * 单击 Campaign 图标，打开[选择 Adobe Campaign 变量](/help/email/campaign-variables.md)对话框并插入来自 Adobe Campaign 的动态内容。

### “文本”选项卡 {#text-tab}

![电子邮件 Teaser 组件的“编辑”对话框中的“文本”选项卡](/help/email/assets/email-teaser-edit-text.png)

* **前标题** - 前标题显示在 Teaser 的标题之前。
* **标题** - 定义显示为 Teaser 大标题的标题。
   * 单击 Campaign 图标，打开[选择 Adobe Campaign 变量](/help/email/campaign-variables.md)对话框并插入来自 Adobe Campaign 的动态内容。
   * **从链接的页面获取标题** - 在选中时，使用链接页面的标题填充标题。
* **描述** - 定义显示为 Teaser 子标题的描述。
   * 单击&#x200B;**选择 Adobe Campaign 变量**&#x200B;图标，打开[选择 Adobe Campaign 变量](/help/email/campaign-variables.md)对话框并插入来自 Adobe Campaign 的动态内容。
   * **从链接的页面获取描述** – 在选中时，使用链接页面的描述填充描述。
* **ID** – 此选项允许控制 HTML 中组件的唯一标识符。
   * 如果留空，系统会自动为您生成一个唯一 ID，可以通过检查结果内容找到该 ID。
   * 如果指定一个 ID，作者有责任确保它是唯一的。
   * 更改 ID 会对 CSS 产生影响。

### “资源”选项卡 {#asset-tab}

![电子邮件 Teaser 组件的“编辑”对话框中的“图像”选项卡](/help/email/assets/email-teaser-edit-image.png)

* **从页面继承精选图像** - 使用链接页面的页面属性中定义的图像，如果没有找到，则使用当前页面。
* **图像资源** - 在[资源浏览器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html?lang=zh-Hans)中放置资源或点击&#x200B;**浏览**&#x200B;选项以从本地文件系统上传。
   * 点按或单击&#x200B;**“清除”**&#x200B;以取消选择当前选定的图像。
   * 点按或单击&#x200B;**“编辑”**&#x200B;可在“资产编辑器中”[管理资产的再现](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html?lang=zh-Hans)。
* **用于辅助功能的替换文本** – 此字段允许您为视障用户定义图像的描述。
   * **从页面继承替换文本** - 此选项使用 DAM 中 `dc:description` 元数据的链接资源值的替代描述或当前页面的替代描述（如果未链接资源）。
* **不提供替换文本** - 此选项将图像标记为被屏幕阅读器等辅助技术忽略，以用于图像纯粹起装饰作用或不向页面传达额外信息的情况。

>[!NOTE]
>
>[Dynamic Media 功能](image.md#dynamic-media)当前在 Teaser 组件中不可用。

### 样式选项卡 {#styles-tab-edit}

电子邮件 Teaser 组件支持 AEM [样式系统。](/help/get-started/authoring.md#component-styling)

使用下拉菜单选择要应用于该组件的样式。在“编辑”对话框中所做的选择与从组件工具栏中选择的操作效果相同。

必须在[“设计”对话框](#design-dialog)中为此组件配置样式，以便选项卡可用。

## “编辑”对话框 {#edit-dialog}

电子邮件 Teaser 组件将图像渲染委派给[图像组件](image.md)。 因此，内容作者可以使用图像组件的[“编辑”对话框](image.md#edit-dialog)来处理 Teaser 图像。

## “设计”对话框 {#design-dialog}

利用“设计”对话框，模板作者可以定义内容作者在使用此组件时具有的 Teaser 选项。

### “Teaser”选项卡 {#teaser-tab}

![电子邮件 Teaser 组件的“设计”对话框](/help/email/assets/email-teaser-design.png)

* **允许的标题元素** – 使用下拉菜单定义作者可以选择哪些标题 HTML 元素作为 Teaser 的标题类型。
* **标题的默认标题元素** – 用于 Teaser 标题类型的默认标题 HTML 元素
* **行动号召**
   * **禁用行动号召** - 对内容作者隐藏&#x200B;**行动号召**&#x200B;选项
* **元素**
   * **隐藏前标题** - 对内容作者隐藏&#x200B;**前标题**&#x200B;选项
   * **隐藏标题** - 对内容作者隐藏&#x200B;**标题**&#x200B;选项
      * 在选中时，将隐藏&#x200B;**标题类型**
   * **显示标题类型**
   * **隐藏描述** – 对内容作者隐藏&#x200B;**描述**&#x200B;选项
* **图像委派** – 信息性显示，指示电子邮件 Teaser 将图像处理委派到的组件。

### 样式选项卡 {#styles-tab}

电子邮件 Teaser 组件支持 AEM [样式系统。](/help/get-started/authoring.md#component-styling)
