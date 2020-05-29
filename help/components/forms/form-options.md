---
title: 表单选项组件
description: 核心组件表单选项组件允许从预定义的各种格式选项中进行选择。
translation-type: tm+mt
source-git-commit: c186e9ec3944d785ab0376769cf7f2307049a809
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 4%

---


# 表单选项组件 {#form-options-component}

核心组件表单选项组件允许从预定义的各种格式选项中进行选择。

## 使用 {#usage}

核心组件表单选项组件允许提交以多种不同方式呈现的不同类型的选项，并打算与表单容器组件一 [起使用](form-container.md)。

选项、标签和单个选项的演示可由配置对话框中的内容编辑器 [定义](#configure-dialog)。

## 版本和兼容性 {#version-and-compatibility}

表单选项组件的当前版本为v2,2018年1月随核心组件版本2.0.0一起推出，本文档对此进行了说明。

下表详细列出了组件的所有受支持版本、与组件版本兼容的AEM版本以及指向先前版本文档的链接。

| 组件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM 云服务 |
|--- |--- |--- |--- |---|
| v2 | - | 兼容 | 兼容 | 兼容 |
| [v1](/help/components/v1/form-options-v1.md) | 兼容 | 兼容 | 兼容 | - |

有关核心组件版本和版本的详细信息，请参阅文档 [核心组件版本](/help/versions.md)。

## 示例组件输出 {#sample-component-output}

要体验表单选项组件以及查看其配置选项以及HTML和JSON输出的示例，请访问组 [件库](https://adobe.com/go/aem_cmp_library_form_options)。

### 技术详细信息 {#technical-details}

有关“表单选项”组件的最 [新技术文档可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_form_options_v2)。

有关开发核心组件的更多详细信息，请参阅核 [心组件开发人员文档](/help/developing/overview.md)。

## 配置对话框 {#configure-dialog}

配置对话框允许内容作者定义应显示的选项类型、标签和可用的选项。

![表单选项组件的编辑对话框](/help/assets/form-options-edit.png)

* **类型** -选项的显示方式
   * **复选框**
   * **单选按钮**
   * **下拉面板**
   * **多选下拉面板**
* **标题** -将作为选项标签显示的标题
* **名称** -随表单数据提交的字段的名称
* **源** -定义选项的位置
   * **本地** -在组件中定义
      * 点按或单击 **添加** 按钮以添加值， **删除** 以删除值
         * **值** -提交表单时选择该选项时保存的值
         * **文本** -表单上显示的选项的标签
         * **活动** -加载表单时，选项被标记为已选
         * **禁用** -选项不可选，但仍显示
   * **列表** -在AEM的其他位置定义的静态列表用于选项
      * **列表** - AEM中静态列表的路径
         * 使用“浏览”按钮查找列表资源
   * **数据源** -数据源用于选项
      * **数据源** -数据源的资源类型
* **帮助消息** -提示用户可在字段中输入的内容
* **ID** —— 此选项允许控制HTML和数据层中组件的唯一标 [识符](/help/developing/data-layer/overview.md)。
   * 如果留空，则会自动为您生成唯一ID，并可通过检查生成的页面找到该ID。
   * 如果指定了ID，则作者有责任确保它是唯一的。
   * 更改ID可能会影响CSS、JS和数据层跟踪。

## 设计对话框 {#design-dialog}

### 样式选项卡 {#styles-tab}

表单选项组件支持AEM样 [式系统](/help/get-started/authoring.md#component-styling)。
