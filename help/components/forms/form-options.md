---
title: 表单选项组件
description: 利用核心组件表单选项组件可从各种格式的预定义选项中进行选择。
role: Architect, Developer, Admin, User
exl-id: 8a74bd37-9b12-4fa6-bff2-53e337b16251
source-git-commit: 9767a3a10cb9a77f385edc0ac3fb00096c0087af
workflow-type: ht
source-wordcount: '549'
ht-degree: 100%

---

# 表单选项组件 {#form-options-component}

利用核心组件表单选项组件可从各种格式的预定义选项中进行选择。

## 用途 {#usage}

利用核心组件表单选项组件可提交通过多种不同方式提供的不同类型的选项，并且此组件旨在与[表单容器组件](form-container.md)结合使用。

多个选项、标签和单个选项的呈现可由内容编辑者在[“配置”对话框](#configure-dialog)中定义。

## 版本和兼容性 {#version-and-compatibility}

表单选项组件的当前版本是 v2，此版本随 2018 年 1 月的核心组件发行版本 2.0.0 的发布引入，具体说明见本文。

下表详细说明了该组件的所有受支持版本、与该组件的版本兼容的 AEM 版本以及指向早期版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v2 | 兼容<br>[版本 2.17.4](/help/versions.md) 和更低版本 | 兼容 | 兼容 |
| [v1](/help/components/v1/form-options-v1.md) | 兼容 | 兼容 | - |

有关核心组件版本的更多信息，请参阅文档[核心组件版本](/help/versions.md)。

## 示例组件输出 {#sample-component-output}

要体验表单选项组件并查看其配置选项示例以及 HTML 和 JSON 输出，请访问[组件库](https://adobe.com/go/aem_cmp_library_form_options_cn)。

### 技术详细信息 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_form_options_v2_cn)有关表单选项组件的最新技术文档。

在[核心组件开发人员文档](/help/developing/overview.md)中可找到有关开发核心组件的其他详细信息。

## “配置”对话框 {#configure-dialog}

利用“配置”对话框，内容作者可以定义应显示的选项类型、标签以及可用的选项。

![表单选项组件的“编辑”对话框](/help/assets/form-options-edit.png)

* **类型** - 如何显示选项
   * **复选框**
   * **单选按钮**
   * **下拉面板**
   * **多选下拉面板**
* **标题** - 将显示为选项标签的标题
* **名称** - 随表单数据一起提交的字段的名称
* **来源** - 在其中定义选项的位置
   * **本地** - 已在组件中定义
      * 点击或单击&#x200B;**添加**&#x200B;按钮可添加值，点击或单击&#x200B;**删除**&#x200B;可删除值
         * **值** - 提交表单期间选择该选项时保存的值
         * **文本** - 表单上显示的选项的标签
         * **活动** - 加载表单时标记为选定的选项
         * **已禁用** - 该选项不可选，但仍会显示
   * **列表** - AEM 中的其他位置定义的静态列表用于此选项
      * **列表** - AEM 中的静态列表的路径
         * 使用“浏览”按钮可找到列表资源
   * **数据源** - 数据源用于选项
      * **数据源** - 数据源的资源类型
* **帮助消息** - 关于用户可在字段中输入的内容的提示
* **ID** - 利用此选项，可以控制 HTML 和[ Data Layer ](/help/developing/data-layer/overview.md)中的组件的唯一标识符。
   * 如果留空，系统会自动为您生成一个唯一 ID，可以通过检查结果页面找到该 ID。
   * 如果指定一个 ID，作者有责任确保它是唯一的。
   * 更改此 ID 会对 CSS、JS 和 Data Layer 跟踪产生影响。

## “设计”对话框 {#design-dialog}

### “样式”选项卡 {#styles-tab}

表单选项组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。
