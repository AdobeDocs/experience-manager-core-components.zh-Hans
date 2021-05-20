---
title: 对核心组件的AMP支持
description: 核心组件支持AMP - Accelerated Mobile Pages
role: Architect, Developer, Administrator
exl-id: 1fd9b6b5-0e4d-48c7-8faa-42e0d4a6bbd0
source-git-commit: 8ff36ca143af9496f988b1ca65475497181def1d
workflow-type: tm+mt
source-wordcount: '558'
ht-degree: 1%

---

# 对核心组件{#amp-support}的AMP支持

从核心组件的[版本2.11.0](/help/versions.md)开始，完全支持[AMP - Accelerated Mobile Pages](https://developers.google.com/amp) -。

本文档概述了AMP的支持方式以及如何为您的站点启用它。 但是，有关完整的技术详细信息，请参阅[GitHub开发人员文档。](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)

## 什么是AMP?{#what-is-amp}

Accelerated Mobile Pages或AMP是一个开源框架，最初由Google设计，旨在优化页面以进行移动浏览。 AMP页面的加载速度通常比标准网页快得多，可提供更好的移动体验。

## 核心组件{#amp-in-core-components}中的AMP

核心组件中对AMP的支持可以完全配置[。](#enabling-amp) 页面的AMP版本可以与标准HTML版本一起提供，也可以根本不提供。

核心组件使用`amp`作为Sling选择器来渲染AMP页面。 例如，`example.html`将呈现正常页面，而`example.amp.html`将呈现AMP版本。

单个项目可以决定是否利用AMP。 事实上，由于AMP和标准HTML页面可以并行交付，因此项目可以选择仅在项目的某些页面上使用AMP。

## 项目{#getting-started}中的AMP支持快速入门

尽管AMP支持提供了极大的灵活性，但要快速入门，只需几个简单的步骤：

1. 根据需要安装AMP支持扩展。
   * 对于AEM as a Cloud Service项目，核心组件会自动提供该扩展，因此无需进行安装。
   * 对于内部部署和AMS项目，安装核心组件时必须明确安装扩展。
1. 安装AMP扩展后，组件作者只需将组件超类型指向扩展中的超类型即可。
1. [在模板](#enabling-amp) 级别或您的各个页面上启用AMP支持。
1. [根据需要部](#css-requirements) 署内联CSS。

### 为页面{#enabling-amp}启用AMP

要为页面启用AMP，必须在[页面策略中选择&#x200B;**AMP模式**。](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html#editing-a-template-page-policy-template-author-developer)

![AMP页面策略选项](/help/assets/amp-policy.png)

* **无AMP**  — 仅将页面作为标准HTML提供。
* **已配对的AMP**  — 页面将以AMP和HTML形式交付。
* **仅限AMP**  — 仅将页面作为AMP交付。

页面的AMP设置也可以在单个页面的[页面属性](https://docs.adobe.com/content/help/zh-Hans/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html)中覆盖。

![AMP页面属性](/help/assets/amp-page-properties.png)

* **继承自页面模板**  — 这是默认值，允许从页面模板的策略中获取该设置。
* **无AMP**  — 仅将页面作为标准HTML提供。
* **已配对的AMP**  — 页面将以AMP和HTML形式交付。
* **仅限AMP**  — 仅将页面作为AMP交付。

### CSS要求{#css-requirements}

将AMP与核心组件结合使用时，主要区别在于AMP要求在`<head>`元素中插入所有[CSS并对其进行优化。](including-clientlibs.md#inlining)

要支持此功能，需使用自定义的页面组件，该组件只会为页面上存在的组件加载特定于AMP的CSS。

>[!NOTE]
>
>由于AMP设计限制，Adobe不支持将响应式网格与页面的AMP版本结合使用。

有关更多要求和技术详细信息，请参阅[GitHub开发人员文档。](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)
