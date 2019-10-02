---
title: 嵌入组件
seo-title: 嵌入组件
description: The Embed Component enables embedding external content in an AEM content page.
seo-description: he Embed Component enables embedding external content in an AEM content page.
content-type: 引用
topic-tags: core-components
translation-type: tm+mt
source-git-commit: 97f1461b57079806f9f96d325d9b763538e32127

---


# Embed Component{#embed-component}

The Core Components Embed Component allows embedding external content in an AEM content page.

## 使用情况 {#usage}

The Core Component Embed Component allows the content author to define selected external content to be embedded within an AEM content page. 此外，还有一个选项可定义要嵌入的自由形式HTML。

* 组件的属性可以在配置对话框中 [定义](#configure-dialog)。
* 将组件添加到页面时的默认值可以在设计对话框中 [定义](#design-dialog)。

## 版本和兼容性 {#version-and-compatibility}

嵌入组件的当前版本为v1，该版本于2019年9月随核心组件的2.7.0版一起推出，本文档对此进行了说明。

下表详细列出了组件的所有受支持版本、与组件版本兼容的AEM版本，以及指向先前版本的文档的链接。

| 组件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |---|
| v1 | 兼容 | 兼容 | 兼容 |

有关核心组件版本和版本的详细信息，请参阅文档核 [心组件版本](versions.md)。

## Sample Component Output {#sample-component-output}

要体验嵌入组件以及查看其配置选项的示例以及HTML和JSON输出，请访问组 [件库](http://opensource.adobe.com/aem-core-wcm-components/library/embed.html)。

## 技术详细信息 {#technical-details}

有关嵌入组件的最新技术文 [档可在GitHub上找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed)。

有关开发核心组件的更多详细信息，请参阅核 [心组件开发人员文档](developing.md)。

## 配置对话框 {#configure-dialog}

The configure dialog allows the content author to define the external resource to be embedded on the page. 首先选择应嵌入的资源类型： **URL**、可 **嵌入****或** HTML。

### URL {#url}

最简单的嵌入方式是URL。 Simply paste the URL of the resource you wish to embed in the URL field. ****&#x200B;组件将尝试访问资源，如果某个处理器可以渲染该资源，则会在 **URL字段下显示确认消息** 。 If not, the field will be marked in error.

The Embed Component ships with processors for the following types of resources:

* Resources that comply with the oEmbed standard including Facebook Post, Instagram, SoundCloud, Twitter, and YouTube[](https://oembed.com/)
* Pinterest

开发人员可以按照嵌入组件的开 [发人员文档添加其他URL处理器。](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed#extending-the-embed-component)

![](assets/screen-shot-2019-09-25-10.08.29.png)

### 可嵌入内容 {#embeddable}

Embeddables allow for more customization of the embedded resource, which can be parameterized and include additional information. An author is able to select from pre-configured trusted embeddables and the component ships with a Youtube embeddable out-of-the-box.

The Embeddable field defines the type of processor you want to use. ****&#x200B;如果是YouTube可嵌入，您随后可以定义：

* **视频ID** —— 要嵌入的资源的YouTube中的唯一视频ID
* **宽度** -嵌入视频的宽度
* **高度** -嵌入视频的高度

其他可嵌入式组件将提供类似的字段，开发人员可以根据嵌入 [组件的开发人员文档进行定义。](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed#extending-the-embed-component)

![](assets/screen-shot-2019-09-25-10.15.00.png)

>[!NOTE]
>必须通过“设计”对话框在模板级别启 [用可嵌入](#design-dialog) ，才能让页面作者使用。

### HTML {#html}

您可以使用嵌入组件将自由格式的HTML添加到页面。

![](assets/screen-shot-2019-09-25-10.20.00.png)

>[!NOTE]
>任何不安全的标记（如脚本）都将从输入的HTML中筛选，并且不会在生成的页面上呈现。

## 设计对话框 {#design-dialog}

设计对话框允许模板作者定义内容作者可以使用嵌入组件的选项以及放置嵌入组件时设置的默认值。

![](assets/screen-shot-2019-09-25-10.25.28.png)

* **禁用URL** —— 在选择内 **容作者时** ，禁用URL选项
* **禁用可嵌入** -在选择内容作 **者时，禁用“可嵌入** ”选项，而不管允许哪个可嵌入处理器。
* **禁用HTML** —— 在选中时 **为内容作者禁用** HTML选项。
* **Allowed Embeddables - Multislect that defines which embeddable processors are available to the content author, provided that the Embeddable option is active.******
