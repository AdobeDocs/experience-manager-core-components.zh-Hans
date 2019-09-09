---
title: 通过核心组件创作
seo-title: 通过核心组件创作
description: 在AEM中，组件是构成所创作页面内容的结构性元素-核心组件提供灵活、功能丰富的创作功能。
seo-description: 在AEM中，组件是构成所创作页面内容的结构性元素-核心组件提供灵活、功能丰富的创作功能。
uuid: 4a54cd4c-3d89-4683-8301-bf1 e634736 e3
content-type: 引用
topic-tags: 创作
discoiquuid: 8751e490-d427-44f2-b767-51935afda988
translation-type: tm+mt
source-git-commit: b6fbef1cff2908533df6573cd3a92266857ba93f

---


# 使用核心组件创作

在 Adobe Experience Manager 中，组件是结构化的元素，用于构成所创作的页面内容。

核心组件提供灵活、功能丰富的创作功能。[We. Retail引用站点](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html) 介绍了核心组件的使用方式。

要体验核心组件并查看其配置选项的示例以及HTML和JSON输出，请访问 [组件库](http://opensource.adobe.com/aem-core-wcm-components/library/content-fragment.html)。

有关在AEM项目上实施核心组件的更深入、面向开发人员的介绍，请参阅 [WKD教程。](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/getting-started.html)

>[!NOTE]
>
>Core Components are not immediately available to authors, the [development team must first integrate them to your environment](using.md). Once integrated, they may be made available and pre-configured via the [template editor](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html).

>[!CAUTION]
>
>核心组件 [需要AEM6.3或更高版本](versions.md) ，并且需要使用 [可编辑的模板](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)。它们不适用于经典UI和静态模板。

## 通过核心组件创作 {#authoring-with-core-components}

作为作者，您将注意核心组件的几个优势，包括：

* Simple to use and well-integrated with the [page editor](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html)

* 功能丰富，可容纳We. Retail以及 [](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html)[组件库中所说明的许多用例](http://opensource.adobe.com/aem-core-wcm-components/library/content-fragment.html)

* [可预配置](#pre-configuring-core-components) ，可定义通过 [模板编辑器可供页面作者使用的功能](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)

* Built around [accessibility guidelines](https://helpx.adobe.com/experience-manager/6-5/managing/using/web-accessibility.html)

* Built to support [responsive layout](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/responsive-layout.html)

* 构建为支持 [轻松定位](localization.md)

Components are available on the **Components** tab of the side panel of the page editor when [editing a page](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html).

组件根据称为组件组的类别进行分组，以轻松组织和筛选组件。组件组名称与 [组件浏览器](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html) 中的组件一起显示，也可以按组筛选，以轻松找到正确的组件。

>[!NOTE]
>
>核心组件是隐藏组的默认部分，在组件浏览器中不可见。
>
>将所需的组件添加到可见用户组，或对其进行自定义以供作者使用。

## 预配置核心组件 {#pre-configuring-core-components}

配置基础组件是开发人员的工作。但是，利用核心组件，模板作者现在可以通过模板编辑器配置许多功能。

例如，如果图像组件不应允许从文件系统上传图像，或者文本组件只应允许某些段落格式，则只需单击一下，即可启用或禁用这些功能。

有关更多信息，请参阅 [创建页面模板](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html) 。

### 编辑和设计对话框 {#edit-and-design-dialogs}

由于核心组件可以由模板作者预先配置来定义允许作为模板一部分的允许的选项，然后由页面作者进一步配置以定义实际页面内容，因此每个组件都可以在两个不同的对话框中具有选项。

|  | 描述 | 其控制功能 | 示例 |
|--- |--- |--- |--- |
| **编辑对话框** | **页面作者** 在为置入的组件进行常规页面编辑期间可以修改的选项 | 组件显示的内容及其最终显示在页面上的方式。 | 格式化内容文本，旋转页面上的图像 |
| **设计对话框** | **模板作者** 在配置页面模板时可以修改的选项。 | 页面作者在编辑组件时可用的选项 | 可用的文本格式选项可用，可使用哪些图像就地选项 |

### 组件样式 {#component-styling}

大多数核心组件的样式都可以使用AEM样式系统进行定义。

* 模板作者可以在该组件的“设计”对话框中定义特定组件可用的样式。
* 然后，内容作者可以选择在添加组件和创建内容时应用哪些样式。

有关详细信息，请参阅 [样式系统](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/style-system.html) 文档。

>[!NOTE]
>
>在AEM6.3中，需要Service Pack(6.3.2.0)或更新版本才能启用样式系统功能。

## 可用核心组件列表 {#list-of-core-components-available}

以下是可用核心组件列表，链接到详细描述其编辑和设计对话框功能的页面。

核心组件的当前版本包含以下组件。

* [折叠](accordion.md)
* [痕迹导航](breadcrumb.md)
* [按钮](button.md)
* [容器](container.md)
* [传送](carousel.md)
* [内容片段](content-fragment-component.md)
* [内容片段列表](content-fragment-list.md)
* [下载](download.md)
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
>某些版本的单独核心组件只能与特定版本的AEM兼容。
>
>有关兼容性信息，请参阅特定组件的各个帮助页面(链接到上一列表)，或参考 [核心组件版本](versions.md) 文档以了解更多信息。

>[!NOTE]
>
>根据您的实例，您可能已经拥有明确按照您的要求开发的自定义组件。这些组件甚至会与此处讨论的某些组件同名。
>表单核心组件与AEM Forms无关。

## 开发人员资源 {#developer-resources}

有关核心组件的技术信息，请参阅 [开发核心组件](developing.md) 开发人员文档。
