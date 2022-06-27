---
title: 表单隐藏组件
description: 利用核心组件表单隐藏组件，可显示隐藏字段。
role: Architect, Developer, Admin, User
exl-id: 0364cd3b-3c09-46db-9392-a67e3f9ea7a5
source-git-commit: 16930ccaa281f9d9c4ddbb890d4222e128557580
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 100%

---

# 表单隐藏组件{#form-hidden-component}

利用核心组件表单隐藏组件，可显示隐藏字段。

## 用途 {#usage}

利用核心组件表单隐藏组件可创建隐藏字段以将有关当前页面的信息传递回 AEM，并且此组件旨在与[表单容器组件](form-container.md)结合使用。

字段属性可由内容编辑者在[“配置”对话框](form-hidden.md)中定义。

## 版本和兼容性 {#version-and-compatibility}

表单隐藏组件的当前版本是 v2，此版本随 2018 年 1 月的核心组件 2.0.0 版的发布引入，具体说明见本文。

下表详细说明了该组件的所有受支持版本、与该组件的版本兼容的 AEM 版本以及指向早期版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v2 | 兼容<br>[版本 2.17.4](/help/versions.md) 和更低版本 | 兼容 | 兼容 |
| [v1](/help/components/v1/form-hidden-v1.md) | 兼容 | 兼容 | 兼容 |

有关核心组件版本的更多信息，请参阅文档[核心组件版本](/help/versions.md)。

## 示例组件输出 {#sample-component-output}

要体验表单隐藏组件并查看其配置选项示例以及 HTML 和 JSON 输出，请访问[组件库](https://adobe.com/go/aem_cmp_library_form_hidden_cn)。

### 技术详细信息 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_form_hidden_v2_cn)有关表单隐藏组件的最新技术文档。

在[核心组件开发人员文档](/help/developing/overview.md)中可找到有关开发核心组件的其他详细信息。

## “配置”对话框 {#configure-dialog}

利用“配置”对话框，内容作者可以定义隐藏字段的参数。

![表单隐藏的“编辑”对话框](/help/assets/form-hidden-edit.png)

* **名称** - 随表单数据一起提交的字段的名称
* **值** - 随表单数据一起提交的字段的值
* **ID** - 利用此选项，可以控制 HTML 和 [Data Layer](/help/developing/data-layer/overview.md) 中的组件的唯一标识符。
   * 如果留空，系统会自动为您生成一个唯一 ID，可以通过检查结果页面找到该 ID。
   * 如果指定一个 ID，作者有责任确保它是唯一的。
   * 更改此 ID 会对 CSS、JS 和 Data Layer 跟踪产生影响。

由于表单隐藏组件通常没有可见属性，因此编辑器中的组件占位符将显示&#x200B;**名称**&#x200B;和&#x200B;**值**&#x200B;字段值（如果已分配），以便帮助作者标识相应的表单隐藏组件。

![表单隐藏组件示例](/help/assets/form-hidden-example.png)

## “设计”对话框 {#design-dialog}

### “样式”选项卡 {#styles-tab}

表单隐藏组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。
