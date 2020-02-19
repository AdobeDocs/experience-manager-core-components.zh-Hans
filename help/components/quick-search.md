---
title: 快速搜索组件
description: “快速搜索”组件为网站提供搜索功能并显示搜索结果，以便访客可以搜索网站并筛选结果。
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

---


# 快速搜索组件 {#quick-search-component}

“快速搜索”组件为网站提供搜索功能并显示搜索结果，以便访客可以轻松找到匹配的内容并查看结果。

## 使用情况 {#usage}

通过“快速搜索”组件，站点访问者可以搜索内容、就地查看结果并轻松导航到相应的页面。 当用户滚动搜索结果时，将动态获取新结果。

通过 [编辑对话框](#edit-dialog) ，内容作者可以定义在内容树中应开始搜索的位置。 使用设 [计对话框](#design-dialog)，模板作者可以为内容树中应开始搜索的位置以及最大结果集大小和最小搜索词长度设置默认值。

## 版本和兼容性 {#version-and-compatibility}

快速搜索组件的当前版本为v1，该版本于2018年1月随核心组件的2.0.0版一起推出，本文档对此进行了说明。

下表详细列出了组件的所有受支持版本、与组件版本兼容的AEM版本，以及指向先前版本的文档的链接。

| 组件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM作为云服务 |
|--- |--- |--- |--- |---|
| v1 | 兼容 | 兼容 | 兼容 | 兼容 |

有关核心组件版本和版本的详细信息，请参阅文档核 [心组件版本](/help/versions.md)。

## 示例组件输出 {#sample-component-output}

以下是从 [We.Retail获取的示例](https://docs.adobe.com/content/help/en/experience-manager-65/developing/bestpractices/we-retail/we-retail.html)。

### 屏幕快照 {#screenshot}

![](/help/assets/screen_shot_2018-01-19at094248.png)

### HTML {#html}

```
<section class="cmp-search" role="search" data-cmp-is="search" data-cmp-min-length="3" data-cmp-results-size="10">
    <form class="cmp-search__form" data-cmp-hook-search="form" method="get" action="/content/we-retail/us/en/equipment.searchresults.json/_jcr_content/root/responsivegrid/search" autocomplete="off">
        <div class="cmp-search__field">
            <i class="cmp-search__icon" data-cmp-hook-search="icon"></i>
            <span class="cmp-search__loading-indicator" data-cmp-hook-search="loadingIndicator"></span>
            <input class="cmp-search__input" data-cmp-hook-search="input" type="text" name="fulltext" placeholder="Search" role="combobox" aria-autocomplete="list" aria-haspopup="true" aria-invalid="false">
            <button class="cmp-search__clear" data-cmp-hook-search="clear">
                <i class="cmp-search__clear-icon"></i>
            </button>
        </div>
    </form>
    <div class="cmp-search__results" data-cmp-hook-search="results" role="listbox" aria-multiselectable="false"></div>
    
<script data-cmp-hook-search="itemTemplate" type="x-template">
    <a class="cmp-search__item" data-cmp-hook-search="item">
        <span class="cmp-search__item-title" data-cmp-hook-search="itemTitle"></span>
    </a>
</script>
</section>
```

### JSON {#json}

```
"search":{  
                     "columnClassNames":"aem-GridColumn aem-GridColumn--default--12",
                     "relativePath":"/jcr:content/root/responsivegrid/search",
                     "resultsSize":10,
                     "searchTermMinimumLength":3,
                     ":type":"core/wcm/components/search/v1/search"
                  }
```

### 技术详细信息 {#technical-details}

>[!NOTE]
>
>保护搜索组件或任何基于AEM的应用程序免受DOS攻击应在更高级别实施，例如，在调度程序上 `mod_security` 使用。

有关“快速搜索组件”的最 [新技术文档可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_search_v1)。

有关开发核心组件的更多详细信息，请参阅核 [心组件开发人员文档](/help/developing/overview.md)。

## Edit Dialog {#edit-dialog}

编辑对话框允许内容作者定义在内容树中应开始搜索的位置。

![](/help/assets/screen_shot_2018-04-03at120132.png)

**搜索根** -从中开始搜索的根页面。 “搜索根”可以是Blueprint主页、语言主页或常规页。

## 设计对话框 {#design-dialog}

使用设计对话框，模板作者可以在内容树中为搜索的开始位置以及最大结果集大小和最小搜索词长度设置默认值。设计对话框允许模板作者定义可供内容作者使用的文本格式选项。

### 属性选项卡 {#properties-tab}

![](/help/assets/screen_shot_2018-04-03at120028.png)

* **搜索根**&#x200B;内容作者将“快速搜索组件”放置到内容页面时搜索根的默认值
* **结果大**&#x200B;小搜索请求获取的最大结果数
* **搜索词最小长**&#x200B;度用于开始搜索的搜索词的最小长度

>[!NOTE]
>
>**结果大小****** 和搜索词最小长度只能在设计模式中设置，因此只能在模板级别设置，这意味着内容作者无法修改这些值。

>[!CAUTION]
>
>**如果结果大小****** 和搜索词最小长度分别设置得过高或过低，则可能会对性能产生影响。

### 样式选项卡 {#styles-tab}

快速搜索组件支持AEM样 [式系统](/help/get-started/authoring.md#component-styling)。
