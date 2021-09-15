---
title: 使用核心组件获得成功的途径
description: 如何成功实施带核心组件的项目
role: Architect, Developer, Admin, User
exl-id: 1ea8cd1c-8435-4ded-82dc-5a7896c53e0c
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: ht
source-wordcount: '564'
ht-degree: 100%

---

# 使用核心组件获得成功的途径 {#paths-to-success}

核心组件的功能强大、灵活且易于使用和自定义。遵循本文档中概述的几个关键准则将确保成功实施带核心组件的项目。

## 获得成功的两个途径 {#two-paths}

有两种实施核心组件的基本方法，虽然可通过这两种方法获得成功，但需要逐个项目对它们进行权衡。

1. 将您的设计映射到核心组件并使用它们提供的 HTML。或者
1. 如果您必须遵循已定义的 HTML 标准，则需要做更多工作，并且无法获得核心组件的所有好处。

## 组件实施中的常见陷阱 {#common-pitfalls}

两个导致带核心组件的项目无法成功实施的常见问题是：

* **最终设计** - 这些设计甚至可能获得高管批准，并且会被移交给开发团队来实现像素完美，而无需考虑底层技术。
* **公司范围内的 HTML 样式指南** - 从自上而下的角度应用样式的组件经常必须教条地遵循此类指南。

在这两种情况下，会对组件提出非常严格和特定的要求，而核心组件或任何现用组件都难以达到这些要求，从而导致需要开发大量的自定义组件。

## 及早开始 {#start-early}

在线框化和设计阶段从核心组件开始，而不是仅在项目的实施阶段考虑核心组件。

### 使用组件库 {#component-library}

参考已处于设计阶段的[组件库](https://adobe.com/go/aem_cmp_library_cn)。核心组件的功能强大且灵活，可将它作为起点来实现更多目标。仅在有实际业务需求，但无法通过核心组件适度满足该需求时添加自定义组件。

### 使用 Adobe XD UI 套件 {#ui-kit}

一旦证明需要自定义组件，就使用 [Adobe XD UI 套件](https://experienceleague.adobe.com/docs/experience-manager-learn/assets/AEM-CoreComponents-UI-Kit.xd)，以便设计人员能够将核心组件用作构建块来开始构建线框和设计。

## 不要忽视强大的功能 {#powerful-features}

AEM 和核心组件的功能非常强大，但却不易被察觉，设计人员可能无法立即获知某些功能的用途。

### 内容片段 {#content-fragments}

[内容片段](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/content-fragments.html)允许您创建渠道中性内容，以及各种（特定于渠道的）变量。您随后可以在创作内容页面时使用这些片段及其变量。

结构化内容片段与更新的 JSON 导出程序结合使用时，还可用于通过 Content Services 将 AEM 内容传送到 AEM 页面以外的渠道。

### 体验片段模板 {#experience-fragment-templates}

满足作者希望重复使用页面各个部分（体验的片段）的需求。如果没有[体验片段，](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/experience-fragments.html)作者需要复制并粘贴该片段。创建并维护这些复制/粘贴体验非常费时，而且容易导致用户错误。体验片段无需复制/粘贴。

### 嵌入组件 {#embed-component}

[嵌入组件](/help/components/embed.md)不仅允许简单地包含外部资源（例如 YouTube 视频内容），而且还可以扩展以适应可满足项目需求的内容。
