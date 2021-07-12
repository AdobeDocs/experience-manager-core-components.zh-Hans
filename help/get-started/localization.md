---
title: 核心组件的本地化功能
description: 核心组件的本地化功能
role: Architect, Developer, Admin, User
exl-id: 9140b65a-6dd7-4ec9-9095-6e8243ec8424
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '725'
ht-degree: 0%

---

# 核心组件的本地化功能 {#localization-features-of-the-core-components}

许多网站要求以跨多种语言和地理区域的本地化格式提供内容。 所选核心组件具有智能参考分辨率，可简化为所有本地化内容创建统一模板的过程，这些模板会根据您的本地化网站结构自动进行调整。

## 示例 — 包含导航和页脚的本地化页面 {#example}

大多数网站都要求所有页面中都有一个页脚。 这些页脚在页面的所有内容中通常保持一致。 但是，对于本地化内容页面，需要显示该页眉或页脚的本地化版本。

同样，导航组件通常必须在所有页面中显示。 但是，它也需要反映本地化页面的内容。

使用[导航核心组件](/help/components/navigation.md)和[体验片段核心组件](/help/components/experience-fragment.md)的本地化功能，以及AEM](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)的[可编辑模板，这将变成一项简单的任务。 该示例还可进一步扩展为使用[语言导航组件](/help/components/language-navigation.md)。

## 内容结构 {#content-structure}

AEM及其核心组件的所有本地化功能都依赖于清晰且符合逻辑的内容结构来提供本地化内容。

假设您的网站名为`my-site`，位于以下位置：

```
/content/my-site
```

还可以说，您使用英文创作网站，并以法语提供网站。 因此，如果您有一个名为`my-page`的简单页面，则会在网站内容树的两个本地化分支中找到该页面：

```
/content
\-- my-site
   +-- en
       \-- my-page
   \-- fr
       \-- my-page
```

它位于这些本地化分支下，您将在其中创建其他网站页面。

页脚通常使用体验片段制作，因此您需要像页面一样的英文和法文版本。 但是，体验片段不是页面，而是可以在页面之间重复使用的页面的一部分，因此它们不会直接位于`/content`下方，作为页面的其余部分。 相反，它们位于自己的文件夹下，但由于它们还必须进行本地化，因此其结构必须与您网站的本地化结构相映射。

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

核心组件通过镜像的本地化结构可以找到相应页面所需的本地化内容。

## 页脚 — 体验片段 {#xf-footer}

体验片段组件非常灵活，非常适合用于页眉或页脚。

由于我们假定的网站提供英语和法语版，因此我们需要创建两个体验片段，这两个片段都名为`footer` [，位于我们之前介绍的位置。](#content-structure)

![](/help/assets/screen-shot-2019-09-09-11.08.28.png)

## 页面模板 {#template}

由于页脚将显示在每个页面上，因此我们需要将体验片段添加到我们的标准页面模板中。

我们的模板简单地称为`my-template`，与我们的其他模板一起提供：

```
/conf/my-site/settings/wcm/templates/my-template
```

在此模板中，我们将添加我们希望页面所基于的基本组件。

* [导航组件](/help/components/navigation.md)
   * 导航组件将显示在每个页面的顶部。
   * 在导航组件中，我们定义导航根，告知组件站点的导航结构开始的位置。
   * 组件可根据导航根自动找到相应的本地化内容。
* [容器组件](/help/components/container.md)
   * 每个页面都将包含一个可编辑的容器组件，以便作者可以在页面上放置其他内容。
* [体验片段](/help/components/experience-fragment.md)
   * 我们将体验片段组件指向我们创作语言中表示页脚的片段路径。
   * 根据该片段的路径和反映本地化页面结构的体验片段的结构，组件可以自动找到相应的本地化内容。

   ![](/help/assets/screen-shot-2019-09-09-11.20.10.png)

## 页面 {#pages}

通过努力设置网站结构和模板，内容作者只需在页面中添加必要的内容即可。 由于组件具有模板和本地化逻辑，因此导航和页脚将自动添加到页面并进行本地化。

例如，作者只需将文本组件等内容添加到英语和法语页面（下面以蓝色表示）即可。

导航组件和体验片段组件来自页面模板，它们知道如何根据本地化结构和页面本身的位置（如下面的白色所示）自动显示正确的内容。

![](/help/assets/screen-shot-2019-09-09-11.22.14.png)

## 把它装在一起 {#fitting-it-all-together}

以下是这些简单但功能强大的元素如何协同工作来为内容作者提供本地化页面的完整图片。

![](/help/assets/screen-shot-2019-09-09-11.27.58.png)
