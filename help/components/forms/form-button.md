---
title: 表单按钮组件
description: 核心组件表单隐藏组件允许在表单中包含隐藏字段。
role: Architect, Developer, Admin, User
exl-id: 1e5cff43-57db-4bfc-b2d2-23307eaf5eb3
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 4%

---

# 表单按钮组件 {#form-button-component}

核心组件表单按钮组件允许包含按钮以在页面上触发操作。

## 使用 {#usage}

核心组件表单按钮组件允许创建按钮字段，通常用于触发表单的提交，并准备与[表单容器组件](form-container.md)一起使用。

[配置对话框](#configure-dialog)中的内容编辑器可定义按钮属性。

## 版本和兼容性 {#version-and-compatibility}

表单按钮组件的当前版本为v2，该版本于2018年1月随核心组件2.0.0版一起引入，在本文档中进行了描述。

下表详细列出了组件的所有受支持版本、组件版本与之兼容的AEM版本，以及指向以前版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v2 | 兼容 | 兼容 | 兼容 |
| [v1](/help/components/v1/form-button-v1.md) | 兼容 | 兼容 | - |

有关核心组件版本和版本的更多信息，请参阅文档[核心组件版本](/help/versions.md)。

## 组件输出示例 {#sample-component-output}

要体验表单按钮组件并查看其配置选项以及HTML和JSON输出的示例，请访问[组件库](https://adobe.com/go/aem_cmp_library_form_button)。

### 技术详细信息 {#technical-details}

有关表单按钮组件[的最新技术文档，请参阅GitHub](https://adobe.com/go/aem_cmp_tech_form_button_v2)。

有关开发核心组件的更多详细信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## 配置对话框 {#configure-dialog}

配置对话框允许内容作者定义按钮的参数。

### “属性”选项卡 {#properties-tab}

![表单按钮组件的编辑对话框](/help/assets/form-button-edit.png)

* **类型**

   * **按钮**
   * **提交**

* **标题**  — 按钮上显示的文本

   * 如果未提供，则默认为按钮类型

* **名称**  — 随表单数据一起提交的按钮的名称
* **值**  — 随表单数据一起提交的按钮的值

* **ID**  — 利用此选项，可控制HTML和数据层中组件的唯一标识符 [的唯一标识符](/help/developing/data-layer/overview.md)。
   * 如果留为空白，则会自动为您生成唯一ID，并且可以通过检查生成的页面找到该ID。
   * 如果指定了ID，则作者有责任确保该ID是唯一的。
   * 更改ID可能会影响CSS、JS和数据层跟踪。

## “设计”对话框 {#design-dialog}

### “样式”选项卡 {#styles-tab}

表单按钮组件支持AEM [样式系统](/help/get-started/authoring.md#component-styling)。
