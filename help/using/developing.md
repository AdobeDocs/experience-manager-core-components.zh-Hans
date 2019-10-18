---
title: 开发核心组件
seo-title: 开发核心组件
description: 核心组件提供强大且可扩展的基本组件，这些组件提供丰富的功能、连续交付、组件版本控制、现代化实施、精益标记和内容的JSON导出。
seo-description: 核心组件提供强大且可扩展的基本组件，这些组件提供丰富的功能、连续交付、组件版本控制、现代化实施、精益标记和内容的JSON导出。
uuid: 68569da2-9bc8-4e20-9a71-e5816ace51ce
contentOwner: 用户
content-type: 参考
topic-tags: 开发
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-new
discoiquuid: 157a2ec3-9fca-4fad-977a-d93013eeb218
translation-type: tm+mt
source-git-commit: 683b4f4705c226275439a408423cbf1b23bea66f

---


# 开发核心组件{#developing-core-components}

## 概述 {#overview}

核心组件提供强大且可扩展的基本组件，其亮点包括：

* 功能丰富
   * [灵活的配置选项](authoring.md) ，可适应许多用例
   * [可预配置的功能](authoring.md#pre-configuring-core-components) ，用于定义哪些功能可供页面作者使用
* 持续交付
   * 频繁的增量功能改进
   * 在GitHub上提 [供源代码](https://github.com/adobe/aem-core-wcm-components) ，让开发人员社区提供反馈和贡献
   * 通过单独发 [布的内容包进行安装](https://github.com/adobe/aem-core-wcm-components/releases) ，以便组件升级与AEM升级独立完成
* [组件版本控制](guidelines.md#component-versioning)
   * [确保版本内的兼容性](#upgrade-of-core-components)，同时允许组件不断改进
   * 允许一个组件的多个版本共存于同一环境中
* 现代实施
   * 在 [HTML模板语言](https://helpx.adobe.com/experience-manager/htl/using/overview.html) (HTL)中定义的标记
   * 使用 [Sling Models实现的内容模型逻辑](https://sling.apache.org/documentation/bundles/models.html)
* 精益标记
   * 从版 [本2.0.0开始](https://getbem.com/) ，以下块元素修饰符(BEM)表示法
      * 先前版本遵循 [Bootstrap](https://getbootstrap.com/css/) 命名惯例
   * Built around [accessibility guidelines](https://helpx.adobe.com/experience-manager/6-5/managing/using/web-accessibility.html)
   * 可用于响应式和移动站点
* 能够将无外设CMS用例的内容模型序列化为JSON
* 可访问
   * 符合 [WCAG 2.0 AA标准](https://helpx.adobe.com/experience-manager/6-5/managing/using/web-accessibility.html)

>[!CAUTION]
>
>核心组件需要AEM 6.3或更高版本以及Java 8，并且需要使用可编辑 [的模板](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)
>
>核心组件不适用于经典UI，也不适用于静态模板。

## Gems 教程概述 {#gems-session-overview}

关于核心组件、组件提供的功能以及它们在 AEM 中的使用方式，请参阅 AEM Gems 教程 [AEM 核心组件。](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/AEM-Core-Components.html)

[Adobe Experience Manager上的Gems](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/aem-index.html) ，是Adobe专家提供的一系列技术深入介绍。 此系列是对产品文档和所有其他技术渠道的补充，使开发人员能够相互交流并深入讨论特定主题。

## WKND 开发人员教程 {#wknd-developer-tutorial}

Get started developing AEM Sites with Core Components by following [this step-by-step tutorial.](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/getting-started.html)

## AEM Project Archetype {#aem-project-archetype}

[AEM Project Archetype将创建一个最小的Adobe Experience Manager项目作为您自己项目的起点，包括一个包含SlingModels的自定义HTL组件的简单示例，用于逻辑和正确实施包含推荐代理模式的核心组件。](overview.md)

## 通过GitHub交付 {#delivered-over-github}

核心组件是在GitHub中开发和提供的。

GITHUB上的代码

您可以在GitHub上找到此页面的代码

* [在GitHub上打开aem-core-wcm-components项目](https://github.com/adobe/aem-core-wcm-components)
* 将项目下载为 [ZIP文件](https://github.com/adobe/aem-core-wcm-components/archive/master.zip)

请参阅 [使用核心组件文档页](using.md) ，了解如何在项目中开始使用它们。

在GitHub上安装核心组件可以进行频繁更新，并倾听AEM开发人员社区的反馈。 此外，这应有助于客户和合作伙伴在构建自定义组件时遵循类似的模式。

>[!NOTE]
>
>要及时了解对核心组件的最新更改，您可以在GitHub上查看 [核心组件存储库](https://github.com/adobe/aem-core-wcm-components) 。

## 组件库

查看组 [件库](http://opensource.adobe.com/aem-core-wcm-components/library.html)，它显示核心组件的当前版本并提供其使用示例。

### 示例内容运行模式 {#sample-content-run-mode}

当示例内容存在时，核心组件会显示在快速启动中，因为 [We.Retail参考站点使用这些组件](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html) 。 但是，在生产中运行（在运行模式中，未启用示例内容）时，核心组件将不再存在，并且必须由开发和／或操作团队在AEM实例中安装。 `nosamplecontent`

>[!NOTE]
>
>在生产环境中，请始终以运行模式运行快 `nosamplecontent` 速启动。 要在运行模式中使用核 `nosamplecontent` 心组件，请按照使用核心组 [件文档页面的说明](using.md) 。

## 技术功能 {#technical-capabilities}

下表概述了核心组件与基础组件之间的差异。

有关其创作功能和可预先配置的选项的详细信息，请 [参阅有关这些功能的创作页面](authoring.md)。

| **功能** | **核心组件** | **基础组件** |
|-----|---|---|
| 逻辑实现 | 带有 [Sling Models注释的Java POJO](https://sling.apache.org/documentation/bundles/models.html) | JSP代码 |
| 标记定义 | [HTML模板语言](https://helpx.adobe.com/experience-manager/htl/user-guide.html) (HTL)语法 | JSP代码 |
| XSS清理 | 由HTL自动化 | 多为手动 |
| CSS类命名 | 基于块元素修 [饰符](https://getbem.com/) (BEM)记号的标准化命名约定（从版本2.0.0开始） | 自定义方案 |
| 对话框定义 | [珊瑚3](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/reference-materials/coral-ui/coralui3/index.html) | Coral 2 +经典UI |
| JSON输出 | [Sling Models Exporter（带有Jackson序列化）](https://sling.apache.org/documentation/bundles/models.html#exporter-framework-since-130) | 默认Sling Servlet |
| 版本控制 | [对于模型和HTL](guidelines.md) | 无 |
| 测试 | 单元测试+集成测试 | 集成测试 |
| 交付 | [通过公共GitHub](https://github.com/adobe/aem-core-wcm-components) | 通过快速入门 |
| License | [Apache许可证](https://www.apache.org/licenses/LICENSE-2.0) | Adobe专有 |
| 贡献 | 通过拉取请求 | 不可能 |
| 辅助功能 | 完全符合 [WCAG 2.0 AA标准](https://helpx.adobe.com/experience-manager/6-5/managing/using/web-accessibility.html) | 仅部分符合 [WCAG 2.0 AA标准](https://helpx.adobe.com/experience-manager/6-5/managing/using/web-accessibility.html) |

## 组件列表 {#component-list}

下表列出了可用的核心组件，它们链接到其API并指示它们替换的基础组件。

| 核心组件 | 描述 | 已更换基础组件 |
|---|---|---|
| [页面](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/page/v2/page) | 使用模板编辑器的响应式页面 | `/libs/foundation/components/page /libs/wcm/foundation/components/page` |
| [痕迹导航](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v2/breadcrumb) | 页面层次导航 | `/libs/foundation/components/breadcrumb` |
| [标题](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/title/v2/title) | H1-H6标题 | `/libs/foundation/components/title /libs/wcm/foundation/components/title` |
| [文本](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/text/v2/text) | 富文本 | `/libs/foundation/components/text /libs/foundation/components/table /libs/wcm/foundation/components/text` |
| [图像](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/image/v2/image) | 智能和延迟加载最佳再现大小 | `/libs/foundation/components/image /libs/foundation/components/adaptiveimage /libs/foundation/components/logo /libs/foundation/components/mobileimage  /libs/foundation/components/mobilelogo /libs/wcm/foundation/components/image` |
| [列表](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/list/v2/list) | 页面列表 | `/libs/foundation/components/list /libs/foundation/components/mobilelist /libs/wcm/foundation/components/list` |
| [社交媒体共享](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/sharing/v1/sharing) | Facebook和Pinterest共享构件 | `-` |
| [表单容器](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/container/v2/container) | 响应式表单段落系统 | `/libs/foundation/components/form/start /libs/foundation/components/form/end` |
| [表单文本](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/text/v2/text) | 文本输入字段 | `/libs/foundation/components/form/text /libs/foundation/components/form/password` |
| [表单选项](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/options/v2/options) | 多个选项输入字段 | `/libs/foundation/components/form/checkbox /libs/foundation/components/form/radio /libs/foundation/components/form/dropdown` |
| [隐藏的表单](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/hidden/v2/hidden) | 隐藏输入字段 | `/libs/foundation/components/form/hidden` |
| [表单按钮](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/button/v2/button) | 提交或自定义按钮 | `/libs/foundation/components/form/submit` |
| [导航](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/navigation/v1/navigation) | 列出嵌套页面层次结构的站点导航组件 | `/libs/foundation/components/topnav /libs/foundation/components/mobiletopnav` |
| [语言导航](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/languagenavigation/v1/languagenavigation) | 列出全球语言结构的语言和国家／地区切换程序 | `-` |
| [快速搜索](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/search/v1/search) | 在下拉菜单中将结果显示为就地建议的搜索组件 | `/libs/foundation/components/search` |
| [Teaser](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/teaser/v1/teaser) | 允许内容作者使用图像、标题或富文本轻松创建Teaser以进一步内容，并链接到其他内容或其他操作 | `-` |
| [选项卡](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/tabs/v1/tabs) | 允许内容作者在多个选项卡中组织页面内容 | `-` |
| [轮播](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/carousel/v1/carousel) | 允许内容作者在旋转的幻灯片轮盘中组织内容 | `/libs/foundation/components/carousel` |
| [内容碎片](https://github.com/adobe/aem-core-wcm-components/tree/master/extension/contentfragment/content/src/content/jcr_root/apps/core/wcm/extension/components/contentfragment/v1/contentfragment) | 允许显示内容片段 | `-` |
| [内容片段列表](https://github.com/adobe/aem-core-wcm-components/tree/master/extension/contentfragment/content/src/content/jcr_root/apps/core/wcm/extension/components/contentfragmentlist/v1/contentfragmentlist) | 允许显示内容片段列表 | `-` |
| [分隔符](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/separator/v1/separator) | 分隔页面上的内容 | `-` |
| [折叠](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/accordion/v1/accordion) | 在可折叠的面板中组织内容面板 | `-` |
| [容器](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/container/v1/container) | 在容器内组织组件 | `-` |
| [按钮](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/button/v1/button) | 在页面上创建按钮 | `-` |
| [下载](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/download/v1/download) | 向页面添加可下载的资源 | `-` |
| [体验片段](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/experience-fragment/v1/experience-fragment) | 将体验片段添加到页面 | `/libs/cq/experience-fragments/editor/components/experiencefragment` |
| [嵌入](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/embed/v1/embed) | 在页面中嵌入外部资源 | - |

### 即将推出的组件 {#upcoming-components}

有关即将推出的核心组件路线图的概述，请参 [阅GitHub上的专题wiki](https://github.com/adobe/aem-core-wcm-components/wiki/home)。

## 升级核心组件 {#upgrade-of-core-components}

版本控制组件的一个好处是它允许将迁移到新AEM版本与迁移到新组件版本分开。 此外，如果有新组件版本可用，它允许将每个组件单独迁移到新版本。

迁移到新AEM版本不会影响核心组件的工作方式，前提是其版本还支持要迁移到的新AEM版本。 对核心组件进行的自定义也不应受到影响，只要它们不使用已弃用或删除 [的API](https://helpx.adobe.com/experience-manager/6-5/release-notes/deprecated-removed-features.html)。

迁移到新版本的核心组件也不会影响组件的工作方式，但可能会为页面作者引入新功能，这可能需要模板编辑器进行一些配置，以防不需要默认行为。 但是，可能需要调整自定义，有关详细信息，请参阅自 [定义核心组件](customizing.md#upgrade-compatibility-of-customizations) 。

## When to Use the Core Components? {#when-to-use-the-core-components}

由于核心组件是全新的，并且具备多种优势，因此建议新的 AEM 项目使用这些组件。对于现有项目，可以考虑在进行更大型项目工作期间进行迁移，例如在重新品牌化或整体重构工作期间。

因此，Adobe提供以下建议：

* **新项目**&#x200B;新项目应始终尝试使用核心组件。 如果核心组件不能直接使用或扩展 [以满足项目要求](customizing.md) ，请按照核心组件中所述的组件架构创建自定义组件。 除非其他可能，否则请避免使用 [基础组件](developing.md)。
* **现有项**&#x200B;目推荐将继续使用 [基础组件](developing.md)，除非计划了站点或组件重构。\
   由于它们被大多数现有项目广泛使用，因此将继 [续支持基础组件。](developing.md)
* **新自定义组**&#x200B;件评估是否可以自 [定义现有核心组件](customizing.md)。\
   否则，建议按照组件准则构建新的自定义 [组件](guidelines.md)。
* **现有自定义**&#x200B;组件如果您的组件按预期工作，则按原样保留它们。\
   否则，请参阅上面的“新建自定义组件”。

## 迁移到核心组件

任何新项目都应使用核心组件来实施。 但是，现有项目通常具有广泛的基础组件实施。

对现有项目（例如重新品牌化或整体重构）进行更大的努力，通常会提供迁移到核心组件的机会。 为便于迁移，Adobe提供了许多迁移工具，鼓励采用核心组件和最新的AEM技术。

[AEM Moderination Tools](http://opensource.adobe.com/aem-modernize-tools/) （AEM现代化工具）允许轻松转换：

* 静态模板到可编辑模板
* 为策略设计配置
* 基础组件到核心组件
* 经典UI到触屏优化UI

有关这些工具的使用的详细信息，请参 [阅其文档](http://opensource.adobe.com/aem-modernize-tools/)。

>[!NOTE]
>
>AEM现代化工具是一项社区工作，Adobe不支持或担保。

## 核心组件支持 {#core-component-support}

核心组件是 AEM 的一个组成部分，依原样提供支持，并作为“快速入门”的一部分提供，须遵循相同的条款和条件。

与其他AEM产品功能一样，一般规则为：首先宣布弃用组件，并且以下AEM版本最早已删除组件。 这样，客户在放弃支持之前，至少可以在一个发布周期内迁移到组件的新版本。

每个组件的版本都清楚地声明了其支持的 AEM 版本。当某个 AEM 版本不再受到支持时，该版本 AEM 的核心组件也不再受到支持。

有关支持组件自定义的详细信息，请参阅自定 [义核心组件](customizing.md) 。

## 基础组件支持 {#foundation-component-support}

由于基础组件在许多AEM版本中用作了大量项目开发的基础，因此在可预见的将来，它们将继续受支持。

However, Adobe's development emphasis has shifted to the Core Components and new features will be added to them, whereas [nearly all Foundation Components have been deprecated with AEM 6.5](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/default-components-foundation.html) and only bug fixes will be made to the Foundation Components going forward.

**阅读下一篇文章：**

* [使用核心组件](using.md) -在您自己的项目中开始使用核心组件。
* [组件准则](guidelines.md) -了解核心组件的实施模式。
