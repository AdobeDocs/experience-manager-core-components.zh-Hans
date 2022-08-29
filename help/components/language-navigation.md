---
title: 语言导航组件
description: 语言导航组件提供对站点的语言/国家或地区导航，以便访客能够导航到采用不同区域设置的相同页面。
role: Architect, Developer, Admin, User
exl-id: 10b218b4-c439-4a0f-a46f-0b15d78b0360
source-git-commit: 327c239b02e0aecee878784c918bfa98d960530e
workflow-type: tm+mt
source-wordcount: '957'
ht-degree: 100%

---

# 语言导航组件{#language-navigation-component}

语言导航组件提供对站点的语言/国家或地区导航，以便访客能够导航到采用不同区域设置的相同页面。

## 用途 {#usage}

网站通常以多种语言提供给不同区域。利用语言导航组件，访客可查看采用不同语言/区域设置的相同页面。因此，如果您访问的是网站的瑞士德语版，则可以轻松切换到相同页面的美国英语版。利用语言导航组件，可以了解站点语言结构并自动查找相应页面。

* 有关语言导航组件本地化功能的工作方式示例，请参阅[以下部分](#example)。
* 有关其他核心组件的本地化功能如何配合使用的示例，请参阅[核心组件页面的本地化功能](/help/get-started/localization.md)。

利用[“编辑”对话框](#edit-dialog)，可以定义全局站点导航根目录以及结构中的导航深度。利用[“设计”对话框](#design-dialog)，模板作者可以设置相同选项的默认值。

## 版本和兼容性 {#version-and-compatibility}

语言导航组件的当前版本是 v2，此版本随 2022 年 2 月的核心组件发行版 2.18.0 的发布引入，具体说明见本文。

下表详细说明了该组件的所有受支持版本、与该组件的版本兼容的 AEM 版本以及指向早期版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v2 | - | 兼容 | 兼容 |
| [v1](v1/language-navigation.md) | 兼容 | 兼容 | 兼容 |

有关核心组件版本的更多信息，请参阅文档[核心组件版本](/help/versions.md)。

## 示例组件输出 {#sample-component-output}

要体验语言导航组件并查看其配置选项示例以及 HTML 和 JSON 输出，请访问[组件库](https://adobe.com/go/aem_cmp_library_langnav_cn)。

## 技术详细信息 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_langnav_v2_cn)有关语言导航组件的最新技术文档。

在[核心组件开发人员文档](/help/developing/overview.md)中可找到有关开发核心组件的其他详细信息。

## “设计”对话框 {#design-dialog}

利用“设计”对话框，可以定义全局站点导航根目录以及结构中的导航深度。

通常，这些配置只需在页面模板级别完成。不过，可通过[“编辑”对话框](#edit-dialog)在页面级别对其进行更改。

### “属性”选项卡 {#properties-tab}

![语言导航组件的“设计”对话框](/help/assets/language-navigation-design.png)

* **导航根目录**
   * 应从该位置开始站点的语言导航。
   * 站点的语言结构始于此根目录下的下一个级别。
* **语言结构深度**
   * **导航根目录**&#x200B;下的内容树的级别数代表了站点的语言结构。示例：
      * `1` 通常意味着您只能选择语言。
      * `2` 通常意味着您可以选择语言和国家/地区。
      * `3` 通常意味着您可以选择语言、国家/地区和区域。

#### 示例 {#example}

假设您的内容与以下内容类似：

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

对于站点 WKND，您可能希望将语言导航组件作为标头的一部分放置在页面模板上。在将组件放入模板中后，您可以将组件的&#x200B;**导航根目录**&#x200B;设置为 `/content/wknd`，因为这是您站点的本地化内容的开始位置。您还需要将&#x200B;**语言结构深度**&#x200B;设置为 `2`，因为您的结构包含两个级别（依次为国家/地区和语言）。

利用&#x200B;**导航根目录**&#x200B;值，语言导航组件获知在 `/content/wknd` 之后开始导航，并且可以通过将内容树中的下两个级别视为站点的语言导航结构（如&#x200B;**语言结构深度**&#x200B;值所定义）来生成语言导航选项。

不论用户在查看什么页面，语言导航组件都可以通过知道当前页面的位置，向后查找到根目录，然后前进到对应的页面，从而找到采用另一种语言的相应页面。

### “样式”选项卡 {#styles-tab}

语言导航组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。

## “编辑”对话框 {#edit-dialog}

### “属性”选项卡 {#properties-tab-edit}

通常，只需在站点的页面模板中添加和配置语言导航组件。不过，如果需要将语言导航组件添加到单个内容页面，内容作者可以利用“编辑”对话框配置[“设计”对话框](#design-dialog)中描述的相同值。

此外，您可以设置 **ID**。利用此选项，可以控制 HTML 和 [Data Layer](/help/developing/data-layer/overview.md) 中的组件的唯一标识符。

* 如果留空，系统会自动为您生成一个唯一 ID，可以通过检查结果页面找到该 ID。
* 如果指定一个 ID，作者有责任确保它是唯一的。
* 更改此 ID 会对 CSS、JS 和 Data Layer 跟踪产生影响。

![语言导航组件的“编辑”对话框](/help/assets/language-navigation-edit.png)

### “辅助功能”选项卡 {#accessibility-tab}

* **标签** - 如果页面上有多个语言导航来设置组件的 aria 标签属性，则应定义此选项。

![语言导航组件的“辅助功能”选项卡](/help/assets/language-navigation-edit-accessibility.png)

### “样式”选项卡 {#styles-tab-edit}

语言导航组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。

使用下拉菜单选择要应用于该组件的样式。在“编辑”对话框中所做的选择与从组件工具栏中选择的操作效果相同。

必须在[“设计”对话框](#design-dialog)中为此组件配置样式，以便下拉菜单可用。

![语言导航组件“编辑”对话框的“样式”选项卡](/help/assets/language-navigation-edit-styles.png)

## Adobe Client Data Layer {#data-layer}

语言导航组件支持 [Adobe Client Data Layer](/help/developing/data-layer/overview.md)。
