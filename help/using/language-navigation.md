---
title: 语言导航组件
seo-title: 语言导航组件
description: 'null'
seo-description: 语言导航组件提供站点的语言/国家/地区导航，以便访客能够在其他区域设置中导航到同一页面。
uuid: ce736458-9cdf-4bc2-b90 f-9c5 a62 fe1 ca0
content-type: 引用
topic-tags: 创作
products: SG_ EXPERIENCE MANAGER/CORECOMMPANES-new
discoiquuid: 8f232eb0-65d5-4075-868-75f1366882c8
disttype: dist5
gnavtheme: 浅色
groupsectionnavitems: 否
hidemerchandisingbar: 继承
hidepromocomponent: 继承
modalsize: 426 x 240
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: eef608fb06001485aa2c2c0b574af412ed7f15a4

---


# Language Navigation Component{#language-navigation-component}

语言导航组件提供站点的语言/国家/地区导航，以便访客能够在不同区域设置导航到同一页面。

## 使用情况 {#usage}

通常，网站以多种语言提供给不同地区。语言导航组件允许访客以不同语言/区域设置查看同一页面。

[编辑对话框](#edit-dialog) 允许全局站点导航根目录的定义以及导航应转到的结构。Using the [design dialog](#design-dialog), the template author can set the default values for the same options.

## Version and Compatibility {#version-and-compatibility}

语言导航组件的当前版本是v1，它是在2018年月核心组件发行版中引入的，它在本文档中进行了介绍。

下表详细说明了组件的所有支持版本、组件版本的AEM版本以及以前版本的文档链接。

| 组件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v1 | 兼容 | 兼容 | 兼容 |


For more information about Core Component versions and releases, see the document [Core Components Versions](versions.md).

## Sample Component Output {#sample-component-output}

To experience the Language Navigation Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library/language-navigation/language-structure/us/en/language-navigation.html).

## Technical Details {#technical-details}

The latest technical documentation about the Language Navigation Component [can be found on GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/languagenavigation/v1/languagenavigation).

Further details about developing Core Components can be found in the [Core Components developer documentation](developing.md).

## Edit Dialog {#edit-dialog}

编辑对话框允许全局站点导航根目录的定义以及导航应转到的结构。

![](assets/screen_shot_2018-01-12at133353.png)

* **导航根** 定义导航结构的根页面。
   * Use the **Open Selection Dialog** button to easily navigate the content structure and select the root.
* **语言结构相对于** 导航根目录的全局语言结构深度。

## Design Dialog {#design-dialog}

使用设计对话框，模板作者可以为编辑对话框中可用的相同选项设置默认值。

### Properties Tab {#properties-tab}

![](assets/screen_shot_2018-01-12at133642.png)

* **导航根内容作者将语言切换程序组件放置到内容页面时导航根** 的默认值
* **语言结构深度** 当内容作者将语言切换程序组件放置到内容页面时语言结构深度的默认值

### Styles Tab {#styles-tab}

The Language Navigation Component supports the AEM [Style System](authoring.md#component-styling).