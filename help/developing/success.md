---
title: 使用核心组件取得成功的途径
description: 如何使用核心组件实施项目时取得成功
role: Architect, Developer, Administrator, Business Practitioner
exl-id: 1ea8cd1c-8435-4ded-82dc-5a7896c53e0c
source-git-commit: 056c5bc15ac9e669c3bf6d5da7f060d6eef02608
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 14%

---

# 核心组件{#paths-to-success}成功路径

核心组件功能强大、灵活，易于使用和自定义。 遵循本文档中概述的一些关键准则，将确保您具有核心组件的项目取得成功。

## 成功的两条路径{#two-paths}

实施核心组成部分有两种基本方法，虽然可以取得成功，但需要逐个项目考虑它们各自的利弊。

1. 将您的设计映射到核心组件，并获取它们提供的HTML。 或者
1. 如果您必须遵守已定义的HTML标准，则需要付出更多努力，而无法从核心组件获得所有好处。

## 组件实施{#common-pitfalls}中的常见缺陷

导致项目无法成功使用核心组件的两个常见问题是：

* **最终设计**  — 这些设计甚至可能获得C级批准，并交给开发团队以实施像素级完美设计，而无需考虑底层技术。
* **公司范围的HTML风格指南**  — 此类指南的后面往往必须由从上到下应用样式的组件以教条的方式遵循。

在这两种情况下，对组件的要求都非常严格和具体，因此很难使核心组件或任何现成的组件符合这些要求，从而导致大量开发自定义组件。

## 提前开始{#start-early}

在线框构建和设计阶段，核心组件不再只是考虑项目实施阶段的核心组件，而是从核心组件开始。

### 使用组件库{#component-library}

引用已处于设计阶段的[组件库](https://adobe.com/go/aem_cmp_library)。 核心组件功能强大且灵活，可以让您充分了解。 仅当存在真正的业务需求且无法使用核心组件实现合理目标时，才添加自定义组件。

### 使用Adobe XD UI包{#ui-kit}

只要对自定义组件有充分的需求，就应利用[适用于Adobe XD的UI套件](https://experienceleague.adobe.com/docs/experience-manager-learn/assets/AEM-CoreComponents-UI-Kit.xd)，以便设计人员能够开始使用核心组件作为构建基块来构建线框和设计。

## 不要忽视强大的功能{#powerful-features}

AEM和核心组件的功能可能非常强大，但也非常微妙，某些功能的可能性对于设计人员来说可能并不直接可见。

### 内容片段 {#content-fragments}

[内容](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/content-fragments.html) 片段允许您创建渠道中性内容，以及（可能特定于渠道）变量。您随后可以在创作内容页面时使用这些片段及其变量。

结构化内容片段与更新的 JSON 导出程序结合使用时，还可用于通过 Content Services 将 AEM 内容传送到 AEM 页面以外的渠道。

### 体验片段模板{#experience-fragment-templates}

满足作者希望重复使用页面各个部分（体验的片段）的需求。
如果没有[体验片段，](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/experience-fragments.html)作者需要复制并粘贴该片段。 创建并维护这些复制/粘贴体验非常费时，而且容易导致用户错误。体验片段无需复制/粘贴。

### 嵌入组件{#embed-component}

[嵌入组](/help/components/embed.md) 件不仅允许简单包含外部资源(如YouTube视频内容)，而且还具有可扩展性，以允许它适应特定于项目需求的内容。
