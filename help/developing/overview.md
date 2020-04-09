---
title: 开发核心组件
description: 核心组件提供强大且可扩展的基本组件，这些组件可以优惠丰富的功能、连续投放、组件版本控制、现代实施、精益标记和内容的JSON导出。
translation-type: tm+mt
source-git-commit: c338428a681f652d17bb972fb6a2abf216a338c3

---


# 开发核心组件 {#developing-core-components}

## When to Use the Core Components? {#when-to-use-the-core-components}

由于核心组件是全新的，并且具备多种优势，因此建议新的 AEM 项目使用这些组件。对于现有项目，可以考虑在进行更大型项目工作期间进行迁移，例如在重新品牌化或整体重构工作期间。

因此，Adobe提供以下建议：

* **新项目**&#x200B;新项目应始终尝试使用核心组件。 如果核心组件不能直接使用或扩展 [以满足项目要求](customizing.md) ，请按照核心组件中所述的组件架构创建自定义组件。 除非其他可能，否则请避免使用 [基础组件](#foundation-component-support)。
* **现有项**&#x200B;目推荐将继续使用 [基础组件](#foundation-component-support)，除非计划了站点或组件重构。\
   由于它们被大多数现有项目广泛使用，因此将继 [续支持基础组件。](#foundation-component-support)
* **新自定义组**&#x200B;件评估是否可以自 [定义现有核心组件](customizing.md)。\
   否则，建议按照组件准则构建新的自定义 [组件](guidelines.md)。
* **现有自定义**&#x200B;组件如果您的组件按预期工作，则按原样保留它们。\
   否则，请参阅上面的“新建自定义组件”。

## 如何使核心组件取得成功 {#how-to-succeed}

核心组件功能强大、灵活且易于使用和自定义。 [遵循几个关键准则](success.md) ，将确保您的核心组件项目取得成功。

## 迁移到核心组件

任何新项目都应使用核心组件来实施。 但是，现有项目通常具有广泛的基础组件实施。

对现有项目（例如重新品牌化或整体重构）进行更大的努力通常会优惠到核心组件。 为便于迁移，Adobe提供了许多迁移工具，鼓励采用核心组件和最新的AEM技术。

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


## 技术功能 {#technical-capabilities}

下表概述了核心组件与基础组件之间的差异。

有关其创作功能和可预先配置的选项的详细信息，请 [参阅有关这些功能的创作页面](/help/get-started/authoring.md)。

| **功能** | **核心组件** | **基础组件** |
|-----|---|---|
| 逻辑实现 | 带有 [Sling Models注释的Java POJO](https://sling.apache.org/documentation/bundles/models.html) | JSP代码 |
| 标记定义 | [HTML模板语言](https://docs.adobe.com/content/help/zh-Hans/experience-manager-htl/using/overview.html) (HTL)语法 | JSP代码 |
| XSS清理 | 由HTL自动化 | 多为手动 |
| CSS类命名 | 基于块元素修 [饰符](https://getbem.com/) (BEM)记号的标准化命名约定（从版本2.0.0开始） | 自定义方案 |
| 对话框定义 | [珊瑚3](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/reference-materials/coral-ui/coralui3/index.html) | Coral 2 +经典UI |
| JSON输出 | [Sling Models Exporter（带有Jackson序列化）](https://sling.apache.org/documentation/bundles/models.html#exporter-framework-since-130) | 默认Sling Servlet |
| 版本控制 | [对于模型和HTL](guidelines.md) | 无 |
| 测试 | 单元测试+集成测试 | 集成测试 |
| 交付 | [通过公共GitHub](https://github.com/adobe/aem-core-wcm-components) | 通过快速入门 |
| License | [Apache许可证](https://www.apache.org/licenses/LICENSE-2.0) | Adobe专有 |
| 贡献 | 通过拉取请求 | 不可能 |
| 辅助功能 | 完全符合 [WCAG 2.0 AA标准](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html | 仅部分符合 [WCAG 2.0 AA标准](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html) |

## 组件列表 {#component-list}

下表列表了可用的核心组件，它们链接到其API并指示它们替换的基础组件。

| 核心组件 | 描述 | 已更换基础组件 |
|---|---|---|
| [页面](https://adobe.com/go/aem_cmp_tech_page_v2) | 使用模板编辑器的响应式页面 | `/libs/foundation/components/page /libs/wcm/foundation/components/page` |
| [痕迹导航](https://adobe.com/go/aem_cmp_tech_breadcrumb_v2) | 页面层次导航 | `/libs/foundation/components/breadcrumb` |
| [标题](https://adobe.com/go/aem_cmp_tech_title_v2) | H1-H6标题 | `/libs/foundation/components/title /libs/wcm/foundation/components/title` |
| [文本](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/text/v2/text) | 富文本 | `/libs/foundation/components/text /libs/foundation/components/table /libs/wcm/foundation/components/text` |
| [图像](https://adobe.com/go/aem_cmp_tech_image_v2) | 智能和延迟加载最佳再现大小 | `/libs/foundation/components/image /libs/foundation/components/adaptiveimage /libs/foundation/components/logo /libs/foundation/components/mobileimage  /libs/foundation/components/mobilelogo /libs/wcm/foundation/components/image` |
| [列表](https://adobe.com/go/aem_cmp_tech_list_v2) | 页面列表 | `/libs/foundation/components/list /libs/foundation/components/mobilelist /libs/wcm/foundation/components/list` |
| [社交媒体共享](https://adobe.com/go/aem_cmp_tech_sharing_v1) | Facebook和Pinterest共享构件 | `-` |
| [表单容器](https://adobe.com/go/aem_cmp_tech_form_container_v2) | 响应式表单段落系统 | `/libs/foundation/components/form/start /libs/foundation/components/form/end` |
| [表单文本](https://adobe.com/go/aem_cmp_tech_form_text_v2) | 文本输入字段 | `/libs/foundation/components/form/text /libs/foundation/components/form/password` |
| [表单选项](https://adobe.com/go/aem_cmp_tech_form_options_v2) | 多个选项输入字段 | `/libs/foundation/components/form/checkbox /libs/foundation/components/form/radio /libs/foundation/components/form/dropdown` |
| [隐藏的表单](https://adobe.com/go/aem_cmp_tech_form_hidden_v2) | 隐藏输入字段 | `/libs/foundation/components/form/hidden` |
| [表单按钮](https://adobe.com/go/aem_cmp_tech_form_button_v2) | 提交或自定义按钮 | `/libs/foundation/components/form/submit` |
| [导航](https://adobe.com/go/aem_cmp_tech_navigation_v1) | 列表嵌套页面层次结构的站点导航组件 | `/libs/foundation/components/topnav /libs/foundation/components/mobiletopnav` |
| [语言导航](https://adobe.com/go/aem_cmp_tech_langnav_v1) | 列表全球语言结构的语言和国家／地区切换程序 | `-` |
| [快速搜索](https://adobe.com/go/aem_cmp_tech_search_v1) | 在下拉菜单中将结果显示为就地建议的搜索组件 | `/libs/foundation/components/search` |
| [Teaser](https://adobe.com/go/aem_cmp_tech_teaser_v1) | 允许内容作者使用图像、标题或富文本轻松创建Teaser以进一步内容，并链接到其他内容或其他操作 | `-` |
| [选项卡](https://adobe.com/go/aem_cmp_tech_tabs_v1) | 允许内容作者在多个选项卡中组织页面内容 | `-` |
| [轮播](https://adobe.com/go/aem_cmp_tech_carousel_v1) | 允许内容作者在旋转的幻灯片轮盘中组织内容 | `/libs/foundation/components/carousel` |
| [内容片段](https://adobe.com/go/aem_cmp_tech_cf_v1) | 允许显示内容片段 | `-` |
| [内容片段列表](https://adobe.com/go/aem_cmp_tech_cflist_v1) | 允许显示内容片段的列表 | `-` |
| [分隔符](https://adobe.com/go/aem_cmp_tech_separator_v1) | 分隔页面上的内容 | `-` |
| [折叠](https://adobe.com/go/aem_cmp_tech_accordion_v1) | 在可折叠的面板中组织内容面板 | `-` |
| [容器](https://adobe.com/go/aem_cmp_tech_container_v1) | 在容器中组织组件 | `-` |
| [按钮](https://adobe.com/go/aem_cmp_tech_button_v1) | 在页面上创建按钮 | `-` |
| [下载](https://adobe.com/go/aem_cmp_tech_download_v1) | 向页面添加可下载的资源 | `-` |
| [体验片段](https://adobe.com/go/aem_cmp_tech_xf_v1) | 将体验片段添加到页面 | `/libs/cq/experience-fragments/editor/components/experiencefragment` |
| [嵌入](https://adobe.com/go/aem_cmp_tech_embed_v1) | 在页面中嵌入外部资源 | - |

### 即将推出的组件 {#upcoming-components}

有关即将推出的核心组件路线图的概述，请参阅GitHub [上的专题wiki](https://github.com/adobe/aem-core-wcm-components/wiki/home)。

## 升级核心组件 {#upgrade-of-core-components}

版本控制组件的一个好处是它允许将迁移到新AEM版本与迁移到新组件版本分开。 此外，如果有新组件版本可用，它允许将每个组件单独迁移到新版本。

迁移到新AEM版本不会影响核心组件的工作方式，前提是其版本还支持要迁移到的新AEM版本。 对核心组件进行的自定义也不应受到影响，只要它们不使用已弃用或删除 [的API](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/release-notes/deprecated-removed-features.html)。

迁移到新版本的核心组件也不会影响组件的工作方式，但可能会为页面作者引入新功能，这可能需要模板编辑器进行一些配置，以防不需要默认行为。 但是，可能需要调整自定义，有关详细信息，请参阅自 [定义核心组件](customizing.md#upgrade-compatibility-of-customizations) 。
