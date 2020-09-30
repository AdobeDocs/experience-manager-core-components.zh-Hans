---
title: 痕迹导航组件
description: 核心组件痕迹导航组件是一个导航组件，它根据页面在内容层次结构中的位置构建链接的痕迹导航。
translation-type: tm+mt
source-git-commit: ff943aeca0333b13e2b9aaf11f316457f001d507
workflow-type: tm+mt
source-wordcount: '709'
ht-degree: 2%

---


# 痕迹导航组件{#breadcrumb-component}

核心组件痕迹导航组件是一个导航组件，它根据页面在内容层次结构中的位置构建链接的痕迹导航。

## 使用 {#usage}

痕迹导航组件显示当前页面在站点层次结构中的位置，允许页面访客从其当前位置导航页面层次结构。 这通常集成到页眉或页脚中。

可用选项（如默认导航级别和显示当前页面或隐藏页面的功能）可由模板作者在设计对话框中 [定义](#design-dialog)。 然后，内容编辑器可以选择是否应显示隐藏页面以及编辑对话框中组件的实际导 [航级别](#edit-dialog)。

## 版本和兼容性 {#version-and-compatibility}

痕迹导航组件的当前版本为v2,2018年1月随核心组件的2.0.0版引入了v2，该版本在本文档中进行了说明。

下表详细列出了组件的所有受支持版本、与组件版本兼容的AEM版本以及指向先前版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM 云服务 |
|--- | --- |--- |---|
| v2 | 兼容 | 兼容 | 兼容 |
| [v1](v1/breadcrumb-v1.md) | 兼容 | 兼容 | - |

有关核心组件版本和版本的详细信息，请参阅文档 [核心组件版本](/help/versions.md)。

## 示例组件输出 {#sample-component-output}

要体验Breadcrumb组件，并查看其配置选项以及HTML和JSON输出的示例，请访问组 [件库](https://adobe.com/go/aem_cmp_library_breadcrumb)。

>[!NOTE]
>
>自核心组件版本2.1.0起，痕迹导航组件支持 [模式.org微数据](https://schema.org/BreadcrumbList)。

## 技术详细信息 {#technical-details}

有关痕迹导航组件的最新技 [术文档可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_breadcrumb_v2)。

有关开发核心组件的更多详细信息，请参阅核 [心组件开发人员文档](/help/developing/overview.md)。

## Edit Dialog {#edit-dialog}

编辑对话框允许内容作者在痕迹导航中隐藏和活动的页面以及它应显示的层次结构深度。

![痕迹导航组件编辑对话框](/help/assets/breadcrumb-edit.png)

* **导航开始级** -在层次结构中，痕迹导航组件应开始向下浏览到当前页面的位置。 例如：

   * 0个开始 `/content`
   * 1个开始，价格 `/content/<yourSite>`
   * 2个开始，价格为 `/content/<yourSite>/<country>`

* **显示隐藏的导航项** -在痕迹导航中显示标记为隐藏的页面（默认情况下，不会显示它们）
* **隐藏当前页** -在痕迹导航中隐藏当前页（默认情况下将显示它）
* **禁用跟踪** -如果层次结构中的页面是重定向，则将显示重定向页面的名称而不是目标。 有关详 [细信息，请参阅](navigation.md#shadow-structure) “导航组件的阴影站点结构支持”。
* **ID** —— 此选项允许控制HTML和数据层中组件的唯一标 [识符](/help/developing/data-layer/overview.md)。
   * 如果留空，则会自动为您生成唯一ID，并可通过检查生成的页面找到该ID。
   * 如果指定了ID，则作者有责任确保它是唯一的。
   * 更改ID可能会影响CSS、JS和数据层跟踪。

## 设计对话框 {#design-dialog}

设计对话框允许模板作者定义用于在痕迹导航中隐藏和活动页面的选项的默认值以及应显示的层次结构深度。

### 主选项卡 {#main-tab}

![](/help/assets/breadcrumb-design.png)

* **导航开始级** -定义在将痕迹导航组件添加到页面时，痕迹导航组件在层次结构中应开始向下走到当前页面的位置的默认值。
* **显示隐藏的导航项** -定义将痕迹导航组 **件添加到页面时显示隐藏的导** 航项，选项的默认值。

   * 它不为作者启用或禁用该选项。 它只设置默认值。

* **隐藏当前页面**-定义将痕迹导航组 **件添加到页面时** ，隐藏当前页面选项的默认值。

   * 它不为作者启用或禁用该选项。 它只设置默认值。

* **禁用跟踪** -定义将痕迹导航组 **件添加到页** 面时，“禁用跟踪”选项的默认值。

### 样式选项卡 {#styles-tab}

痕迹导航组件支持AEM [样式系统](/help/get-started/authoring.md#component-styling)。
