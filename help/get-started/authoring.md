---
title: 通过核心组件创作
description: 在AEM中，组件是构成所创作页面内容的结构元素 — 核心组件提供灵活且功能丰富的创作功能。
role: Architect, Developer, Admin, User
exl-id: 56e58303-a178-45ab-b59d-e374c9cf90cf
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '764'
ht-degree: 8%

---

# 使用核心组件创作

在 Adobe Experience Manager 中，组件是结构化元素，用于构成所创作的页面内容。

核心组件提供了灵活且功能丰富的创作功能。 [WKND引用站点](https://wknd.site)及其说明了如何使用核心组件来实施丰富的网站体验。

要体验核心组件并查看其配置选项以及HTML和JSON输出的示例，请访问[组件库](https://adobe.com/go/aem_cmp_library)。

有关使用[AEM项目原型](/help/developing/archetype/overview.md)在AEM项目上实施核心组件的更深入、面向开发人员的介绍，请参阅[ WKND教程。](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)

>[!NOTE]
>
>核心组件不可直接供作者使用，[开发团队必须先将它们集成到您的环境中](/help/get-started/using.md)。集成后，即可通过[模板编辑器](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)使用和预配置模板。

>[!CAUTION]
>
>核心组件[需要AEM 6.4或更高版本](/help/versions.md)，并且需要使用[可编辑的模板](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)。 它们不适用于经典UI，也不适用于静态模板。

## 通过核心组件创作 {#authoring-with-core-components}

作为作者，您会注意到核心组件的几个优势，包括：

* 使用简单，与[页面编辑器](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html)集成良好

* 功能丰富，可适应许多用例，如[WKND引用站点](https://wknd.site)以及[组件库](https://adobe.com/go/aem_cmp_library)中所示

* [预配置](#pre-configuring-core-components) 以通过模板编辑器定义页面作者可用的 [功能](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)

* 围绕[无障碍准则](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html)构建

* 构建为支持[响应式布局](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/responsive-layout.html)

* 构建为支持[轻松本地化](localization.md)

在[编辑页面](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html)时，可在页面编辑器侧面板的&#x200B;**组件**&#x200B;选项卡上使用组件。

组件会根据称为组件组的类别进行分组，以便轻松组织和过滤组件。 组件组名称与组件一起显示在[组件浏览器](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html)中，并且还可以按组进行过滤，以轻松找到正确的组件。

>[!NOTE]
>
>默认情况下，核心组件是隐藏组的一部分，在组件浏览器中不可见。
>
>将所需组件添加到可见的组，或自定义这些组件以供作者使用。

## 预配置核心组件 {#pre-configuring-core-components}

配置基础组件是开发人员的工作。 但是，使用核心组件，模板作者现在可以通过模板编辑器配置许多功能。

例如，如果图像组件不应允许从文件系统上传图像，或者如果文本组件应仅允许某些段落格式，则只需单击一下即可启用或禁用这些功能。

有关更多信息，请参阅[创建页面模板](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html) 。

### 编辑和设计对话框 {#edit-and-design-dialogs}

由于核心组件可由模板作者进行预配置以定义允许哪些选项作为模板的一部分，然后由页面作者进一步配置以定义实际的页面内容，因此每个组件可以在两个不同的对话框中具有选项。

|  | 描述 | 控制内容 | 示例 |
|--- |--- |--- |--- |
| **编辑对话框** | 在对放置的组件进行正常页面编辑期间，**页面作者**&#x200B;可修改的选项 | 组件显示的内容以及组件最终在页面上的显示方式。 | 设置内容文本的格式，旋转页面上的图像 |
| **“设计”对话框** | 配置页面模板时，**模板作者**&#x200B;可修改的选项。 | 编辑组件时，页面作者可以使用哪些选项 | 哪些文本格式选项可用，哪些图像就地选项可用 |

### 组件样式 {#component-styling}

大多数核心组件的样式都可以使用AEM样式系统来定义。

* 模板作者可以在该组件的“设计”对话框中定义哪些样式可用于特定组件。
* 然后，内容作者可以选择要在添加组件和创建内容时应用的样式。

有关更多详细信息，请参阅[样式系统](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/style-system.html)文档。

## 开发人员资源 {#developer-resources}

有关核心组件的技术信息，请参阅[开发核心组件](/help/developing/overview.md)开发人员文档。
