---
title: 快速搜索组件
description: “快速搜索”组件向网站提供搜索功能并显示搜索结果，以便访客可以搜索网站并筛选结果。
role: 架构师、开发人员、管理员、业务从业者
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 2%

---


# 快速搜索组件{#quick-search-component}

“快速搜索”组件向网站提供搜索功能并显示搜索结果，以便访客可以轻松找到匹配的内容和视图结果。

## 使用 {#usage}

“快速搜索”组件优惠站点访客搜索内容、将结果视图到位并轻松导航到匹配页面的功能。 当用户滚动搜索结果时，将动态获取新结果。

[编辑对话框](#edit-dialog)允许内容作者定义在内容树中搜索应开始的位置。 使用[设计对话框](#design-dialog)，模板作者可以设置内容树中应开始搜索的位置的默认值以及最大结果集大小和最小搜索词长度。

## 版本和兼容性{#version-and-compatibility}

快速搜索组件的当前版本为v1,2018年1月随核心组件版本2.0.0引入了v1，本文档对此进行了说明。

下表详细列出了组件的所有受支持版本、与组件版本兼容的AEM版本，以及指向先前版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v1 | 兼容 | 兼容 | 兼容 |

有关核心组件版本和版本的详细信息，请参阅文档[核心组件版本](/help/versions.md)。

### 技术详细信息{#technical-details}

>[!NOTE]
>
>应在更高级别实现保护搜索组件或任何基于AEM的应用程序免受DOS攻击，例如，在调度程序上使用`mod_security`。

有关快速搜索组件[的最新技术文档可在GitHub](https://adobe.com/go/aem_cmp_tech_search_v1)上找到。

有关开发核心组件的更多详细信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## 编辑对话框{#edit-dialog}

通过编辑对话框，内容作者可以定义搜索在内容树中应开始的位置。

![快速搜索组件的编辑对话框](/help/assets/quick-search-edit.png)

**搜索根**  — 从中开始搜索的根页面。“搜索根”可以是蓝图主控、语言主控或常规页面。
* **ID**  — 此选项允许控制HTML和数据层中组件的唯一 [标识符](/help/developing/data-layer/overview.md)。
   * 如果留空，系统会为您自动生成唯一ID，通过检查生成的页面可以找到它。
   * 如果指定了ID，则作者有责任确保它是唯一的。
   * 更改ID可能会影响CSS、JS和数据图层跟踪。

## 设计对话框{#design-dialog}

使用设计对话框，模板作者可以设置内容树中搜索应开始的位置的默认值以及最大结果集大小和最小搜索词长度。设计对话框允许模板作者定义可供内容作者使用的文本格式选项。

### 属性选项卡{#properties-tab}

![“快速搜索组件”的设计对话框](/help/assets/quick-search-design.png)

* **搜索**
根内容作者将快速搜索组件放置到内容页面时搜索根的默认值
* **结果**
大小搜索请求获取的结果的最大数量
* **搜索词最小**
长度要开始搜索的搜索词的最小长度

>[!NOTE]
>
>**结果** 大小 **和搜索词** 最小长度只能在设计模式中设置，因此只能在模板级别设置，这意味着内容作者无法修改这些值。

>[!CAUTION]
>
>**如果** 结果大 **小和搜索词** 最小长度分别设置为过高或过低，则会对性能产生影响。

### 样式选项卡{#styles-tab}

快速搜索组件支持AEM [样式系统](/help/get-started/authoring.md#component-styling)。
