---
title: Teaser组件
seo-title: Teaser组件
description: Teaser组件可显示图像、标题、富文本以及可选链接到进一步内容。
seo-description: Teaser组件可显示图像、标题、富文本以及可选链接到进一步内容。
uuid: 46989314-df37-448b-8562-c707043 f2160
contentOwner: Bohnert
content-type: 引用
topic-tags: 核心组件
discoiquuid: e597c18e-3643-41be -9788-a7872 f1 ab90
translation-type: tm+mt
source-git-commit: eef608fb06001485aa2c2c0b574af412ed7f15a4

---


# Teaser Component{#teaser-component}

核心组件Teaser组件可显示图像、标题、富文本以及可选链接到进一步内容。

## 使用情况 {#usage}

Teaser组件允许内容作者轻松创建使用图像、标题或丰富文本并链接到其他内容或其他操作的Teaser。

The template author can use the [design dialog](#design-dialog) to define if the options to create call-to-actions and add links are available as well as disabling various display options. The content author can use the [configure dialog](#configure-dialog) to set an image, define CTAs, set titles and descriptions, and configure links to the individual teaser. [可以访问](image.md#edit-dialog)[图像组件](image.md) 的编辑对话框以修改Teaser图像。

## Version and Compatibility {#version-and-compatibility}

Teaser组件的当前版本为v1，该版本是在2018年月核心组件中引入的，它是在核心组件中引入的，它在文档中进行了介绍。

下表详细说明了组件的所有支持版本、组件版本的AEM版本以及以前版本的文档链接。

| 组件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|---|---|---|---|
| v1 | 兼容 | 兼容 | 兼容 |

## Sample Component Output {#sample-component-output}

To experience the Teaser Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library/teaser.html).

### Technical Details {#technical-details}

The latest technical documentation about the Teaser Component [can be found on GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/teaser/v1/teaser).

Further details about developing Core Components can be found in the [Core Components developer documentation](developing.md).

## Configure Dialog {#configure-dialog}

内容作者可以使用配置对话框定义单个Teaser的属性。There is also an [edit dialog](#edit-dialog) to modify the teaser image if one is selected.

### 图像 {#image}

![](assets/screen_shot_2018-07-03at104125.png)

* **图像资产**
   * Drop an asset from the [asset browser](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/author-environment-tools.html) or tap the **browse** option to upload from a local file system.
   * Tap or click **Clear** to de-select the currently selected image.
   * Tap or click **Edit** to [mange the renditions of the asset](https://helpx.adobe.com/experience-manager/6-5/assets/using/managing-assets-touch-ui.html) in the asset editor.

### 文本 {#text}

![](assets/screen_shot_2018-07-03at104138.png)

* **标题** 定义要作为Teaser标题显示的标题。
* **从链接页面** 获取标题在选中后，标题将填充链接页面的标题。
* **描述** 定义要显示为Teaser子标题的描述。
* **获取链接页面** 的说明后，将使用链接页面的描述填充描述。

### Links &amp; Actions {#links-actions}

![](assets/screen_shot_2018-07-03at104146.png)

* **链接** 链接应用于Teaser。使用路径浏览器选择链接目标。
* **选中“在选中时** 启用行动动员”选项可定义“行动动员”的定义。列表中的第一个“调用行动动员”链接用作其他Teaser元素的链接。

## Edit Dialog {#edit-dialog}

The Teaser Component delegates image rendering to the [Image Component](image.md). Therefore the [edit dialog](image.md#edit-dialog of the Image Component is available to the content author to manipulate the teaser image.

## Design Dialog {#design-dialog}

设计对话框允许模板作者定义内容作者在使用此组件时所拥有的Teaser选项。

### Teaser Tab {#teaser-tab}

![](assets/screen_shot_2018-07-03at105958.png)

* **行为召唤**
   * **为内容作者禁用“调用行动**”隐藏“ **行动动员”** 选项
* **元素**
   * **隐藏标题**
      * Hides the **Title** option for content authors
      * When selected the **Title Type** is hidden
   * **隐藏说明** 隐藏内容作者 **的说明** 选项
* **标题类型** 定义要由Teaser标题使用的H标记。
* **链接**
   * **不链接图像** 当选定时，Teaser图像未链接
   * **不链接标题** 当选中时，Teaser标题未链接

### Styles Tab {#styles-tab}

The Teaser Component supports the AEM [Style System](authoring.md#component-styling).
