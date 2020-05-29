---
title: 分隔符组件
description: 分隔符组件在页面上的组件之间创建一个分隔符
translation-type: tm+mt
source-git-commit: c186e9ec3944d785ab0376769cf7f2307049a809
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 5%

---


# 分隔符组件 {#separator-component}

核心组件分隔符组件显示用于分隔内容的水平规则。

## 使用 {#usage}

分隔器组件允许内容作者轻松创建水平规则作为内容之间的分隔，以更好地组织页面上的信息。

## 版本和兼容性 {#version-and-compatibility}

当前版本的分隔组件为v1，该版本在2019年2月随核心组件的2.3.0版本一起推出，并在本文档中加以说明。

下表详细列出了组件的所有受支持版本、与组件版本兼容的AEM版本以及指向先前版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM 云服务 |
|---|---|---|---|
| v1 | 兼容 | 兼容 | 兼容 |

## 示例组件输出 {#sample-component-output}

要体验分隔符组件以及其配置选项以及HTML和JSON输出的示例，请访问组 [件库](https://adobe.com/go/aem_cmp_library_separator)。

### 技术详细信息 {#technical-details}

有关Separator Component的最新技术文 [档可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_separator_v1)。

有关开发核心组件的更多详细信息，请参阅核 [心组件开发人员文档](/help/developing/overview.md)。

## 配置对话框 {#configure-dialog}

![分隔符组件的编辑对话框](/help/assets/separator-edit.png)

* **ID** —— 此选项允许控制HTML和数据层中组件的唯一标 [识符](/help/developing/data-layer/overview.md)。
   * 如果留空，则会自动为您生成唯一ID，并可通过检查生成的页面找到该ID。
   * 如果指定了ID，则作者有责任确保它是唯一的。
   * 更改ID可能会影响CSS、JS和数据层跟踪。

## 设计对话框 {#design-dialog}

设计对话框允许模板作者定义应用于分隔符组件的样式。

### 样式选项卡 {#styles-tab}

分隔符组件支持AEM [样式系统](/help/get-started/authoring.md#component-styling)。
