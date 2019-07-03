---
title: 导航组件
seo-title: 导航组件
description: 'null'
seo-description: 导航组件允许用户轻松导航全球化的站点结构。
uuid: 616c03fb-39b3-402a-b990-f56 c87 bc6 df4
content-type: 引用
topic-tags: 创作
products: SG_ EXPERIENCE MANAGER/CORECOMMPANES-new
discoiquuid: da8d67d7-b65 e-4041-bc0 e-e998 f24 a68 f9
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


# Navigation Component{#navigation-component}

导航组件允许用户轻松导航全球化的站点结构。

## 使用情况 {#usage}

导航组件允许通过Blueprint的Live Copy、语言母版的语言副本或简单的页面树构建任何导航层次结构。它允许页面用户轻松导航站点结构。

[编辑对话框](#edit-dialog) 允许内容作者定义导航根页面以及导航深度。[设计对话框](#design-dialog) 允许模板作者为导航根和深度定义默认值。

## Version and Compatibility {#version-and-compatibility}

导航组件的当前版本是v1，它是在2018年月版的核心组件中引入的，它在文档中进行了介绍。

下表详细说明了组件的所有支持版本、组件版本的AEM版本以及以前版本的文档链接。

| 组件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v1 | 兼容 | 兼容 | 兼容 |


For more information about Core Component versions and releases, see the document [Core Components Versions](versions.md).

## Sample Component Output {#sample-component-output}

To experience the Navigation Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library/navigation.html).

## Technical Details {#technical-details}

The latest technical documentation about the Navigation Component [can be found on GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/navigation/v1/navigation).

Further details about developing Core Components can be found in the [Core Components developer documentation](developing.md).

>[!NOTE]
>
>As of Core Components release 2.1.0, the Navigation Component supports [schema.org microdata](https://schema.org).

## Edit Dialog {#edit-dialog}

在编辑对话框中，内容作者可以定义导航的根页面和导航结构的深度。

![](assets/screen_shot_2018-04-03at112055.png)

* **导航根** 根页面，用于生成导航树。
* **排除导航根目录** 排除生成树中的导航根，仅包括其后代。
* **收集所有子页面** 收集导航根后代的所有页面。
* **导航结构深度** 定义组件应相对于导航根显示的导航树级别的级别(仅当未选择所有子页面 **** 时才可用)。

## Design Dialog {#design-dialog}

设计对话框允许模板作者为内容作者设置导航根页面和导航深度的默认值。

### Properties Tab {#properties-tab}

![](assets/screen_shot_2018-04-03at112357.png)

* **导航根** 导航结构根页面的默认值，用于生成导航树并在内容作者将组件添加到页面时默认使用该值。
* **不包括导航根** 选项用于排除生成树中导航根的选项的默认值。
* **收集所有子页面** 此选项的默认值用于收集导航根的所有后代的所有页面。
* **导航结构深度** 导航结构深度的默认值。

### Styles Tab {#styles-tab}

The Navigation Component supports the AEM [Style System](authoring.md#component-styling).