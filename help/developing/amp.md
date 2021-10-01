---
title: 核心组件的 AMP 支持
description: 核心组件支持 AMP - 移动页面加速
role: Architect, Developer, Admin
exl-id: 1fd9b6b5-0e4d-48c7-8faa-42e0d4a6bbd0
source-git-commit: 2ac16b15718128feefbe903e92f276b16fe96f69
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 96%

---

# 核心组件的 AMP 支持 {#amp-support}

自核心组件的[版本 2.11.0](/help/versions.md) 起，完全支持 [AMP - 移动页面加速](https://developers.google.com/amp)。

本文档概述了 AMP 的支持方式以及如何为您的站点启用它。有关完整技术详细信息，请参阅 [GitHub 开发人员文档。](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)

## 什么是 AMP？ {#what-is-amp}

移动页面加速 (AMP) 是一个开源框架，最初由 Google 设计，用于优化页面以便于移动浏览。AMP 页面的加载速度通常比标准网页快得多，这将提供更出色的移动体验。

## 核心组件中的 AMP {#amp-in-core-components}

对核心组件中的 AMP 的支持是[安全可配置的。](#enabling-amp) AMP 版本的页面可单独提供、与标准 HTML 版本一起提供，或根本不提供。

核心组件使用 `amp` 作为 Sling 选择器来渲染 AMP 页面。例如，`example.html` 将渲染一般页面，`example.amp.html` 将为 AMP 版本。

各个项目均可决定是否利用 AMP。实际上，由于 AMP 和标准 HTML 页面可以并行交付，因此项目可以选择仅在其某些页面上使用 AMP。

## 项目中的 AMP 支持快速入门 {#getting-started}

AMP 支持提供了很大的灵活性，快速开始使用 AMP 只需执行几个简单步骤：

1. 安装 AMP 支持扩展（如果需要）。
   * 对于 AEM as a Cloud Service 项目，扩展自动随核心组件提供，而无需安装。
   * 对于内部部署和 AMS 项目，安装核心组件时必须显式安装扩展。
1. 安装 AMP 扩展后，组件作者必须将组件超类型指向扩展中的超类型。
1. 在模板级别或单个页面上[启用 AMP 支持](#enabling-amp)。
1. 根据需要[部署内联 CSS](#css-requirements)。

### 为页面启用 AMP {#enabling-amp}

要为页面启用 AMP，必须在[页面策略](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html#editing-a-template-page-policy-template-author-developer)中选择 **AMP 模式**。

![AMP 页面策略选项](/help/assets/amp-policy.png)

* **无 AMP** - 仅以标准 HTML 形式提供页面。
* **成对 AMP** - 以 AMP 和 HTML 形式提供页面。
* **仅 AMP** - 仅以 AMP 形式提供页面。

也可在单个页面的[页面属性](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html)中覆盖页面的 AMP 设置。

![AMP 页面属性](/help/assets/amp-page-properties.png)

* **从页面模板继承** - 这是默认值，允许从页面模板的策略中获取设置。
* **无 AMP** - 仅以标准 HTML 形式提供页面。
* **成对 AMP** - 以 AMP 和 HTML 形式提供页面。
* **仅 AMP** - 仅以 AMP 形式提供页面。

### CSS 要求 {#css-requirements}

在将 AMP 与核心组件结合使用时，主要区别在于 AMP 要求在 `<head>` 元素中将所有 [CSS 内联](including-clientlibs.md#inlining) 并进行优化。

为了满足此要求，可使用自定义页面组件，它只为页面上显示的组件加载特定于 AMP 的 CSS。

>[!NOTE]
>
>由于 AMP 设计限制，Adobe 不支持将响应式网格用于页面的 AMP 版本。

有关其他要求和技术详细信息，请参阅 [GitHub 开发人员文档。](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)
