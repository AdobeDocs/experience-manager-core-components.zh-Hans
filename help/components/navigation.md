---
title: 导航组件
description: 使用导航组件，用户可轻松地在全局化网站结构中导航。
role: Architect, Developer, Admin, User
exl-id: 9154f2a3-3d1e-4865-a413-298748fa66d3
source-git-commit: 327c239b02e0aecee878784c918bfa98d960530e
workflow-type: tm+mt
source-wordcount: '1540'
ht-degree: 100%

---

# 导航组件{#navigation-component}

使用导航组件，用户可轻松地在全局化网站结构中导航。

## 用途 {#usage}

导航组件列出页面树，这样网站的用户可以轻松地在网站结构中导航。

导航组件可以自动检测网站的全局化网站结构，[并自动适应本地化的页面。](#localized-site-structure)此外，它可以使用[影子重定向页面](#shadow-structure)支持任意网站结构，以展示您的主内容结构之外的其他结构。

利用[“编辑”对话框](#edit-dialog)，内容作者可以定义导航根页面以及导航深度。利用[“设计”对话框](#design-dialog)，模板作者可以定义导航根和深度的默认值。

## 版本和兼容性 {#version-and-compatibility}

导航组件的当前版本是 v2，此版本随 2022 年 2 月的核心组件发行版 2.18.0 的发布引入，具体说明见本文。

下表详细说明了该组件的所有受支持版本、与该组件的版本兼容的 AEM 版本以及指向早期版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v2 | - | 兼容 | 兼容 |
| [v1](v1/navigation.md) | 兼容 | 兼容 | 兼容 |

有关核心组件版本的更多信息，请参阅文档[核心组件版本](/help/versions.md)。

## 本地化网站结构支持 {#localized-site-structure}

网站通常以多种语言提供给不同区域。通常，每个本地化的页面将包含一个导航元素，该元素包括在页面模板中。使用导航组件，您可以在模板上为网站的所有页面放置一个导航元素，然后它可根据全局化的网站结构，自动适应单独的本地化页面。

* 有关导航组件本地化功能的工作方式示例，请参阅[以下部分](#example-localization)。
* 有关核心组件的本地化功能如何配合使用的示例，请参阅[核心组件页面的本地化功能](/help/get-started/localization.md)。

### 示例 {#example-localization}

假设您的内容与以下内容类似：

```
/content
+-- wknd
   +-- language-masters
      +-- de
         \-- experience
            \-- arctic-surfing-in-lofoten
      +-- en
         \-- experience
            \-- arctic-surfing-in-lofoten
      +-- es
      +-- fr
      \-- it
   +-- us
      +-- en
         \-- experience
            \-- arctic-surfing-in-lofoten
      \-- es
   \-- ch
      +-- de
         \-- experience
            \-- arctic-surfing-in-lofoten
      +-- fr
      \-- it
+-- wknd-events
\-- wknd-shop
```

对于站点 WKND，您可能希望将导航组件作为标头的一部分放置在页面模板上。将导航组件放到模板中之后，您可以将组件的&#x200B;**导航根**&#x200B;设置为 `/content/wknd/language-masters/en`，因为这是您网站的主内容的开始位置。您可能还希望将&#x200B;**导航结构深度**&#x200B;设置为 `2`，因为您可能不希望组件显示完整的内容树，而是只显示前两个级别，以将其用作概览。

使用&#x200B;**导航根**&#x200B;值，导航组件即可知道在 `/content/wknd/language-masters/en` 之后开始导航，并且可以向下递归网站的结构两级（如&#x200B;**导航结构深度**&#x200B;值所定义）来生成导航选项。

不论用户在查看什么本地化页面，导航组件都可以通过知道当前页面的位置，向后查找到根，然后前进到对应的页面，从而找到对应的本地化页面。

因此，如果访客查看 `/content/ch/de/experience/arctic-surfing-in-lofoten`，组件就会知道根据 `/content/wknd/language-masters/de` 生成导航结构。与此类似，如果访客查看 `/content/us/en/experience/arctic-surfing-in-lofoten`，组件就会知道根据 `/content/wknd/language-masters/en` 生成导航结构。

## 影子网站结构支持 {#shadow-structure}

有时候，需要为访客创建不同于实际网站结构的导航菜单。可能某个促销需要通过重新排列内容的列表，在菜单中突出显示特定内容。使用仅仅重定向到其他内容页面的影子页面，导航组件可以生成所需的任意导航结构。

为此，您需要：

1. 创建影子页面作为表示所需网站结构的空页面。这通常称为影子网站结构。
1. 在这些页面的页面属性中，将&#x200B;**重定向**&#x200B;值设置为指向实际内容页面。
1. 在影子页面的页面属性中，设置&#x200B;**在导航中隐藏**&#x200B;选项。
1. 将导航组件的&#x200B;**导航根**&#x200B;值设置为指向新影子网站结构的根。

然后导航组件将根据影子网站结构渲染菜单。组件渲染的链接指向影子页面重定向到的实际内容页面，而不是影子页面本身。此外，组件显示实际页面的名称并正确地突出显示活动页面，即使导航是基于影子页面。导航组件有效地使影子页面对访客完全透明。

>[!NOTE]
>影子页面使得导航选项更灵活，但请注意，以后此结构的维护是完全手动的。如果您重新排列实际网站内容或者添加/删除内容，则必须根据需要手动更新影子结构。

>[!NOTE]
>渲染影子网站结构时，导航逻辑只递归影子页面。该逻辑不会递归重定向目标的结构。

## 导航中的重定向 {#redirects}

如果页面具有重定向目标（无论它指向的是外部 URL 还是另一个 AEM 页面），则包含指向该点的链接的导航组件将直接指向重定向目标的 URL。

### 示例 {#redirect-example}

* 创建重定向到页面 B 的页面 A。
* 创建重定向到 `https://aemcomponents.dev` 的页面 C
* 在页面 D 上，插入包含页面 A 和 C 的导航组件
* 随后，生成的相应链接将直接指向页面 B 和 `https://aemcomponents.dev`

## 示例组件输出 {#sample-component-output}

要体验导航组件并查看其配置选项示例以及 HTML 和 JSON 输出，请访问[组件库](https://adobe.com/go/aem_cmp_library_navigation_cn)。

## 技术详细信息 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_navigation_v2_cn)有关导航组件的最新技术文档。

在[核心组件开发人员文档](/help/developing/overview.md)中可找到有关开发核心组件的其他详细信息。

>[!NOTE]
>
>截至核心组件版本 2.1.0，导航组件支持 [schema.org 微数据](https://schema.org)。

## “编辑”对话框 {#edit-dialog}

在“编辑”对话框中，内容作者可以定义导航的根页面以及导航结构的深度。

### “属性”选项卡 {#properties-tab}

![导航组件“编辑”对话框的“属性”选项卡](/help/assets/navigation-edit-properties.png)

* **导航根** - 用于生成导航树的根页面。
* **排除根级别** - 通常根不应包含在导航中。使用此选项，您可以指定从根开始往上，需要排除多少个级别。例如：
   * 0 = 显示根级别
   * 1 = 排除根级别
   * 2 = 排除根以及往上的 1 级
   * 以此类推。
* **收集所有子页面** - 收集导航根的所有子级页面。
* **导航结构深度** - 定义在导航树中，组件应相对于导航根向下显示多少级（仅在未选中&#x200B;**收集所有子页面**&#x200B;时可用）。
* **禁用影子** - 如果在层级中的页面是重定向的，则将显示重定向页面的名称而不是目标。有关更多信息，请参阅[影子网站结构支持](#shadow-structure)。
* **ID** - 利用此选项，可以控制 HTML 和 [Data Layer](/help/developing/data-layer/overview.md) 中的组件的唯一标识符。
   * 如果留空，系统会自动为您生成一个唯一 ID，可以通过检查结果页面找到该 ID。
   * 如果指定一个 ID，作者有责任确保它是唯一的。
   * 更改此 ID 会对 CSS、JS 和 Data Layer 跟踪产生影响。

### “辅助功能”选项卡 {#accessibility-tab}

![导航组件“编辑”对话框的“辅助功能”选项卡](/help/assets/navigation-edit-accessibility.png)

在&#x200B;**辅助功能**&#x200B;选项卡上，可以为组件的 [ARIA 辅助功能](https://www.w3.org/WAI/standards-guidelines/aria/)标签设置值。

* **标签** - 组件的 ARIA 标签属性的值

### “样式”选项卡 {#styles-tab-edit}

导航组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。

使用下拉菜单选择要应用于该组件的样式。在“编辑”对话框中所做的选择与从组件工具栏中选择的操作效果相同。

必须在[“设计”对话框](#design-dialog)中为此组件配置样式，以便下拉菜单可用。

![导航组件“编辑”对话框的“样式”选项卡](/help/assets/navigation-edit-styles.png)

## “设计”对话框 {#design-dialog}

模板作者可以使用“设计”对话框设置向内容作者显示的导航根页面和导航深度的默认值。

### “属性”选项卡 {#properties-tab-design}

![导航组件的“设计”对话框](/help/assets/navigation-design.png)

* **导航根** - 导航结构的根页面的默认值，该页面将用于生成导航树，在内容作者将组件添加到页面时使用该默认值。
* **排除根级别** - 通常根不应包含在导航中。使用此选项，您可以指定从根开始往上，需要默认排除多少个级别。例如：
   * 0 = 显示根级别
   * 1 = 排除根级别
   * 2 = 排除根以及往上的 1 级
   * 以此类推。
* **收集所有子页面** - 选项的默认值，将收集导航根的所有子级页面。
* **导航结构深度** - 导航结构深度的默认值。
* **禁用影子** - 在添加导航组件时是否应禁用影子的默认值。

### “样式”选项卡 {#styles-tab}

导航组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。

## Adobe Client Data Layer {#data-layer}

导航组件支持 [Adobe Client Data Layer](/help/developing/data-layer/overview.md)。
