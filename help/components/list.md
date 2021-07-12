---
title: 列表组件
description: 核心组件列表组件允许轻松创建动态和静态列表。
role: Architect, Developer, Admin, User
exl-id: 662ab508-0253-4d28-b95c-8c4cde8173bd
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '979'
ht-degree: 4%

---

# 列表组件{#list-component}

核心组件列表组件允许轻松创建动态和静态列表。

## 使用 {#usage}

列表组件可用于创建子页面的动态列表或任意定义项目的静态列表。 可用列表类型和格式选项可由模板作者在[设计对话框](#design-dialog)中定义。 内容编辑器可以从可用的列表类型中进行选择，以及如何在[编辑对话框](#edit-dialog)中设置列表元素的格式。

## 版本和兼容性 {#version-and-compatibility}

列表组件的当前版本为v2，该版本于2018年1月随核心组件2.0.0版引入，在本文档中进行了描述。

下表详细列出了组件的所有受支持版本、组件版本与之兼容的AEM版本，以及指向以前版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v2 | 兼容 | 兼容 | 兼容 |
| [v1](v1/list-v1.md) | 兼容 | 兼容 | - |

有关核心组件版本和版本的更多信息，请参阅文档[核心组件版本](/help/versions.md)。

## 组件输出示例 {#sample-component-output}

要体验列表组件并查看其配置选项以及HTML和JSON输出的示例，请访问[组件库](https://adobe.com/go/aem_cmp_library_list)。

### 技术详细信息 {#technical-details}

有关列表组件[的最新技术文档，请参阅GitHub](https://adobe.com/go/aem_cmp_tech_list_v2)。

有关开发核心组件的更多详细信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## 编辑对话框 {#edit-dialog}

编辑对话框允许内容作者配置列表和列表项。

### “列表设置”选项卡 {#list-settings-tab}

列表可以采用不同的方式构建。

* [子页面](#child-pages)
* [固定列表](#fixed-list)
* [搜索](#search-options)
* [标记](#tags)

无论如何生成列表，都有可始终配置的[排序和ID选项](#sort-options)。

![列表组件的编辑对话框](/help/assets/list-edit.png)

根据内容作者选择如何构建列表，其他配置选项将发生更改。

#### 子页面 {#child-pages}

列表可以由当前页面或其他页面的子页面构建。

![子页面选项](/help/assets/list-edit-child-pages.png)

* **父页面**
   * 其子页面应列出的页面
   * 留空以使用当前页面

* **子级深**
度应使用层级中下方的层数

#### 固定列表 {#fixed-list}

可以使用固定的项目列表来构建列表。

![固定列表选项](/help/assets/list-edit-fixed.png)

点按或单击&#x200B;**Add**&#x200B;按钮，以在列表中插入新项目。

* 在列表中输入项目的文本，或使用&#x200B;**选择对话框**&#x200B;从AEM中选择项目。
* 使用拖动手柄重新排列列表中的项目。
* 使用垃圾桶图标删除列表中的项目。

#### 搜索 {#search-options}

可以使用搜索AEM内容的结果构建列表。

![搜索列表选项](/help/assets/list-edit-search.png)

* **搜**
索查询将运行全文搜索以生成列表元素的字符串
* **搜索**
应在何处运行搜索
   * 使用&#x200B;**选择对话框**&#x200B;选择AEM中的位置
   * 若留空，则使用当前页面

#### 标记 {#tags}

列表可以使用与特定位置下的特定标记匹配的页面来构建。

![标记列表选项](/help/assets/list-edit-tags.png)

* **父页**
面标记匹配的起始位置
   * 使用&#x200B;**选择对话框**&#x200B;选择AEM中的位置
   * 若留空，则使用当前页面
* ****
标记应匹配的标记
   * 使用&#x200B;**Browse**&#x200B;对话框选择标记
* ****
匹配定义哪些类型的匹配可使页面有资格包含在列表中
   * **任何标记**
   * **所有标记**

#### 排序选项 {#sort-options}

无论您选择如何构建列表，都始终可以定义某些排序选项。

![排序选项](/help/assets/list-edit-sort-options.png)

* **排序**
依据元素的排序方式
   * **标题**
   * **上次修改日期**
* **排序**
顺序应对项目进行排序的顺序
   * **升序**
   * **降序**
* **最大**
项目列表中显示的最大项目数。
   * 留空可返回所有项目。
* **ID**  — 利用此选项，可控制HTML和数据层中组件的唯一标识符 [的唯一标识符](/help/developing/data-layer/overview.md)。
   * 如果留为空白，则会自动为您生成唯一ID，并且可以通过检查生成的页面找到该ID。
   * 如果指定了ID，则作者有责任确保该ID是唯一的。
   * 更改ID可能会影响CSS、JS和数据层跟踪。

### “项目设置”选项卡 {#item-settings-tab}

使用“项目设置”选项卡，可以配置列表元素的格式。

![项目设置](/help/assets/list-edit-items.png)

* **将项**
目关联项目关联到相应页面
* **显示**
描述显示链接项目的描述
* **显示**
链接项目的DateShow修改日期

## “设计”对话框 {#design-dialog}

设计对话框允许模板作者定义允许内容作者使用的列表类型以及可用的项目设置。

### 列表设置 {#list-settings}

在&#x200B;**列表设置**&#x200B;选项卡中，可以定义日期格式以及内容作者可以在组件中使用哪些类型的列表。

![列表组件的设计对话框列表设置](/help/assets/list-design-list-settings.png)

* **日期**
格式用于显示上次修改日期的格式
* **禁用**
子项禁用组件中的子项列表类型
* **禁用**
静态组件中的静态列表类型
* **禁用**
搜索在组件中禁用搜索列表类型
* **禁用**
标记在组件中禁用标记列表类型

### 项目设置 {#item-settings}

在&#x200B;**项目设置**&#x200B;选项卡上，可以为内容作者的组件中应该可用的各个列表元素定义格式选项。

![列出组件的设计对话框项设置](/help/assets/list-design-item-settings.png)

* **链接**
项目编辑对话框中的启用链接 [项目选项](#edit-dialog)
* **显示描**
述编辑对话框中的启用显示 [描述选项](#edit-dialog)
* **显示**
日期编辑对话框中的启用显示 [日期选项](#edit-dialog)

### “样式”选项卡 {#styles-tab}

图像组件支持AEM [样式系统](/help/get-started/authoring.md#component-styling)。

## Adobe客户端数据层 {#data-layer}

列表组件支持[Adobe客户端数据层。](/help/developing/data-layer/overview.md)
