---
title: 核心组件的成功路径
description: 如何使用核心组件实施项目时取得成功
translation-type: tm+mt
source-git-commit: c338428a681f652d17bb972fb6a2abf216a338c3

---


# 核心组件的成功路径 {#paths-to-success}

核心组件功能强大、灵活且易于使用和自定义。 按照本文档中概述的几项关键准则，将确保您的核心组件项目取得成功。

## 成功的两条途径 {#two-paths}

实施核心组成部分有两种基本方法，这种方法可能会取得成功，但也有各自的权衡，需要逐项考虑。

1. 将您的设计映射到核心组件，并获取它们提供的HTML。 或者
1. 如果您必须遵守已定义的HTML标准，则需要付出更多努力，而不是获得核心组件的所有优势。

## 组件实施中的常见缺陷 {#common-pitfalls}

导致项目无法成功使用核心组件的两个常见问题是：

* **最终设计** -这些设计甚至可能得到C级批准，并交给开发团队，以便在不考虑底层技术的情况下实现像素完美型。
* **公司范围的HTML样式指南** -此类指南通常必须由从上到下透视应用样式的组件教条式地遵循。

在这两种情况下，对组件的要求都非常紧密和具体，因此很难使核心组件或任何现成的组件符合这些要求，从而导致自定义组件的大规模开发。

## 开始早 {#start-early}

在线框化和设计阶段，已经与核心组件开始，而不是只考虑项目实施阶段的核心组件。

### 使用组件库 {#component-library}

引用已 [经处于设计阶段的组件库](https://adobe.com/go/aem_cmp_library) 。 核心组件功能强大、灵活，可让您远离起点。 只有在真正有业务需求时，才能添加自定义组件，而这些需求无法通过核心组件合理实现。

### 使用Adobe XD的UI套件 {#ui-kit}

一旦对自定义组件有了成熟的需求，就应利用Adobe XD [](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/assets/overview/AEM_UI-kit_Wireframe.xd) UI套件，以便设计人员能够将构建线框和设计与核心组件作为构件块进行开始。

## 不要忽视强大的功能 {#powerful-features}

AEM和核心组件的功能可能非常强大，但也非常微妙，某些功能的可能性对设计人员来说可能并不直接。

### 内容片段 {#content-fragments}

[内容片段](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/content-fragments.html) ，允许您创建不含渠道的内容以及(可能特定于渠道的)变量。 您随后可以在创作内容页面时使用这些片段及其变量。

结构化内容片段与更新的 JSON 导出程序结合使用时，还可用于通过 Content Services 将 AEM 内容传送到 AEM 页面以外的渠道。

### 体验片段模板 {#experience-fragment-templates}

满足作者希望重复使用页面各个部分（体验的片段）的需求。
Without [Experience Fragments,](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/experience-fragments.html) the author would need to copy and paste that fragment. 创建并维护这些复制/粘贴体验非常费时，而且容易导致用户错误。体验片段无需复制/粘贴。

### 嵌入组件 {#embed-component}

[嵌入组件](/help/components/embed.md) 不仅允许简单地包含外部资源（如YouTube视频内容），而且还可扩展以允许其容纳特定于项目需求的内容。