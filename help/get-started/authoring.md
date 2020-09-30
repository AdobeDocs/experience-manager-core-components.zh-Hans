---
title: 通过核心组件创作
description: 在AEM中，组件是构成所创作页面内容的结构元素——核心组件优惠灵活且功能丰富的创作功能。
translation-type: tm+mt
source-git-commit: 4813748bcfa83ce7c73e81d4e4d445ecc8215d26
workflow-type: tm+mt
source-wordcount: '764'
ht-degree: 7%

---


# 使用核心组件进行创作

在 Adobe Experience Manager 中，组件是结构化元素，用于构成所创作的页面内容。

核心组件优惠灵活且功能丰富的创作功能。 WKND [参考站点](https://wknd.site) 及其说明如何使用核心组件来实现丰富的网站体验。

要体验核心组件并查看其配置选项以及HTML和JSON输出的示例，请访问组 [件库](https://adobe.com/go/aem_cmp_library)。

有关在AEM项目上使用AEM项目原型实施核心组件的更深入、面向开发人员的介绍， [请查看WKND教](/help/developing/archetype/overview.md) 程 [中的相关内容。](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)

>[!NOTE]
>
>核心组件不可直接供作者使用，[开发团队必须先将它们集成到您的环境中](/help/get-started/using.md)。Once integrated, they may be made available and pre-configured via the [template editor](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html).

>[!CAUTION]
>
>核心组 [件需要AEM 6.4或更高](/help/versions.md) ，并且需要使用可编 [辑的模板](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)。 它们不适用于经典UI，也不适用于静态模板。

## 通过核心组件创作 {#authoring-with-core-components}

作为作者，您将注意到核心组件的几个优势，包括：

* Simple to use and well-integrated with the [page editor](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html)

* 功能丰富，可容纳WKND参考站点和组 [件库中所](https://wknd.site) 示的许多 [用例](https://adobe.com/go/aem_cmp_library)

* [可预先配置](#pre-configuring-core-components) ，以通过模板编辑器定义页面作者可使用 [的功能](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)

* Built around [accessibility guidelines](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html)

* Built to support [responsive layout](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/responsive-layout.html)

* 专为支持轻松 [本地化而构建](localization.md)

Components are available on the **Components** tab of the side panel of the page editor when [editing a page](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html).

组件根据称为组件组的类别进行分组，以便轻松组织和筛选组件。 组件组名称随组件浏览器中的组 [件一起显](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html) 示，还可以按组进行筛选以轻松找到正确的组件。

>[!NOTE]
>
>默认情况下，核心组件是隐藏组的一部分，在组件浏览器中不可见。
>
>将所需的组件添加到可见组或自定义它们，以供作者使用。

## 预配置核心组件 {#pre-configuring-core-components}

配置基础组件是开发人员的工作。 但是，在核心组件中，模板作者现在可以通过模板编辑器配置许多功能。

例如，如果图像组件不应允许从文件系统上传图像，或者文本组件应仅允许某些段落格式，则只需单击一下即可启用或禁用这些功能。

有关详 [细信息，请参](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html) 阅创建页面模板。

### 编辑和设计对话框 {#edit-and-design-dialogs}

由于模板作者可以预先配置核心组件以定义允许哪些选项作为模板的一部分，然后页面作者进一步配置以定义实际的页面内容，因此每个组件可以在两个不同的对话框中具有选项。

|  | 描述 | 它控制什么 | 示例 |
|--- |--- |--- |--- |
| **编辑对话框** | 页面作者 **在正常** 、已放置组件的页面编辑过程中可以修改的选项 | 组件显示的内容及其最终在页面上的显示方式。 | 设置内容文本的格式，旋转页面上的图像 |
| **设计对话框** | 配置页面模 **板时** ，模板作者可以修改的选项。 | 页面作者在编辑组件时可以使用哪些选项 | 有哪些文本格式选项可用，哪些图像就地选项可用 |

### 组件样式 {#component-styling}

大多数核心组件的样式都可以使用AEM样式系统进行定义。

* 模板作者可以在该组件的“设计”对话框中定义哪些样式可用于特定组件。
* 然后，内容作者可以选择在添加组件和创建内容时应用的样式。

有关更多详细信息，请 [参阅样式系](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/style-system.html) 统文档。

## 开发人员资源 {#developer-resources}

有关核心 [组件的技术信息](/help/developing/overview.md) ，请参阅开发核心组件开发人员文档。
