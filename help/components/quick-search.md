---
title: 快速搜索组件
description: 快速搜索组件为网站提供搜索功能并显示搜索结果，以便访客可以搜索网站并筛选结果。
translation-type: tm+mt
source-git-commit: c186e9ec3944d785ab0376769cf7f2307049a809
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 2%

---


# 快速搜索组件 {#quick-search-component}

快速搜索组件为网站提供搜索功能并显示搜索结果，使访客可以轻松找到匹配的内容和视图结果。

## 使用 {#usage}

快速搜索组件优惠站点能够访客搜索内容、将结果视图到位并轻松导航到匹配的页面。 当用户滚动搜索结果时，将动态获取新结果。

通过 [编辑对话框](#edit-dialog) ，内容作者可以定义在内容树中搜索应开始的位置。 使用设 [计对话框](#design-dialog)，模板作者可以设置内容树中应开始搜索的位置的默认值以及最大结果集大小和最小搜索词长度。

## 版本和兼容性 {#version-and-compatibility}

快速搜索组件的当前版本为v1,2018年1月随核心组件版本2.0.0一起推出，本文档对此进行了说明。

下表详细列出了组件的所有受支持版本、与组件版本兼容的AEM版本以及指向先前版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM 云服务 |
|--- |--- |--- |---|
| v1 | 兼容 | 兼容 | 兼容 |

有关核心组件版本和版本的详细信息，请参阅文档 [核心组件版本](/help/versions.md)。

### 技术详细信息 {#technical-details}

>[!NOTE]
>
>保护搜索组件或任何基于AEM的应用程序免受DOS攻击的方法应在更高的级别实施，例如，在调度程 `mod_security` 序上使用。

有关“快速搜索组件”的最 [新技术文档可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_search_v1)。

有关开发核心组件的更多详细信息，请参阅核 [心组件开发人员文档](/help/developing/overview.md)。

## Edit Dialog {#edit-dialog}

编辑对话框允许内容作者定义在内容树中搜索应开始的位置。

![快速搜索组件的编辑对话框](/help/assets/quick-search-edit.png)

**搜索根** -从中开始搜索的根页面。 搜索根目录可以是Blueprint主页、语言主页或常规页。
* **ID** —— 此选项允许控制HTML和数据层中组件的唯一标 [识符](/help/developing/data-layer/overview.md)。
   * 如果留空，则会自动为您生成唯一ID，并可通过检查生成的页面找到该ID。
   * 如果指定了ID，则作者有责任确保它是唯一的。
   * 更改ID可能会影响CSS、JS和数据层跟踪。

## 设计对话框 {#design-dialog}

使用设计对话框，模板作者可以设置内容树中搜索应开始的位置的默认值以及最大结果集大小和最小搜索词长度。设计对话框允许模板作者定义可供内容作者使用的文本格式选项。

### 属性选项卡 {#properties-tab}

![“快速搜索”组件的设计对话框](/help/assets/quick-search-design.png)

* **搜索根**&#x200B;内容作者将快速搜索组件放置到内容页面时搜索根的默认值
* **结果大**&#x200B;小搜索请求获取的结果的最大数量
* **搜索词最小长**&#x200B;度要开始搜索的搜索词的最小长度

>[!NOTE]
>
>**结果大小****和搜索词最小长度只能在设计模式下设置** ，因此只能在模板级别设置，这意味着内容作者无法修改这些值。

>[!CAUTION]
>
>**如果结果** “大 **小”和“搜索词最小长度** ”分别设置为过高或过低，则可能会对性能产生影响。

### 样式选项卡 {#styles-tab}

快速搜索组件支持AEM样 [式系统](/help/get-started/authoring.md#component-styling)。
