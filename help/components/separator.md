---
title: 分隔符组件
description: 分隔符组件在页面上的组件之间创建分隔符
role: 架构师、开发人员、管理员、业务从业者
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 5%

---


# 分隔符组件 {#separator-component}

核心组件分隔符组件显示用于分隔内容的水平规则。

## 使用 {#usage}

使用分隔符组件，内容作者可以轻松创建水平规则作为内容之间的分隔线，以更好地组织页面上的信息。

## 版本和兼容性{#version-and-compatibility}

Separator Component的当前版本为v1,2019年2月随核心组件版本2.3.0引入了v1，本文档对此进行了说明。

下表详细列出了组件的所有受支持版本、与组件版本兼容的AEM版本，以及指向先前版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|---|
| v1 | 兼容 | 兼容 | 兼容 |

## 示例组件输出{#sample-component-output}

要体验Separator组件，并查看其配置选项以及HTML和JSON输出的示例，请访问[组件库](https://adobe.com/go/aem_cmp_library_separator)。

### 技术详细信息{#technical-details}

有关Separator组件[的最新技术文档可在GitHub](https://adobe.com/go/aem_cmp_tech_separator_v1)上找到。

有关开发核心组件的更多详细信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## 配置对话框{#configure-dialog}

![分隔符组件的编辑对话框](/help/assets/separator-edit.png)

* **ID**  — 此选项允许控制HTML和数据层中组件的唯一 [标识符](/help/developing/data-layer/overview.md)。
   * 如果留空，系统会为您自动生成唯一ID，通过检查生成的页面可以找到它。
   * 如果指定了ID，则作者有责任确保它是唯一的。
   * 更改ID可能会影响CSS、JS和数据图层跟踪。

## 设计对话框{#design-dialog}

设计对话框允许模板作者定义应用于分隔符组件的样式。

### 样式选项卡{#styles-tab}

分隔符组件支持AEM [样式系统](/help/get-started/authoring.md#component-styling)。
