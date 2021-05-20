---
title: 嵌入组件
description: 嵌入组件允许在AEM内容页面中嵌入外部内容。
role: Architect, Developer, Administrator, Business Practitioner
exl-id: 985fa304-70a3-4329-957e-76d1832a06f1
source-git-commit: 8ff36ca143af9496f988b1ca65475497181def1d
workflow-type: tm+mt
source-wordcount: '1341'
ht-degree: 2%

---

# 嵌入组件{#embed-component}

核心组件嵌入组件允许在AEM内容页面中嵌入外部内容。

## 使用 {#usage}

核心组件嵌入组件允许内容作者定义要嵌入到AEM内容页面中的选定外部内容。 此外，还有一个选项可定义要嵌入的自由格式HTML。

* 可以在[配置对话框](#configure-dialog)中定义组件的属性。
* 将组件添加到页面时的默认值，可在[设计对话框](#design-dialog)中定义。

## 版本和兼容性{#version-and-compatibility}

嵌入组件的当前版本为v1，该版本已在2019年9月核心组件版本2.7.0中引入，该版本在此文档中进行了描述。

下表详细列出了组件的所有受支持版本、组件版本与之兼容的AEM版本，以及指向以前版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | 兼容 | 兼容 | 兼容 |

有关核心组件版本和版本的更多信息，请参阅文档[核心组件版本](/help/versions.md)。

## 组件输出示例{#sample-component-output}

要体验嵌入组件以及查看其配置选项以及HTML和JSON输出的示例，请访问[组件库](https://adobe.com/go/aem_cmp_library_embed)。

## 技术详细信息{#technical-details}

有关嵌入组件[的最新技术文档，请参阅GitHub](https://adobe.com/go/aem_cmp_tech_embed_v1)。

有关开发核心组件的更多详细信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## 配置对话框{#configure-dialog}

配置对话框允许内容作者定义要嵌入到页面上的外部资源。 首先选择应嵌入的资源类型：

* [URL](#url)
* [可嵌入内容](#embeddable)
* [HTML](#html)

对于每种类型的可嵌入内容，您可以定义广告&#x200B;**ID**。 此选项允许控制HTML和[数据层](/help/developing/data-layer/overview.md)中组件的唯一标识符。

* 如果留为空白，则会自动为您生成唯一ID，并且可以通过检查生成的页面找到该ID。
* 如果指定了ID，则作者有责任确保该ID是唯一的。
* 更改ID可能会影响CSS、JS和数据层跟踪。

### URL {#url}

最简单的嵌入方式是URL。 只需将要嵌入到&#x200B;**URL**&#x200B;字段中的资源的URL进行粘贴即可。 该组件将尝试访问该资源，如果某个处理器可以呈现该资源，则会在&#x200B;**URL**&#x200B;字段下显示确认消息。 如果没有，则该字段将被标记为错误。

嵌入组件随附有适用于以下类型资源的处理器：

* 符合[oEmbed标准](https://oembed.com/)的资源，包括Facebook Post、Instagram、SoundCloud、Twitter和YouTube
* Pinterest

开发人员可以按照嵌入组件的开发人员文档添加[的其他URL处理器。](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed#extending-the-embed-component)

![URL的嵌入组件编辑对话框](/help/assets/embed-url.png)

### 可嵌入内容 {#embeddable}

可嵌入式允许对嵌入式资源进行更多自定义，该资源可以进行参数化并包含其他信息。 作者可以从预配置的可信任可嵌入项中进行选择，并且组件随YouTube可嵌入的现成组件一起提供。

**Embeddable**&#x200B;字段定义要使用的处理器类型。 对于YouTube可嵌入项，您随后可以定义：

* **视频ID**  — 来自要嵌入的资源YouTube的唯一视频ID
* **宽度**  — 嵌入式视频的宽度
* **高度**  — 嵌入式视频的高度
* **启用静音**  — 此参数指定视频是否默认播放为静音。启用此选项可增加自动播放在现代浏览器中工作的机会。
* **启用自动播放**  — 此参数指定在播放器加载时是否自动开始播放初始视频。仅当在发布实例中或在创作实例中使用&#x200B;**查看已发布内容**&#x200B;选项时，此操作才有效。
* **启用循环**  — 对于单个视频，此参数指定播放器是否应重复播放初始视频。对于播放列表，播放器播放整个播放列表，然后在第一个视频处再次开始。
* **启用内联播放(iOS)**  — 此参数控制iOS上HTML5播放器中的视频是内联播放（开）还是全屏播放（关）。
* **非限制相关视频**  — 如果禁用此选项，则相关视频将来自与刚才播放的视频相同的渠道，否则，将来自任何渠道。

请注意，必须通过[设计对话框](#design-dialog)激活“enable”选项，并且可以将其设置为默认值。

其他可嵌入项将提供类似的字段，开发人员可在[之后根据嵌入组件的开发人员文档进行定义。](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed#extending-the-embed-component)

![嵌入组件的可嵌入项编辑对话框](/help/assets/embed-embeddable.png)

>[!NOTE]
>必须通过[设计对话框](#design-dialog)在模板级别启用可嵌入项，才能供页面作者使用。

### HTML {#html}

您可以使用嵌入组件将自由格式的HTML添加到页面中。

![HTML的嵌入组件的编辑对话框](/help/assets/embed-html.png)

>[!NOTE]
>任何不安全的标记（如脚本）都将从输入的HTML中过滤，而不会在生成的页面上呈现。

#### 安全 {#security}

出于安全考虑，作者可以输入的HTML标记会进行筛选，以避免跨站点脚本攻击，例如允许作者获取管理权限的攻击。

*通常，所有* 脚本和 `style` 元素以及所有和 `on*` 属 `style` 性都将从输出中删除。

但是，这些规则更加复杂，因为嵌入组件遵循AEM全局HTML AntiSamy卫生框架筛选规则集，可在`/libs/cq/xssprotection/config.xml`中找到该规则集。 如果需要，开发人员可以覆盖此配置以进行特定于项目的配置。

有关内部部署安装](https://docs.adobe.com/content/help/en/experience-manager-65/developing/introduction/security.html)和[AEM as a Cloud Service安装的[AEM开发人员文档中提供了其他安全信息。](https://docs.adobe.com/content/help/zh-Hans/experience-manager-cloud-service/security/home.html)

>[!NOTE]
>尽管AntiSamy卫生框架规则可以通过覆盖`/libs/cq/xssprotection/config.xml`来配置，但这些更改会影响所有HTL和JSP行为，而不仅影响嵌入核心组件。

## 设计对话框{#design-dialog}

设计对话框允许模板作者定义内容作者可用的选项，这些选项使用嵌入组件，并在放置嵌入组件时设置默认值。

### 可嵌入类型选项卡{#embeddable-types-tab}

![“嵌入组件”的设计对话框](/help/assets/embed-design.png)

* **禁用URL**  — 选择后， **** 将禁用内容作者的URL选项
* **禁用可嵌入**  — 选择内 **** 容作者的Embeddable选项后，无论允许哪些可嵌入处理器。
* **禁用HTML**  — 选择后， **** 将禁用内容作者的HTML选项。
* **允许的可嵌入项**  — 多选项，用于定义哪些可嵌入的处理器可供内容作者使用，前提是 **** Embeddableoption处于活动状态。

### YouTube选项卡{#youtube-tab}

![嵌入组件设计对话框的YouTube选项卡](/help/assets/embed-design-youtube.png)

* **允许配置静音行为**  — 允许内容作者在选择YouTube嵌 **入** 类型后在组件中配置启用静音选项
   * **默认值为mute**  — 选择YouTube嵌 **入类** 型后，自动设置“启用静音”选项
* **允许配置自动播放行为**  — 允许内容作者在选择YouTube嵌 **入** 类型后在组件中配置启用自动播放选项
   * **自动播放的默认值**  — 在选择YouTube嵌 **入类** 型后自动设置启用自动播放选项
* **允许配置循环行为**  — 允许内容作者在选择YouTube嵌 **入** 类型后在组件中配置启用加载项
   * **默认值为loop**  — 在选择YouTube嵌 **入** 类型后自动设置启用加载项
* **允许配置内联播放(iOS)**  — 允许内容作者在选择YouTube嵌 **入类型时在组件中配置启用内联播放(iOS)** 选项
   * **内联播放(iOS)的默认值**  — 在选择YouTube嵌 **入类型时自动设置“启用内联播放(iOS)”** 选项
* **允许配置内联视频**  — 允许内容作者在选择YouTube嵌 **入类** 型后，在组件中配置“不受限制的相关视频”选项
   * **非限制相关视频的默认值**  — 在选择YouTube嵌 **入类型时** 自动设置非限制相关视频选项
