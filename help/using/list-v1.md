---
title: 列表组件(v1)
seo-title: 列表组件(v1)
description: 'null'
seo-description: 核心组件列表组件允许轻松创建动态和静态列表。
uuid: 06658c9d-cbf2-4bfe-b425-d980 d1181908
content-type: 引用
products: SG_ EXPERIENCE MANAGER/CORECOMMPANES-new
discoiquuid: 7c130ccc-83ff-464d-b58 f-d581 f4365 dbd
disttype: dist5
gnavtheme: 浅色
groupsectionnavitems: 否
hidemerchandisingbar: 继承
hidepromocomponent: 继承
modalsize: 426 x 240
noindex: 'true'
index: n
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1bbec9b1f109df88964dce051a58d111bf6cafaa

---


# 列表组件(v1){#list-component-v}

核心组件列表组件允许轻松创建动态和静态列表。

## 使用情况 {#usage}

列表组件可用于创建例如子页面的动态列表或任意定义项目的静态列表。

可用列表类型和格式选项可由设计对话框中的模板作者 [定义](list-v1.md#main-pars_title_1995166862)。内容编辑器可以从可用的列表类型中进行选择，以及如何格式化 [编辑对话框](list-v1.md#main-pars_title)中的列表元素。

## 版本和兼容性 {#version-and-compatibility}

本文档描述了列表组件的v1，该组件最初随AEM6.3的核心组件版本1.0.0一起引入。

下表列出了列表组件的v1的兼容性。

| AEM 版本 | 列表组件v1 |
|--- |--- |
| 6.3 | 兼容 |
| 6.4 | 兼容 |

>[!CAUTION]
>
>本文档描述了列表组件的v1。
>
>有关列表组件当前版本的详细信息，请参阅 [列表组件](list.md) 文档。

## 示例组件输出 {#sample-component-output}

以下示例取自 [We. Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)。

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
>核心组件中的JSON导出需要核心组件版本1.1.0。有关更多信息，请参见核心组件v [](versions.md#main-pars_title_236368006) 的兼容性信息。

## 编辑对话框 {#edit-dialog}

编辑对话框允许内容作者配置列表和列表元素。

### 列表设置 {#list-settings}

列表可以以不同的方式构建。

* [子页面](list-v1.md#main-pars_title_1861279796)
* [固定列表](list-v1.md#main-pars_title_1227896889)
* [搜索](list-v1.md#main-pars_title_1224003560)
* [标记](list-v1.md#main-pars_title_700759533)

无论列表是如何构建的，都有 [可以始终配置的“排序选项](list-v1.md#main-pars_title_1568376452) ”。

![](assets/chlimage_1-38.png)

根据内容作者选择构建列表的方式，其他配置选项将会更改。

#### 子页面 {#child-pages}

可以构建当前页面或其他页面的子页面的列表。

![](assets/chlimage_1-39.png)

* **父页面**
   * 子页面应制作列表的页面
   * 留空可使用当前页面
* **子深度** -应使用层次结构中的下拉级别

#### 固定列表 {#fixed-list}

可以使用项目的固定列表构建列表。

![](assets/chlimage_1-40.png)

点按或单击 **添加** 按钮以将新项目插入列表。

* 在列表中输入项目的文本，或使用 **选择对话框** 从AEM中选择项目。
* 使用拖动手柄重新排列列表中的项目。
* 使用垃圾桶图标可删除列表中的项目。

#### 搜索 {#search}

可以使用搜索AEM内容的搜索结果构建列表。

![](assets/chlimage_1-41.png)

* **搜索查询** -将运行全文搜索以生成列表元素的字符串
* **在中** 搜索-应在其中运行搜索
   * 使用 **选择对话框** 在AEM中选择位置
   * 如果留空，请使用当前页面

#### 标记 {#tags}

可以使用与特定位置匹配特定标记的页面构建列表。

![](assets/chlimage_1-42.png)

* **父页面** -标记匹配的位置
   * 使用 **选择对话框** 在AEM中选择位置
   * 如果留空，请使用当前页面
* **标记** -应匹配哪些标签
   * 使用“ **浏览** ”对话框选择标记
* **匹配** -定义应确定要包含在列表中的页面的类型
   * **任何标记**
   * **所有标记**

#### 排序选项 {#sort-options}

无论您选择如何构建列表，都有某些可始终定义的排序选项。

![](assets/chlimage_1-43.png)

* **排序依据** -如何订购元素
   * **标题**
   * **上次修改日期**
* **排序顺序** -应在其中订购项目的顺序
   * **升序**
   * **降序**
* **最大项目** -列表中显示的最大项目数。
   * 留空可返回所有项目。

### 项目设置 {#item-settings}

使用 **“项目设置** ”选项卡，可以配置列表元素的格式。

![](assets/chlimage_1-44.png)

* **链接项目**将项目链接到相应页面
* **显示说明**显示链接项的说明
* **显示日期**显示链接项目的修改日期

## 设计对话框 {#design-dialog}

设计对话框允许模板作者定义应允许内容作者以及可用项目设置的列表类型。

### 列表设置 {#list-settings-1}

在 **“列表设置** ”选项卡上，可以定义日期格式以及组件中应提供给内容作者的列表类型。

![](assets/chlimage_1-45.png)

* **日期格式** -用于显示上次修改日期的格式
* **禁用子项** -禁用组件中的子级列表类型
* **禁用静态** -禁用组件中的静态列表类型
* **禁用搜索** -禁用组件中的搜索列表类型
* **禁用标记** -禁用组件中的标记列表类型

### 项目设置 {#item-settings-1}

在 **“项目设置** ”选项卡上，可以定义内容作者组件中应提供的各个列表元素的格式选项。

![](assets/chlimage_1-46.png)

* **“链接项目** -启用链接项目”选项( [在编辑对话框中)](list-v1.md#main-pars_title_550499279)
* **在编辑对话框中显示描述** -启用显示 [描述选项](list-v1.md#main-pars_title_550499279)
* **显示日期** -在 [编辑对话框中启用显示日期选项](list-v1.md#main-pars_title_550499279)

## 技术详细信息 {#technical-details}

有关List组件 [的最新技术文档可在GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/list/v1/list)上找到。

可以从GitHub下载整个核心组件项目。

有关开发核心组件的更多详细信息，请参阅 [核心组件开发人员文档](developing.md)。
