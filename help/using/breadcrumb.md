---
title: 痕迹导航组件
seo-title: 痕迹导航组件
description: 'null'
seo-description: 核心组件痕迹导航组件是一个导航组件，它根据页面在内容层次结构中的位置构建了链接痕迹导航。
uuid: 13e858d5-24ad-4144-adc4-0fa1 ffd257 c1
contentOwner: 用户
content-type: 引用
topic-tags: 创作
products: SG_ EXPERIENCE MANAGER/CORECOMMPANES-new
discoiquuid: ed237df-08b8-4deb-9881-66a1f0d65ef3
modalsize: 426 x 240
translation-type: tm+mt
source-git-commit: eef608fb06001485aa2c2c0b574af412ed7f15a4

---


# Breadcrumb Component{#breadcrumb-component}

核心组件痕迹导航组件是一个导航组件，它根据页面在内容层次结构中的位置构建了链接痕迹导航。

## 使用情况 {#usage}

痕迹导航组件显示站点层次结构中当前页面的位置，允许页面访问者从其当前位置导航页面层次结构。这通常集成到页眉或页脚中。

Available options, such as the default navigation level and the ability to show the current page or hidden pages, can be defined by the template author in the [design dialog](#design-dialog). The content editor can then choose if hidden pages should be shown or not and the actual navigation level for the component in the [edit dialog](#edit-dialog).

## Version and Compatibility {#version-and-compatibility}

Breadcrumb Component的当前版本是v2，它是在2018年月核心组件发行版中引入的，它在本文档中进行了介绍。

下表详细说明了组件的所有支持版本、组件版本的AEM版本以及以前版本的文档链接。

| 组件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v2 | 兼容 | 兼容 | 兼容 |
| [v1](breadcrumb-v1.md) | 兼容 | 兼容 | 兼容 |

For more information about Core Component versions and releases, see the document [Core Components Versions](versions.md).

## Sample Component Output {#sample-component-output}

To experience the Breadcrumb Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library/breadcrumb/hidden/level-1/level-2/breadcrumb.html).

>[!NOTE]
>
>As of Core Components release 2.1.0, the Breadcrumb Component supports [schema.org microdata](https://schema.org/BreadcrumbList).

## Technical Details {#technical-details}

The latest technical documentation about the Breadcrumb Component [can be found on GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v2/breadcrumb).

Further details about developing Core Components can be found in the [Core Components developer documentation](developing.md).

## Edit Dialog {#edit-dialog}

编辑对话框允许内容作者禁止痕迹导航中的隐藏和活动页面以及纵向应显示的层次结构中的深度。

![](assets/screen_shot_2018-01-12at124250.png)

* **导航开始级别** -在层次结构中，痕迹导航组件应开始向下导航到当前页面。例如We. Retail：

   * 0 starts at `/content`

   * 1 starts at `/content/we-retail`
   * 2 starts at `/content/we-retail/<country>`

* **显示隐藏的导航项目** -在痕迹导航中显示标记为隐藏的页面(默认情况下不显示它们)
* **隐藏当前页面**-禁止痕迹导航中的当前页面(默认情况下将显示它)

## Design Dialog {#design-dialog}

设计对话框允许模板作者定义默认值，这些值用于禁止痕迹导航中隐藏和活动页面的隐藏以及其应显示的层次结构中的深度。

### Main Tab {#main-tab}

![](assets/screen_shot_2018-01-12at124437.png)

* **导航开始级别** -定义在将痕迹导航组件添加到页面时痕迹导航组件应开始向下导航至当前页面的默认值。
* **显示隐藏的导航项目** -定义将痕迹导航组件添加到页面时 **显示隐藏导航项目** 选项的默认值。

   * 它不为作者启用或禁用选项。它只设置默认值。

* **隐藏当前页面**-在将痕迹导航组件添加到页面时，定义 **隐藏当前页面** 选项的默认值。

   * 它不为作者启用或禁用选项。它只设置默认值。

### Styles Tab {#styles-tab}

The Breadcrumb Component supports the AEM [Style System](authoring.md#component-styling).