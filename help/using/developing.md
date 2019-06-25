---
title: 开发核心组件
seo-title: 开发核心组件
description: 核心组件提供强大、可扩展的基本组件，它们提供功能丰富的功能、连续交付、组件版本控制、现代化实施、精简标记和JSON内容导出。
seo-description: 核心组件提供强大、可扩展的基本组件，它们提供功能丰富的功能、连续交付、组件版本控制、现代化实施、精简标记和JSON内容导出。
uuid: 68569da2-9bc8-4e20-9a71-e5816 ace51 ce
contentOwner: 用户
content-type: 引用
topic-tags: developing
products: SG_ EXPERIENCE MANAGER/CORECOMMPANES-new
discoiquuid: 157a2ec3-9fca-4fad-977a-d93013 eeb218
translation-type: tm+mt
source-git-commit: bea783936100abe899f9b60e4a09522514755db2

---


# Developing Core Components{#developing-core-components}

## 概述 {#overview}

核心组件提供强大、可扩展的基本组件，它们的突出显示有：

* 功能丰富的功能
   * [灵活的配置选项](authoring.md) ，可容纳多种用例
   * [可预先配置的功能](authoring.md#pre-configuring-core-components) ，可定义页面作者可使用的功能
* 持续交付
   * 频繁递增功能改进
   * Availability of the [source code on GitHub](https://github.com/adobe/aem-core-wcm-components) to allow the developer community to give feedback and contribute
   * Installation through a [separately released content package](https://github.com/adobe/aem-core-wcm-components/releases) for component upgrades to be done independently from AEM upgrades
* [组件版本控制](guidelines.md#component-versioning)
   * [确保版本中的兼容性](#upgrade-of-core-components)，但允许组件进行改进
   * 允许一个组件的多个版本共存在同一个环境上
* 现代化实施
   * [HTML模板语言](https://helpx.adobe.com/experience-manager/htl/using/overview.html) (HTL)中定义的标记
   * Content model logic implemented with [Sling Models](https://sling.apache.org/documentation/bundles/models.html)
* 精简标记
   * Following [Block Element Modifier](https://getbem.com/) (BEM) notation as of Release 2.0.0
      * Prior release follow [Bootstrap](https://getbootstrap.com/css/) naming conventions
   * Built around [accessibility guidelines](https://helpx.adobe.com/experience-manager/6-5/managing/using/web-accessibility.html)
   * 可用于响应式和移动站点
* 将内容模型串行化为无外设CMS用例的功能
* 可访问
   * Compliant with the [WCAG 2.0 AA standard](https://helpx.adobe.com/experience-manager/6-5/managing/using/web-accessibility.html)

>[!CAUTION]
>
>Core Components require AEM 6.3 or later and Java 8 and and require the use of [editable templates](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)
>
>核心组件不适用于经典UI和静态模板。

## Gems Session Overview {#gems-session-overview}

For an introduction to the Core Components, the features they offer, and how they are leveraged in AEM, check out the AEM Gems Session [AEM Core Components.](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/AEM-Core-Components.html)

[Adobe Experience Manager](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/aem-index.html) 的Gems是由Adobe专家提供的一系列技术深层产品。本系列对产品文档和所有其他技术渠道进行了补充，允许开发人员接触并深入了解特定主题。

## WKND Developer Tutorial {#wknd-developer-tutorial}

Get started developing AEM Sites with Core Components by following [this step-by-step tutorial.](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/getting-started.html)

## Delivered over GitHub {#delivered-over-github}

核心组件是通过GitHub开发和交付的。

关于GTHub的代码

您可以在GitHub上找到此页面的代码

* [在GitHub上打开aem-core-wcm-components项目](https://github.com/adobe/aem-core-wcm-components)
* Download the project as [a ZIP file](https://github.com/adobe/aem-core-wcm-components/archive/master.zip)

See the [Using Core Components](using.md) documentation page to learn how to get started using them in your project.

通过GitHub上的核心组件可以频繁更新，并倾听AEM开发人员社区的反馈。此外，这应帮助客户和合作伙伴在构建自定义组件时遵循类似模式。

>[!NOTE]
>
>To keep up-to-date on the latest changes to the core components, you can watch the [Core Components repository](https://github.com/adobe/aem-core-wcm-components) on GitHub.

## 组件库

Check out the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library.html), which showcases the current release of the Core Components and gives examples of their usage.

### Sample Content Run-Mode {#sample-content-run-mode}

The Core Components are visible in the Quickstart when the sample content is present, because the [We.Retail reference site](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html) uses them. However, when running in production (in `nosamplecontent` runmode, without sample content enabled), the core components won&#39;t be present anymore and must be installed on the AEM instances by the development and/or operations team.

>[!NOTE]
>
>In production environments, always run the Quickstart in `nosamplecontent` runmode. To use the Core Components in `nosamplecontent` runmode, follow the instructions of the [Using Core Components](using.md) documentation page.

## Technical Capabilities {#technical-capabilities}

下表概述了核心组件与基础组件之间的差异。

For details about their authoring capabilities and options to pre-configurable them, [refer to the authoring page about them](authoring.md).

| **功能** | **核心组件** | **基础组件** |
|-----|---|---|
| 逻辑实施 | Java POJOs with [Sling Models](https://sling.apache.org/documentation/bundles/models.html) annotations | JSP代码 |
| 标记定义 | [HTML模板语言](https://helpx.adobe.com/experience-manager/htl/user-guide.html) (HTL)语法 | JSP代码 |
| XSS清理 | HTL自动化 | 大多数手动手册 |
| CSS类命名 | Standardized naming convention based on [Block Element Modifier](https://getbem.com/) (BEM) notation (as of release 2.0.0) | 自定义方案 |
| 对话框定义 | [Coral3](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/reference-materials/coral-ui/coralui3/index.html) | Coral+经典UI |
| JSON输出 | [Sling Model Exporter with Jackson序列化](https://sling.apache.org/documentation/bundles/models.html#exporter-framework-since-130) | 默认Sling servlet |
| 版本控制 | [针对模型和HTL](guidelines.md) | 无 |
| 测试 | Unit测试+集成测试 | 集成测试 |
| 交付 | [通过公共GitHub](https://github.com/adobe/aem-core-wcm-components) | 通过快速入门 |
| License | [Apache许可证](https://www.apache.org/licenses/LICENSE-2.0) | Adobe专有 |
| 贡献 | 通过拉取请求 | 不可能 |
| 辅助功能 | Fully compliant with the [WCAG 2.0 AA standard](https://helpx.adobe.com/experience-manager/6-5/managing/using/web-accessibility.html) | Only partially compliant with the [WCAG 2.0 AA standard](https://helpx.adobe.com/experience-manager/6-5/managing/using/web-accessibility.html) |

## Component List {#component-list}

下表列出了可用的核心组件，链接到其API，并指示它们替换的基础组件。

| 核心组件 | 描述 | 替换了基础组件 |
|---|---|---|
| [页面](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/page/v2/page) | 使用模板编辑器的响应式页面 | `/libs/foundation/components/page /libs/wcm/foundation/components/page` |
| [痕迹导航](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v2/breadcrumb) | 页面层次结构导航 | `/libs/foundation/components/breadcrumb` |
| [标题](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/title/v2/title) | H1-H标题 | `/libs/foundation/components/title /libs/wcm/foundation/components/title` |
| [文本](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/text/v2/text) | 富文本 | `/libs/foundation/components/text /libs/foundation/components/table /libs/wcm/foundation/components/text` |
| [图像](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/image/v2/image) | 智能和延迟加载最佳再现大小 | `/libs/foundation/components/image /libs/foundation/components/adaptiveimage /libs/foundation/components/logo /libs/foundation/components/mobileimage  /libs/foundation/components/mobilelogo /libs/wcm/foundation/components/image` |
| [列表](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/list/v2/list) | 页面列表 | `/libs/foundation/components/list /libs/foundation/components/mobilelist /libs/wcm/foundation/components/list` |
| [社交媒体共享](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/sharing/v1/sharing) | Facebook和Pinterest共享构件 | `-` |
| [表单容器](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/container/v2/container) | 响应式表单段落系统 | `/libs/foundation/components/form/start /libs/foundation/components/form/end` |
| [表单文本](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/text/v2/text) | 文本输入字段 | `/libs/foundation/components/form/text /libs/foundation/components/form/password` |
| [表单选项](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/options/v2/options) | 多选项输入字段 | `/libs/foundation/components/form/checkbox /libs/foundation/components/form/radio /libs/foundation/components/form/dropdown` |
| [隐藏的表单](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/hidden/v2/hidden) | 隐藏输入字段 | `/libs/foundation/components/form/hidden` |
| [表单按钮](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/button/v2/button) | 提交或自定义按钮 | `/libs/foundation/components/form/submit` |
| [导航](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/navigation/v1/navigation) | 列出嵌套页面层次结构的站点导航组件 | `/libs/foundation/components/topnav /libs/foundation/components/mobiletopnav` |
| [语言导航](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/languagenavigation/v1/languagenavigation) | 列出全局语言结构的语言和国家/地区切换程序 | `-` |
| [快速搜索](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/search/v1/search) | 将结果显示为下拉菜单中的就地建议的搜索组件 | `/libs/foundation/components/search` |
| [Teaser](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/teaser/v1/teaser) | 允许内容作者轻松创建一个Teaser，使用图像、标题或丰富文本以及链接到其他内容或其他操作来进一步内容 | `-` |
| [选项卡](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/tabs/v1/tabs) | 允许内容作者在多个选项卡中组织页面内容 | `-` |
| [传送](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/carousel/v1/carousel) | 允许内容作者在旋转的幻灯片旋转中组织内容 | `/libs/foundation/components/carousel` |
| [内容碎片](https://github.com/adobe/aem-core-wcm-components/tree/master/extension/contentfragment/content/src/content/jcr_root/apps/core/wcm/extension/components/contentfragment/v1/contentfragment) | 允许显示内容片段 | `-` |
| [内容碎片列表](https://github.com/adobe/aem-core-wcm-components/tree/master/extension/contentfragment/content/src/content/jcr_root/apps/core/wcm/extension/components/contentfragmentlist/v1/contentfragmentlist) | 允许显示内容片段列表 | `-` |
| [分隔符](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/separator/v1/separator) | 分离页面上的内容 | `-` |
| [折叠](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/accordion/v1/accordion) | 在可折叠折叠面板中组织内容面板 | `-` |
| [容器](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/container/v1/container) | 组织容器内的组件 | `-` |
| [按钮](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/button/v1/button) | 在页面上创建按钮 | `-` |
| [下载](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/download/v1/download) | 向页面添加可下载的资产 | `-` |

### Upcoming components {#upcoming-components}

正在积极处理以下核心组件。They haven&#39;t been released yet, but can be previewed in the [development branch](https://github.com/adobe/aem-core-wcm-components/tree/development):

* 嵌入
* 模态

## Upgrade of Core Components {#upgrade-of-core-components}

版本组件的一个优点是它允许将迁移到新的AEM版本，从迁移到新的组件版本。此外，如果新组件版本可用，则允许将每个组件的各个组件迁移到新版本。

迁移到新AEM版本不会影响核心组件的工作方式，前提是其版本还支持正在迁移到的新AEM版本。Customizations made to the Core Components should not be affected either, as long as they don&#39;t use APIs that have been [deprecated or removed](https://helpx.adobe.com/experience-manager/6-5/release-notes/deprecated-removed-features.html).

向核心组件的新版本迁移不会影响组件的工作方式，但可能会向页面作者引入新功能，这可能需要模板编辑器进行一些配置，以防不需要默认行为。Customizations however might need to be adapted, for more details see the [Customizing Core Components](customizing.md#upgrade-compatibility-of-customizations) page.

## When to Use the Core Components? {#when-to-use-the-core-components}

由于核心组件是全新的并且提供多个优势，因此建议新AEM项目使用它们。对于现有项目，迁移应属于较大项目的一部分，例如品牌或整体重构。

因此，Adobe提供以下建议：

* **新项目** 新项目应始终尝试使用核心组件。If Core Components cannot be used directly or [extended](customizing.md) to satisfy project requirements, then create a custom component following the component architecture set forth in core components. Except where not otherwise possible, avoid using the [foundation components](developing.md).
* **除非计划了站点或组件重构，否则现有项目** 推荐始终使用 [基础组件](developing.md)。\
   As they are very widely used by most existing projects, the foundation components [will continue to be supported.](developing.md)
* **新自定义组件** 评估是否可以自定义 [现有核心组件](customizing.md)。\
   If not, recommendation is to build a new custom component following the [Component Guidelines](guidelines.md).
* **现有自定义组件** 如果您的组件按预期工作，则保留它们不变。\
   如果没有，请参阅上面的“新建自定义组件”。

## 迁移到核心组件

任何新项目都应通过核心组件进行实施。但是，现有项目通常会大量实施基础组件。

对现有项目(例如品牌或整体重构)的更大努力通常会提供迁移到核心组件的机会。为了促进迁移，Adobe提供了许多迁移工具，以鼓励采用核心组件和最新AEM技术。

[AEM现代化工具](http://opensource.adobe.com/aem-modernize-tools/) 可轻松转换：

* 可编辑模板的静态模板
* 设计配置到策略
* 核心组件的基础组件
* 与触屏优化UI的经典UI

For further information about the usage of these tools, [see their documentation](http://opensource.adobe.com/aem-modernize-tools/).

>[!NOTE]
>
>AEM现代化工具是社区工作，Adobe不支持或替代这些工具。

## Core Component Support {#core-component-support}

核心组件是AEM不可分割的一部分，按相同的条款和条件提供支持，如同它们是作为快速入门的一部分提供的一样。

与其他AEM产品功能一样，一般规则是：首次宣布已弃用组件，以及最早删除的AEM版本。这样，客户至少可以在放下支持之前，为客户提供至少一个发布周期。

每个组件的版本清楚地陈述了其支持的AEM版本。当支持某个版本的AEM时，也支持该版本AEM的核心组件。

For details about the support of component customizations, see the [Customizing Core Components](customizing.md) page.

## Foundation Component Support {#foundation-component-support}

由于基础组件已经作为许多AEM版本上如此多的项目开发基础，它们将继续支持可预见的未来。

However, Adobe&#39;s development emphasis has shifted to the Core Components and new features will be added to them, whereas [nearly all Foundation Components have been deprecated with AEM 6.5](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/default-components-foundation.html) and only bug fixes will be made to the Foundation Components going forward.

**阅读下一步：**

* [使用核心组件](using.md) -在您自己的项目中与核心组件快速入门。
* [组件指南](guidelines.md) -了解核心组件的实施模式。
