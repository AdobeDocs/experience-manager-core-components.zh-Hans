---
title: 通过核心组件创作
description: 在AEM中，组件是构成所创作页面内容的结构元素 — 核心组件优惠灵活且功能丰富的创作功能。
role: 架构师、开发人员、管理员、业务从业者
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '769'
ht-degree: 8%

---


# 使用核心组件创作

在 Adobe Experience Manager 中，组件是结构化元素，用于构成所创作的页面内容。

核心组件优惠了灵活且功能丰富的创作功能。 [WKND参考站点](https://wknd.site)及其说明如何使用核心组件来实现丰富的网站体验。

要体验核心组件并查看其配置选项以及HTML和JSON输出的示例，请访问[组件库](https://adobe.com/go/aem_cmp_library)。

有关在AEM项目上使用[AEM项目原型](/help/developing/archetype/overview.md)在WKND教程中实施核心组件的更深入、面向开发人员的介绍，请参阅[。](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)

>[!NOTE]
>
>核心组件不可直接供作者使用，[开发团队必须先将它们集成到您的环境中](/help/get-started/using.md)。集成后，可以通过[模板编辑器](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)使它们可用并预配置。

>[!CAUTION]
>
>核心组件[需要AEM 6.4或更高版本](/help/versions.md)，并且需要使用[可编辑的模板](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)。 它们不适用于经典UI，也不适用于静态模板。

## 通过核心组件创作 {#authoring-with-core-components}

作为作者，您将注意到核心组件的几个优势，包括：

* 简单易用，与[页面编辑器](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html)集成良好

* 功能丰富，可适应[WKND参考站点](https://wknd.site)和[组件库](https://adobe.com/go/aem_cmp_library)中所示的许多用例

* [可预配](#pre-configuring-core-components) 置，通过模板编辑器定义哪些功能可供页面作 [者使用](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)

* 围绕[辅助功能指南](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html)构建

* 专为支持[响应式布局](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/responsive-layout.html)而构建

* 专为支持[轻松本地化](localization.md)而构建

当[编辑页面](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html)时，可在页面编辑器侧面板的&#x200B;**组件**&#x200B;选项卡上使用组件。

组件会根据称为组件组的类别进行分组，以便轻松组织和筛选组件。 组件组名称随组件一起显示在[组件浏览器](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html)中，还可以按组过滤以轻松找到正确的组件。

>[!NOTE]
>
>默认情况下，核心组件是隐藏组的一部分，在组件浏览器中不可见。
>
>将所需的组件添加到可见组或自定义它们以供作者使用。

## 预配置核心组件{#pre-configuring-core-components}

配置基础组件是开发人员的工作。 但是，使用核心组件，模板作者现在可以通过模板编辑器配置许多功能。

例如，如果图像组件不应允许从文件系统上传图像，或者文本组件应仅允许某些段落格式，则只需单击一下即可启用或禁用这些功能。

有关详细信息，请参阅[创建页面模板](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)。

### 编辑和设计对话框{#edit-and-design-dialogs}

由于模板作者可以预先配置核心组件以定义允许哪些选项作为模板的一部分，然后页面作者进一步配置以定义实际的页面内容，因此每个组件可以在两个不同的对话框中具有选项。

|  | 描述 | 其控制 | 示例 |
|--- |--- |--- |--- |
| **编辑对话框** | 在为放置的组件进行常规页面编辑期间，**页面作者**&#x200B;可修改的选项 | 组件显示的内容及其最终在页面上的显示方式。 | 设置内容文本的格式，旋转页面上的图像 |
| **设计对话框** | 配置页面模板时，**模板作者**&#x200B;可修改的选项。 | 页面作者在编辑组件时可以使用哪些选项 | 哪些文本格式选项可用，哪些图像就地选项可用 |

### 组件样式{#component-styling}

大多数核心组件的样式可以使用AEM样式系统进行定义。

* 模板作者可以在该组件的“设计”对话框中定义哪些样式可用于特定组件。
* 然后，内容作者可以选择在添加组件和创建内容时应用的样式。

有关更多详细信息，请参阅[样式系统](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/style-system.html)文档。

## 开发人员资源 {#developer-resources}

有关核心组件的技术信息，请参阅[开发核心组件](/help/developing/overview.md)开发人员文档。
