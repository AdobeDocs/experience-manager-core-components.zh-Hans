---
title: 表单选项组件
description: 核心组件表单选项组件允许从各种格式的预定义选项中进行选择。
role: Architect, Developer, Admin, User
exl-id: 8a74bd37-9b12-4fa6-bff2-53e337b16251
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '545'
ht-degree: 3%

---

# 表单选项组件 {#form-options-component}

核心组件表单选项组件允许从各种格式的预定义选项中进行选择。

## 使用 {#usage}

核心组件表单选项组件允许以多种不同方式提交不同类型的选项，这些选项将与[表单容器组件](form-container.md)一起使用。

选项、标签和单个选项的表示方式可由[配置对话框](#configure-dialog)中的内容编辑器定义。

## 版本和兼容性 {#version-and-compatibility}

表单选项组件的当前版本为v2，该版本于2018年1月随核心组件2.0.0版一起引入，在本文档中进行了描述。

下表详细列出了组件的所有受支持版本、组件版本与之兼容的AEM版本，以及指向以前版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v2 | 兼容 | 兼容 | 兼容 |
| [v1](/help/components/v1/form-options-v1.md) | 兼容 | 兼容 | - |

有关核心组件版本和版本的更多信息，请参阅文档[核心组件版本](/help/versions.md)。

## 组件输出示例 {#sample-component-output}

要体验表单选项组件并查看其配置选项以及HTML和JSON输出的示例，请访问[组件库](https://adobe.com/go/aem_cmp_library_form_options)。

### 技术详细信息 {#technical-details}

有关表单选项组件[的最新技术文档可在GitHub](https://adobe.com/go/aem_cmp_tech_form_options_v2)上找到。

有关开发核心组件的更多详细信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## 配置对话框 {#configure-dialog}

配置对话框允许内容作者定义应显示的选项类型、标签以及可用的选项。

![表单选项组件的编辑对话框](/help/assets/form-options-edit.png)

* **类型**  — 选项的显示方式
   * **复选框**
   * **单选按钮**
   * **下拉面板**
   * **多选下拉面板**
* **标题**  — 将作为选项标签显示的标题
* **名称**  — 使用表单数据提交的字段的名称
* **来源**  — 定义选项的位置
   * **本地**  — 在组件中定义
      * 点按或单击&#x200B;**Add**&#x200B;按钮以添加值， **Delete**&#x200B;可删除值
         * **值**  — 提交表单时选择该选项时保存的值
         * **文本**  — 表单上显示的选项的标签
         * **活动**  — 在表单加载时，选项被标记为已选中
         * **禁用**  — 选项不可选，但仍显示
   * **列表**  — 在AEM中其他位置定义的静态列表用于各个选项
      * **列表**  - AEM中静态列表的路径
         * 使用Browse按钮查找列表资源
   * **数据源**  — 使用数据源进行选项
      * **数据源**  — 数据源的资源类型
* **帮助消息**  — 向用户提供可在字段中输入内容的提示
* **ID**  — 利用此选项，可控制HTML和数据层中组件的唯一标识符 [的唯一标识符](/help/developing/data-layer/overview.md)。
   * 如果留为空白，则会自动为您生成唯一ID，并且可以通过检查生成的页面找到该ID。
   * 如果指定了ID，则作者有责任确保该ID是唯一的。
   * 更改ID可能会影响CSS、JS和数据层跟踪。

## “设计”对话框 {#design-dialog}

### “样式”选项卡 {#styles-tab}

表单选项组件支持AEM [样式系统](/help/get-started/authoring.md#component-styling)。
