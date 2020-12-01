---
title: 核心组件的成功路径
description: 如何通过核心组件实现项目
translation-type: tm+mt
source-git-commit: c338428a681f652d17bb972fb6a2abf216a338c3
workflow-type: tm+mt
source-wordcount: '570'
ht-degree: 14%

---


# 核心组件{#paths-to-success}的成功路径

核心组件功能强大、灵活，易于使用和自定义。 遵循本文档中概述的几项关键指南，将确保您的核心组件项目取得成功。

## 成功的两条路径{#two-paths}

实施核心部分有两种基本方法，可以取得成功，但需要逐个项目考虑它们自己的权衡。

1. 将您的设计映射到核心组件，并采用它们提供的HTML。 或者
1. 如果您必须遵守已定义的HTML标准，则需要付出更多努力，而不是获得核心组件的所有优势。

## 组件实现中的常见缺陷{#common-pitfalls}

导致核心组件无法成功的项目的两个常见问题是：

* **最终设计** -这些设计甚至可能得到C级批准，并交给开发团队进行像素级完美化实施，而无需考虑底层技术。
* **公司范围的HTML样式指南** -此类指南往往必须由从上到下透视应用样式的组件教条式地遵循。

在这两种情况下，对组件的要求都非常严格和特定，因此很难使核心组件或任何现成的组件符合这些要求，从而导致自定义组件的大量开发。

## 开始早期{#start-early}

在线框化和设计阶段，已与核心组件开始，而不是只考虑项目实施阶段的核心组件。

### 使用组件库{#component-library}

引用设计阶段中已有的[组件库](https://adobe.com/go/aem_cmp_library)。 核心组件功能强大、灵活，可以帮助您达到最高要求。 只有在真正有业务需求且核心组件无法合理实现时，才添加自定义组件。

### 使用Adobe XD{#ui-kit}的UI套件

只要对自定义组件有充分的需求，就应利用适用于Adobe XD的[UI套件](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/assets/overview/AEM_UI-kit_Wireframe.xd)，这样设计人员就可以开始构建线框和以核心组件为构件的设计。

## 不要忽视强大的功能{#powerful-features}

AEM和核心组件的功能可能非常强大，但也非常微妙，某些功能的可能性对设计人员来说可能并不直接。

### 内容片段 {#content-fragments}

[内](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/content-fragments.html) 容片段允许您创建渠道中性内容，以及(可能特定于渠道的)变量。您随后可以在创作内容页面时使用这些片段及其变量。

结构化内容片段与更新的 JSON 导出程序结合使用时，还可用于通过 Content Services 将 AEM 内容传送到 AEM 页面以外的渠道。

### 体验片段模板{#experience-fragment-templates}

满足作者希望重复使用页面各个部分（体验的片段）的需求。
如果没有[体验片段，](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/experience-fragments.html)作者需要复制并粘贴该片段。 创建并维护这些复制/粘贴体验非常费时，而且容易导致用户错误。体验片段无需复制/粘贴。

### 嵌入组件{#embed-component}

[嵌入组](/help/components/embed.md) 件不仅允许简单地包含外部资源（如YouTube视频内容），还可扩展以允许它容纳特定于项目需求的内容。