---
title: 通过核心组件创作
description: 在AEM中，组件是构成创作页面内容的结构元素——核心组件提供灵活且功能丰富的创作功能。
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

---


# 使用核心组件创作

在 Adobe Experience Manager 中，组件是结构化元素，用于构成所创作的页面内容。

核心组件提供灵活且功能丰富的创作功能。 WKND参 [考站点及其说明](https://wknd.site) ，如何使用核心组件来实现丰富的网站体验。

要体验核心组件并查看其配置选项的示例以及HTML和JSON输出，请访问组 [件库](https://adobe.com/go/aem_cmp_library)。

有关在AEM项目上使用 [AEM Project Archetype实施核心组件的更深入、面向开发人员的介绍](/help/developing/archetype/overview.md) ，请查 [看WKND教程。](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)

>[!NOTE]
>
>核心组件不可直接供作者使用，[开发团队必须先将它们集成到您的环境中](/help/get-started/using.md)。Once integrated, they may be made available and pre-configured via the [template editor](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html).

>[!CAUTION]
>
>核心组 [件需要AEM 6.3或更高版本](/help/versions.md) ，并且需要使用可编 [辑的模板](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)。 它们不使用经典UI，也不使用静态模板。

## 通过核心组件创作 {#authoring-with-core-components}

作为作者，您将注意到核心组件的几个优点，包括：

* Simple to use and well-integrated with the [page editor](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html)

* 功能丰富，可适应 [WKND参考站点和组件库中说明的许多](https://wknd.site)[用例](https://adobe.com/go/aem_cmp_library)

* [可预配置](#pre-configuring-core-components) ，以通过模板编辑器定义哪些功能可供页面作 [者使用](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)

* Built around [accessibility guidelines](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html)

* Built to support [responsive layout](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/responsive-layout.html)

* 专为支持轻松本地 [化而构建](localization.md)

Components are available on the **Components** tab of the side panel of the page editor when [editing a page](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html).

组件按称为组件组的类别进行分组，以便轻松组织和筛选组件。 组件组名称随组件浏览器中的组件一 [起显示](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html) ，还可以按组进行筛选以轻松找到正确的组件。

>[!NOTE]
>
>核心组件是隐藏组的默认部分，在组件浏览器中不可见。
>
>将所需的组件添加到可见组或自定义这些组件，以供作者使用。

## 预配置核心组件 {#pre-configuring-core-components}

配置基础组件是开发人员的工作。 但是，使用核心组件，模板作者现在可以通过模板编辑器配置许多功能。

例如，如果图像组件不应允许从文件系统上传图像，或者文本组件应仅允许某些段落格式，则只需单击一下即可启用或禁用这些功能。

有关详 [细信息，请参阅创建页面模板](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html) 。

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

有关更多详细信息，请参 [阅样式系统文](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/style-system.html) 档。

>[!NOTE]
>
>在AEM 6.3中，需要Service Pack 2(6.3.2.0)或更高版本才能启用样式系统功能。

## 可用核心组件列表 {#list-of-core-components-available}

以下是链接到页面的可用核心组件列表，详细描述了这些组件的编辑和设计对话框功能。

当前版本的核心组件具有以下组件。

* [折叠](/help/components/accordion.md)
* [痕迹导航](/help/components/breadcrumb.md)
* [按钮](/help/components/button.md)
* [容器](/help/components/container.md)
* [轮播](/help/components/carousel.md)
* [内容片段](/help/components/content-fragment-component.md)
* [内容片段列表](/help/components/content-fragment-list.md)
* [下载](/help/components/download.md)
* [嵌入](/help/components/embed.md)
* [体验片段](/help/components/experience-fragment.md)
* [表单按钮](/help/components/forms/form-button.md)
* [表单容器](/help/components/forms/form-container.md)
* [隐藏的表单](/help/components/forms/form-hidden.md)
* [表单选项](/help/components/forms/form-options.md)
* [表单文本](/help/components/forms/form-text.md)
* [图像](/help/components/image.md)
* [语言导航](/help/components/language-navigation.md)
* [列表](/help/components/list.md)
* [导航](/help/components/navigation.md)
* [页面](/help/components/page.md)
* [快速搜索](/help/components/quick-search.md)
* [分隔符](/help/components/separator.md)
* [社交媒体共享](/help/components/sharing.md)
* [选项卡](/help/components/tabs.md)
* [文本](/help/components/text.md)
* [标题](/help/components/title.md)

>[!CAUTION]
>
>个别核心组件的某些版本可能仅与特定版本的 AEM 兼容。
>
>有关兼容性信息，请参阅特定组件对应的帮助页面（可在上文中的列表中点击相应链接），或参考[核心组件版本](/help/versions.md)文档以了解更多信息。

>[!NOTE]
>
>根据您的实例，您可能已经拥有明确按照您的要求开发的自定义组件。这些组件甚至会与此处讨论的某些组件同名。
>表单核心组件与AEM Forms无关。

## 开发人员资源 {#developer-resources}

有关核心 [组件的技术信息](/help/developing/overview.md) ，请参阅开发核心组件开发人员文档。
