---
title: 核心组件的本地化功能
seo-title: 核心组件的本地化功能
description: 核心组件的本地化功能
seo-description: 核心组件的本地化功能
content-type: reference
topic-tags: core-components
index: y
internal: n
translation-type: tm+mt
source-git-commit: 0f84eb6d52b9d6d76a4347d371367acf3d34e58e

---


# 核心组件的本地化功能 {#localization-features-of-the-core-components}

许多网站需要以本地化格式跨多种语言和地域提供内容。 选定的核心组件采用智能参考分辨率，可轻松为所有本地化内容创建统一的模板，这些模板会根据本地化的站点结构自动调整。

## 示例——带有导航和表尾的本地化页面 {#example}

大多数站点都需要在所有页面中显示页脚。 这些页脚在页面的所有内容中通常保持一致。 但是，对于本地化内容页面，需要显示该页眉或页脚的本地化版本。

同样，导航组件通常必须显示在所有页面上。 但是，它还需要反映本地化页面的内容。

使用导航核心组件和 [体验片段核心组件的本地化功能](navigation.md) ，以及AEM [的可编辑模板](experience-fragment.md)[](https://docs.adobe.com/content/help/en/experience-manager-64/authoring/siteandpage/templates.html)，这将变成一项简单的任务。 该示例还可以进一步扩展以使用 [语言导航组件](language-navigation.md) 。

## 内容结构 {#content-structure}

AEM及其核心组件的所有本地化功能都依赖于一个清晰、逻辑的本地化内容结构。

假设您的站点只是被称为，并 `my-site` 位于此处：

```
/content/my-site
```

还可以说，您使用英语创作网站并以法语提供。 因此，如果您有一个名为的简单页 `my-page` 面，该页面将位于站点内容树中的两个本地化分支中：

```
/content
\-- my-site
   +-- en
       \-- my-page
   \-- fr
       \-- my-page
```

它位于这些本地化分支下，您将在其中创建其他站点页面。

页脚通常使用体验片段制作，因此您需要像页面一样的英语和法语版本。 但是，体验片段不是页面，而是可以跨页面重复使用的页面部分，因此它们不会直接位于您的其余页 `/content` 面下方。 相反，它们位于自己的文件夹下，但由于它们也必须进行本地化，因此其结构必须与站点的本地化结构相反。

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

通过镜像的本地化结构，核心组件才能找到相应页面所需的本地化内容。

## 页脚——体验片段 {#xf-footer}

体验片段组件非常灵活，非常适合页眉或页脚。

由于我们假设的网站提供英语和法语版本，因此我们需要创建两个体验片段，这两个片段都在我们之 `footer` 前 [描述的位置中调用。](#content-structure)

![](assets/screen-shot-2019-09-09-11.08.28.png)

## 页面模板 {#template}

由于页脚将显示在每页上，因此我们需要将体验片段添加到我们的标准页面模板中。

我们的模板只需调用， `my-template` 并且与我们的其他模板一起使用：

```
/conf/my-site/settings/wcm/templates/my-template
```

在此模板中，我们将添加我们希望页面基于的基本组件。

* [导航组件](navigation.md)
   * 导航组件将显示在每页的顶部。
   * 在导航组件中，我们定义导航根目录，告诉组件站点的导航结构开始的位置。
   * 根据导航根目录，组件可以自动找到相应的本地化内容。
* [容器组件](container.md)
   * 每个页面都将包含一个可编辑的容器组件，这样作者就可以在页面上放置其他内容。
* [体验片段](experience-fragment.md)
   * 我们将体验片段组件指向我们创作语言中表示页脚的片段路径。
   * 根据该片段的路径和反映本地化页面结构的体验片段的结构，组件可以自动找到相应的本地化内容。
   ![](assets/screen-shot-2019-09-09-11.20.10.png)

## 页面 {#pages}

通过在设置站点结构和模板时进行艰苦的工作，内容作者只需向页面添加必要的内容。 由于这些模板和组件的本地化逻辑，导航和表尾将自动添加到页面并进行本地化。

例如，作者只需向英语和法语页面（在下面以蓝色表示）添加文本组件等内容。

导航组件和体验片段组件来自页面模板，并且知道根据本地化结构和页面本身的位置（如下面的白色表示）自动显示正确的内容。

![](assets/screen-shot-2019-09-09-11.22.14.png)

## 将其整合在一起 {#fitting-it-all-together}

下面是这些简单但功能强大的元素如何协同工作来为内容作者提供本地化页面的完整说明。

![](assets/screen-shot-2019-09-09-11.27.58.png)
