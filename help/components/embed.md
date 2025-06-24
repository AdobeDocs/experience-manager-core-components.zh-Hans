---
title: 嵌入组件
description: 使用嵌入组件可以在 AEM 内容页面中嵌入外部内容。
role: Architect, Developer, Admin, User
exl-id: 985fa304-70a3-4329-957e-76d1832a06f1
source-git-commit: dd30def59a8f037864da875ef4c831b11f766e57
workflow-type: tm+mt
source-wordcount: '1343'
ht-degree: 100%

---


# 嵌入组件 {#embed-component}

利用核心组件嵌入组件，可以在 AEM 内容页面中嵌入外部内容。

{{traditional-aem}}

## 用途 {#usage}

利用核心组件嵌入组件，内容作者可以将所选外部内容定义为嵌入到 AEM 内容页面中。此外，还有一个选择，即定义嵌入的自由格式的 HTML。

* 组件的属性可在[“配置”对话框](#configure-dialog)中定义。
* 将组件添加到页面时的组件默认值可以在[“设计”对话框](#design-dialog)中定义。

## 版本和兼容性 {#version-and-compatibility}

嵌入组件的当前版本是 v2，此版本随 2022 年 2 月的核心组件发行版 2.18.0 的发布引入，具体说明见本文。

下表详细说明了该组件的所有受支持版本、与该组件的版本兼容的 AEM 版本以及指向早期版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|--- |--- |---|---|---|
| v2 | - | 兼容 | 兼容 | 兼容 |
| [v1](v1/embed.md) | 兼容 | 兼容 | - | 兼容 |

有关核心组件版本的更多信息，请参阅文档[核心组件版本](/help/versions.md)。

## 示例组件输出 {#sample-component-output}

要体验嵌入组件并查看其配置选项示例以及 HTML 和 JSON 输出，请访问[组件库](https://adobe.com/go/aem_cmp_library_embed_cn)。

## 技术详细信息 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_embed_v2_cn)有关嵌入组件的最新技术文档。

在[核心组件开发人员文档](/help/developing/overview.md)中可找到有关开发核心组件的其他详细信息。

## “配置”对话框 {#configure-dialog}

利用“配置”对话框，内容作者可以定义要在页面上嵌入的外部资源。

### “属性”选项卡 {#properties-tab}

首先选择要嵌入什么类型的资源：

* [URL](#url)
* [可嵌入内容](#embeddable)
* [HTML](#html)

对于每种可嵌入的类型，您可以定义 **ID**。利用此选项，可以控制 HTML 和 [Data Layer](/help/developing/data-layer/overview.md) 中的组件的唯一标识符。

* 如果留空，系统会自动为您生成一个唯一 ID，可以通过检查结果页面找到该 ID。
* 如果指定一个 ID，作者有责任确保它是唯一的。
* 更改此 ID 会对 CSS、JS 和 Data Layer 跟踪产生影响。

#### URL {#url}

最简单的嵌入是 URL。只需将待嵌入资源的 URL 粘贴到 **URL** 字段中。组件将尝试访问资源，如果它可以由处理程序之一渲染，则会在 **URL** 字段下显示确认消息。如果不能，该字段将标记为出错。

嵌入组件附带了用于以下资源类型的处理程序：

* 符合 [oEmbed 标准](https://oembed.com/)的资源，包括 Facebook Post、Instagram、SoundCloud、Twitter 和 YouTube
* Pinterest

开发人员可以[按照嵌入组件的开发人员文档](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed#extending-the-embed-component)，添加额外的 URL 处理程序。

![嵌入组件的 URL 的“编辑”对话框](/help/assets/embed-url.png)

#### 可嵌入内容 {#embeddable}

可嵌入内容允许对嵌入的资源进行更多的自定义，这些自定义可以参数化并包括额外信息。作者能够从 YouTube 提供的现成可嵌入内容中，选择预配置的可信可嵌入内容。

**可嵌入内容**&#x200B;字段定义所要使用的处理程序的类型。在使用 YouTube 可嵌入内容时，您可以定义：

* **视频 ID** - YouTube 中待嵌入资源的唯一视频 ID
* **宽度** - 所嵌入视频的宽度
* **高度** - 所嵌入视频的高度
* **启用静音** - 此参数指定默认情况下播放的视频是否静音。启用此项会增加自动播放在现代浏览器中工作的可能性。
* **启用自动播放** - 此参数指定在加载了播放器时，是否自动开始播放初始视频。这仅在发布实例上或者在创作实例上使用&#x200B;**以发布的形式查看**&#x200B;选项时有效。
* **启用自动循环** - 在单个视频的情况下，此参数指定播放器是否应重复播放初始视频。在有播放列表的情况下，播放器播放整个播放列表，然后从第一个视频从头开始。
* **启用内联播放 (iOS)** - 此参数控制在 iOS 上的 HTML5 播放器中，是内联播放（打开）还是全屏播放（关闭）。
* **不受限相关视频** - 如果禁用此选项，则相关视频将来自与刚播放的视频相同的频道，否则来自任何频道。

其他可嵌入内容将提供类似的字段，并可由开发人员[按照嵌入组件的开发人员文档](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed#extending-the-embed-component)定义。

![嵌入组件的可嵌入内容的“编辑”对话框](/help/assets/embed-embeddable.png)

>[!NOTE]
>
>可嵌入内容必须通过[“设计”对话框](#design-dialog)在模板级别启用，然后才可供内容作者使用。

#### HTML {#html}

您可以使用嵌入组件将自由格式的 HTML 添加到页面。

![嵌入组件的 HTML 的“编辑”对话框](/help/assets/embed-html.png)

>[!NOTE]
>任何不安全的标记（例如脚本）将从输入的 HTML 中筛选掉，不在生成的页面上渲染。

##### 安全性 {#security}

出于安全目的，作者可以输入的 HTML 标记将筛选掉，以避免跨网站脚本攻击，例如，此类攻击可允许作者获取管理权限。

一般来说，所有脚本和 `style` 元素以及 `on*` 和 `style` 属性都将从输出中删除。

但是，规则更复杂，因为嵌入组件遵循 AEM 的全局 HTML AntiSamy 净化框架筛选规则集，此规则集可在 `/libs/cq/xssprotection/config.xml` 中找到。如果需要，这可以由开发人员覆盖以提供项目特定的配置。

其他安全信息可在[适用于内部部署安装的 AEM 开发人员文档](https://experienceleague.adobe.com/docs/experience-manager-65/developing/introduction/security.html?lang=zh-Hans)以及 [AEM as a Cloud Service 安装](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/security/home.html?lang=zh-Hans)中找到。

>[!NOTE]
>
>虽然 AntiSamy 净化框架规则可以通过覆盖 `/libs/cq/xssprotection/config.xml` 来配置，但这些更改会影响到所有 HTL 和 JSP 行为，而不只是嵌入核心组件。

### “样式”选项卡 {#styles-tab-edit}

![嵌入组件“编辑”对话框的“样式”选项卡](/help/assets/embed-styles.png)

嵌入组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。

使用下拉菜单选择要应用于该组件的样式。在“编辑”对话框中所做的选择与从组件工具栏中选择的操作效果相同。

必须在[“设计”对话框](#design-dialog)中为此组件配置样式，以便下拉菜单可用。

## “设计”对话框 {#design-dialog}

使用“设计”对话框，模板作者可以定义哪些选项可供使用嵌入组件的内容作者使用，以及在放置嵌入组件时的默认设置。

### “可嵌入内容类型”选项卡 {#embeddable-types-tab}

![嵌入组件的“设计”对话框](/help/assets/embed-design.png)

* **禁用 URL** - 在选中时，对内容作者禁用 **URL** 选项
* **禁用可嵌入内容** - 在选中时，对内容作者禁用&#x200B;**可嵌入内容**&#x200B;选项，而无论允许了什么可嵌入内容处理程序。
* **禁用 HTML** - 在选中时，对内容作者禁用 **HTML** 选项。
* **允许可嵌入内容** - 多项选择，定义哪些可嵌入内容处理程序可供内容作者使用，前提是激活了&#x200B;**可嵌入内容**&#x200B;选项。

### “YouTube”选项卡 {#youtube-tab}

![嵌入组件的“设计”对话框的“YouTube”选项卡](/help/assets/embed-design-youtube.png)

* **允许静音行为配置** - 允许内容作者在选择了 YouTube 嵌入类型时，在组件中配置&#x200B;**启用静音**&#x200B;选项
   * **默认静音值** - 在选择了 YouTube 嵌入类型时，自动设置&#x200B;**启用静音**&#x200B;选项
* **允许自动播放行为配置** - 允许内容作者在选择了 YouTube 嵌入类型时，在组件中配置&#x200B;**启用自动播放**&#x200B;选项
   * **默认自动播放值** - 在选择了 YouTube 嵌入类型时，自动设置&#x200B;**启用自动播放**&#x200B;选项
* **允许循环行为配置** - 允许内容作者在选择了 YouTube 嵌入类型时，在组件中配置&#x200B;**启用循环**&#x200B;选项
   * **默认循环值** - 在选择了 YouTube 嵌入类型时，自动设置&#x200B;**启用循环**&#x200B;选项
* **允许内联播放 (iOS) 配置** - 允许内容作者在选择了 YouTube 嵌入类型时，在组件中配置&#x200B;**启用内联播放 (iOS)** 选项
   * **默认内联播放 (iOS) 值** - 在选择了 YouTube 嵌入类型时，自动设置&#x200B;**启用内联播放 (iOS)** 选项
* **允许内联视频配置** - 允许内容作者在选择了 YouTube 嵌入类型时，在组件中配置&#x200B;**不受限相关视频**&#x200B;选项
   * **默认不受限相关视频值** - 在选择了 YouTube 嵌入类型时，自动设置&#x200B;**不受限相关视频**&#x200B;选项
