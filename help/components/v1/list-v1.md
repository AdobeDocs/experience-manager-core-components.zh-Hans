---
title: 列表组件(v1)
description: 核心组件列表组件允许轻松创建动态和静态列表。
index: n
role: 架构师、开发人员、管理员、业务从业者
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '859'
ht-degree: 4%

---


# 列表组件(v1){#list-component-v}

核心组件列表组件允许轻松创建动态和静态列表。

## 使用 {#usage}

列表组件可用于创建子页面的动态列表或任意定义项的静态列表。

模板作者可以在[设计对话框](#design-dialog)中定义可用列表类型和格式选项。 内容编辑器可以从可用的列表类型中进行选择，并在[编辑对话框](#edit-dialog)中设置列表元素的格式。

## 版本和兼容性{#version-and-compatibility}

本文档描述了列表组件的v1，该组件最初随AEM 6.3的核心组件版本1.0.0引入。

下表列表了列表组件v1的兼容性。

| AEM 版本 | 列表组件v1 |
|--- |--- |
| 6.3 | 兼容 |
| 6.4 | 兼容 |

>[!CAUTION]
>
>本文档描述了列表组件的v1。
>
>有关列表组件当前版本的详细信息，请参阅[列表组件](/help/components/list.md)文档。

## 示例组件输出{#sample-component-output}

以下是从[We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)取的示例。

### 屏幕快照 {#screenshot}

![](/help/assets/chlimage_1-47.png)

### HTML {#html}

```
<div class="cmp cmp-list aem-GridColumn aem-GridColumn--default--12">

<ul>
    <li>
    <article>
        <a href="/content/we-retail/us/en/experience/arctic-surfing-in-lofoten.html">
            <span class="cmp-list--item-title">Arctic Surfing In Lofoten</span>
            
        </a>
        
    </article>
</li>

    <li>
    <article>
        <a href="/content/we-retail/us/en/experience/summit-success-in-the-himalayas.html">
            <span class="cmp-list--item-title">Summit Success in the Himalayas</span>
            
        </a>
        
    </article>
</li>

    <li>
    <article>
        <a href="/content/we-retail/us/en/experience/climbing-on-kalymnos-island--greece.html">
            <span class="cmp-list--item-title">Climbing on Kalymnos Island, Greece</span>
            
        </a>
        
    </article>
</li>

    <li>
    <article>
        <a href="/content/we-retail/us/en/experience/running-at-the-great-wall-marathon.html">
            <span class="cmp-list--item-title">Running at the Great Wall Marathon</span>
            
        </a>
        
    </article>
</li>

    <li>
    <article>
        <a href="/content/we-retail/us/en/experience/skiing-deep-powder-in-siberia.html">
            <span class="cmp-list--item-title">Skiing deep powder in Siberia</span>
            
        </a>
        
    </article>
</li>

    <li>
    <article>
        <a href="/content/we-retail/us/en/experience/climbing-in-the-massif-du-mont-blanc.html">
            <span class="cmp-list--item-title">Climbing in the Massif du Mont Blanc</span>
            
        </a>
        
    </article>
</li>
</ul>

</div>
```

### JSON {#json}

```
"articles_list": {
              "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
              ":type": "weretail/components/content/articleslist",
              "tagsMatch": "any",
              "displayAs": "teaser",
              "feedEnabled": "true",
              "listFrom": "children",
              "limit": "0",
              "orderBy": "cq:lastModified",
              "pageMax": "0"
            }
```

>[!NOTE]
>
>从核心组件导出JSON需要1.1.0版的核心组件。 有关详细信息，请参阅核心组件v1](/help/versions.md)的[兼容性信息。

## 编辑对话框{#edit-dialog}

编辑对话框允许内容作者配置列表和列表元素。

### 列表设置 {#list-settings}

列表可以采用不同的方式构建。

* [子页面](#child-pages)
* [固定列表](#fixed-list)
* [搜索](#search-list)
* [标记](#tags)

无论如何构建列表，总有[排序选项](#sort-options)可以始终进行配置。

![](/help/assets/chlimage_1-38.png)

根据内容作者选择如何构建列表，其他配置选项将会更改。

#### 子页面 {#child-pages}

列表可以由当前页面或其他页面的子页面构建。

![](/help/assets/chlimage_1-39.png)

* **父页面**
   * 其子页面应生成列表的页面
   * 留空以使用当前页面
* **子级深度**  — 应使用层次结构中向下的层数

#### 固定列表{#fixed-list}

列表可以使用固定的项目列表来构建。

![](/help/assets/chlimage_1-40.png)

点按或单击&#x200B;**添加**&#x200B;按钮，将新项目插入列表。

* 在列表中为项目输入文本，或使用&#x200B;**选择对话框**&#x200B;从AEM中选择项目。
* 使用拖动手柄重新排列列表中的项目。
* 使用垃圾桶图标删除列表中的项目。

#### 搜索 {#search-list}

列表可以使用搜索AEM内容的结果来构建。

![](/help/assets/chlimage_1-41.png)

* **搜索查询**  — 将运行全文搜索以生成列表元素的字符串
* **搜索范围**  — 应在何处运行搜索
   * 使用&#x200B;**选择对话框**&#x200B;选择AEM中的位置
   * 如果留空，则使用当前页

#### 标记 {#tags}

列表可以使用与特定位置下的特定标记匹配的页面构建。

![](/help/assets/chlimage_1-42.png)

* **父页面**  — 标记匹配应开始的位置
   * 使用&#x200B;**选择对话框**&#x200B;选择AEM中的位置
   * 如果留空，则使用当前页
* **标记**  — 应匹配哪些标记
   * 使用&#x200B;**浏览**&#x200B;对话框选择标记
* **匹配**  — 定义哪些类型的匹配应使页面有资格包含在列表中
   * **任何标记**
   * **所有标记**

#### 排序选项{#sort-options}

无论您选择如何构建列表，总是可以定义某些排序选项。

![](/help/assets/chlimage_1-43.png)

* **排序依据**  — 应如何对元素进行排序
   * **标题**
   * **上次修改日期**
* **排序**  — 项目的排序顺序
   * **升序**
   * **降序**
* **最大项目** -列表中显示的最大项目数。
   * 留空可返回所有项目。

### 项目设置 {#item-settings}

使用&#x200B;**项目设置**&#x200B;选项卡，可以配置列表元素的格式。

![](/help/assets/chlimage_1-44.png)

* **链接**
项目链接项目到相应页面
* **显示**
说明显示链接项的说明
* **显示**
日期显示链接项的修改日期

## 设计对话框{#design-dialog}

设计对话框允许模板作者定义允许内容作者使用哪些类型的列表以及可用的项目设置。

### 列表设置 {#list-settings-1}

在&#x200B;**列表设置**&#x200B;选项卡上，可以定义日期格式以及内容作者在组件中可以使用的列表类型。

![](/help/assets/chlimage_1-45.png)

* **日期格式**  — 用于显示上次修改日期的格式
* **禁用子项**  — 禁用组件中的子列表类型
* **禁用静态**  — 禁用组件中的静态列表类型
* **禁用搜索**  — 禁用组件中的搜索列表类型
* **禁用标记**  — 在组件中禁用标记列表类型

### 项目设置 {#item-settings-1}

在&#x200B;**项目设置**&#x200B;选项卡上，可以为内容作者的组件中应可用的各个列表元素定义格式选项。

![](/help/assets/chlimage_1-46.png)

* **链接项目**  — 编辑对话框中的“启用链 [接项目”选项](#edit-dialog)
* **显示说明**  — 编辑对话框中的“启用显示 [说明”选项](#edit-dialog)
* **显示日期**  — 编辑对话框中的启用显示 [日期选项](#edit-dialog)

## 技术详细信息{#technical-details}

有关列表组件[的最新技术文档可在GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/list/v1/list)上找到。

整个核心组件项目可从GitHub下载。

有关开发核心组件的更多详细信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。
