---
title: 电子邮件内容片段组件
description: 利用电子邮件内容片段组件，可以在您的内容中显示内容片段。
role: Architect, Developer, Admin, User
exl-id: 9bc6b730-0d2a-4e5b-891c-d2f67f600bcc
source-git-commit: 33976c0e745ad091a142109f70541f01a31edc5b
workflow-type: tm+mt
source-wordcount: '668'
ht-degree: 100%

---


# 电子邮件内容片段组件 {#email-content-fragment-component}

利用电子邮件内容片段组件，可以在您的内容中显示[内容片段](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html)。

## 用途 {#usage}

利用电子邮件内容片段组件，可以在您的电子邮件内容中包含[内容片段](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html)。 内容片段是多渠道结构化内容，可以集中创作并轻松重用。

* 可[“配置”对话框](#configure-dialog)中选择片段及其属性。
* 可[“设计”对话框](#design-dialog)中定义用于处理特定图像的资源类型。
* 编辑选项在[内容片段编辑器](#edit-dialog)中打开选定的片段，为与电子邮件核心组件一起使用而定制。

## 版本和兼容性 {#version-and-compatibility}

电子邮件内容片段组件的当前版本是 v1，此版本随 2022 年 10 月的电子邮件核心组件发行版本 X 的发布引入，具体说明见本文档。

下表详细说明了该组件的所有受支持版本、与该组件的版本兼容的 AEM 版本以及指向早期版本文档的链接。

| 组件版本 | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | 兼容 | 兼容 |

有关电子邮件核心组件版本的更多信息，请参阅文档[电子邮件核心组件版本。](/help/email/versions.md)

## 示例组件输出 {#sample-component-output}

要体验电子邮件内容片段组件并查看其配置选项示例以及 HTML 和 JSON 输出，请访问[组件库。](https://adobe.com/go/aem_cmp_library_email_cf_cn)

## 技术详细信息 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_email_cf_v1_cn)有关电子邮件内容片段列表组件的最新技术文档。

在[核心组件开发人员文档](/help/developing/overview.md)中可找到有关开发核心组件的其他详细信息。

## “配置”对话框 {#configure-dialog}

利用“配置”对话框，内容作者可以定义要包含的内容片段及其元素。

### “属性”选项卡 {#properties-tab}

![电子邮件内容片段组件](/help/email/assets/email-content-fragment-edit-properties.png)

* **内容片段**

   * 所需内容片段的路径
   * **“选择”对话框**&#x200B;可用于定位片段

* **显示模式**
   * **单个文本元素** - 允许选择一个多行文本元素并启用段落控制选项
* **变体** – 要使用的内容片段的变体（默认为 **Master**）

* **ID** – 此选项允许控制 HTML 中组件的唯一标识符。
   * 如果留空，系统会自动为您生成一个唯一 ID，可以通过检查结果内容找到该 ID。
   * 如果指定一个 ID，作者有责任确保它是唯一的。
   * 更改 ID 会对 CSS 产生影响。

### “段落控制”选项卡 {#paragraph-control-tab}

![电子邮件内容片段组件](/help/assets/content-fragment-edit-paragraph.png)

* **段落** – 允许选择所有段落或一个范围
   * **全部** - 显示所有段落
   * **范围**
      * 指定应显示的段落的范围（用分号分隔）
      * 例如，如果为 `1;3-5;7;9-*`，则包含第一段、第三段到第五段、第七段、第九段到最后一段
* **将标题处理为它们自己的段落**

## “编辑”对话框 {#edit-dialog}

一旦您使用电子邮件内容片段组件配置了一个内容片段，当您在内容编辑器中选择该组件时，它会显示一个&#x200B;**编辑**&#x200B;选项。

![电子邮件内容片段组件工具栏](/help/email/assets/email-content-fragment-edit-toolbar.png)

点击或单击&#x200B;**编辑**&#x200B;按钮打开内容片段编辑器。 内容片段编辑器已扩展为包括用于&#x200B;**选择 Adobe Campaign 变量**&#x200B;将 Adobe Campaign 变量插入到您的内容片段中。

![电子邮件的内容片段编辑器](/help/email/assets/email-content-fragment-editor.png)

有关编辑和创作内容片段的更多信息，请参阅文档[创作片段内容。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/assets/content-fragments/content-fragments-variations.html)

## “设计”对话框 {#design-dialog}

当电子邮件内容片段组件配置有内容片段时，当您在内容编辑器中选择它时，工具栏会显示一个用于打开内容片段编辑器的按钮。


### 主选项卡 {#main-tab}

![电子邮件内容片段组件“设计”对话框](/help/email/assets/email-content-fragment-design.png)

* **内部响应式网格**

   * 用于内部响应式网格的 Sling 资源类型

### 样式选项卡 {#styles-tab}

电子邮件体验片段组件支持 AEM [样式系统。](/help/get-started/authoring.md#component-styling)
