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
source-git-commit: 1243d6cc1b0b015ee2f37ae89d0e2e42d366cc02

---


# 列表组件{#list-component}

核心组件列表组件允许轻松创建动态和静态列表。

## 使用情况 {#usage}

列表组件可用于创建例如子页面的动态列表或任意定义项目的静态列表。可用列表类型和格式选项可由设计对话框中的模板作者 [定义](#design-dialog)。内容编辑器可以从可用的列表类型中进行选择，以及如何格式化 [编辑对话框](#edit-dialog)中的列表元素。

## 版本和兼容性 {#version-and-compatibility}

列表组件的当前版本为v2，该版本是在2018年月核心组件中引入的，它是在核心组件中引入的，它在文档中进行了介绍。

下表详细说明了组件的所有支持版本、组件版本的AEM版本以及以前版本的文档链接。

| 组件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v2 | 兼容 | 兼容 | 兼容 |
| [v1](list-v1.md) | 兼容 | 兼容 | 兼容 |

有关核心组件版本和版本的更多信息，请参阅文档 [核心组件版本](versions.md)。

## 示例组件输出 {#sample-component-output}

以下示例取自 [We. Retail](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html)。

### 屏幕快照 {#screenshot}

![](assets/screen_shot_2018-01-12at105924.png)

### 组件库

要体验列表组件以及查看其配置选项的示例以及HTML和JSON输出，请访问 [组件库](http://opensource.adobe.com/aem-core-wcm-components/library/list.html)。

### 技术详细信息 {#technical-details}

有关List组件 [的最新技术文档可在GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/list/v2/list)上找到。

有关开发核心组件的更多详细信息，请参阅 [核心组件开发人员文档](developing.md)。

## 编辑对话框 {#edit-dialog}

编辑对话框允许内容作者配置列表和列表项。

### 列表设置选项卡 {#list-settings-tab}

列表可以以不同的方式构建。

* [子页面](#child-pages)
* [固定列表](#fixed-list)
* [搜索](#search-options)
* [标记](#tags)

无论列表是如何构建的，都有 [可以始终配置的“排序选项](#sort-options) ”。

![](assets/chlimage_1-38.png)

根据内容作者选择构建列表的方式，其他配置选项将会更改。

#### 子页面 {#child-pages}

可以构建当前页面或其他页面的子页面的列表。

![](assets/chlimage_1-39.png)

* **父页面**
   * 子页面应制作列表的页面
   * 留空可使用当前页面

* **子级深度**应使用层次结构中的级别级别

#### 固定列表 {#fixed-list}

可以使用项目的固定列表构建列表。

![](assets/chlimage_1-40.png)

点按或单击 **添加** 按钮以将新项目插入列表。

* 在列表中输入项目的文本，或使用 **选择对话框** 从AEM中选择项目。
* 使用拖动手柄重新排列列表中的项目。
* 使用垃圾桶图标可删除列表中的项目。

#### 搜索 {#search-options}

可以使用搜索AEM内容的搜索结果构建列表。

![](assets/chlimage_1-41.png)

* **搜索查询**将运行全文搜索的字符串，以生成列表元素
* **在应运行搜索的**位置搜索
   * 使用 **选择对话框** 在AEM中选择位置
   * 如果留空，请使用当前页面

#### 标记 {#tags}

可以使用与特定位置匹配特定标记的页面构建列表。

![](assets/chlimage_1-42.png)

* **父页面**应开始标记的父页面
   * 使用 **选择对话框** 在AEM中选择位置
   * 如果留空，请使用当前页面
* **标记**应匹配的标记
   * 使用“ **浏览** ”对话框选择标记
* **匹配**定义应确定要包含在列表中的页面的类型。
   * **任何标记**
   * **所有标记**

#### 排序选项 {#sort-options}

无论您选择如何构建列表，都有某些可始终定义的排序选项。

![](assets/chlimage_1-43.png)

* **排序依据**如何订购元素
   * **标题**
   * **上次修改日期**
* **排序顺序**应订购项目的顺序
   * **升序**
   * **降序**
* **最大项目**列表中显示的项目最大数量。
   * 留空可返回所有项目。

### “项目设置”选项卡 {#item-settings-tab}

使用“项目设置”选项卡，可以配置列表元素的格式。

![](assets/chlimage_1-44.png)

* **链接项目**将项目链接到相应页面
* **显示说明**显示链接项的说明
* **显示日期**显示链接项目的修改日期

## 设计对话框 {#design-dialog}

设计对话框允许模板作者定义应允许内容作者以及可用项目设置的列表类型。

### 列表设置 {#list-settings}

在 **“列表设置** ”选项卡上，可以定义日期格式以及组件中应提供给内容作者的列表类型。

![](assets/chlimage_1-45.png)

* **用于显示上次修改日期的日期格式**格式
* **禁用子项**禁用组件中的子级列表类型
* **禁用静态**禁用组件中的静态列表类型
* **禁用搜索**禁用组件中的搜索列表类型
* **禁用标记**禁用组件中的标记列表类型

### 项目设置 {#item-settings}

在 **“项目设置** ”选项卡上，可以定义内容作者组件中应提供的各个列表元素的格式选项。

![](assets/chlimage_1-46.png)

* **在编辑对话框中链接项目**启用链接 [项目选项](#edit-dialog)
* **在编辑对话框中显示描述**的启用说明 [选项](#edit-dialog)
* **在编辑对话框中显示日期**启用显示 [日期选项](#edit-dialog)

### 样式选项卡 {#styles-tab}

图像组件支持AEM [Style System](authoring.md#component-styling)。