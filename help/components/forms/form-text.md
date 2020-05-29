---
title: 表单文本组件
description: 核心组件表单文本组件允许输入表单文本以供提交。
translation-type: tm+mt
source-git-commit: c186e9ec3944d785ab0376769cf7f2307049a809
workflow-type: tm+mt
source-wordcount: '579'
ht-degree: 7%

---


# 表单文本组件{#form-text-component}

核心组件表单文本组件允许输入表单文本以供提交。

## 使用 {#usage}

表单文本组件允许提交不同类型的文本，并准备与表单容器组 [件一起使用](form-container.md)。 文本验证、标签和帮助消息的类型可由内容编辑器在“配置”对话框 [中定义](#configure-dialog)。

## 版本和兼容性 {#version-and-compatibility}

表单文本组件的当前版本为v2,2018年1月随核心组件版本2.0.0一起推出v2，该版本在本文档中进行了说明。

下表详细列出了组件的所有受支持版本、与组件版本兼容的AEM版本以及指向先前版本文档的链接。

| 组件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM 云服务 |
|--- |--- |--- |--- |---|
| v2 | - | 兼容 | 兼容 | 兼容 |
| [v1](/help/components/v1/form-text-v1.md) | 兼容 | 兼容 | 兼容 | - |

有关核心组件版本和版本的详细信息，请参阅文档 [核心组件版本](/help/versions.md)。

## 示例组件输出 {#sample-component-output}

要体验表单文本组件以及查看其配置选项以及HTML和JSON输出的示例，请访问组 [件库](https://adobe.com/go/aem_cmp_library_form_text)。

### 技术详细信息 {#technical-details}

有关表单文本组件的最新技 [术文档可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_form_text_v2)。

有关开发核心组件的更多详细信息，请参阅核 [心组件开发人员文档](/help/developing/overview.md)。

## 配置对话框 {#configure-dialog}

配置对话框允许内容作者定义要输入的文本类型以及默认值和标签。

### 属性选项卡 {#properties-tab}

![“属性”选项卡](/help/assets/form-text-edit-properties.png)

* **约束** -要输入并将验证的文本类型
   * **文本**
   * **文本区域**
   * **电子邮件**
   * **电话**
   * **日期**
   * **数字**
   * **密码**
* **文本行** -要在文本区域中显示的行数(仅当“约束”设 **置为** “文本区 **域”时显示**)
* **标签** -将为字段显示的标签
* **隐藏标签以免显示** -如果标签仅用于辅助功能目的而是必需的，并且不会传递有关该字段的任何其他可视信息，则需要
* **元素名称** -随表单数据提交的字段的名称
* **值** -字段中预填充的默认值
* **ID** —— 此选项允许控制HTML和数据层中组件的唯一标 [识符](/help/developing/data-layer/overview.md)。
   * 如果留空，则会自动为您生成唯一ID，并可通过检查生成的页面找到该ID。
   * 如果指定了ID，则作者有责任确保它是唯一的。
   * 更改ID可能会影响CSS、JS和数据层跟踪。

### 关于选项卡 {#about-tab}

![“关于”选项卡](/help/assets/form-text-edit-about.png)

* **帮助消息** -提示用户可在字段中输入的内容
* **将帮助消息显示为占位符** -在表单输入为空且未聚焦时在表单输入内显示帮助消息

### 约束选项卡 {#constraints-tab}

![约束选项卡](/help/assets/form-text-edit-constraints.png)

* **约束消息**
   * 如果该值对于所选的类型无效，则在提交表单时，将以工具提示形式显示消息
   * 不显示文本 **和文本** 区 **域约束** 类型。
* **必需** -如果选中，则用户必须在提交表单之前填写值
   * **必需消息** -如果字段留空，则消息将作为工具提示显示
* **设为只读** -如果选中，用户无法修改字段的值

## 设计对话框 {#design-dialog}

### 样式选项卡 {#styles-tab}

表单文本组件支持AEM样 [式系统](/help/get-started/authoring.md#component-styling)。
