---
title: 自适应Forms核心组件 — 顶部的选项卡
description: 在核心组件上使用或自定义自适应Forms选项卡。
role: Architect, Developer, Admin, User
source-git-commit: d2a6108f17f6e0c6b91bec84893d64a8bd48effd
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 16%

---


# 顶部选项卡 {#tabs-on-top-adaptive-forms-core-component}

自适应表单中的顶部选项卡布局是一种将表单的相关字段和部分组织到单独选项卡中的方法。 每个选项卡都由一个选项卡标签表示，通常位于表单顶部，并包含一组特定的表单字段和部分。 此布局允许用户轻松导航和访问表单的不同部分，从而使其更易于使用，并且不会太难以置信。 当表单包含大量字段和部分时，通常会使用该字段和部分，因此有必要将它们划分为较小且可管理的块。 选项卡还允许用户使用键盘快捷键导航表单，从而帮助残障用户更轻松地访问表单，从而改进辅助功能。

**示例**

![](/help/adaptive-forms/assets/tabs.png)

## 用途 {#reasons-to-use-tab-on-the-top-layout}

在自适应表单中对顶部布局使用选项卡的原因有多种：

* **组织**:可使用选项卡将表单的不同部分组织为不同的类别，从而更便于用户导航和查找所需的信息。

* **空间保护**:选项卡一次只能显示表单的一个部分，有助于节省页面空间。

* **改善了用户体验**:选项卡可让表单更直观、更易于使用，从而改善用户体验。

* **移动设备友好**:制表符可减少滚动并简化字段之间的切换，从而使表单在移动设备上更加友好。

简而言之，选项卡可以使表单更有条理、更高效、更方便用户和更易于访问。

## 版本和兼容性 {#version-and-compatibility}

自适应Forms折叠核心组件是作为适用于AEM 6.5.16.0 Forms或更高版本的核心组件2.0.4的一部分于2023年2月发布的，该组件适用于Cloud Service和核心组件1.1.12或更高版本。 下表显示了所有受支持的版本、AEM兼容性以及指向相应文档的链接：

| 组件版本 | AEM as a Cloud Service | AEM 6.5.16.0 Forms或更高版本 |
|---|---|---|
| v1 | 兼容<br>[版本 2.0.4](/help/adaptive-forms/version.md) 和更高版本 | 与兼容<br>[版本1.1.12](/help/adaptive-forms/version.md) 但低于2.0.0。 |

有关核心组件版本的信息，请参阅[核心组件版本](/help/adaptive-forms/version.md)文档。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技术详细信息 {#technical-details}

可在 [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/tabsontop/v1/tabsontop) 上的技术文档中获得关于自适应表单顶部选项卡核心组件的最新信息。有关开发核心组件的更多信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## “配置”对话框 {#configure-dialog}

您可以使用“配置”对话框轻松地针对访客的热门体验自定义选项卡。 您还可以轻松地在顶部选项上定义选项卡，以提供无缝的用户体验。

## “设计”对话框 {#design-dialog}
