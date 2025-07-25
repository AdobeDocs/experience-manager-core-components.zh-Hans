---
title: 列表组件
description: 利用核心组件列表组件，可以轻松地创建动态和静态列表。
role: Architect, Developer, Admin, User
exl-id: 662ab508-0253-4d28-b95c-8c4cde8173bd
source-git-commit: dd30def59a8f037864da875ef4c831b11f766e57
workflow-type: ht
source-wordcount: '1204'
ht-degree: 100%

---


# 列表组件{#list-component}

利用核心组件列表组件，可以轻松地创建动态和静态列表。

{{traditional-aem}}

## 用途 {#usage}

列表组件可用于创建子页面的动态列表或者任意定义项的静态列表。可用的列表类型以及格式化选项可以由模板作者在[“设计”对话框](#design-dialog)中定义。内容编辑者可在[“编辑”对话框](#edit-dialog)中从可用列表类型以及如何格式化列表元素中选择。

## 版本和兼容性 {#version-and-compatibility}

列表组件的当前版本是 v4，此版本在 2023 年 2 月发行核心组件 2.22.0 版本时引入，具体说明见本文。

下表详细说明了该组件的所有受支持版本、与该组件的版本兼容的 AEM 版本以及指向早期版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|--- |--- |--- |---|---|
| v4 | - | 兼容 | 兼容 |
| [v3](/help/components/v3/list.md) | - | 兼容 | 兼容 | 兼容 |
| [v2](/help/components/v2/list.md) | 兼容 | 兼容 | - | 兼容 |
| [v1](/help/components/v1/list-v1.md) | 兼容 | 兼容 | - | 兼容 |

有关核心组件版本的更多信息，请参阅文档[核心组件版本](/help/versions.md)。

## 列表中的重定向 {#redirects}

如果页面具有重定向目标（无论它指向的是外部 URL 还是另一个 AEM 页面），则包含指向该点的链接的列表将直接指向重定向目标的 URL。

### 示例 {#redirect-example}

* 创建重定向到页面 B 的页面 A。
* 创建重定向到 `https://aemcomponents.dev` 的页面 C
* 在页面 D 上，插入包含页面 A 和 C 的列表组件
* 随后，生成的相应链接将直接指向页面 B 和 `https://aemcomponents.dev`

## 示例组件输出 {#sample-component-output}

要体验列表组件并查看其配置选项示例以及 HTML 和 JSON 输出，请访问[组件库](https://adobe.com/go/aem_cmp_library_list_cn)。

### 技术详细信息 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_list_v3_cn)有关列表组件的最新技术文档。

在[核心组件开发人员文档](/help/developing/overview.md)中可找到有关开发核心组件的其他详细信息。

## “编辑”对话框 {#edit-dialog}

利用“编辑”对话框，内容作者可以配置列表和列表项。

### “列表设置”选项卡 {#list-settings-tab}

列表可以通过不同方式构建。

* [子页面](#child-pages)
* [固定列表](#fixed-list)
* [搜索](#search-options)
* [标记](#tags)

不论如何构建列表，始终可以配置[排序和 ID 选项](#sort-options)。

![列表组件的“编辑”对话框](/help/assets/list-edit.png)

根据内容作者选择如何构建列表，可以更改其他配置选项。

#### 子页面 {#child-pages}

列表可以由当前页面的子页面或其他页面构建。

![子页面选项](/help/assets/list-edit-child-pages.png)

* **父页面**
   * 其子页面应该用于生成列表的页面
   * 留空可使用当前页面

* **子级深度**
应该使用层级中向下的多少层

#### 固定列表 {#fixed-list}

列表可使用固定项列表构建。

![固定列表选项](/help/assets/list-edit-fixed.png)

点击或单击添加&#x200B;**按钮**&#x200B;可在列表中插入新项。

* 在&#x200B;**链接**&#x200B;字段输入以下两者之一
   * 完全限定的 URL
   * 现有 AEM 内容的相对 URL
      * 您可以使用&#x200B;**“选择”对话框**&#x200B;在 AEM 中选择项目。
* 在&#x200B;**文本**&#x200B;字段中，输入将在列表中显示的链接文本。
* 如果链接应在新的浏览器选项卡中打开，请选中该复选框

在为列表创建了多个项目后，便可以排列列表。

* 使用拖动手柄重新排列列表中的项。
* 使用垃圾桶图标可删除列表中的项。

#### 搜索 {#search-options}

列表可使用对 AEM 内容搜索的结果来构建。

![搜索列表选项](/help/assets/list-edit-search.png)

* **搜索查询**
用于运行全文搜索以生成列表项的字符串
* **搜索范围**
运行搜索的位置
   * 使用&#x200B;**“选择”对话框**&#x200B;可在 AEM 中选择位置
   * 如果留空则使用当前页面

#### 标记 {#tags}

列表可以使用在特定位置下与特定标记匹配的页面构建。

![标记列表选项](/help/assets/list-edit-tags.png)

* **父页面**
开始标记匹配的位置
   * 使用&#x200B;**“选择”对话框**&#x200B;可在 AEM 中选择位置
   * 如果留空则使用当前页面
* **标记**
应该匹配的标记
   * 使用&#x200B;**浏览**&#x200B;对话框选择标记。
* **匹配**
定义用什么类型的匹配来限定可以包括在列表中的页面
   * **任何标记**
   * **所有标记**

#### 排序选项 {#sort-options}

不论您选择如何构建列表，始终可以定义特定的排序选项。

![排序选项](/help/assets/list-edit-sort-options.png)

* **排序方式**
应该如何对元素排序
   * **标题**
   * **上次修改日期**
* **排序顺序**
对项排序所用的顺序
   * **升序**
   * **降序**
* **最大项数**
列表中显示的项的最大数量。
   * 留空可返回所有项。
* **ID** - 利用此选项，可以控制 HTML 和[ Data Layer ](/help/developing/data-layer/overview.md)中的组件的唯一标识符。
   * 如果留空，系统会自动为您生成一个唯一 ID，可以通过检查结果页面找到该 ID。
   * 如果指定一个 ID，作者有责任确保它是唯一的。
   * 更改此 ID 会对 CSS、JS 和 Data Layer 跟踪产生影响。

### “项设置”选项卡 {#item-settings-tab}

使用“项设置”选项卡，可以配置列表元素的格式化。

![项设置](/help/assets/list-edit-item-settings.png)

* **链接项** - 将项链接到对应的页面
* **显示描述** - 显示链接项的描述
* **显示日期** - 显示链接项的修改日期
* **显示为 Teaser** - 在选中时，该项将显示为 Teaser

### “样式”选项卡 {#styles-tab-edit}

列表组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。

使用下拉菜单选择要应用于该组件的样式。在“编辑”对话框中所做的选择与从组件工具栏中选择的操作效果相同。

必须在[“设计”对话框](#design-dialog)中为此组件配置样式，以便下拉菜单可用。

![列表组件“编辑”对话框的“样式”选项卡](/help/assets/list-edit-styles.png)

## “设计”对话框 {#design-dialog}

模板作者可以使用“设计”对话框定义允许内容作者使用什么类型的列表以及可用的项设置。

### 列表设置 {#list-settings}

在&#x200B;**列表设置**&#x200B;选项卡上，可以定义日期格式以及在组件中什么类型的列表可供内容作者使用。

![列表组件的“设计”对话框列表设置](/help/assets/list-design-list-settings.png)

* **日期格式**
用于显示上次修改日期的格式
* **禁用子级**
禁用组件中的子级列表类型
* **禁用静态**
禁用组件中的静态列表类型
* **禁用搜索**
禁用组件中的搜索列表类型
* **禁用标记**
禁用组件中的标记列表类型

### 项设置 {#item-settings}

在&#x200B;**项设置**&#x200B;选项卡上，可以定义在组件中可供内容作者使用的单独列表元素的格式化选项。

![列表组件的“设计”对话框项设置](/help/assets/list-design-item-settings.png)

* **链接项**
在[“编辑”对话框](#edit-dialog)中启用“链接项”选项
* **显示描述**
在[“编辑”对话框](#edit-dialog)中启用“显示描述”选项
* **显示日期**
在[“编辑”对话框](#edit-dialog)中启用“显示日期”选项

### “样式”选项卡 {#styles-tab}

图像组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。

## Adobe Client Data Layer {#data-layer}

列表组件支持 [Adobe Client Data Layer](/help/developing/data-layer/overview.md)。
