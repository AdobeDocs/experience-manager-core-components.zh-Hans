---
title: 表单文本组件
description: 核心组件表单文本组件允许输入表单文本以供提交。
role: Architect, Developer, Admin, User
exl-id: e8fa3881-51fb-4726-9654-8f93acfb7464
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 7%

---

# 表单文本组件{#form-text-component}

核心组件表单文本组件允许输入表单文本以供提交。

## 使用 {#usage}

表单文本组件允许提交不同类型的文本，并准备与[表单容器组件](form-container.md)一起使用。 文本验证、标签和帮助消息的类型可由[配置对话框](#configure-dialog)中的内容编辑器定义。

## 版本和兼容性 {#version-and-compatibility}

表单文本组件的当前版本为v2，该版本在2018年1月核心组件版本2.0.0中引入，在本文档中进行了描述。

下表详细列出了组件的所有受支持版本、组件版本与之兼容的AEM版本，以及指向以前版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v2 | 兼容 | 兼容 | 兼容 |
| [v1](/help/components/v1/form-text-v1.md) | 兼容 | 兼容 | - |

有关核心组件版本和版本的更多信息，请参阅文档[核心组件版本](/help/versions.md)。

## 组件输出示例 {#sample-component-output}

要体验表单文本组件并查看其配置选项以及HTML和JSON输出的示例，请访问[组件库](https://adobe.com/go/aem_cmp_library_form_text)。

### 技术详细信息 {#technical-details}

有关表单文本组件[的最新技术文档，请参阅GitHub](https://adobe.com/go/aem_cmp_tech_form_text_v2)。

有关开发核心组件的更多详细信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## 配置对话框 {#configure-dialog}

配置对话框允许内容作者定义要输入的文本类型以及默认值和标签。

### “属性”选项卡 {#properties-tab}

![“属性”选项卡](/help/assets/form-text-edit-properties.png)

* **约束**  — 要输入并将针对其进行验证的文本类型
   * **文本**
   * **文本区域**
   * **电子邮件**
   * **电话**
   * **日期**
   * **数字**
   * **密码**
* **文本行**  — 要在文本区域中显示的行数(仅当“约束”设置为“文 **** 本区域” **时显示**)
* **标签**  — 将为字段显示的标签
* **隐藏标签以防显示**  — 如果仅出于辅助功能目的而需要标签，并且不会传递有关该字段的任何其他可视化信息，则需要此标签
* **元素名称**  — 随表单数据一起提交的字段的名称
* **值**  — 在字段中预填充的默认值
* **ID**  — 利用此选项，可控制HTML和数据层中组件的唯一标识符 [的唯一标识符](/help/developing/data-layer/overview.md)。
   * 如果留为空白，则会自动为您生成唯一ID，并且可以通过检查生成的页面找到该ID。
   * 如果指定了ID，则作者有责任确保该ID是唯一的。
   * 更改ID可能会影响CSS、JS和数据层跟踪。

### 关于选项卡 {#about-tab}

![“关于”选项卡](/help/assets/form-text-edit-about.png)

* **帮助消息**  — 向用户提示可在字段中输入的内容
* **将帮助消息显示为占位符**  — 在表单输入中显示帮助消息，当该消息为空且未集中

### 约束选项卡 {#constraints-tab}

![“约束”选项卡](/help/assets/form-text-edit-constraints.png)

* **约束消息**
   * 如果该值对于所选的类型无效，则在提交表单时，将以工具提示形式显示消息
   * 未显示&#x200B;**Text**&#x200B;和&#x200B;**Text Area**&#x200B;约束类型
* **必需**  — 如果选中此项，则用户必须在提交表单之前填写值
   * **必需消息**  — 如果字段留空，则消息将显示为工具提示
* **设为只读**  — 如果选中，则用户无法修改字段的值

## “设计”对话框 {#design-dialog}

### “样式”选项卡 {#styles-tab}

表单文本组件支持AEM [样式系统](/help/get-started/authoring.md#component-styling)。
