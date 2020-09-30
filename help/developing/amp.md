---
title: 对核心组件的AMP支持
description: 核心组件支持AMP —— 加速移动页面
translation-type: tm+mt
source-git-commit: 2926c51c2ab97b50b9ec4942cd5415c15a1411b6
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 0%

---


# 对核心组件的AMP支持 {#amp-support}

从2. [11.0版](/help/versions.md) 本的核心组 [件开始，完全支持AMP](https://developers.google.com/amp) —— 加速移动页面。

此文档概述了如何支持AMP以及如何为您的站点启用它。 但是，有关完整的技术详细信息，请参 [阅GitHub开发人员文档。](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)

## 什么是AMP? {#what-is-amp}

加速移动页面或AMP是最初由Google设计用于优化移动浏览页面的开放源码框架。 AMP页面的加载速度通常比标准网页快得多，可提供更好的移动体验。

## 核心组件中的AMP {#amp-in-core-components}

可完全配置核心组件中对AMP [的支持。](#enabling-amp) AMP版本的页面可以与标准HTML版本一起提供，或者根本不提供。

核心组件 `amp` 用作Sling选择器来渲染AMP页面。 例如， `example.html` 将呈现普通页面 `example.amp.html` ，并将显示AMP版本。

单个项目可以决定是否利用AMP。 事实上，由于AMP和标准HTML页可以并行交付，因此项目可以选择仅在项目的特定页面上使用AMP。

## 项目中的AMP支持入门 {#getting-started}

尽管AMP支持优惠具有很大的灵活性，但快速入门只需要几个简单的步骤：

1. 根据需要安装AMP支持扩展。
   * 对于AEM作为Cloud Service项目，核心组件可自动使用该扩展，无需安装。
   * 对于内部部署和AMS项目，安装核心组件时必须显式安装扩展。
1. 安装AMP扩展后，组件作者只需将组件超类型指向扩展中的那些类型。
1. [在模板级别](#enabling-amp) ，或在您的各个页面上启用AMP支持。
1. [根据需要部署](#css-requirements) inlined CSS。

### 为页面启用AMP {#enabling-amp}

要为页面启用AMP，必 **须在页面策** 略中 [选择AMP模式。](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html#editing-a-template-page-policy-template-author-developer)

![AMP页策略选项](/help/assets/amp-policy.png)

* **无AMP** —— 页面仅作为标准HTML提供。
* **成对AMP** —— 页面以AMP和HTML的形式传送。
* **仅AMP** —— 页面仅作为AMP传送。

页面的AMP设置也可以在单个页面的 [页面属性](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html) 中被覆盖。

![AMP页面属性](/help/assets/amp-page-properties.png)

* **继承自页面模板** -这是默认值，允许从页面模板的策略中执行设置。
* **无AMP** —— 页面仅作为标准HTML提供。
* **成对AMP** —— 页面以AMP和HTML的形式传送。
* **仅AMP** —— 页面仅作为AMP传送。

### CSS要求 {#css-requirements}

将AMP与核心组件一起使用时，主要区别在于AMP要求 [在元素中嵌入](including-clientlibs.md#inlining)`<head>` 所有CSS并进行优化。

为支持此功能，将使用自定义的页面组件，该组件仅加载页面上所存在的组件的特定于AMP的CSS。

有关更多要求和技术详细信息，请参 [阅GitHub开发人员文档。](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)
