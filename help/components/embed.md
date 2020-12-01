---
title: 嵌入组件
description: 嵌入组件允许在AEM内容页面中嵌入外部内容。
translation-type: tm+mt
source-git-commit: c186e9ec3944d785ab0376769cf7f2307049a809
workflow-type: tm+mt
source-wordcount: '944'
ht-degree: 2%

---


# 嵌入组件{#embed-component}

核心组件嵌入组件允许在AEM内容页面中嵌入外部内容。

## 使用 {#usage}

核心组件嵌入组件允许内容作者定义要嵌入AEM内容页面中的选定外部内容。 此外，还有一个选项可定义要嵌入的自由形式HTML。

* 组件的属性可以在[配置对话框](#configure-dialog)中定义。
* 将组件添加到页面时的默认值可以在[设计对话框](#design-dialog)中定义。

## 版本和兼容性{#version-and-compatibility}

嵌入组件的当前版本为v1,2019年9月在核心组件的2.7.0版中引入了v1，本文档对此进行了说明。

下表详细列出了组件的所有受支持版本、与组件版本兼容的AEM版本以及指向先前版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | 兼容 | 兼容 | 兼容 |

有关核心组件版本和版本的详细信息，请参阅文档[核心组件版本](/help/versions.md)。

## 示例组件输出{#sample-component-output}

要体验嵌入组件以及其配置选项以及HTML和JSON输出的示例，请访问[组件库](https://adobe.com/go/aem_cmp_library_embed)。

## 技术详细信息{#technical-details}

有关嵌入组件[的最新技术文档可在GitHub](https://adobe.com/go/aem_cmp_tech_embed_v1)上找到。

有关开发核心组件的更多详细信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## 配置对话框{#configure-dialog}

配置对话框允许内容作者定义要嵌入到页面上的外部资源。 首先选择应嵌入的资源类型：

* [URL](#url)
* [可嵌入内容](#embeddable)
* [HTML](#html)

对于每种类型的可嵌入式，您可以定义ad **ID**。 此选项允许控制HTML和[数据层](/help/developing/data-layer/overview.md)中组件的唯一标识符。

* 如果留空，则会自动为您生成唯一ID，并可通过检查生成的页面找到该ID。
* 如果指定了ID，则作者有责任确保它是唯一的。
* 更改ID可能会影响CSS、JS和数据层跟踪。

### URL {#url}

最简单的嵌入方式是URL。 只需将要嵌入到&#x200B;**URL**&#x200B;字段中的资源的URL粘贴即可。 该组件将尝试访问资源，如果某个处理器可以渲染该资源，它将在&#x200B;**URL**&#x200B;字段下显示确认消息。 否则，将错误标记该字段。

嵌入组件随处理器提供，适用于以下类型的资源：

* 符合[oEmbed standard](https://oembed.com/)的资源，包括Facebook Post、Instagram、SoundCloud、Twitter和YouTube
* Pinterest

开发人员可以在嵌入组件的开发人员文档之后，通过[添加其他URL处理器。](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed#extending-the-embed-component)

![URL的嵌入组件的编辑对话框](/help/assets/embed-url.png)

### 可嵌入内容 {#embeddable}

可嵌入式允许对嵌入式资源进行更多自定义，该资源可以进行参数化并包含附加信息。 作者可以从预配置的可信任可嵌入式中进行选择，并且组件随附一个现成的Youtube可嵌入式。

**可嵌入**&#x200B;字段定义要使用的处理器类型。 对于YouTube可嵌入式，您随后可以定义：

* **视频ID**  —— 要嵌入的资源的YouTube中的唯一视频ID
* **宽度** -嵌入视频的宽度
* **高度** -嵌入视频的高度

其他可嵌入项将优惠类似的字段，可由开发人员在嵌入组件的开发人员文档后[定义。](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed#extending-the-embed-component)

![可嵌入式组件的嵌入组件编辑对话框](/help/assets/embed-embeddable.png)

>[!NOTE]
>必须通过[设计对话框](#design-dialog)在模板级别启用可嵌入式，才能让页面作者使用。

### HTML {#html}

您可以使用嵌入组件将自由格式HTML添加到页面。

![HTML的嵌入组件的编辑对话框](/help/assets/embed-html.png)

>[!NOTE]
>任何不安全标记（如脚本）都将从输入的HTML中过滤，并且不会在生成的页面上呈现。

#### 安全 {#security}

作者可以输入的HTML标记会出于安全目的进行筛选，以避免跨站点脚本攻击，例如，这些攻击可能允许作者获得管理权限。

*通常，所* 有脚本 `style` 和元素以及所 `on*` 有和 `style` 属性都将从输出中删除。

但是，这些规则更复杂，因为嵌入组件遵循AEM的全局HTML AntiSamy卫生框架过滤规则集，可在`/libs/cq/xssprotection/config.xml`找到。 如果需要，开发人员可以覆盖该配置以进行项目特定配置。

可在[AEM开发人员文档中找到有关内部部署安装](https://docs.adobe.com/content/help/en/experience-manager-65/developing/introduction/security.html)以及作为Cloud Service安装的[AEM的其他安全信息。](https://docs.adobe.com/content/help/zh-Hans/experience-manager-cloud-service/security/home.html)

>[!NOTE]
>尽管可以通过覆盖`/libs/cq/xssprotection/config.xml`来配置AntiSamy卫生框架规则，但这些更改会影响所有HTL和JSP行为，而不仅影响嵌入核心组件。

## 设计对话框{#design-dialog}

设计对话框允许模板作者定义内容作者可以使用嵌入组件的选项以及放置嵌入组件时设置的默认值。

![嵌入组件的设计对话框](/help/assets/embed-design.png)

* **禁用URL**  —— 在选择内 **** 容作者时禁用URL选项
* **禁用可嵌入** -在选择 **** 内容作者时禁用“可嵌入”选项，而不管允许哪个可嵌入处理器。
* **禁用HTML**  —— 在选 **** 择内容作者时禁用HTML选项。
* **允许的可嵌入** -定义内容作者可以使用哪些可嵌入式处理器的多分辨率，前提是“可嵌 **** 入”选项处于活动状态。
