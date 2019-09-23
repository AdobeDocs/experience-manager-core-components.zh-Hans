---
title: 语言导航组件
seo-title: 语言导航组件
description: 'null'
seo-description: 语言导航组件为站点提供语言／国家／地区导航，以便访客可以在不同区域设置中导航到同一页面。
uuid: ce736458-9cdf-4bc2-b90f-9c5a62fe1ca0
content-type: 引用
topic-tags: 创作
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-新
discoiquuid: 8f232eb0-65d5-4075-8668-75f1366882c8
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
source-git-commit: c4e86960ec271464661193f6409cd93d1b9ec51b

---


# Language Navigation Component{#language-navigation-component}

语言导航组件为站点提供语言／国家／地区导航，以便访客可以在不同区域设置中导航到同一页面。

## 使用情况 {#usage}

网站通常针对不同区域以多种语言提供。 语言导航组件允许访客查看不同语言／区域设置的同一页面。 因此，如果您是瑞士德语版网站的读者，您可以轻松切换到同一页面的美国英语版。 “语言导航”组件负责理解站点语言结构并自动查找相应的页面。

* 有关语言导航组件的本地化功能如何工作的示例，请参 [阅以下部分](#example)。
* 有关其他核心组件的本地化功能如何协同工作的示例，请参阅核 [心组件的本地化功能页面](localization.md)。

编辑 [对话框允许定义全局站点导航根目录](#edit-dialog) ，以及导航应深入到结构中的程度。 使用设 [计对话框](#design-dialog)，模板作者可以为相同的选项设置默认值。

## 版本和兼容性 {#version-and-compatibility}

语言导航组件的当前版本为v1,v1是2018年1月随核心组件版本2.0.0一起引入的，本文档对此进行了说明。

下表详细列出了组件的所有受支持版本、与组件版本兼容的AEM版本，以及指向先前版本的文档的链接。

| 组件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v1 | 兼容 | 兼容 | 兼容 |

有关核心组件版本和版本的详细信息，请参阅文档核 [心组件版本](versions.md)。

## 示例组件输出 {#sample-component-output}

要体验语言导航组件以及其配置选项以及HTML和JSON输出的示例，请访问组件 [库](http://opensource.adobe.com/aem-core-wcm-components/library/language-navigation/language-structure/us/en/language-navigation.html)。

## 技术详细信息 {#technical-details}

有关语言导航组件的最新技 [术文档可在GitHub上找到](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/languagenavigation/v1/languagenavigation)。

有关开发核心组件的更多详细信息，请参阅核 [心组件开发人员文档](developing.md)。

## 设计对话框 {#design-dialog}

编辑对话框允许定义全局站点导航根目录以及导航应深入到结构中的程度。

通常，这些配置只需在页面模板级别完成。 但是，可以通过编辑对话框在页面级别更改 [它们](#edit-dialog)。

### 属性选项卡 {#properties-tab}

![](assets/screen_shot_2018-01-12at133642.png)

* **导航根目录**
   * 站点的语言导航应从此处开始。
   * 站点的语言结构从此根目录下的下一级开始。
* **语言结构深度**
   * 这是导航根目录下的内容树的 **级别** ，表示站点的语言结构。 示例:
      * `1` 通常意味着您只有语言选择权。
      * `2` 通常意味着你有语言和国家的选择。
      * `3` 通常意味着您可以选择语言、国家／地区。

#### 示例 {#example}

假设您的内容类似于：

```
/content
+-- we-retail
   +-- language-masters
   +-- us
      +-- en
      \-- es
   \-- ch
      +-- de
      +-- fr
      \-- it
+-- wknd-events
\-- wknd-shop
```

对于站点We.Retail，您可能希望将语言导航组件作为标题的一部分放置在页面模板上。 模板一经加入，您便可将组件的 **导航根** (Navigation Root `/content/we-retail` )设置为，因为该站点的本地化内容就从此开始。 您还希望将“语言结构深 **度”设置为** , `2` 因为您的结构是两个级别（国家／地区，然后是语言）。

使用“导 **航根** ”值，语言组件知道在导航开始后，它可以生成语言导航选项，方法是将内容树中的后两个级别识别为站点的语言导航结构(由“语言结构深度”值定义 `/content/we-retail`**** )。

无论用户查看的是哪个页面，语言导航组件都可以通过了解当前页面的位置并返回到根目录，然后转发到相应的页面来找到使用其他语言的相应页面。

### 样式选项卡 {#styles-tab}

语言导航组件支持AEM样 [式系统](authoring.md#component-styling)。

## Edit Dialog {#edit-dialog}

通常，语言导航组件只需添加到站点的页面模板并在其上进行配置。 但是，如果需要将语言导航组件添加到单个内容页面，则编辑对话框允许内容作者配置与设计对话框中所述的相 [同值](#design-dialog)。

![](assets/screen_shot_2018-01-12at133353.png)
