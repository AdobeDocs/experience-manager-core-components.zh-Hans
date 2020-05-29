---
title: 列表组件
description: 核心组件列表组件允许轻松创建动态和静态列表。
translation-type: tm+mt
source-git-commit: c186e9ec3944d785ab0376769cf7f2307049a809
workflow-type: tm+mt
source-wordcount: '968'
ht-degree: 4%

---


# 列表组件{#list-component}

核心组件列表组件允许轻松创建动态和静态列表。

## 使用 {#usage}

列表组件可用于创建子页面的动态列表或任意定义项的静态列表。 可用列表类型和格式选项可由模板作者在设计对话框中 [定义](#design-dialog)。 内容编辑器可以从可用的列表类型中进行选择，以及如何在编辑对话框中设置列表 [元素的格式](#edit-dialog)。

## 版本和兼容性 {#version-and-compatibility}

列表组件的当前版本为v2,2018年1月随核心组件的2.0.0版一起推出v2，该版本在本文档中进行了说明。

下表详细列出了组件的所有受支持版本、与组件版本兼容的AEM版本以及指向先前版本文档的链接。

| 组件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM 云服务 |
|--- |--- |--- |--- |---|
| v2 | - | 兼容 | 兼容 | 兼容 |
| [v1](v1/list-v1.md) | 兼容 | 兼容 | 兼容 | - |

有关核心组件版本和版本的详细信息，请参阅文档 [核心组件版本](/help/versions.md)。

## 示例组件输出 {#sample-component-output}

要体验列表组件，并查看其配置选项以及HTML和JSON输出的示例，请访问组 [件库](https://adobe.com/go/aem_cmp_library_list)。

### 技术详细信息 {#technical-details}

有关列表组件的最新技 [术文档可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_list_v2)。

有关开发核心组件的更多详细信息，请参阅核 [心组件开发人员文档](/help/developing/overview.md)。

## Edit Dialog {#edit-dialog}

编辑对话框允许内容作者配置列表和列表项。

### 列表设置选项卡 {#list-settings-tab}

列表可以采用不同的方式构建。

* [子页面](#child-pages)
* [固定列表](#fixed-list)
* [搜索](#search-options)
* [标记](#tags)

无论如何构建列表，总 [是可以配置排序](#sort-options) 和ID选项。

![列表组件的编辑对话框](/help/assets/list-edit.png)

根据内容作者选择如何构建列表，其他配置选项将发生更改。

#### 子页面 {#child-pages}

列表可以由当前页面或其他页面的子页面构建。

![子页面选项](/help/assets/list-edit-child-pages.png)

* **父页面**
   * 子页面应生成列表的页面
   * 留空以使用当前页面

* **子级深**&#x200B;度层次中应使用多少级

#### Fixed List {#fixed-list}

列表可以使用固定列表项来构建。

![修复的列表选项](/help/assets/list-edit-fixed.png)

点按或单击 **添加** 按钮，将新项目插入列表。

* 在列表中为项目输入文本，或使 **用选择** 对话框从AEM中选择项目。
* 使用拖动手柄重新排列列表中的项目。
* 使用垃圾桶图标删除列表中的项目。

#### 搜索 {#search-options}

列表可以使用AEM内容搜索结果构建。

![搜索列表选项](/help/assets/list-edit-search.png)

* **搜索**&#x200B;查询将运行全文搜索以生成列表元素的字符串
* **搜索**&#x200B;应在何处运行搜索
   * 使用选 **择对话框** ，在AEM中选择位置
   * 如果留空，则使用当前页面

#### 标记 {#tags}

列表可以使用与特定位置下的特定标记匹配的页面构建。

![标记列表选项](/help/assets/list-edit-tags.png)

* **父页面**&#x200B;标记匹配的位置应开始
   * 使用选 **择对话框** ，在AEM中选择位置
   * 如果留空，则使用当前页面
* **标记**&#x200B;应匹配哪些标记
   * 使用“浏 **览** ”对话框选择标记
* **匹**&#x200B;配定义哪些类型的匹配应使页面有资格包含在列表中
   * **任何标记**
   * **所有标记**

#### 排序选项 {#sort-options}

无论选择如何构建列表，总是可以定义某些排序选项。

![排序选项](/help/assets/list-edit-sort-options.png)

* **排序依**&#x200B;据元素的排序方式
   * **标题**
   * **上次修改日期**
* **排序**&#x200B;项目的排序顺序
   * **升序**
   * **降序**
* **最大项**&#x200B;目列表中显示的最大项目数。
   * 留空将返回所有项目。
* **ID** —— 此选项允许控制HTML和数据层中组件的唯一标 [识符](/help/developing/data-layer/overview.md)。
   * 如果留空，则会自动为您生成唯一ID，并可通过检查生成的页面找到该ID。
   * 如果指定了ID，则作者有责任确保它是唯一的。
   * 更改ID可能会影响CSS、JS和数据层跟踪。

### 项目设置选项卡 {#item-settings-tab}

使用“项目设置”选项卡，可以配置列表元素的格式。

![项目设置](/help/assets/list-edit-items.png)

* **链接项目**&#x200B;将项目链接到相应页面
* **显示说**&#x200B;明显示链接项的说明
* **显示日期**&#x200B;显示链接项的修改日期

## 设计对话框 {#design-dialog}

设计对话框允许模板作者定义内容作者应允许的列表类型以及可用的项目设置。

### 列表设置 {#list-settings}

在“ **列表设置** ”选项卡上，可以定义列表格式以及内容作者在组件中可以使用的类型。

![列表组件的设计对话框列表设置](/help/assets/list-design-list-settings.png)

* **日期格**&#x200B;式用于显示上次修改日期的格式
* **禁用子项**&#x200B;禁用组件中的子列表类型
* **禁用静态**&#x200B;禁用组件中的静态列表类型
* **禁用搜索**&#x200B;在组件中禁用搜索列表类型
* **禁用标记**&#x200B;在组件中禁用标记列表类型

### 项目设置 {#item-settings}

在“项 **目设置** ”选项卡上，可以定义内容作者在组件中应可用的各个列表元素的格式选项。

![列表组件的设计对话框项设置](/help/assets/list-design-item-settings.png)

* **链接项目**&#x200B;编辑对话框中的“启用链接 [项目”选项](#edit-dialog)
* **在编辑对话**&#x200B;框中显示说明启用显示 [说明选项](#edit-dialog)
* **编辑对话框**&#x200B;中的显示日期启用显示 [日期选项](#edit-dialog)

### 样式选项卡 {#styles-tab}

图像组件支持AEM样 [式系统](/help/get-started/authoring.md#component-styling)。
