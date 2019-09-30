---
title: 嵌入组件
seo-title: 嵌入组件
description: 嵌入组件支持在AEM内容页面中嵌入外部内容。
seo-description: 嵌入组件支持在AEM内容页面中嵌入外部内容。
content-type: 引用
topic-tags: 核心组件
translation-type: tm+mt
source-git-commit: 6882a0d8247328c403dc11a25ed9d079aefede69

---


# 嵌入组件{#embed-component}

核心组件嵌入组件允许在AEM内容页面中嵌入外部内容。

## 使用情况 {#usage}

核心组件嵌入组件允许内容作者定义要嵌入到AEM内容页面中的选定外部内容。 此外，还有一个选项可定义要嵌入的自由形式HTML。

* 组件的属性可以在配置对话框中 [定义](#configure-dialog)。
* 将组件添加到页面时的默认值可以在设计对话框中 [定义](#design-dialog)。

## 版本和兼容性 {#version-and-compatibility}

嵌入组件的当前版本为v1，该版本于2019年9月随核心组件的2.7.0版一起推出，本文档对此进行了说明。

下表详细列出了组件的所有受支持版本、与组件版本兼容的AEM版本，以及指向先前版本的文档的链接。

| 组件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |---|
| v1 | 兼容 | 兼容 | 兼容 |

有关核心组件版本和版本的详细信息，请参阅文档核 [心组件版本](versions.md)。

## 示例组件输出 {#sample-component-output}

要体验嵌入组件以及查看其配置选项的示例以及HTML和JSON输出，请访问组 [件库](http://opensource.adobe.com/aem-core-wcm-components/library/embed.html)。

## 技术详细信息 {#technical-details}

有关嵌入组件的最新技术文 [档可在GitHub上找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed)。

有关开发核心组件的更多详细信息，请参阅核 [心组件开发人员文档](developing.md)。

## 配置对话框 {#configure-dialog}

配置对话框允许内容作者定义要嵌入到页面上的外部资源。 首先选择应嵌入的资源类型： **URL**、可 **嵌入****或** HTML。

### URL {#url}

最简单的嵌入方式是URL。 只需粘贴要嵌入到URL字段中的资源的 **URL** 。 组件将尝试访问资源，如果某个处理器可以渲染该资源，则会在 **URL字段下显示确认消息** 。 否则，该字段将被标记为错误。

嵌入组件随附以下类型的资源的处理器：

* 符合Facebook Post、 [Instagram](https://oembed.com/) 、SoundCloud、Twitter和YouTube等oEmbed标准的资源
* Pinterest

开发人员可以按照嵌入组件的开 [发人员文档添加其他URL处理器。](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed#extending-the-embed-component)

![](assets/screen-shot-2019-09-25-10.08.29.png)

### 可嵌入 {#embeddable}

可嵌入式允许对嵌入式资源进行更多自定义，该嵌入式资源可以参数化并包含附加信息。 作者可以从预配置的可信任可嵌入式中进行选择，该组件随附现成的Youtube处理器。

“可 **嵌入** ”字段定义要使用的处理器类型。 对于YouTube处理器，您随后可以定义：

* **视频ID** —— 要嵌入的资源的YouTube中的唯一视频ID
* **宽度** -嵌入视频的宽度
* **高度** -嵌入视频的高度

其他处理器将提供类似的字段，并且可由开发人员根据嵌入 [组件的开发人员文档进行定义。](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed#extending-the-embed-component)

![](assets/screen-shot-2019-09-25-10.15.00.png)

>[!NOTE]
>必须通过设计对话框在模板级别启用嵌入式处理 [器](#design-dialog) ，才能让页面作者使用。

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
* **允许的可嵌入** -定义内容作者可以使用哪些可嵌入处理器的多选项，前提是“可 **嵌入** ”选项处于活动状态。
