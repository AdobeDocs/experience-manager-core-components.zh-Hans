---
title: 核心组件的本地化功能
description: 核心组件的本地化功能
role: Architect, Developer, Admin, User
exl-id: 9140b65a-6dd7-4ec9-9095-6e8243ec8424
source-git-commit: 888719359f9a1d1c9dccff97fb639b332f2be54c
workflow-type: tm+mt
source-wordcount: '723'
ht-degree: 100%

---

# 核心组件的本地化功能 {#localization-features-of-the-core-components}

许多网站要求以本地化格式跨多种语言和地域提供内容。选定的核心组件具有智能参考解析功能，可轻松为所有本地化内容创建一个统一的模板，此模板会自动根据本地化站点结构进行调整。

## 示例 - 带导航和页脚的本地化页面 {#example}

大多数站点都要求跨所有页面显示页脚。通常，这些页脚在页面的所有内容中是一致的。不过，对于本地化的内容页面，需要显示该页眉或页脚的本地化版本。

同样，导航组件通常必须跨所有页面显示。但它还需要反映本地化页面的内容。

通过将[导航核心组件](/help/components/navigation.md)和[体验片段核心组件](/help/components/experience-fragment.md)的本地化功能与 [AEM 的可编辑模板](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)结合使用，可轻松完成此任务。也可以进一步扩展此示例以使用[语言导航组件](/help/components/language-navigation.md)。

## 内容结构 {#content-structure}

AEM 及其核心组件的所有本地化功能都依赖本地化内容的清楚合理的内容结构。

假定您的站点称作 `my-site` 并位于此处：

```
/content/my-site
```

假定您用英语创作您的站点并提供其法语版本。如果您有一个称作 `my-page` 的简单页面，则会在站点的内容树中找到该页面的两个本地化分支：

```
/content
\-- my-site
   +-- en
       \-- my-page
   \-- fr
       \-- my-page
```

您将在这两个本地化分支下创建其他站点页面。

通常将使用体验片段创建页脚，因此您将同时需要英语版和法语版，就像您的页面一样。然而，体验片段不是页面，而是能够跨页面重复使用的页面部分，因此它们并不会作为页面的其余部分直接位于 `/content` 下。相反，体验片段位于自己的文件夹下，但由于它们也必须进行本地化，因此其结构必须镜像站点的本地化结构。

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

利用镜像的本地化结构，核心组件可以为相应的页面找到必要的本地化内容。

## 页脚 - 体验片段 {#xf-footer}

体验片段组件很灵活，非常适用于页眉或页脚。

由于我们假定的网站具有英语版和法语版，因此我们需要[在之前描述的位置](#content-structure)创建两个称作 `footer` 的体验片段。

![](/help/assets/screen-shot-2019-09-09-11.08.28.png)

## 页面模板 {#template}

由于页脚将显示在每个页面上，因此我们需要将体验片段添加到我们的标准页面模板中。

我们的模板称作 `my-template` 并且与其他模板位于同一位置：

```
/conf/my-site/settings/wcm/templates/my-template
```

在此模板中，我们将添加需作为页面基础的基本组件。

* [导航组件](/help/components/navigation.md)
   * 导航组件将显示在每个页面的顶部。
   * 在导航组件中，我们定义了导航根目录，以便组件获知站点的导航结构的开始位置。
   * 该组件会自动根据导航根目录查找对应的本地化内容。
* [容器组件](/help/components/container.md)
   * 每个页面都将包含一个可编辑的容器组件，以便作者能够在页面上放置其他内容。
* [体验片段](/help/components/experience-fragment.md)
   * 我们将体验片段组件指向代表页脚的片段的创作语言中的片段路径。
   * 此组件会自动根据片段的路径和镜像本地化页面结构的体验片段的结构来查找相应的本地化内容。

   ![](/help/assets/screen-shot-2019-09-09-11.20.10.png)

## 页面 {#pages}

通过尽可能将站点结构和模板设置得完善，内容作者只需将必要内容添加到页面即可。得益于模板和组件的本地化逻辑，导航和页脚将自动添加到页面并进行本地化。

例如，作者只需将文本组件等内容添加到英语版页面和法语版页面（下面用蓝色表示）。

导航组件和体验片段组件来自页面模板，它们会自动根据本地化结构和页面本身的位置（下图用白色表示）显示正确的内容。

![](/help/assets/screen-shot-2019-09-09-11.22.14.png)

## 整合所有元素 {#fitting-it-all-together}

下面全面介绍了这些简单且功能强大的元素如何共同为内容作者提供本地化的页面。

![](/help/assets/screen-shot-2019-09-09-11.27.58.png)
