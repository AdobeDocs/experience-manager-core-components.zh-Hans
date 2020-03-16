---
title: 表单隐藏组件
description: 核心组件表单隐藏组件允许显示隐藏字段。
translation-type: tm+mt
source-git-commit: 95c0621f5423bfa515fe5e8b693e127ea56b4ae0

---


# 表单隐藏组件{#form-hidden-component}

核心组件表单隐藏组件允许显示隐藏字段。

## 使用情况 {#usage}

核心组件表单隐藏组件允许创建隐藏字段，以将有关当前页面的信息传回AEM，并准备与表单容器组件一起 [使用](form-container.md)。

字段属性可由内容编辑器在配置对话框中 [定义](form-hidden.md)。

## 版本和兼容性 {#version-and-compatibility}

表单隐藏组件的当前版本为v2,v2是在2018年1月随核心组件版本2.0.0一起引入的，本文档对此进行了说明。

下表详细列出了组件的所有受支持版本、与组件版本兼容的AEM版本，以及指向先前版本的文档的链接。

| 组件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM 云服务 |
|--- |--- |--- |--- |---|
| v2 | 兼容 | 兼容 | 兼容 | 兼容 |
| [v1](/help/components/v1/form-hidden-v1.md) | 兼容 | 兼容 | 兼容 | - |

有关核心组件版本和版本的详细信息，请参阅文档核 [心组件版本](/help/versions.md)。

## 示例组件输出 {#sample-component-output}

要体验表单隐藏组件以及查看其配置选项的示例以及HTML和JSON输出，请访问组 [件库](https://adobe.com/go/aem_cmp_library_form_hidden)。

### 技术详细信息 {#technical-details}

有关表单隐藏组件的最新技 [术文档可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_form_hidden_v2)。

有关开发核心组件的更多详细信息，请参阅核 [心组件开发人员文档](/help/developing/overview.md)。

## 配置对话框 {#configure-dialog}

配置对话框允许内容作者定义隐藏字段的参数。

![](/help/assets/chlimage_1-26.png)

* **名称**&#x200B;随表单数据一起提交的字段的名称
* **值**&#x200B;随表单数据一起提交的字段的值
* **标识**&#x200B;符页面上的标识符应是唯一的，并且可用于将脚本绑定到此表单字段

由于表单隐藏组件通常没有可见属性，因此，如果为作者分配了“名称”和“值 ******** ”字段值，则编辑器中组件的占位符会显示这些字段值，以帮助作者识别相应的“表单隐藏”组件。

![](/help/assets/screenshot_2018-10-19at094927.png)

## 设计对话框 {#design-dialog}

“表单隐藏”组件没有设计对话框。
