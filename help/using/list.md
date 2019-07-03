---
title: 列表组件
seo-title: 列表组件
description: 'null'
seo-description: 核心组件列表组件允许轻松创建动态和静态列表。
uuid: 50a572e8-b444-4f7 d-82bc-5a93 eb4 be95
contentOwner: 用户
content-type: 引用
topic-tags: 创作
products: SG_ EXPERIENCE MANAGER/CORECOMMPANES-new
discoiquuid: 89053323-621-46ed-896a-31a42c55282e
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


# 列表组件{#list-component}

核心组件列表组件允许轻松创建动态和静态列表。

## 使用情况 {#usage}

列表组件可用于创建例如子页面的动态列表或任意定义项目的静态列表。The type of lists available and formatting options can be defined by the template author in the [design dialog](#design-dialog). The content editor can select from available list types and how to format the list elements in the [edit dialog](#edit-dialog).

## Version and Compatibility {#version-and-compatibility}

列表组件的当前版本为v2，该版本是在2018年月核心组件中引入的，它是在核心组件中引入的，它在文档中进行了介绍。

下表详细说明了组件的所有支持版本、组件版本的AEM版本以及以前版本的文档链接。

| 组件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v2 | 兼容 | 兼容 | 兼容 |
| [v1](list-v1.md) | 兼容 | 兼容 | 兼容 |

For more information about Core Component versions and releases, see the document [Core Components Versions](versions.md).

## Sample Component Output {#sample-component-output}

To experience the List Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library/list.html).

### Technical Details {#technical-details}

The latest technical documentation about the List Component [can be found on GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/list/v2/list).

Further details about developing Core Components can be found in the [Core Components developer documentation](developing.md).

## Edit Dialog {#edit-dialog}

编辑对话框允许内容作者配置列表和列表项。

### List Settings Tab {#list-settings-tab}

列表可以以不同的方式构建。

* [子页面](#child-pages)
* [固定列表](#fixed-list)
* [搜索](#search-options)
* [标记](#tags)

Regardless of how the list is built, there are [Sort Options](#sort-options) that can always be configured.

![](assets/chlimage_1-38.png)

根据内容作者选择构建列表的方式，其他配置选项将会更改。

#### 子页面 {#child-pages}

可以构建当前页面或其他页面的子页面的列表。

![](assets/chlimage_1-39.png)

* **父页面**
   * 子页面应制作列表的页面
   * 留空可使用当前页面

* **子级深度** 应使用层次结构中的级别级别

#### Fixed List {#fixed-list}

可以使用项目的固定列表构建列表。

![](assets/chlimage_1-40.png)

Tap or click the **Add** button to inset a new item to the list.

* Enter text for the item in the list or use the **Selection Dialog** to choose an item from AEM.
* 使用拖动手柄重新排列列表中的项目。
* 使用垃圾桶图标可删除列表中的项目。

#### 搜索 {#search-options}

可以使用搜索AEM内容的搜索结果构建列表。

![](assets/chlimage_1-41.png)

* **搜索查询** 将运行全文搜索的字符串，以生成列表元素
* **在应运行搜索的** 位置搜索
   * Use the **Selection Dialog** to choose the location in AEM
   * 如果留空，请使用当前页面

#### 标记 {#tags}

可以使用与特定位置匹配特定标记的页面构建列表。

![](assets/chlimage_1-42.png)

* **父页面** 应开始标记的父页面
   * Use the **Selection Dialog** to choose the location in AEM
   * 如果留空，请使用当前页面
* **标记** 应匹配的标记
   * Use the **Browse** dialog to select the tags
* **匹配** 定义应确定要包含在列表中的页面的类型。
   * **任何标记**
   * **所有标记**

#### Sort Options {#sort-options}

无论您选择如何构建列表，都有某些可始终定义的排序选项。

![](assets/chlimage_1-43.png)

* **排序依据** 如何订购元素
   * **标题**
   * **上次修改日期**
* **排序顺序** 应订购项目的顺序
   * **升序**
   * **降序**
* **最大项目** 列表中显示的项目最大数量。
   * 留空可返回所有项目。

### Item Settings Tab {#item-settings-tab}

使用“项目设置”选项卡，可以配置列表元素的格式。

![](assets/chlimage_1-44.png)

* **链接项目** 将项目链接到相应页面
* **显示说明** 显示链接项的说明
* **显示日期** 显示链接项目的修改日期

## Design Dialog {#design-dialog}

设计对话框允许模板作者定义应允许内容作者以及可用项目设置的列表类型。

### 列表设置 {#list-settings}

On the **List Settings** tab, the date format can be defined as well as what type of lists should be available in the component to the content authors.

![](assets/chlimage_1-45.png)

* **用于显示上次修改日期的日期格式** 格式
* **禁用子项** 禁用组件中的子级列表类型
* **禁用静态** 禁用组件中的静态列表类型
* **禁用搜索** 禁用组件中的搜索列表类型
* **禁用标记** 禁用组件中的标记列表类型

### 项目设置 {#item-settings}

On the **Item Settings** tab, the formatting options for the individual list elements that should be available in the component for the content authors can be defined.

![](assets/chlimage_1-46.png)

* **在编辑对话框中链接项目** 启用链接 [项目选项](#edit-dialog)
* **在编辑对话框中显示描述** 的启用说明 [选项](#edit-dialog)
* **在编辑对话框中显示日期** 启用显示 [日期选项](#edit-dialog)

### Styles Tab {#styles-tab}

The Image Component supports the AEM [Style System](authoring.md#component-styling).