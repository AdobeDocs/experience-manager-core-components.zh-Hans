---
title: 列表组件 (v1)
description: 利用核心组件列表组件，可以轻松地创建动态和静态列表。
index: n
role: Architect, Developer, Admin, User
exl-id: 510d059c-e60a-40aa-9032-66a901109f6e
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: ht
source-wordcount: '854'
ht-degree: 100%

---

# 列表组件 (v1) {#list-component-v}

利用核心组件列表组件，可以轻松地创建动态和静态列表。

## 用途 {#usage}

列表组件可用于创建子页面的动态列表或者任意定义项的静态列表。

可用的列表类型以及格式化选项可以由模板作者在[“设计”对话框](#design-dialog)中定义。内容编辑者可在[“编辑”对话框](#edit-dialog)中从可用列表类型以及如何格式化列表元素中选择。

## 版本和兼容性 {#version-and-compatibility}

本文档介绍了列表组件 (v1)，它最初随带 AEM 6.3 的核心组件 1.0.0 版引入。

下表列出了列表组件 (v1) 的兼容性。

| AEM 版本 | 列表组件 v1 |
|--- |--- |
| 6.3 | 兼容 |
| 6.4 | 兼容 |

>[!CAUTION]
>
>本文档介绍了列表组件 (v1)。
>
>有关当前版本的列表组件的详细信息，请参阅[列表组件](/help/components/list.md)文档。

## 示例组件输出 {#sample-component-output}

以下是摘自 [We.Retail](https://helpx.adobe.com/cn/experience-manager/6-4/sites/developing/using/we-retail.html) 的示例。

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
>从核心组件执行 JSON 导出需要版本 1.1.0 的核心组件。有关更多信息，请参阅[核心组件 v1 的兼容性信息](/help/versions.md)。

## “编辑”对话框 {#edit-dialog}

利用“编辑”对话框，内容作者可以配置列表和列表元素。

### 列表设置 {#list-settings}

列表可以通过不同方式构建。

* [子页面](#child-pages)
* [固定列表](#fixed-list)
* [搜索](#search-list)
* [标记](#tags)

无论构建列表的方式如何，始终可以配置[排序选项](#sort-options)。

![](/help/assets/chlimage_1-38.png)

根据内容作者选择如何构建列表，可以更改其他配置选项。

#### 子页面 {#child-pages}

列表可以由当前页面的子页面或其他页面构建。

![](/help/assets/chlimage_1-39.png)

* **父页面**
   * 其子页面应该用于生成列表的页面
   * 留空可使用当前页面
* **子级深度** - 应该使用层级中向下的多少层

#### 固定列表 {#fixed-list}

列表可使用固定项列表构建。

![](/help/assets/chlimage_1-40.png)

点击或单击添加&#x200B;**按钮**&#x200B;可在列表中插入新项。

* 在列表中为项输入文本，或者使用&#x200B;**“选择”对话框**&#x200B;从 AEM 中选择项。
* 使用拖动手柄重新排列列表中的项。
* 使用垃圾桶图标可删除列表中的项。

#### 搜索 {#search-list}

列表可使用对 AEM 内容搜索的结果来构建。

![](/help/assets/chlimage_1-41.png)

* **搜索查询** - 用于运行全文搜索以生成列表项的字符串
* **搜索范围** - 运行搜索的位置
   * 使用&#x200B;**“选择”对话框**&#x200B;可在 AEM 中选择位置
   * 如果留空则使用当前页面

#### 标记 {#tags}

列表可以使用在特定位置下与特定标记匹配的页面构建。

![](/help/assets/chlimage_1-42.png)

* **父页面** - 开始标记匹配的位置
   * 使用&#x200B;**“选择”对话框**&#x200B;可在 AEM 中选择位置
   * 如果留空则使用当前页面
* **标记** - 应该匹配的标记
   * 使用&#x200B;**浏览**&#x200B;对话框选择标记。
* **匹配** - 定义用什么类型的匹配来限定可以包括在列表中的页面
   * **任何标记**
   * **所有标记**

#### 排序选项 {#sort-options}

不论您选择如何构建列表，始终可以定义特定的排序选项。

![](/help/assets/chlimage_1-43.png)

* **排序方式** - 应该如何对元素排序
   * **标题**
   * **上次修改日期**
* **排序顺序** - 对项排序所用的顺序
   * **升序**
   * **降序**
* **最大项数** - 列表中显示的项的最大数量。
   * 留空可返回所有项。

### 项设置 {#item-settings}

使用&#x200B;**项设置**&#x200B;选项卡，可以配置列表元素的格式化。

![](/help/assets/chlimage_1-44.png)

* **链接项**
将项链接到对应的页面
* **显示描述**
显示链接项的描述
* **显示日期**
显示链接项的修改日期

## “设计”对话框 {#design-dialog}

模板作者可以使用“设计”对话框定义允许内容作者使用什么类型的列表以及可用的项设置。

### 列表设置 {#list-settings-1}

在&#x200B;**列表设置**&#x200B;选项卡上，可以定义日期格式以及在组件中什么类型的列表可供内容作者使用。

![](/help/assets/chlimage_1-45.png)

* **日期格式** - 用于显示上次修改日期的格式
* **禁用子级** - 禁用组件中的子级列表类型
* **禁用静态** - 禁用组件中的静态列表类型
* **禁用搜索** - 禁用组件中的搜索列表类型
* **禁用标记** - 禁用组件中的标记列表类型

### 项设置 {#item-settings-1}

在&#x200B;**项设置**&#x200B;选项卡上，可以定义在组件中可供内容作者使用的单独列表元素的格式化选项。

![](/help/assets/chlimage_1-46.png)

* **链接项** - 在[“编辑”对话框](#edit-dialog)中启用“链接项”选项
* **显示描述** - 在[“编辑”对话框](#edit-dialog)中启用“显示描述”选项
* **显示日期** - 在[“编辑”对话框](#edit-dialog)中启用“显示日期”选项

## 技术详细信息 {#technical-details}

[在 GitHub 上可找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/list/v1/list)有关列表组件的最新技术文档。

从 GitHub 可下载整个核心组件项目。

在[核心组件开发人员文档](/help/developing/overview.md)中可找到有关开发核心组件的其他详细信息。
