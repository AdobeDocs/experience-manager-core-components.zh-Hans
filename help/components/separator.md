---
title: 分隔符组件
description: 分隔符组件在页面上的组件之间创建隔断
role: Architect, Developer, Admin, User
exl-id: 79f19368-67fa-4864-93f7-2aa801d13fdb
source-git-commit: 9767a3a10cb9a77f385edc0ac3fb00096c0087af
workflow-type: ht
source-wordcount: '308'
ht-degree: 100%

---

# 分隔符组件 {#separator-component}

核心组件分隔符组件显示分隔内容的水平规则。

## 用途 {#usage}

使用分隔符组件，内容作者可以轻松地创建水平规则作为内容之间的隔断，以更好地排列页面上的信息。

## 版本和兼容性 {#version-and-compatibility}

分隔符组件的当前版本是 V1，此版本随 2019 年 2 月的核心组件发行版 2.3.0 的发布引入，具体说明见本文。

下表详细说明了该组件的所有受支持版本、与该组件的版本兼容的 AEM 版本以及指向早期版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|---|
| v1 | 兼容<br>[版本 2.17.4](/help/versions.md) 和更低版本 | 兼容 | 兼容 |

## 示例组件输出 {#sample-component-output}

要体验分隔符组件并查看其配置选项示例以及 HTML 和 JSON 输出，请访问[组件库](https://adobe.com/go/aem_cmp_library_separator_cn)。

### 技术详细信息 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_separator_v1_cn)有关分隔符组件的最新技术文档。

在[核心组件开发人员文档](/help/developing/overview.md)中可找到有关开发核心组件的其他详细信息。

## “配置”对话框 {#configure-dialog}

![分隔符组件的“编辑”对话框](/help/assets/separator-edit.png)

* **ID** - 利用此选项，可以控制 HTML 和 [Data Layer](/help/developing/data-layer/overview.md) 中的组件的唯一标识符。
   * 如果留空，系统会自动为您生成一个唯一 ID，可以通过检查结果页面找到该 ID。
   * 如果指定一个 ID，作者有责任确保它是唯一的。
   * 更改此 ID 会对 CSS、JS 和 Data Layer 跟踪产生影响。

## “设计”对话框 {#design-dialog}

利用“设计”对话框，模板作者可以定义应用于分隔符组件的样式。

### “样式”选项卡 {#styles-tab}

分隔符组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。
