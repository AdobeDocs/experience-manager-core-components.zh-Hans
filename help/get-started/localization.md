---
title: 核心组件的本地化功能
description: 核心组件的本地化功能
role: 架构师、开发人员、管理员、业务从业者
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '730'
ht-degree: 0%

---


# 核心组件{#localization-features-of-the-core-components}的本地化功能

许多网站要求以本地化格式跨多种语言和地域提供内容。 选定的核心组件具有智能参考分辨率，可简化为所有本地化内容创建一个统一模板的过程，这些模板将根据您的本地化网站结构自动调整。

## 示例 — 具有导航和页脚的本地化页面{#example}

大多数站点要求所有页面都显示一个页脚。 这些页脚在页面的所有内容中通常保持一致。 但是，对于本地化内容页面，需要显示该页眉或页脚的本地化版本。

同样，导航组件通常必须在所有页面上显示。 但是，它还需要反映本地化页面的内容。

使用[导航核心组件](/help/components/navigation.md)和[体验片段核心组件](/help/components/experience-fragment.md)的本地化功能以及AEM](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)的[可编辑模板，这将变为简单的任务。 该示例还可进一步扩展以使用[语言导航组件](/help/components/language-navigation.md)。

## 内容结构{#content-structure}

AEM及其核心组件的所有本地化功能都依赖于一个清晰、符合逻辑的内容结构来实现本地化内容。

假设您的站点名为`my-site`，位于以下位置：

```
/content/my-site
```

还可以说，您使用英语创作网站，并使用法语优惠网站。 因此，如果您有一个名为`my-page`的简单页面，则该页面位于站点内容树中的两个本地化分支中：

```
/content
\-- my-site
   +-- en
       \-- my-page
   \-- fr
       \-- my-page
```

它位于这些本地化分支下，您将在其中创建其他站点页面。

页脚通常使用体验片段制作，因此您需要的英语和法语版本与页面相同。 但是，体验片段不是页面，而是可跨页面重复使用的页面的一部分，因此它们不会直接位于`/content`下方作为您的其余页面。 相反，它们位于自己的文件夹下，但由于它们也必须本地化，因此它们的结构必须与站点的本地化结构相反。

```
/content
+-- experience-fragments
   +-- en
      \-- footer
   \-- fr
      \-- footer
\-- my-site
   +-- en
      \-- my-page
   \-- fr
      \-- my-page
```

通过镜像的本地化结构，核心组件可以找到对应页面所需的本地化内容。

## Page Footer — 体验片段{#xf-footer}

体验片段组件非常灵活，非常适合页眉或页脚。

由于我们假想的网站提供英语和法语版本，因此我们需要创建两个体验片段，这两个片段都在我们之前介绍的位置中称为`footer` [。](#content-structure)

![](/help/assets/screen-shot-2019-09-09-11.08.28.png)

## 页面模板 {#template}

由于页脚将显示在每个页面上，因此我们需要将体验片段添加到我们的标准页面模板中。

我们的模板只称为`my-template`，它位于我们的其他模板中：

```
/conf/my-site/settings/wcm/templates/my-template
```

在此模板中，我们将添加我们希望页面所基于的基本组件。

* [导航组件](/help/components/navigation.md)
   * 导航组件将显示在每个页面的顶部。
   * 在导航组件中，我们定义导航根，告知组件站点的导航结构开始。
   * 根据导航根，组件可以自动找到相应的本地化内容。
* [容器组件](/help/components/container.md)
   * 每个页面都将包含一个可编辑的容器组件，这样作者就可以在页面上放置其他内容。
* [体验片段](/help/components/experience-fragment.md)
   * 我们使用我们的创作语言将体验片段组件指向片段路径，该语言代表页脚。
   * 根据该片段的路径和反映本地化页面结构的体验片段的结构，组件可以自动找到相应的本地化内容。

   ![](/help/assets/screen-shot-2019-09-09-11.20.10.png)

## 页面 {#pages}

通过在设置站点结构和模板时进行艰苦的工作，内容作者只需向页面中添加必要的内容。 借助模板和组件的本地化逻辑，导航和表尾将自动添加到页面并本地化。

例如，作者只需向英文和法文页面添加文本组件等内容（以下蓝色表示）。

导航组件和体验片段组件来自页面模板，它们知道根据本地化结构和页面本身的位置（在下面以白色表示）自动显示正确的内容。

![](/help/assets/screen-shot-2019-09-09-11.22.14.png)

## 将它整合在一起{#fitting-it-all-together}

以下是这些简单但强大的元素如何相互配合以为内容作者提供本地化页面的完整说明。

![](/help/assets/screen-shot-2019-09-09-11.27.58.png)
