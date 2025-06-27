---
title: 快速搜索组件 (v1)
description: 快速搜索组件提供对网站的搜索功能并显示搜索结果，以便访客能够搜索网站并筛选结果。
role: Architect, Developer, Admin, User
exl-id: 60a043b7-d82c-4bc1-b91a-b77f748f7bc2
index: n
source-git-commit: 92a3ec273a5be6751c1503835b9c2e5cbd61bb9e
workflow-type: ht
source-wordcount: '646'
ht-degree: 100%

---


# 快速搜索组件 (v1) {#quick-search-component}

快速搜索组件提供对网站的搜索功能并显示搜索结果，以便访客能够轻松找到匹配内容并查看结果。

## 用途 {#usage}

利用快速搜索组件，网站访客能够搜索内容、就地查看结果和轻松导航到匹配页面。在用户滚动浏览搜索结果时，将动态获取新结果。

利用[“编辑”对话框](#edit-dialog)，内容作者可以定义内容树中开始搜索的位置。利用[“设计”对话框](#design-dialog)，模板作者可以设置内容树中开始搜索的位置的默认值，以及最大结果集大小和最小搜索词长度。

## 版本和兼容性 {#version-and-compatibility}

快速搜索组件的当前版本是 v1，此版本随 2018 年 1 月的核心组件 2.0.0 版的发布引入，具体说明见本文。

下表详细说明了该组件的所有受支持版本、与该组件的版本兼容的 AEM 版本以及指向早期版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v1 | 与<br>[版本 2.17.4](/help/versions.md) 和更低版本兼容 | 兼容 | 兼容 |

>[!CAUTION]
>
>本文档介绍了快速搜索组件 (v1)。
>>有关当前版本的快速搜索组件的详细信息，请参阅[快速搜索组件](/help/components/quick-search.md)文档。

有关核心组件版本的更多信息，请参阅文档[核心组件版本](/help/versions.md)。

### 技术详细信息 {#technical-details}

>[!NOTE]
>
>应对搜索组件或任何基于 AEM 的应用程序实施更高级别的保护以使其免受 DOS 攻击，例如，通过使用 Dispatcher 上的 `mod_security`。

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_search_v1_cn)有关快速搜索组件的最新技术文档。

在[核心组件开发人员文档](/help/developing/overview.md)中可找到有关开发核心组件的其他详细信息。

## “编辑”对话框 {#edit-dialog}

利用“编辑”对话框，内容作者可以定义内容树中开始搜索的位置。

![快速搜索组件的“编辑”对话框](/help/assets/quick-search-edit.png)

**搜索根** - 要从其开始搜索的根页面。搜索根可以是 Blueprint 母版页、语言母版页或常规页。
* **ID** - 利用此选项，可以控制 HTML 和[Data Layer 中的组件的唯一标识符。](/help/developing/data-layer/overview.md)
   * 如果留空，系统会自动为您生成一个唯一 ID，可以通过检查结果页面找到该 ID。
   * 如果指定一个 ID，作者有责任确保它是唯一的。
   * 更改此 ID 会对 CSS、JS 和 Data Layer 跟踪产生影响。

>[!NOTE]
>
>如果&#x200B;**搜索根**&#x200B;未配置或无法解析，则快速搜索默认为在当前页面下搜索。

## “设计”对话框 {#design-dialog}

利用“设计”对话框，模板作者可以设置内容树中开始搜索的位置的默认值以及最大结果集大小和最小搜索词长度。“设计”对话框允许模板作者定义哪些文本格式选项可供内容作者使用。

### “属性”选项卡 {#properties-tab}

![快速搜索组件的“设计”对话框](/help/assets/quick-search-design.png)

* **搜索根**
内容作者在内容页面上放置快速搜索组件时搜索根的默认值
* **结果大小**
搜索请求获取的结果的最大数目
* **搜索词最小长度**
用于开始搜索的搜索词的最小长度

>[!NOTE]
>
>由于只能在设计模式中设置&#x200B;**结果大小**&#x200B;和&#x200B;**搜索词最小长度**，因此它们仅处于模板级别，这意味着内容作者无法修改这些值。

>[!CAUTION]
>
>如果&#x200B;**结果大小**&#x200B;和&#x200B;**搜索词最小长度**&#x200B;分别设置得太高或太低，则会影响性能。

### “样式”选项卡 {#styles-tab}

快速搜索组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。
