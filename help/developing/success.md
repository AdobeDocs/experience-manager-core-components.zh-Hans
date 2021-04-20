---
title: 核心组件的成功路径
description: 如何通过核心组件实现项目
role: Architect, Developer, Administrator, Business Practitioner
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '575'
ht-degree: 13%

---


# 核心组件{#paths-to-success}的成功路径

核心组件功能强大、灵活，易于使用和自定义。 遵循本文档中概述的几条关键指南，将确保您的核心组件项目取得成功。

## 成功的两条路径{#two-paths}

实施核心部分有两种基本办法，可以取得成功，但也有各自的取舍，需要逐个项目加以考虑。

1. 将您的设计映射到核心组件，并采用它们提供的HTML。 或者
1. 如果您必须遵守已定义的HTML标准，则需要付出更多努力，而不能从核心组件中获得所有好处。

## 组件实施{#common-pitfalls}中的常见缺陷

导致项目无法成功使用核心组件的两个常见问题是：

* **最终设计**  — 这些设计甚至可能是C级批准的，并交给开发团队以实施像素完美型设计，而不必担心底层技术。
* **公司范围的HTML样式指南**  — 此类指南通常必须由从上到下透视应用样式的组件教条式地遵循。

在这两种情况下，对组件的要求都非常紧密和具体，因此很难使核心组件或任何现成的组件符合这些要求，从而导致自定义组件的大规模开发。

## 开始早{#start-early}

在线框化和设计阶段，已经与核心组件开始，而不是只考虑项目实施阶段的核心组件。

### 使用组件库{#component-library}

引用已在设计阶段的[组件库](https://adobe.com/go/aem_cmp_library)。 核心组件功能强大、灵活，可以帮助您从头开始。 只有在存在真正无法通过核心组件实现的真正业务需求时添加自定义组件。

### 使用Adobe XD {#ui-kit}的UI套件

一旦对自定义组件有了充分的需求，就应利用适用于Adobe XD的[ UI套件](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/assets/overview/AEM_UI-kit_Wireframe.xd)，以便设计人员能够开始构建线框和以核心组件作为构建块的设计。

## 不要忽视强大的功能{#powerful-features}

AEM和核心组件的功能可能非常强大，但也非常微妙，某些功能的可能性对设计人员来说可能并不直接。

### 内容片段 {#content-fragments}

[内容](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/content-fragments.html) 片段允许您创建渠道中性内容，以及(可能特定于渠道的)变量。您随后可以在创作内容页面时使用这些片段及其变量。

结构化内容片段与更新的 JSON 导出程序结合使用时，还可用于通过 Content Services 将 AEM 内容传送到 AEM 页面以外的渠道。

### 体验片段模板{#experience-fragment-templates}

满足作者希望重复使用页面各个部分（体验的片段）的需求。
如果没有[体验片段，](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/experience-fragments.html)作者需要复制并粘贴该片段。 创建并维护这些复制/粘贴体验非常费时，而且容易导致用户错误。体验片段无需复制/粘贴。

### 嵌入组件{#embed-component}

[嵌入](/help/components/embed.md) 组件不仅允许简单地包含外部资源（如YouTube视频内容），而且还可扩展以允许它容纳特定于项目需求的内容。