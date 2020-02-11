---
title: 列表组件(v1)
description: 核心组件列表组件允许轻松创建动态和静态列表。
index: n
translation-type: tm+mt
source-git-commit: 5439f90faef28c72367419bb7429a3a880b65229

---


# 列表组件(v1){#list-component-v}

核心组件列表组件允许轻松创建动态和静态列表。

## 使用情况 {#usage}

列表组件可用于创建子页面的动态列表或任意定义项目的静态列表。

可用列表类型和格式选项可由模板作者在设计对话框中定 [义](list-v1.md#main-pars_title_1995166862)。 内容编辑器可以从可用的列表类型中进行选择，以及如何在编辑对话框中设置列 [表元素格式](list-v1.md#main-pars_title)。

## 版本和兼容性 {#version-and-compatibility}

本文档描述了最初随AEM 6.3的核心组件版本1.0.0引入的列表组件的v1。

下表列出了列表组件的v1的兼容性。

| AEM 版本 | 列表组件v1 |
|--- |--- |
| 6.3 | 兼容 |
| 6.4 | 兼容 |

>[!CAUTION]
>
>本文档描述了列表组件的v1。
>
>有关列表组件当前版本的详细信息，请参阅列 [表组件文档](list.md) 。

## 示例组件输出 {#sample-component-output}

以下是从 [We.Retail获取的示例](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)。

### 屏幕快照 {#screenshot}

![](assets/chlimage_1-47.png)

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
>从核心组件导出JSON时，需要发行1.1.0版的核心组件。 有关详细信息， [请参阅核心组件v1的兼容性信息](versions.md#main-pars_title_236368006) 。

## Edit Dialog {#edit-dialog}

编辑对话框允许内容作者配置列表和列表元素。

### 列表设置 {#list-settings}

列表可以采用不同的方式构建。

* [子页面](list-v1.md#main-pars_title_1861279796)
* [固定列表](list-v1.md#main-pars_title_1227896889)
* [搜索](list-v1.md#main-pars_title_1224003560)
* [标记](list-v1.md#main-pars_title_700759533)

无论如何构建列表，都有 [可以始终配置的排序选项](list-v1.md#main-pars_title_1568376452) 。

![](assets/chlimage_1-38.png)

根据内容作者选择如何构建列表，其他配置选项将会更改。

#### 子页面 {#child-pages}

列表可以由当前页面或其他页面的子页面构建。

![](assets/chlimage_1-39.png)

* **父页面**
   * 其子页面应该列出的页面
   * 留空以使用当前页面
* **子级深度** -层次结构中应使用多少个级别

#### Fixed List {#fixed-list}

可以使用项目的固定列表生成列表。

![](assets/chlimage_1-40.png)

点按或单击 **添加** 按钮，将新项目插入列表。

* 在列表中输入项目文本，或使用“选择 **对话框** ”从AEM中选择项目。
* 使用拖动手柄重新排列列表中的项目。
* 使用垃圾桶图标可删除列表中的项目。

#### 搜索 {#search}

可以使用AEM内容搜索结果生成列表。

![](assets/chlimage_1-41.png)

* **搜索查询** -将运行全文搜索以生成列表元素的字符串
* **搜索范围** -应在何处运行搜索
   * 使用“ **选择”对话框** ，在AEM中选择位置
   * 如果留空，则使用当前页面

#### 标记 {#tags}

列表可以使用与特定位置下的特定标记匹配的页面构建。

![](assets/chlimage_1-42.png)

* **父页面** -标记匹配应从何处开始
   * 使用“ **选择”对话框** ，在AEM中选择位置
   * 如果留空，则使用当前页面
* **标记** -哪些标记应匹配
   * 使用“浏 **览** ”对话框选择标记
* **匹配** -定义哪些类型的匹配应使页面符合列表中的条件
   * **任何标记**
   * **所有标记**

#### 排序选项 {#sort-options}

无论您选择如何构建列表，总是可以定义某些排序选项。

![](assets/chlimage_1-43.png)

* **排序依据** -元素的排序方式
   * **标题**
   * **上次修改日期**
* **排序顺序** -应按顺序对项目进行排序
   * **升序**
   * **降序**
* **最大项目** -列表中显示的最大项目数。
   * 留空将返回所有项目。

### 项目设置 {#item-settings}

使用“ **项目设置** ”选项卡，可以配置列表元素的格式。

![](assets/chlimage_1-44.png)

* **链接项目**&#x200B;将项目链接到相应的页面
* **显示说明**&#x200B;显示链接项的说明
* **显示日期**&#x200B;显示链接项目的修改日期

## 设计对话框 {#design-dialog}

设计对话框允许模板作者定义内容作者应允许的列表类型以及可用的项目设置。

### 列表设置 {#list-settings-1}

在“列 **表设置** ”选项卡上，可以定义日期格式以及内容作者在组件中应可以使用的列表类型。

![](assets/chlimage_1-45.png)

* **日期格式** -用于显示上次修改日期的格式
* **禁用子项** -禁用组件中的子项列表类型
* **禁用静态** -禁用组件中的静态列表类型
* **禁用搜索** -禁用组件中的搜索列表类型
* **禁用标记** -在组件中禁用标记列表类型

### 项目设置 {#item-settings-1}

在“项 **目设置** ”选项卡上，可以为内容作者的组件中应可用的各个列表元素定义格式选项。

![](assets/chlimage_1-46.png)

* **链接项目** -编辑对话框中的“启用链接 [项目”选项](list-v1.md#main-pars_title_550499279)
* **显示描述** -在编辑对话框中启用显示 [描述选项](list-v1.md#main-pars_title_550499279)
* **显示日期** -编辑对话框中的启用显示 [日期选项](list-v1.md#main-pars_title_550499279)

## 技术详细信息 {#technical-details}

有关列表组件的最新技术文 [档可在GitHub上找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/list/v1/list)。

整个核心组件项目可从GitHub下载。

有关开发核心组件的更多详细信息，请参阅核 [心组件开发人员文档](developing.md)。
