---
title: 痕迹导航组件
description: 核心组件痕迹导航组件是一个导航组件，用于根据页面在内容层次结构中的位置构建链接的痕迹导航。
role: Architect, Developer, Administrator, Business Practitioner
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 2%

---


# 痕迹导航组件{#breadcrumb-component}

核心组件痕迹导航组件是一个导航组件，用于根据页面在内容层次结构中的位置构建链接的痕迹导航。

## 使用 {#usage}

痕迹导航组件显示当前页面在站点层次结构中的位置，允许页面访客从其当前位置导航页面层次结构。 这通常集成到页眉或页脚中。

模板作者在[设计对话框](#design-dialog)中可以定义可用选项，如默认导航级别和显示当前页面或隐藏页面的功能。 然后，内容编辑器可以选择是否显示隐藏页面以及组件在[编辑对话框](#edit-dialog)中的实际导航级别。

## 版本和兼容性{#version-and-compatibility}

Breadcrumb组件的当前版本为v2,2018年1月随核心组件版本2.0.0引入了v2，本文档对此进行了说明。

下表详细列出了组件的所有受支持版本、与组件版本兼容的AEM版本，以及指向先前版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- | --- |--- |---|
| v2 | 兼容 | 兼容 | 兼容 |
| [v1](v1/breadcrumb-v1.md) | 兼容 | 兼容 | - |

有关核心组件版本和版本的详细信息，请参阅文档[核心组件版本](/help/versions.md)。

## 示例组件输出{#sample-component-output}

要体验Breadcrumb组件，并查看其配置选项以及HTML和JSON输出的示例，请访问[组件库](https://adobe.com/go/aem_cmp_library_breadcrumb)。

>[!NOTE]
>
>自核心组件版本2.1.0起，Breadcrumb组件支持[模式.org microdata](https://schema.org/BreadcrumbList)。

## 技术详细信息{#technical-details}

有关Breadcrumb组件[的最新技术文档可在GitHub](https://adobe.com/go/aem_cmp_tech_breadcrumb_v2)上找到。

有关开发核心组件的更多详细信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## 编辑对话框{#edit-dialog}

通过编辑对话框，内容作者可以隐藏痕迹导航中的隐藏和活动页面以及应显示的层次结构中的深度。

![痕迹导航组件编辑对话框](/help/assets/breadcrumb-edit.png)

* **导航开始级**  — 在层次结构中，痕迹导航组件应开始向下浏览到当前页面的位置。例如：

   * `/content`处的0个开始
   * `/content/<yourSite>`处的1个开始
   * `/content/<yourSite>/<country>`处的2个开始

* **显示隐藏的导航项**  — 显示在痕迹导航中标记为隐藏的页面（默认情况下不显示它们）
* **隐藏当前页面**  — 在痕迹导航中隐藏当前页面（默认情况下将显示该页面）
* **禁用遮蔽**  — 如果层次结构中的页面是重定向，则将显示重定向页面的名称而不是目标。有关详细信息，请参阅导航组件的[阴影站点结构支持](navigation.md#shadow-structure)。
* **ID**  — 此选项允许控制HTML和数据层中组件的唯一 [标识符](/help/developing/data-layer/overview.md)。
   * 如果留空，系统会为您自动生成唯一ID，通过检查生成的页面可以找到它。
   * 如果指定了ID，则作者有责任确保它是唯一的。
   * 更改ID可能会影响CSS、JS和数据图层跟踪。

## 设计对话框{#design-dialog}

设计对话框允许模板作者定义用于隐藏痕迹导航中隐藏和活动页面的选项的默认值以及应显示的层次结构中的深度。

### 主选项卡{#main-tab}

![](/help/assets/breadcrumb-design.png)

* **导航开始** 级别 — 定义在将痕迹导航组件添加到页面时，痕迹导航组件应开始在层次结构中向下浏览到当前页面的位置的默认值。
* **显示隐藏的导航项**  — 定义将痕迹导航组 **件添加到** 页面时显示隐藏的导航项选项的默认值。

   * 它不为作者启用或禁用此选项。 它只设置默认值。

* **隐藏当前页面** — 定义将痕迹导航组 **件添** 加到页面时隐藏当前页面选项的默认值。

   * 它不为作者启用或禁用此选项。 它只设置默认值。

* **禁用遮蔽**  — 定义将痕迹导航组 **件添** 加到页面时“禁用阴影”选项的默认值。

### 样式选项卡{#styles-tab}

痕迹导航组件支持AEM [样式系统](/help/get-started/authoring.md#component-styling)。

## Adobe客户端数据层{#data-layer}

痕迹导航组件支持[Adobe客户端数据层。](/help/developing/data-layer/overview.md)
