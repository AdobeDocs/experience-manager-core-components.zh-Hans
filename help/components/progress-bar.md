---
title: 进度栏组件
description: 进度栏组件以可视方式表示向目标的进度
translation-type: tm+mt
source-git-commit: c186e9ec3944d785ab0376769cf7f2307049a809
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 3%

---


# 进度栏组件 {#progress-bar-component}

核心组件进度栏组件以可视方式表示目标的进度。

## 使用 {#usage}

进度栏组件允许内容作者通过定义完成百分比轻松创建进度栏，从而直观地显示向目标前进的进度。

## 版本和兼容性 {#version-and-compatibility}

进度栏组件的当前版本为v1,2020年5月随核心组件版本2.9.0一起推出，本文档对此进行了说明。

下表详细列出了组件的所有受支持版本、与组件版本兼容的AEM版本以及指向先前版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM 云服务 |
|---|---|---|---|
| v1 | 兼容 | 兼容 | 兼容 |

## 示例组件输出 {#sample-component-output}

要体验进度栏组件并查看其配置选项以及HTML和JSON输出的示例，请访问组 [件库](https://adobe.com/go/aem_cmp_library_progress)。

### 技术详细信息 {#technical-details}

有关“进度栏组件”的最 [新技术文档可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_progress_v1)。

有关开发核心组件的更多详细信息，请参阅核 [心组件开发人员文档](/help/developing/overview.md)。

## 配置对话框 {#configure-dialog}

![进度栏组件的编辑对话框](/help/assets/progress-bar-edit.png)

* **完成** -进度（以百分比表示）
* **ID** —— 此选项允许控制HTML和数据层中组件的唯一标 [识符](/help/developing/data-layer/overview.md)。
   * 如果留空，则会自动为您生成唯一ID，并可通过检查生成的页面找到该ID。
   * 如果指定了ID，则作者有责任确保它是唯一的。
   * 更改ID可能会影响CSS、JS和数据层跟踪。

## 设计对话框 {#design-dialog}

设计对话框允许模板作者定义应用于进度栏组件的样式。

### 样式选项卡 {#styles-tab}

进度栏组件支持AEM样 [式系统](/help/get-started/authoring.md#component-styling)。
