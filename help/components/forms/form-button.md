---
title: 表单按钮组件
description: 利用核心组件表单隐藏组件，可在表单中包含隐藏字段。
role: Architect, Developer, Admin, User
exl-id: 1e5cff43-57db-4bfc-b2d2-23307eaf5eb3
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: ht
source-wordcount: '412'
ht-degree: 100%

---

# 表单按钮组件 {#form-button-component}

利用核心组件表单按钮组件，可在页面上包含按钮来触发操作。

## 用途 {#usage}

利用核心组件表单按钮组件，可以创建按钮字段（这通常会触发表单提交），并且此组件旨在与[表单容器组件](form-container.md)结合使用。

按钮属性可由内容编辑者在[“配置”对话框](#configure-dialog)中定义。

## 版本和兼容性 {#version-and-compatibility}

表单按钮组件的当前版本是 v2，此版本随 2018 年 1 月的核心组件发行版本 2.0.0 的发布引入，具体说明见本文。

下表详细说明了该组件的所有受支持版本、与该组件的版本兼容的 AEM 版本以及指向早期版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v2 | 兼容 | 兼容 | 兼容 |
| [v1](/help/components/v1/form-button-v1.md) | 兼容 | 兼容 | - |

有关核心组件版本的更多信息，请参阅文档[核心组件版本](/help/versions.md)。

## 示例组件输出 {#sample-component-output}

要体验表单按钮组件并查看其配置选项示例以及 HTML 和 JSON 输出，请访问[组件库](https://adobe.com/go/aem_cmp_library_form_button_cn)。

### 技术详细信息 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_form_button_v2_cn)有关表单按钮组件的最新技术文档。

在[核心组件开发人员文档](/help/developing/overview.md)中可找到有关开发核心组件的其他详细信息。

## “配置”对话框 {#configure-dialog}

利用“配置”对话框，内容作者可以定义按钮的参数。

### “属性”选项卡 {#properties-tab}

![表单按钮组件的“编辑”对话框](/help/assets/form-button-edit.png)

* **类型**

   * **按钮**
   * **提交**

* **标题** - 按钮上显示的文本

   * 如果未提供，则默认为按钮类型

* **名称** - 随表单数据一起提交的按钮的名称
* **值** - 随表单数据一起提交的按钮的值

* **ID** - 利用此选项，可以控制 HTML 和 [Data Layer](/help/developing/data-layer/overview.md) 中的组件的唯一标识符。
   * 如果留空，系统会自动为您生成一个唯一 ID，可以通过检查结果页面找到该 ID。
   * 如果指定一个 ID，作者有责任确保它是唯一的。
   * 更改此 ID 会对 CSS、JS 和 Data Layer 跟踪产生影响。

## “设计”对话框 {#design-dialog}

### “样式”选项卡 {#styles-tab}

表单按钮组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。
