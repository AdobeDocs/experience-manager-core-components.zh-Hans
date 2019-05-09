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
source-git-commit: 1bbec9b1f109df88964dce051a58d111bf6cafaa

---


# 开发核心组件{#developing-core-components}

## 概述 {#overview}

核心组件提供强大、可扩展的基本组件，它们的突出显示有：

* 功能丰富的功能
   * [灵活的配置选项](authoring.md) ，可容纳多种用例
   * [可预先配置的功能](authoring.md#pre-configuring-core-components) ，可定义页面作者可使用的功能
* 持续交付
   * 频繁递增功能改进
   * 在GitHub上提供 [源代码，](https://github.com/adobe/aem-core-wcm-components) 使开发人员社区能够提供反馈和贡献
   * 通过 [单独发布的内容包进行安装](https://github.com/adobe/aem-core-wcm-components/releases) ，以便从AEM升级独立完成组件升级
* [组件版本控制](guidelines.md#component-versioning)
   * [确保版本中的兼容性](#upgrade-of-core-components)，但允许组件进行改进
   * 允许一个组件的多个版本共存在同一个环境上
* 现代化实施
   * [HTML模板语言](https://helpx.adobe.com/experience-manager/htl/using/overview.html) (HTL)中定义的标记
   * 使用 [Sling模型实现的内容模型逻辑](https://sling.apache.org/documentation/bundles/models.html)
* 精简标记
   * 从Release2.0.0中遵循 [块元素修饰符](https://getbem.com/) (BEM)记号
      * 上一版本遵循 [Bootstrap](https://getbootstrap.com/css/) 命名惯例
   * 围绕 [辅助功能指导原则构建](https://helpx.adobe.com/experience-manager/6-5/managing/using/web-accessibility.html)
   * 可用于响应式和移动站点
* 将内容模型串行化为无外设CMS用例的功能
* 可访问
   * 符合 [WCAG2.0AA标准](https://helpx.adobe.com/experience-manager/6-5/managing/using/web-accessibility.html)

>[!CAUTION]
>
>核心组件需要AEM6.3或更高版本以及Java8。
>
>核心组件不能与经典UI一起使用。

## Gems会话概述 {#gems-session-overview}

有关核心组件的介绍、它们提供的功能以及如何在AEM中利用它们，请参阅AEM Gems会话 [AEM核心组件。](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/AEM-Core-Components.html)

[Adobe Experience Manager](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/aem-index.html) 的Gems是由Adobe专家提供的一系列技术深层产品。本系列对产品文档和所有其他技术渠道进行了补充，允许开发人员接触并深入了解特定主题。

## WKD开发人员教程 {#wknd-developer-tutorial}

[通过分步教程，开始使用核心组件开发AEM Sites。](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/getting-started.html)

## 通过GitHub交付 {#delivered-over-github}

核心组件是通过GitHub开发和交付的。

关于GTHub的代码

您可以在GitHub上找到此页面的代码

* [在GitHub上打开aem-core-wcm-components项目](https://github.com/adobe/aem-core-wcm-components)
* 将项目下载为 [ZIP文件](https://github.com/adobe/aem-core-wcm-components/archive/master.zip)

请参阅 [使用核心组件](using.md) 文档页面，了解如何开始在项目中使用它们。

通过GitHub上的核心组件可以频繁更新，并倾听AEM开发人员社区的反馈。此外，这应帮助客户和合作伙伴在构建自定义组件时遵循类似模式。

>[!NOTE]
>
>要始终更新核心组件的最新更改，您可以观看GitHub上 [的核心组件存储库](https://github.com/adobe/aem-core-wcm-components) 。

## 组件库

查看 [组件库，该库](http://opensource.adobe.com/aem-core-wcm-components/library.html)展示了核心组件的当前版本并提供了其用法示例。

### 示例内容运行模式 {#sample-content-run-mode}

当示例内容存在时，核心组件在快速启动中可见，因为 [We. Retail引用站点](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html) 使用它们。但是，在生产中运行时(在 `nosamplecontent` 运行模式中，未启用示例内容)，核心组件不再存在，并且必须由开发和/或操作团队在AEM实例上安装。

>[!NOTE]
>
>在生产环境中，始终在 `nosamplecontent` 运行模式下运行快速启动。要在运行模式中 `nosamplecontent` 使用核心组件，请按照 [“使用核心组件](using.md) ”文档页面的说明操作。

## 技术能力 {#technical-capabilities}

下表概述了核心组件与基础组件之间的差异。

有关其创作功能和选项可预配置的详细信息， [请参阅有关它们](authoring.md)的创作页面。

| **功能** | **核心组件** | **基础组件** |
|-----|---|---|
| 逻辑实施 | 带 [Sling Model](https://sling.apache.org/documentation/bundles/models.html) 注释的Java Pojos | JSP代码 |
| 标记定义 | [HTML模板语言](https://helpx.adobe.com/experience-manager/htl/user-guide.html) (HTL)语法 | JSP代码 |
| XSS清理 | HTL自动化 | 大多数手动手册 |
| CSS类命名 | 基于 [块元素修饰符](https://getbem.com/) (BEM)记号的标准化命名约定(从第2.0.0版起) | 自定义方案 |
| 对话框定义 | [Coral3](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/reference-materials/coral-ui/coralui3/index.html) | Coral+经典UI |
| JSON输出 | [Sling Model Exporter with Jackson序列化](https://sling.apache.org/documentation/bundles/models.html#exporter-framework-since-130) | 默认Sling servlet |
| 版本控制 | [针对模型和HTL](guidelines.md) | 无 |
| 测试 | Unit测试+集成测试 | 集成测试 |
| 交付 | [通过公共GitHub](https://github.com/adobe/aem-core-wcm-components) | 通过快速入门 |
| License | [Apache许可证](https://www.apache.org/licenses/LICENSE-2.0) | Adobe专有 |
| 贡献 | 通过拉取请求 | 不可能 |
| 辅助功能 | 完全符合 [WCAG2.0AA标准](https://helpx.adobe.com/experience-manager/6-5/managing/using/web-accessibility.html) | 仅部分兼容WCAG [2.0AA标准](https://helpx.adobe.com/experience-manager/6-5/managing/using/web-accessibility.html) |

## 组件列表 {#component-list}

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

### 即将推出的组件 {#upcoming-components}

正在积极处理以下核心组件。它们尚未发布，但可以在 [开发分支中预览](https://github.com/adobe/aem-core-wcm-components/tree/development)：

* 视频
* 下载

## 核心组件升级 {#upgrade-of-core-components}

版本组件的一个优点是它允许将迁移到新的AEM版本，从迁移到新的组件版本。此外，如果新组件版本可用，则允许将每个组件的各个组件迁移到新版本。

迁移到新AEM版本不会影响核心组件的工作方式，前提是其版本还支持正在迁移到的新AEM版本。对核心组件所做的自定义不应受影响，只要它们不使用 [已弃用或删除](https://helpx.adobe.com/experience-manager/6-5/release-notes/deprecated-removed-features.html)的API。

向核心组件的新版本迁移不会影响组件的工作方式，但可能会向页面作者引入新功能，这可能需要模板编辑器进行一些配置，以防不需要默认行为。但是，可能需要调整自定义，以了解更多详细信息，请参阅 [自定义核心组件](customizing.md#upgrade-compatibility-of-customizations) 页面。

## 何时使用核心组件？ {#when-to-use-the-core-components}

由于核心组件是全新的并且提供多个优势，因此建议新AEM项目使用它们。对于现有项目，迁移应属于较大项目的一部分，例如品牌或整体重构。

因此，Adobe提供以下建议：

* **新项目**新项目应始终尝试使用核心组件。如果核心组件不能直接使用或 [扩展](customizing.md) 以满足项目要求，请根据核心组件中所述的组件架构创建自定义组件。除非否则可能，否则避免使用 [基础组件](developing.md)。
* **除非计划了站点或组件重构，否则现有项目**推荐始终使用 [基础组件](developing.md)。\
   由于它们被大多数现有项目广泛使用，因此将继续支持基础组件 [。](developing.md)
* **新自定义组件**评估是否可以自定义 [现有核心组件](customizing.md)。\
   如果没有，则建议根据 [组件准则构建新的自定义组件](guidelines.md)。
* **现有自定义组件**如果您的组件按预期工作，则保留它们不变。\
   如果没有，请参阅上面的“新建自定义组件”。

### 核心组件支持 {#core-component-support}

核心组件是AEM不可分割的一部分，按相同的条款和条件提供支持，如同它们是作为快速入门的一部分提供的一样。

与其他AEM产品功能一样，一般规则是：首次宣布已弃用组件，以及最早删除的AEM版本。这样，客户至少可以在放下支持之前，为客户提供至少一个发布周期。

每个组件的版本清楚地陈述了其支持的AEM版本。当支持某个版本的AEM时，也支持该版本AEM的核心组件。

有关组件自定义支持的详细信息，请参阅 [自定义核心组件](customizing.md) 页面。

### 基础组件支持 {#foundation-component-support}

由于基础组件已经作为许多版本的如此多的项目开发基础，因此它们将继续支持可预见的未来。

但是，Adobe的开发重点已转移到核心组件中，新功能将添加到这些组件中，而将对基础组件进行错误修复

**阅读下一步：**

* [使用核心组件](using.md) -在您自己的项目中与核心组件快速入门。
* [组件指南](guidelines.md) -了解核心组件的实施模式。
