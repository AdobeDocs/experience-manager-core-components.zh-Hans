---
title: 列表组件
description: 核心组件列表组件允许轻松创建动态和静态列表。
translation-type: tm+mt
source-git-commit: d3ebcea5fa1523c1a986841cd3d1a64e16e85f6d
workflow-type: tm+mt
source-wordcount: '979'
ht-degree: 4%

---


# 列表组件{#list-component}

核心组件列表组件允许轻松创建动态和静态列表。

## 使用 {#usage}

列表组件可用于创建子页面的动态列表或任意定义项的静态列表。 模板作者可以在[设计对话框](#design-dialog)中定义可用列表类型和格式选项。 内容编辑器可以从可用的列表类型中进行选择，并在[编辑对话框](#edit-dialog)中设置列表元素的格式。

## 版本和兼容性{#version-and-compatibility}

列表组件的当前版本为v2,2018年1月随核心组件版本2.0.0引入了v2，本文档对此进行了说明。

下表详细列出了组件的所有受支持版本、与组件版本兼容的AEM版本，以及指向先前版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v2 | 兼容 | 兼容 | 兼容 |
| [v1](v1/list-v1.md) | 兼容 | 兼容 | - |

有关核心组件版本和版本的详细信息，请参阅文档[核心组件版本](/help/versions.md)。

## 示例组件输出{#sample-component-output}

要体验列表组件及其配置选项以及HTML和JSON输出的示例，请访问[组件库](https://adobe.com/go/aem_cmp_library_list)。

### 技术详细信息{#technical-details}

有关列表组件[的最新技术文档可在GitHub](https://adobe.com/go/aem_cmp_tech_list_v2)上找到。

有关开发核心组件的更多详细信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## 编辑对话框{#edit-dialog}

编辑对话框允许内容作者配置列表和列表项。

### 列表设置选项卡{#list-settings-tab}

列表可以采用不同的方式构建。

* [子页面](#child-pages)
* [固定列表](#fixed-list)
* [搜索](#search-options)
* [标记](#tags)

无论如何构建列表，始终可以配置[排序和ID选项](#sort-options)。

![列表组件的编辑对话框](/help/assets/list-edit.png)

根据内容作者选择如何构建列表，其他配置选项将会更改。

#### 子页面 {#child-pages}

列表可以由当前页面或其他页面的子页面构建。

![子页面选项](/help/assets/list-edit-child-pages.png)

* **父页面**
   * 其子页面应生成列表的页面
   * 留空以使用当前页面

* **子级深**
度层次结构中应使用的级别数

#### 固定列表{#fixed-list}

列表可以使用固定的项目列表来构建。

![固定列表选项](/help/assets/list-edit-fixed.png)

点按或单击&#x200B;**添加**&#x200B;按钮，将新项目插入列表。

* 在列表中为项目输入文本，或使用&#x200B;**选择对话框**&#x200B;从AEM中选择项目。
* 使用拖动手柄重新排列列表中的项目。
* 使用垃圾桶图标删除列表中的项目。

#### 搜索 {#search-options}

列表可以使用搜索AEM内容的结果来构建。

![搜索列表选项](/help/assets/list-edit-search.png)

* **搜索**
查询要运行全文搜索以生成列表元素的字符串
* **搜索**
位置应运行搜索
   * 使用&#x200B;**选择对话框**&#x200B;选择AEM中的位置
   * 如果留空，则使用当前页

#### 标记 {#tags}

列表可以使用与特定位置下的特定标记匹配的页面构建。

![标记列表选项](/help/assets/list-edit-tags.png)

* **父页**
面标记匹配应开始的位置
   * 使用&#x200B;**选择对话框**&#x200B;选择AEM中的位置
   * 如果留空，则使用当前页
* **标**
记应匹配哪些标记
   * 使用&#x200B;**浏览**&#x200B;对话框选择标记
* **匹**
配定义哪些类型的匹配应使页面有资格包含在列表中
   * **任何标记**
   * **所有标记**

#### 排序选项{#sort-options}

无论您选择如何构建列表，总是可以定义某些排序选项。

![排序选项](/help/assets/list-edit-sort-options.png)

* **排序**
依据元素的排序方式
   * **标题**
   * **上次修改日期**
* **排序**
顺序对项目进行排序的顺序
   * **升序**
   * **降序**
* **最大**
项目显示在列表中的最大项目数。
   * 留空可返回所有项目。
* **ID**  — 此选项允许控制HTML和数据层中组件的唯一 [标识符](/help/developing/data-layer/overview.md)。
   * 如果留空，系统会为您自动生成唯一ID，通过检查生成的页面可以找到它。
   * 如果指定了ID，则作者有责任确保它是唯一的。
   * 更改ID可能会影响CSS、JS和数据图层跟踪。

### 项目设置选项卡{#item-settings-tab}

使用“项目设置”选项卡，可以配置列表元素的格式。

![项目设置](/help/assets/list-edit-items.png)

* **链接**
项目链接项目到相应页面
* **显示**
说明显示链接项的说明
* **显示**
日期显示链接项的修改日期

## 设计对话框{#design-dialog}

设计对话框允许模板作者定义允许内容作者使用哪些类型的列表以及可用的项目设置。

### 列表设置 {#list-settings}

在&#x200B;**列表设置**&#x200B;选项卡上，可以定义日期格式以及内容作者在组件中可以使用的列表类型。

![列表组件的设计对话框列表设置](/help/assets/list-design-list-settings.png)

* **日期**
格式用于显示上次修改日期的格式
* **禁用**
子项禁用组件中的子列表类型
* **禁用**
静态禁用组件中的静态列表类型
* **禁用**
搜索禁用组件中的搜索列表类型
* **禁用标**
签在组件中禁用标签列表类型

### 项目设置 {#item-settings}

在&#x200B;**项目设置**&#x200B;选项卡上，可以为内容作者的组件中应可用的各个列表元素定义格式选项。

![列表组件的设计对话框项设置](/help/assets/list-design-item-settings.png)

* **链接项**
目编辑对话框中的“启用链 [接项目”选项](#edit-dialog)
* **显示**
说明在编辑对话框中启用“显示 [说明”选项](#edit-dialog)
* **显示日**
期在编辑对话框中启用显示 [日期选项](#edit-dialog)

### 样式选项卡{#styles-tab}

图像组件支持AEM [样式系统](/help/get-started/authoring.md#component-styling)。

## Adobe客户端数据层{#data-layer}

列表组件支持[Adobe客户端数据层。](/help/developing/data-layer/overview.md)
