---
title: 表单文本组件
description: 利用核心组件表单文本组件，可以输入表单文本供提交。
role: Architect, Developer, Admin, User
exl-id: e8fa3881-51fb-4726-9654-8f93acfb7464
source-git-commit: 6fbc781db555bc6abaed1d122a9a8756e3d53222
workflow-type: tm+mt
source-wordcount: '578'
ht-degree: 99%

---

# 表单文本组件{#form-text-component}

利用核心组件表单文本组件，可以输入表单文本供提交。

## 用途 {#usage}

使用表单文本组件可提交不同类型的文本，此组件旨在与[表单容器组件](form-container.md)结合使用。文本验证的类型、标签和帮助消息可由内容编辑者在[“配置”对话框](#configure-dialog)中定义。

## 版本和兼容性 {#version-and-compatibility}

表单文本组件的当前版本是 v2，此版本随 2018 年 1 月的核心组件发行版本 2.0.0 的发布引入，具体说明见本文。

下表详细说明了该组件的所有受支持版本、与该组件的版本兼容的 AEM 版本以及指向早期版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM 6.5磅 | AEM as a Cloud Service |
|--- |--- |--- |---|---|
| v2 | 与<br>[版本 2.17.4](/help/versions.md) 和更低版本兼容 | 兼容 | 兼容 | 兼容 |
| [v1](/help/components/v1/form-text-v1.md) | 兼容 | 兼容 | - | 兼容 |

有关核心组件版本的更多信息，请参阅文档[核心组件版本](/help/versions.md)。

## 示例组件输出 {#sample-component-output}

要体验表单文本组件并查看其配置选项示例以及 HTML 和 JSON 输出，请访问[组件库](https://adobe.com/go/aem_cmp_library_form_text_cn)。

### 技术详细信息 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_form_text_v2_cn)有关表单文本组件的最新技术文档。

在[核心组件开发人员文档](/help/developing/overview.md)中可找到有关开发核心组件的其他详细信息。

## “配置”对话框 {#configure-dialog}

利用“配置”对话框，内容作者可以定义要作为默认值和标签输入的文本的类型。

### “属性”选项卡 {#properties-tab}

![“属性”选项卡](/help/assets/form-text-edit-properties.png)

* **约束** - 要输入并进行验证的文本的类型。
   * **文本**
   * **文本区域**
   * **电子邮件**
   * **电话**
   * **日期**
   * **数字**
   * **密码**
* **文本行** - 在文本区域中显示的行数（仅在&#x200B;**约束**&#x200B;设置为&#x200B;**文本区域**&#x200B;时显示）
* **标签** - 将为字段显示的标签
* **隐藏标签以不被显示** - 在标签仅用于辅助功能且不影响有关字段的任何其他可视信息时需要
* **元素名称** - 随表单数据一起提交的字段的名称
* **值** - 在字段中预填充的默认值
* **ID** - 利用此选项，可以控制 HTML 和[ Data Layer ](/help/developing/data-layer/overview.md)中的组件的唯一标识符。
   * 如果留空，系统会自动为您生成一个唯一 ID，可以通过检查结果页面找到该 ID。
   * 如果指定一个 ID，作者有责任确保它是唯一的。
   * 更改此 ID 会对 CSS、JS 和 Data Layer 跟踪产生影响。

### “关于”选项卡 {#about-tab}

![“关于”选项卡](/help/assets/form-text-edit-about.png)

* **帮助消息** - 关于用户可在字段中输入的内容的提示
* **将帮助消息显示为占位符** - 当表单输入为空且焦点不在其上时，在表单输入中显示帮助消息

### “约束”选项卡 {#constraints-tab}

![“约束”选项卡](/help/assets/form-text-edit-constraints.png)

* **约束消息**
   * 如果该值对于所选的类型无效，则在提交表单时，将以工具提示形式显示消息
   * 对于&#x200B;**文本**&#x200B;和&#x200B;**文本区域**&#x200B;约束类型不显示
* **必填** - 如果选择，用户必须在提交表单之前填充值
   * **必填消息** - 字段留空时显示为工具提示的消息
* **使只读** - 如果选中，用户无法修改字段的值

## “设计”对话框 {#design-dialog}

### “样式”选项卡 {#styles-tab}

表单文本组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。
