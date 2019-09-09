---
title: 核心组件的本地化功能
seo-title: 核心组件的本地化功能
description: 核心组件的本地化功能
seo-description: 核心组件的本地化功能
content-type: 引用
topic-tags: 核心组件
index: y
internal: n
translation-type: tm+mt
source-git-commit: 4af4873edf290f93733b0997b0e7a19c6c9e26f2

---


# 核心组件的本地化功能 {#localization-features-of-the-core-components}

许多网站要求以本地化格式提供跨多种语言和地理位置的内容。核心组件具有智能参考功能，可让您轻松地为所有本地化内容创建统一的模板，以便根据您的本地化站点结构自动调整。

## 示例-带有导航和页脚的本地化页面 {#example}

大多数站点需要在所有页面上显示页脚。这些页脚通常在页面的所有内容中保持一致。但是，对于本地化的内容页面，需要显示该标题或页脚的本地化版本。

同样，通常必须在所有页面中显示导航组件。但是，它还需要反映本地化页面的内容。

使用 [导航核心组件](navigation.md) 和 [体验片段核心组件](experience-fragment.md) 的本地化功能以及AEM [的可编辑模板](https://docs.adobe.com/content/help/en/experience-manager-64/authoring/siteandpage/templates.html)。

## 内容结构 {#content-structure}

AEM及其核心组件的所有本地化功能都依赖于本地化内容的清晰、逻辑内容结构。

假设您的站点被简单调用 `my-site` ，位于这里：

```
/content/my-site
```

还可以说，您用英语创作了您的站点，并提供法语版本。因此，如果您在站点内容树中有一个简单的页面，将在两个本地化分支中调用 `my-page` 它：

```
/content
\-- my-site
   +-- en
       \-- my-page
   \-- fr
       \-- my-page
```

在这些本地化分支下，您可以创建其他站点页面。

页面页脚通常使用体验片段制作，因此您需要像页面一样需要英语和法语版本。但是，体验片段不是页面，而是可以重复使用的页面部分，因此它们不会直接作为 `/content` 页面的其余部分。它们位于自己的文件夹下，但由于还必须本地化，因此他们的结构必须镜像站点的本地化结构。

```
/content
+-- experience-fragments
   +-- en
      +-- footer
   \-- fr
      +-- footer
\-- my-site
   +-- en
      \-- my-page
   \-- fr
      \-- my-page
```

核心组件通过镜像的本地化结构，可找到对应页面的必要本地化内容。

## Page Footer-体验片段 {#footer}

体验片段组件非常灵活，适合页面页眉或页脚。

因为我们的假设网站是以英语和法语提供的，我们将需要创建两个体验片段，这两个片段都是在 `footer`[我们之前描述的位置进行调用的。](#content-structure)

![](assets/screen-shot-2019-09-09-11.08.28.png)

## 页面模板 {#template}

由于页脚将显示在每个页面上，我们需要将体验片段添加到标准页面模板。

我们只调用 `my-template` 我们的模板并使用我们的其他模板：

```
/conf/my-site/settings/wcm/templates/my-template
```

在此模板中，我们将添加希望页面基于的基本组件。

* [导航组件](navigation.md)
   * 导航组件将显示在每个页面的顶部。
   * 在导航组件中，我们定义导航根目录，告知站点的导航结构开始的位置。
   * 组件可基于导航根目录自动找到相应的本地化内容。
* 布局容器
   * 每个页面都将包含一个可编辑的布局容器组件，以便作者能够在页面上放置其他内容。
* [体验片段](experience-fragment.md)
   * 我们将Experience Frage Compagent组件指向我们的片段的创作语言片段路径，该片段表示页脚。
   * 该组件基于该片段的路径和镜像本地化页面结构的体验片段的结构，可自动找到相应的本地化内容。
   ![](assets/screen-shot-2019-09-09-11.20.10.png)

## 页面 {#pages}

通过在设置站点结构和模板中执行繁重工作，作者只需为页面添加必要的内容。由于组件的本地化逻辑，导航和表尾将自动本地化。

例如，作者只需将文本组件添加到英语和法语页面(以蓝色表示)。

导航组件和体验片段组件知道根据本地化结构和页面本身的位置自动显示正确的内容(以下面的白色表示)。

![](assets/screen-shot-2019-09-09-11.22.14.png)

## 全部配合 {#fitting-it-all-together}

以下全面了解这些简单但强大的元素如何协同工作，为内容作者提供本地化页面。

![](assets/screen-shot-2019-09-09-11.27.58.png)
