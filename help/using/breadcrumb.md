---
title: 痕迹导航组件
description: 核心组件痕迹导航组件是一个导航组件，它根据页面在内容层次结构中的位置构建链接的痕迹导航。
translation-type: tm+mt
source-git-commit: 60df01ca9efe59b67bad57610d04496a2cdded9e

---


# 痕迹导航组件{#breadcrumb-component}

核心组件痕迹导航组件是一个导航组件，它根据页面在内容层次结构中的位置构建链接的痕迹导航。

## 使用情况 {#usage}

痕迹导航组件显示当前页面在站点层次结构中的位置，允许页面访客从其当前位置在页面层次结构中导航。 这通常集成到页眉或页脚中。

可用选项（如默认导航级别和显示当前页面或隐藏页面的功能）可由模板作者在设计对话框中定 [义](#design-dialog)。 然后，内容编辑器可以选择是否应显示隐藏的页面以及编辑对话框中组件的实际导 [航级别](#edit-dialog)。

## 版本和兼容性 {#version-and-compatibility}

Breadcrumb组件的当前版本为v2，该版本在2018年1月随核心组件的2.0.0版一起推出，本文档对此进行了说明。

下表详细列出了组件的所有受支持版本、与组件版本兼容的AEM版本，以及指向先前版本的文档的链接。

| 组件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM作为云服务 |
|--- |--- |--- |--- |---|
| v2 | 兼容 | 兼容 | 兼容 | 兼容 |
| [v1](breadcrumb-v1.md) | 兼容 | 兼容 | 兼容 | - |

有关核心组件版本和版本的详细信息，请参阅文档核 [心组件版本](versions.md)。

## 示例组件输出 {#sample-component-output}

要体验Breadcrumb组件，并查看其配置选项以及HTML和JSON输出的示例，请访问组 [件库](https://adobe.com/go/aem_cmp_library_breadcrumb)。

>[!NOTE]
>
>自核心组件版本2.1.0起，Breadcrumb组件支持 [schema.org microdata](https://schema.org/BreadcrumbList)。

## 技术详细信息 {#technical-details}

有关痕迹导航组件的最新技 [术文档可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_breadcrumb_v2)。

有关开发核心组件的更多详细信息，请参阅核 [心组件开发人员文档](developing.md)。

## Edit Dialog {#edit-dialog}

编辑对话框允许内容作者禁止痕迹导航中隐藏和活动的页面，以及应显示的层次结构中的深度。

![](assets/screen_shot_2018-01-12at124250.png)

* **导航开始级别** -在层次结构中，痕迹导航组件应开始向下走到当前页面的位置。 例如，在We.Retail中：

   * 0开始于 `/content`

   * 1开始于 `/content/we-retail`
   * 2开始 `/content/we-retail/<country>`

* **显示隐藏的导航项** -显示痕迹导航中标记为隐藏的页面（默认情况下，不会显示它们）
* **隐藏当前页面**-在痕迹导航中隐藏当前页面（默认情况下将显示该页面）

## 设计对话框 {#design-dialog}

设计对话框允许模板作者定义用于隐藏痕迹导航中隐藏和活动页面的选项的默认值以及应显示的层次结构中的深度。

### 主选项卡 {#main-tab}

![](assets/screen_shot_2018-01-12at124437.png)

* **导航开始级别** -定义在将痕迹导航组件添加到页面时，痕迹导航组件在层次结构中应该开始向下走到当前页面的位置的默认值。
* **显示隐藏的导航项** -定义将痕迹导航组件添加到页面时 **显示隐藏的导航项** ，选项的默认值。

   * 它不为作者启用或禁用此选项。 它只设置默认值。

* **隐藏当前页面**-定义将痕迹导航组件添加到页面时 **** 隐藏当前页面选项的默认值。

   * 它不为作者启用或禁用此选项。 它只设置默认值。

### 样式选项卡 {#styles-tab}

痕迹导航组件支持AEM样 [式系统](authoring.md#component-styling)。