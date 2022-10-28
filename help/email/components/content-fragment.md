---
title: 电子邮件内容片段组件
description: 电子邮件内容片段组件允许在内容中显示内容片段。
role: Architect, Developer, Admin, User
hidefromtoc: true
index: false
source-git-commit: 8bebe3ca036557f3f7c6b8ec0e65d6d104d5ffae
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 电子邮件内容片段组件 {#email-content-fragment-component}

电子邮件内容片段组件允许显示 [内容片段](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html) 中。

## 用途 {#usage}

电子邮件内容片段组件允许包含 [内容片段](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html) 中。 内容片段是多渠道结构化内容，可以集中创作并轻松重复使用。

* 可以在 [配置对话框。](#configure-dialog)
* 可在 [“设计”对话框。](#design-dialog)
* 编辑选项可在 [内容片段编辑器，](#edit-dialog) 自定义以与电子邮件核心组件一起使用。

## 版本和兼容性 {#version-and-compatibility}

电子邮件内容片段组件的当前版本为v1，该版本于2022年10月随电子邮件核心组件X版引入，在此文档中进行了描述。

下表详细说明了该组件的所有受支持版本、与该组件的版本兼容的 AEM 版本以及指向早期版本文档的链接。

| 组件版本 | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | 兼容 | 兼容 |

有关电子邮件核心组件版本和版本的更多信息，请参阅此文档 [电子邮件核心组件版本。](/help/email/versions.md)

## 示例组件输出 {#sample-component-output}

要体验电子邮件内容片段组件并查看其配置选项以及HTML和JSON输出的示例，请访问 [组件库。](https://adobe.com/go/aem_cmp_library_email_cf)

## 技术详细信息 {#technical-details}

有关电子邮件内容片段组件的最新技术文档 [可在GitHub上找到。](https://adobe.com/go/aem_cmp_tech_email_cf_v1)

有关开发核心组件的更多详细信息，请参阅 [核心组件开发人员文档。](/help/developing/overview.md)

## “配置”对话框 {#configure-dialog}

配置对话框允许内容作者定义要包含的内容片段和该片段的元素。

### “属性”选项卡 {#properties-tab}

![电子邮件内容片段组件](/help/email/assets/email-content-fragment-edit-properties.png)

* **内容片段**

   * 所需内容片段的路径
   * **“选择”对话框**&#x200B;可用于定位片段

* **显示模式**
   * **单个文本元素** - 允许选择一个多行文本元素并启用段落控制选项
* **变体** - 要使用的内容片段的变体（默认为 **Master**）

* **ID**  — 此选项允许控制组件在HTML中的唯一标识符。
   * 如果留空，则会自动为您生成唯一ID，并且可以通过检查生成的内容来找到该ID。
   * 如果指定一个 ID，作者有责任确保它是唯一的。
   * 更改ID可能会对CSS产生影响。

### “段落控制”选项卡 {#paragraph-control-tab}

![电子邮件内容片段组件](/help/assets/content-fragment-edit-paragraph.png)

* **段落** - 允许选择所有段落或一个范围
   * **全部** - 显示所有段落
   * **范围**
      * 指定应显示的段落的范围（用分号分隔）
      * 例如 `1;3-5;7;9-*` 将第一、第三至第五、第七和第九段列入最后各段
* **将标题处理为它们自己的段落**

## “编辑”对话框 {#edit-dialog}

使用电子邮件内容片段组件配置内容片段后，在内容编辑器中选择该组件时，会显示 **编辑** 选项。

![电子邮件内容片段组件的工具栏](/help/email/assets/email-content-fragment-edit-toolbar.png)

点按或单击 **编辑** 按钮可打开内容片段编辑器。 内容片段编辑器已扩展为包含 **选择Adobe Campaign变量** 将Adobe Campaign变量插入内容片段。

![电子邮件的内容片段编辑器](/help/email/assets/email-content-fragment-editor.png)

有关编辑和创作内容片段的更多信息，请参阅此文档 [创作片段内容。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/assets/content-fragments/content-fragments-variations.html)

## “设计”对话框 {#design-dialog}

使用内容片段配置电子邮件内容片段组件后，当您在内容编辑器中选择该组件时，工具栏会显示一个用于打开内容片段编辑器的按钮。


### 主选项卡 {#main-tab}

![电子邮件内容片段组件的设计对话框](/help/email/assets/email-content-fragment-design.png)

* **内部响应式网格**

   * 用于内部响应式网格的 Sling 资源类型

### 样式选项卡 {#styles-tab}

电子邮件体验片段组件支持AEM [样式系统。](/help/get-started/authoring.md#component-styling)
