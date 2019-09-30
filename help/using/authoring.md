---
title: 通过核心组件创作
seo-title: 通过核心组件创作
description: 在AEM中，组件是构成创作页面内容的结构元素——核心组件提供灵活且功能丰富的创作功能。
seo-description: 在AEM中，组件是构成创作页面内容的结构元素——核心组件提供灵活且功能丰富的创作功能。
uuid: 4a54cd4c-3d89-4683-8301-bf1e634736e3
content-type: 引用
topic-tags: 创作
discoiquuid: 8751e490-d427-44f2-b767-51935afda988
translation-type: tm+mt
source-git-commit: bf1993085c4cd95121cb6d78be8c52934802b645

---


# 使用核心组件创作

在 Adobe Experience Manager 中，组件是结构化的元素，用于构成所创作的页面内容。

核心组件提供灵活且功能丰富的创作功能。 The [We.Retail reference site](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html) illustrates how the core components can be used.

要体验核心组件并查看其配置选项的示例以及HTML和JSON输出，请访问组 [件库](http://opensource.adobe.com/aem-core-wcm-components/library/content-fragment.html)。

有关在AEM项目上实施核心组件的更深入、面向开发人员的介绍，请参阅 [WKND教程。](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/getting-started.html)

>[!NOTE]
>
>Core Components are not immediately available to authors, the [development team must first integrate them to your environment](using.md). Once integrated, they may be made available and pre-configured via the [template editor](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html).

>[!CAUTION]
>
>核心组 [件需要AEM 6.3或更高版本](versions.md) ，并且需要使用可编 [辑的模板](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)。 它们不使用经典UI，也不使用静态模板。

## 通过核心组件创作 {#authoring-with-core-components}

作为作者，您将注意到核心组件的几个优点，包括：

* Simple to use and well-integrated with the [page editor](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html)

* 功能丰富，可容纳We.Retail和 [组件库中所示的](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html) 许多 [用例](http://opensource.adobe.com/aem-core-wcm-components/library/content-fragment.html)

* [可预配置](#pre-configuring-core-components) ，以通过模板编辑器定义哪些功能可供页面作 [者使用](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)

* Built around [accessibility guidelines](https://helpx.adobe.com/experience-manager/6-5/managing/using/web-accessibility.html)

* Built to support [responsive layout](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/responsive-layout.html)

* 专为支持轻松本地 [化而构建](localization.md)

Components are available on the **Components** tab of the side panel of the page editor when [editing a page](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html).

组件按称为组件组的类别进行分组，以便轻松组织和筛选组件。 组件组名称随组件浏览器中的组件一 [起显示](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html) ，还可以按组进行筛选以轻松找到正确的组件。

>[!NOTE]
>
>核心组件是隐藏组的默认部分，在组件浏览器中不可见。
>
>将所需的组件添加到可见组或自定义这些组件，以供作者使用。

## 预配置核心组件 {#pre-configuring-core-components}

配置基础组件是开发人员的工作。 但是，使用核心组件，模板作者现在可以通过模板编辑器配置许多功能。

例如，如果图像组件不应允许从文件系统上传图像，或者文本组件应仅允许某些段落格式，则只需单击一下即可启用或禁用这些功能。

有关详 [细信息，请参阅创建页面模板](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html) 。

### 编辑和设计对话框 {#edit-and-design-dialogs}

由于模板作者可以预先配置核心组件以定义允许哪些选项作为模板的一部分，然后页面作者进一步配置这些选项以定义实际的页面内容，因此每个组件可以在两个不同的对话框中具有选项。

|  | 描述 | 它控制什么 | 示例 |
|--- |--- |--- |--- |
| **编辑对话框** | 页面作者在 **正常页面编辑** ，对所放置的组件可修改的选项 | 组件显示的内容及其最终在页面上的显示方式。 | 设置内容文本的格式，旋转页面上的图像 |
| **设计对话框** | 配置页面模 **板时** ，模板作者可以修改的选项。 | 页面作者在编辑组件时可以使用哪些选项 | 哪些文本格式选项可用，哪些图像就地选项可用 |

### 组件样式 {#component-styling}

大多数核心组件的样式都可以使用AEM样式系统进行定义。

* 模板作者可以在该组件的“设计”对话框中定义哪些样式可用于特定组件。
* 然后，内容作者可以选择在添加组件和创建内容时应用的样式。

有关更多详细信息，请参 [阅样式系统文](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/style-system.html) 档。

>[!NOTE]
>
>在AEM 6.3中，需要Service Pack 2(6.3.2.0)或更高版本才能启用样式系统功能。

## 可用核心组件列表 {#list-of-core-components-available}

以下是链接到页面的可用核心组件列表，详细描述了这些组件的编辑和设计对话框功能。

核心组件的当前版本具有以下组件。

* [折叠](accordion.md)
* [痕迹导航](breadcrumb.md)
* [按钮](button.md)
* [容器](container.md)
* [传送](carousel.md)
* [内容片段](content-fragment-component.md)
* [内容片段列表](content-fragment-list.md)
* [下载](download.md)
* [嵌入](embed.md)
* [体验片段](experience-fragment.md)
* [表单按钮](form-button.md)
* [表单容器](form-container.md)
* [隐藏的表单](form-hidden.md)
* [表单选项](form-options.md)
* [表单文本](form-text.md)
* [图像](image.md)
* [语言导航](language-navigation.md)
* [列表](list.md)
* [导航](navigation.md)
* [页面](page.md)
* [快速搜索](quick-search.md)
* [分隔符](separator.md)
* [社交媒体共享](sharing.md)
* [选项卡](tabs.md)
* [文本](text.md)
* [标题](title.md)

>[!CAUTION]
>
>某些版本的单个核心组件可能仅与某些版本的AEM兼容。
>
>有关兼容性信息，请参阅特定组件的单个帮助页面（在上一列表中链接到），或参考核心组件版本文档以了解更多信息。 [](versions.md)

>[!NOTE]
>
>根据您的实例，您可能已经拥有明确按照您的要求开发的自定义组件。这些组件甚至会与此处讨论的某些组件同名。
>表单核心组件与AEM Forms无关。

## 开发人员资源 {#developer-resources}

有关核心 [组件的技术信息](developing.md) ，请参阅开发核心组件开发人员文档。
