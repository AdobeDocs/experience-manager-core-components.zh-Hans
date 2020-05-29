---
title: 语言导航组件
description: 语言导航组件为站点提供语言／国家／地区导航，以便访客可以在不同区域设置中导航到同一页面。
translation-type: tm+mt
source-git-commit: c186e9ec3944d785ab0376769cf7f2307049a809
workflow-type: tm+mt
source-wordcount: '832'
ht-degree: 2%

---


# Language Navigation Component{#language-navigation-component}

语言导航组件为站点提供语言／国家／地区导航，以便访客可以在不同区域设置中导航到同一页面。

## 使用 {#usage}

网站通常以多种语言为不同区域提供。 语言导航组件允许访客视图不同语言／区域设置的同一页面。 因此，如果您是瑞士德语版网站的读者，您可以轻松切换到同一页的美国英语版。 语言导航组件可处理理解站点语言结构的过程并自动查找相应的页面。

* 有关语言导航组件的本地化功能如何工作的示例，请参 [阅以下部分](#example)。
* 有关其他核心组件的本地化功能如何协同工作的示例，请参 [阅核心组件页面的本地化功能](/help/get-started/localization.md)。

编 [辑对话框](#edit-dialog) ，可定义全局站点导航根目录以及导航应深入到结构中的程度。 使用设 [计对话框](#design-dialog)，模板作者可以设置相同选项的默认值。

## 版本和兼容性 {#version-and-compatibility}

语言导航组件的当前版本为v1，该版本在2018年1月随核心组件的2.0.0版一起推出，并在本文档中进行了说明。

下表详细列出了组件的所有受支持版本、与组件版本兼容的AEM版本以及指向先前版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM 云服务 |
|--- |--- |--- |---|
| v1 | 兼容 | 兼容 | 兼容 |

有关核心组件版本和版本的详细信息，请参阅文档 [核心组件版本](/help/versions.md)。

## 示例组件输出 {#sample-component-output}

要体验语言导航组件以及查看其配置选项以及HTML和JSON输出的示例，请访问组 [件库](https://adobe.com/go/aem_cmp_library_langnav)。

## 技术详细信息 {#technical-details}

有关语言导航组件的最新技 [术文档可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_langnav_v1)。

有关开发核心组件的更多详细信息，请参阅核 [心组件开发人员文档](/help/developing/overview.md)。

## 设计对话框 {#design-dialog}

编辑对话框允许定义全局站点导航根目录以及导航应深入到结构中的程度。

通常，这些配置只需在页面模板级别完成。 但是，可以通过编辑对话框在页面级别 [更改它们](#edit-dialog)。

### 属性选项卡 {#properties-tab}

![语言导航组件的设计对话框](/help/assets/language-navigation-design.png)

* **导航根目录**
   * 这是站点的语言导航应开始的位置。
   * 站点的语言结构从此根目录下的下一级开始。
* **语言结构深度**
   * 这是导航根下的内容树的 **级别** ，表示站点的语言结构。 示例：
      * `1` 通常意味着您只有语言选择权。
      * `2` 通常意味着你有语言和国家的选择。
      * `3` 通常意味着您可以选择语言、国家和地区。

#### 示例 {#example}

假设您的内容类似于：

```
/content
+-- wknd
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

对于站点WKND，您可能希望将语言导航组件作为标题的一部分放置在页面模板上。 模板的一部分后，您可以将组件的 **导航根** 设置为 `/content/wknd` ，因为这是该站点的本地化内容的开始。 您还希望将“语言结 **构深度** ”设置为 `2` ，因为您的结构是两个级别（国家／地区然后是语言）。

使用“ **导航根** ”值，语言组件知道在导航开始后，它可以生成语言导航选项，方法是将内容树中的后两个级别识别为站点的语言导航结构(由“语言结构深度”值 `/content/wknd` 定义 **** )。

无论用户正在查看哪个页面，语言导航组件都能够通过了解当前页面的位置并返回到根目录，然后转发到相应的页面，以其他语言查找相应页面。

### 样式选项卡 {#styles-tab}

语言导航组件支持AEM [样式系统](/help/get-started/authoring.md#component-styling)。

## Edit Dialog {#edit-dialog}

通常，只需在站点的页面模板中添加和配置语言导航组件。 但是，如果需要将语言导航组件添加到单个内容页面，则通过编辑对话框，内容作者可以配置与设计对话框中所述的相 [同的值](#design-dialog)。

此外，您还可以设 **置ID**。 此选项允许控制HTML和数据层中组件的唯一标 [识符](/help/developing/data-layer/overview.md)。

* 如果留空，则会自动为您生成唯一ID，并可通过检查生成的页面找到该ID。
* 如果指定了ID，则作者有责任确保它是唯一的。
* 更改ID可能会影响CSS、JS和数据层跟踪。

![语言导航组件的编辑对话框](/help/assets/language-navigation-edit.png)
