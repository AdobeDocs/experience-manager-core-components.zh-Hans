---
title: 语言导航组件
description: 语言导航组件为站点提供语言/国家/地区导航，以便访客可以在不同区域设置中导航到同一页面。
role: Architect, Developer, Admin, User
exl-id: 10b218b4-c439-4a0f-a46f-0b15d78b0360
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '846'
ht-degree: 2%

---

# 语言导航组件{#language-navigation-component}

语言导航组件为站点提供语言/国家/地区导航，以便访客可以在不同区域设置中导航到同一页面。

## 使用 {#usage}

网站通常针对不同区域以多种语言提供。 语言导航组件允许访客以不同语言/区域设置查看同一页面。 因此，如果你是瑞士德语版网站的读者，你可以轻松地切换到同一页面的美国英语版。 语言导航组件可处理对站点语言结构的理解并自动查找相应的页面。

* 有关语言导航组件的本地化功能如何工作的示例，请参阅[下面的部分](#example)。
* 有关其他核心组件的本地化功能如何协同工作的示例，请参阅核心组件页面](/help/get-started/localization.md)的[本地化功能。

[编辑对话框](#edit-dialog)允许定义全局站点导航根目录以及导航应深入到的结构中。 使用[设计对话框](#design-dialog)，模板作者可以为相同选项设置默认值。

## 版本和兼容性 {#version-and-compatibility}

语言导航组件的当前版本为v1，该版本于2018年1月随核心组件2.0.0版引入，在本文档中进行了描述。

下表详细列出了组件的所有受支持版本、组件版本与之兼容的AEM版本，以及指向以前版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v1 | 兼容 | 兼容 | 兼容 |

有关核心组件版本和版本的更多信息，请参阅文档[核心组件版本](/help/versions.md)。

## 组件输出示例 {#sample-component-output}

要体验语言导航组件并查看其配置选项以及HTML和JSON输出的示例，请访问[组件库](https://adobe.com/go/aem_cmp_library_langnav)。

## 技术详细信息 {#technical-details}

有关语言导航组件[的最新技术文档，请参阅GitHub](https://adobe.com/go/aem_cmp_tech_langnav_v1)。

有关开发核心组件的更多详细信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## “设计”对话框 {#design-dialog}

编辑对话框允许定义全局站点导航根目录以及导航在结构中的深度。

通常，只需在页面模板级别完成这些配置。 但是，可以通过[编辑对话框](#edit-dialog)在页面级别更改它们。

### “属性”选项卡 {#properties-tab}

![语言导航组件的设计对话框](/help/assets/language-navigation-design.png)

* **导航根目录**
   * 这是网站语言导航的起始位置。
   * 站点的语言结构从此根下的下一级开始。
* **语言结构深度**
   * 这是&#x200B;**导航根**&#x200B;下的内容树级别代表站点的语言结构。 示例：
      * `1` 通常意味着您只有语言选项。
      * `2` 通常意味着您可以选择语言和国家/地区。
      * `3` 通常意味着您可以选择语言、国家/地区和地区。

#### 示例 {#example}

假设您的内容如下所示：

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

对于网站WKND，您可能希望将语言导航组件作为标题的一部分放置在页面模板上。 模板的一部分后，您可以将组件的&#x200B;**导航根**&#x200B;设置为`/content/wknd`，因为这是该站点的本地化内容的开始位置。 您还希望将&#x200B;**语言结构深度**&#x200B;设置为`2`，因为您的结构是两个级别（国家/地区，语言）。

使用&#x200B;**导航根**&#x200B;值，语言组件知道在`/content/wknd`导航开始后，它可以通过识别内容树中的后两个级别作为站点的语言导航结构（由&#x200B;**语言结构深度**&#x200B;值定义）来生成语言导航选项。

无论用户查看的是什么页面，语言导航组件都能够以其他语言找到相应的页面，方法是知道当前页面的位置并向后工作到根页面，然后转到相应的页面。

### “样式”选项卡 {#styles-tab}

语言导航组件支持AEM [样式系统](/help/get-started/authoring.md#component-styling)。

## 编辑对话框 {#edit-dialog}

通常，只需在网站的页面模板中添加和配置语言导航组件即可。 但是，如果语言导航组件需要添加到单个内容页面，则编辑对话框允许内容作者配置与[设计对话框](#design-dialog)中所述的相同值。

此外，您还可以设置&#x200B;**ID**。 此选项允许控制HTML和[数据层](/help/developing/data-layer/overview.md)中组件的唯一标识符。

* 如果留为空白，则会自动为您生成唯一ID，并且可以通过检查生成的页面找到该ID。
* 如果指定了ID，则作者有责任确保该ID是唯一的。
* 更改ID可能会影响CSS、JS和数据层跟踪。

![语言导航组件的编辑对话框](/help/assets/language-navigation-edit.png)

## Adobe客户端数据层 {#data-layer}

语言导航组件支持[Adobe客户端数据层。](/help/developing/data-layer/overview.md)
