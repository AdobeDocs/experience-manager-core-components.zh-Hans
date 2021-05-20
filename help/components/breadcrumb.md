---
title: 痕迹导航组件
description: 核心组件痕迹导航组件是一个导航组件，可根据页面在内容层次结构中的位置生成链接的痕迹导航。
role: Architect, Developer, Administrator, Business Practitioner
exl-id: 19d65b9d-a407-4f50-9c55-8de0f12222ed
source-git-commit: 8ff36ca143af9496f988b1ca65475497181def1d
workflow-type: tm+mt
source-wordcount: '722'
ht-degree: 2%

---

# 痕迹导航组件{#breadcrumb-component}

核心组件痕迹导航组件是一个导航组件，可根据页面在内容层次结构中的位置生成链接的痕迹导航。

## 使用 {#usage}

痕迹导航组件显示当前页面在网站层次结构中的位置，从而允许页面访客从其当前位置导航页面层次结构。 它通常集成到页眉或页脚中。

可用选项（如默认导航级别和显示当前页面或隐藏页面的功能）可由模板作者在[设计对话框](#design-dialog)中定义。 然后，内容编辑器可以选择是否应显示隐藏的页面以及组件在[编辑对话框](#edit-dialog)中的实际导航级别。

## 版本和兼容性{#version-and-compatibility}

痕迹导航组件的当前版本为v2，该版本在2018年1月随核心组件2.0.0版引入，该版本在本文档中进行了描述。

下表详细列出了组件的所有受支持版本、组件版本与之兼容的AEM版本，以及指向以前版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- | --- |--- |---|
| v2 | 兼容 | 兼容 | 兼容 |
| [v1](v1/breadcrumb-v1.md) | 兼容 | 兼容 | - |

有关核心组件版本和版本的更多信息，请参阅文档[核心组件版本](/help/versions.md)。

## 组件输出示例{#sample-component-output}

要体验痕迹导航组件并查看其配置选项以及HTML和JSON输出的示例，请访问[组件库](https://adobe.com/go/aem_cmp_library_breadcrumb)。

>[!NOTE]
>
>从核心组件2.1.0版开始，痕迹导航组件支持[schema.org微数据](https://schema.org/BreadcrumbList)。

## 技术详细信息{#technical-details}

有关痕迹导航组件[的最新技术文档，请参阅GitHub](https://adobe.com/go/aem_cmp_tech_breadcrumb_v2)。

有关开发核心组件的更多详细信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## 编辑对话框{#edit-dialog}

编辑对话框允许内容作者在痕迹导航中禁止隐藏和活动页面以及该页面应显示的层次结构深度。

![痕迹导航组件编辑对话框](/help/assets/breadcrumb-edit.png)

* **导航开始级别**  — 在层次结构中，痕迹导航组件应该开始向下导航到当前页面的位置。例如：

   * 0从`/content`开始
   * 1从`/content/<yourSite>`开始
   * 2从`/content/<yourSite>/<country>`开始

* **显示隐藏的导航项**  — 显示痕迹导航中标记为隐藏的页面（默认情况下，不会显示这些页面）
* **隐藏当前页面**  — 在痕迹导航中禁止当前页面（默认情况下将显示该页面）
* **禁用跟踪**  — 如果层级中的页面是重定向，则将显示重定向页面的名称，而不是目标页面。有关更多信息，请参阅导航组件的[阴影站点结构支持](navigation.md#shadow-structure)。
* **ID**  — 利用此选项，可控制HTML和数据层中组件的唯一标识符 [的唯一标识符](/help/developing/data-layer/overview.md)。
   * 如果留为空白，则会自动为您生成唯一ID，并且可以通过检查生成的页面找到该ID。
   * 如果指定了ID，则作者有责任确保该ID是唯一的。
   * 更改ID可能会影响CSS、JS和数据层跟踪。

## 设计对话框{#design-dialog}

设计对话框允许模板作者定义用于在痕迹导航中禁止隐藏和活动页面的选项的默认值以及应显示的层次结构深度。

### 主选项卡{#main-tab}

![](/help/assets/breadcrumb-design.png)

* **导航开始级别**  — 定义在将痕迹导航组件添加到页面时，痕迹导航组件在层次结构中应开始向下导航到当前页面的位置的默认值。
* **显示隐藏的导航项**  — 定义将痕迹导航组 **件添加** 到页面时显示隐藏的导航项选项的默认值。

   * 它不会为作者启用或禁用选项。 它仅设置默认值。

* **隐藏当前页面** — 定义将痕迹导航组 **件添** 加到页面时“隐藏当前页面”选项的默认值。

   * 它不会为作者启用或禁用选项。 它仅设置默认值。

* **禁用跟踪**  — 定义将痕迹导航组 **件添** 加到页面时禁用阴影选项的默认值。

### 样式选项卡{#styles-tab}

痕迹导航组件支持AEM [样式系统](/help/get-started/authoring.md#component-styling)。

## Adobe客户端数据层{#data-layer}

痕迹导航组件支持[Adobe客户端数据层。](/help/developing/data-layer/overview.md)
