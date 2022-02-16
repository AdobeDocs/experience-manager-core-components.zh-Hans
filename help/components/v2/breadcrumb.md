---
title: 痕迹导航组件 (v2)
description: 核心组件痕迹导航组件是一个导航组件，它根据页面在内容层级中的位置构建链接的痕迹导航。
role: Architect, Developer, Admin, User
source-git-commit: f8aa86d58ba71ede3c3cd867c45aafff06923325
workflow-type: tm+mt
source-wordcount: '680'
ht-degree: 97%

---


# 痕迹导航组件 (v2) {#breadcrumb-component}

核心组件痕迹导航组件是一个导航组件，它根据页面在内容层级中的位置构建链接的痕迹导航。

## 用途 {#usage}

痕迹导航组件显示当前页面在站点层级中的位置，并允许页面访客从其当前位置导航页面层级。它通常集成到页眉或页脚中。

可用选项（例如，默认导航级别和显示当前页面或隐藏页面的能力）可由模板作者在[“设计”对话框](#design-dialog)中定义。然后，内容编辑者可以在[“编辑”对话框](#edit-dialog)中选择是否显示隐藏的页面以及组件的实际导航级别。

## 版本和兼容性 {#version-and-compatibility}

本文档介绍了痕迹导航组件v2，该组件在2018年1月的核心组件2.0.0版中引入。

>[!CAUTION]
>
>本文档介绍了痕迹导航组件 (v2)。
>
>有关当前版本的痕迹导航组件的详细信息，请参阅[痕迹导航组件](/help/components/breadcrumb.md)文档。

## 示例组件输出 {#sample-component-output}

要体验痕迹导航组件并查看其配置选项示例以及 HTML 和 JSON 输出，请访问[组件库](https://adobe.com/go/aem_cmp_library_breadcrumb_cn)。

>[!NOTE]
>
>截至核心组件发行版本 2.1.0，痕迹导航组件支持 [schema.org 微数据](https://schema.org/BreadcrumbList)。

## 技术详细信息 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_breadcrumb_v2_cn)有关痕迹导航组件的最新技术文档。

在[核心组件开发人员文档](/help/developing/overview.md)中可找到有关开发核心组件的其他详细信息。

## “编辑”对话框 {#edit-dialog}

利用“编辑”对话框，内容作者可以在痕迹导航中禁止显示隐藏的页面和活动的页面以及它应显示的层级中的深度。

![痕迹导航组件“编辑”对话框](/help/assets/breadcrumb-edit.png)

* **导航开始级别** - 层级中的位置，痕迹导航组件从该位置开始向下导航到当前页面。例如：

   * 0 在 `/content` 开始
   * 1 在 `/content/<yourSite>` 开始
   * 2 在 `/content/<yourSite>/<country>` 开始

* **显示隐藏的导航项目** - 在痕迹导航中显示标记为隐藏的页面（默认情况，这些页面不会显示）
* **隐藏当前页面** - 在痕迹导航中禁止显示当前页面（默认情况，该页面将显示）
* **禁用影子** - 如果在层级中的页面是重定向的，则将显示重定向页面的名称而不是目标。有关更多信息，请参阅导航组件的[影子网站结构支持](../v1/navigation.md#shadow-structure)。
* **ID** - 利用此选项，可以控制 HTML 和 [Data Layer](/help/developing/data-layer/overview.md) 中的组件的唯一标识符。
   * 如果留空，系统会自动为您生成一个唯一 ID，可以通过检查结果页面找到该 ID。
   * 如果指定一个 ID，作者有责任确保它是唯一的。
   * 更改此 ID 会对 CSS、JS 和 Data Layer 跟踪产生影响。

## “设计”对话框 {#design-dialog}

利用“设计”对话框，模板作者可以定义选项的默认值，以便在痕迹导航中禁止显示隐藏的页面和活动的页面，以及指定应显示的层级中的深度。

### 主选项卡 {#main-tab}

![](/help/assets/breadcrumb-design.png)

* **导航开始级别** - 定义层级中位置的默认值，在将痕迹导航组件添加到页面后，它会从该位置开始向下导航到当前页面。
* **显示隐藏导航项目** - 在向页面添加痕迹导航组件时，定义&#x200B;**显示隐藏导航项目**&#x200B;选项的默认值。

   * 它不会为作者启用或禁用该选项。它仅设置默认值。

* **隐藏当前页面** - 在向页面添加痕迹导航组件时，定义&#x200B;**隐藏当前页面**&#x200B;选项的默认值。

   * 它不会为作者启用或禁用该选项。它仅设置默认值。

* **禁用影子** - 在向页面添加痕迹导航组件时，定义&#x200B;**禁用影子**&#x200B;选项的默认值。

### “样式”选项卡 {#styles-tab}

痕迹导航组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。

## Adobe Client Data Layer {#data-layer}

痕迹导航组件支持 [Adobe Client Data Layer](/help/developing/data-layer/overview.md)。
