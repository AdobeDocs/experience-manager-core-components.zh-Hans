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
source-git-commit: 600aefa49d6247c290b8fb9f6acf5548126b3f61

---


# 使用核心组件创作

在 Adobe Experience Manager 中，组件是结构化的元素，用于构成所创作的页面内容。本节介绍核心组件，该组件提供了创建页面的基本内容类型。

核心组件提供灵活、功能丰富的创作功能。[We. Retail引用站点](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html) 介绍了核心组件的使用方式。

>[!NOTE]
>
>核心组件不可立即供作者使用， [开发团队必须首先将其集成到您的环境](using.md)中。集成后，可以通过 [模板编辑器](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html) 或 [在设计模式](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/default-components-designmode.html)下使用和预配置它们。

>[!CAUTION]
>
>核心组件 [需要AEM6.3或更高版本](versions.md) ，并且不能与经典UI一起使用。

## 通过核心组件创作 {#authoring-with-core-components}

要了解核心组件，请查看 [组件库，该库](http://opensource.adobe.com/aem-core-wcm-components/library.html)显示核心组件并提供其用法示例。

作为作者，您将注意核心组件的几个优势，包括：

* 简单易用并与 [页面编辑器紧密集成](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html)
* 功能丰富，可满足We. Retail [中所说明的许多用例](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html)
* [可预先配置](#pre-configuring-core-components) ，以定义哪些功能可供页面作者使用
   * 通过可编辑模板的 [](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)[模板编辑器](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/page-templates-editable.html)
   * 通过 [](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/default-components-designmode.html)[静态模板的设计模式](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/page-templates-static.html)

* 围绕 [辅助功能指导原则构建](https://helpx.adobe.com/experience-manager/6-5/managing/using/web-accessibility.html)

* 支持 [响应式布局](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/responsive-layout.html)

编辑页面时，页面编辑器侧面板 **的组件** 选项卡 [](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html)上会显示组件。

组件根据称为组件组的类别进行分组，以轻松组织和筛选组件。组件组名称与 [组件浏览器](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html) 中的组件一起显示，也可以按组筛选，以轻松找到正确的组件。

>[!NOTE]
>
>核心组件是隐藏组的默认部分，在组件浏览器中不可见。
>
>将所需的组件添加到可见用户组，或对其进行自定义以供作者使用。

## 预配置核心组件 {#pre-configuring-core-components}

配置基础组件是开发人员的工作。但是，利用核心组件，模板作者现在可以通过模板编辑器或设计模式配置许多功能。

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

* [痕迹导航](breadcrumb.md)
* [表单按钮](form-button.md)
* [传送](carousel.md)
* [表单容器](form-container.md)
* [内容片段](content-fragment-component.md)
* [内容片段列表](content-fragment-list.md)
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
* [Teaser](teaser.md)
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
