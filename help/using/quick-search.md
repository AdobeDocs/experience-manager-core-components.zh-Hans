---
title: 快速搜索组件
seo-title: 快速搜索组件
description: 'null'
seo-description: 快速搜索组件为网站提供搜索功能并显示搜索结果，以便访客能够搜索站点并过滤结果。
uuid: a ba69be3-537e-4f20-20f17-b4 b7174 a8 e88
content-type: 引用
topic-tags: 创作
products: SG_ EXPERIENCE MANAGER/CORECOMMPANES-new
discoiquuid: 906a684d-5663-4497-bef3-37f13 d5 b46 c7
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
source-git-commit: 1bbec9b1f109df88964dce051a58d111bf6cafaa

---


# 快速搜索组件{#quick-search-component}

快速搜索组件为网站提供搜索功能并显示搜索结果，以便访客能够轻松找到匹配的内容并查看结果。

## 使用情况 {#usage}

“快速搜索”组件为站点访问者提供搜索内容、就地查看结果以及轻松导航到匹配页面的功能。用户滚动搜索结果时会动态获取新结果。

[编辑对话框](#edit-dialog) 允许内容作者定义应开始搜索的内容树中的位置。使用 [设计对话框](#design-dialog)，模板作者可以为内容树中的位置设置默认值，以及最大结果集大小和最小搜索词长度。

## 版本和兼容性 {#version-and-compatibility}

快速搜索组件的当前版本是v1，它是在2018年月版的核心组件中引入的，它在文档中进行了介绍。

下表详细说明了组件的所有支持版本、组件版本的AEM版本以及以前版本的文档链接。

| 组件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v1 | 兼容 | 兼容 | 兼容 |

有关核心组件版本和版本的更多信息，请参阅文档 [核心组件版本](versions.md)。

## 示例组件输出 {#sample-component-output}

以下示例取自 [We. Retail](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html)。

### 屏幕快照 {#screenshot}

![](assets/screen_shot_2018-01-19at094248.png)

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
>应在更高级别上使用对搜索组件或任何基于AEM的应用程序进行保护的应用程序，例如，在调度程序 `mod_security` 上使用。

有关快速搜索组件 [的最新技术文档可在GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/search/v1/search)上找到。

有关开发核心组件的更多详细信息，请参阅 [核心组件开发人员文档](developing.md)。

## 编辑对话框 {#edit-dialog}

编辑对话框允许内容作者定义应开始搜索的内容树中的位置。

![](assets/screen_shot_2018-04-03at120132.png)

**搜索根目录** -开始搜索的根页面。搜索根目录可以是Blueprint master、language master或常规页面。

## 设计对话框 {#design-dialog}

使用设计对话框，模板作者可以为内容树中的位置设置默认值，以及最大的结果集大小和最小搜索词长度。设计对话框允许模板作者定义内容作者可使用的文本格式选项。

### 属性选项卡 {#properties-tab}

![](assets/screen_shot_2018-04-03at120028.png)

* **搜索根**内容作者将“快速搜索组件”放置到内容页面时搜索根目录的默认值
* **结果大小**通过搜索请求获取的最大结果数
* **搜索词最小长度**搜索词的最小长度以开始搜索

>[!NOTE]
>
>**结果大小** 和 **搜索期限最小长度** 只能在设计模式下设置，因此只能在模板级别设置，这意味着内容作者不能修改这些值。

>[!CAUTION]
>
>**结果大小** 和 **搜索期限最小长度** 在设置过高或过低时会影响效果。

### 样式选项卡 {#styles-tab}

快速搜索组件支持AEM [Style System](authoring.md#component-styling)。