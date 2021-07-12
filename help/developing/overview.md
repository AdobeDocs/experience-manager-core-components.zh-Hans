---
title: 开发核心组件
description: 核心组件提供了强大且可扩展的基本组件，这些组件提供了丰富的功能、连续交付、组件版本控制、现代实施、精益标记和内容的JSON导出。
role: Architect, Developer, Admin
exl-id: 0f79cac1-a3b0-487e-90be-0bd8263d3912
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '1591'
ht-degree: 14%

---

# 开发核心组件 {#developing-core-components}

## 何时使用核心组件？ {#when-to-use-the-core-components}

由于核心组件是全新的，并且具备多种优势，因此建议新的 AEM 项目使用这些组件。对于现有项目，可以考虑在进行更大型项目工作期间进行迁移，例如在重新品牌化或整体重构工作期间。

因此，Adobe提供了以下建议：

* **新项**
目新项目应始终尝试使用核心组件。如果核心组件不能直接使用或[extended](customizing.md)以满足项目要求，请按照核心组件中规定的组件架构创建自定义组件。 除非其他情况，否则请避免使用[基础组件](/help/versions.md#foundation-component-support)。
* **除非**
计划了站点或组件重 [构，否则现有项目推荐将继续使用基础组件](/help/versions.md#foundation-component-support)。\
   由于这些组件在大多数现有项目中的使用非常广泛，因此将继续支持基础组件[。](/help/versions.md#foundation-component-support)
* **新自定义**
组件评估是否可 [以自定义现有核心组件](customizing.md)。\
   如果没有，建议按照[组件准则](guidelines.md)构建新的自定义组件。
* **现有自定**
义组件如果您的组件正常工作，请按原样保留它们。
\
   如果没有，请参阅上面的“新建自定义组件”。

## 如何使用核心组件取得成功 {#how-to-succeed}

核心组件功能强大、灵活，易于使用和自定义。 [遵循一些关键](success.md) 准则将确保您具有核心组件的项目取得成功。

## 迁移到核心组件

任何新项目都应使用核心组件进行实施。 但是，现有项目通常会大量实施基础组件。

### 从基础组件迁移 {#from-foundation}

对现有项目进行更大的努力（例如重新品牌化或整体重构）通常会提供迁移到核心组件的机会。 为了促进此迁移，Adobe提供了许多迁移工具，以鼓励采用核心组件和最新的AEM技术。

[AEM现代化工](http://opensource.adobe.com/aem-modernize-tools/) 具包，可轻松转换：

* 静态模板到可编辑模板
* 设计配置到策略
* 基础组件到核心组件
* 经典 UI 到触控式 UI

有关这些工具用法的更多信息，请[参阅其文档](http://opensource.adobe.com/aem-modernize-tools/)。

>[!NOTE]
>
>AEM现代化工具是社区共同努力的结果，不受Adobe支持或保证。

## 通过移动到AEM as aCloud Service迁移 {#via-aemaacs}

由于AEM as a Cloud Service会自动附带最新版本的核心组件，因此当您从内部部署AEM安装中移动时，将需要在项目`pom.xml`文件中删除对核心组件的任何依赖项。

您的代理组件仍会像以前一样工作，因为   代理指向必要的超类型，且超类型路径的版本为。 这样，只需删除依赖项，核心组件便可以像在内部部署中那样在AEMaCS中工作。

与任何其他AEM SDK项目一样，您还需要向AEM AaCS Jar添加依赖项。 这并非特定于核心组件，而是必需的。

```xml
<dependency>
   <groupId>com.adobe.aem</groupId>
   <artifactId>aem-sdk-api</artifactId>
</dependency>
```

有关AEMaaCS项目的更多信息，请参阅文档[AEM项目结构](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html)。

## 核心组件支持 {#core-component-support}

核心组件是 AEM 的一个组成部分，依原样提供支持，并作为“快速入门”的一部分提供，须遵循相同的条款和条件。

与其他AEM产品功能一样，一般规则为：组件最先宣布弃用，并且最早会在以下AEM版本中删除。 这为客户提供了至少一个发布周期，以便在停止对组件的支持之前迁移到组件的新版本。

每个组件的版本都清楚地声明了其支持的 AEM 版本。当某个 AEM 版本不再受到支持时，该版本 AEM 的核心组件也不再受到支持。

有关组件自定义支持的详细信息，请参阅[自定义核心组件](customizing.md)页面。


## 技术能力 {#technical-capabilities}

下表概述了核心组件与基础组件之间的差异。

有关其创作功能和预配置选项的详细信息， [请参阅有关这些功能的创作页面](/help/get-started/authoring.md)。

| **功能** | **核心组件** | **基础组件** |
|-----|---|---|
| 逻辑实施 | 带有[Sling模型](https://sling.apache.org/documentation/bundles/models.html)批注的Java POJO | JSP代码 |
| 标记定义 | [HTML模板语言](https://docs.adobe.com/content/help/zh-Hans/experience-manager-htl/using/overview.html) (HTL)语法 | JSP代码 |
| XSS清理 | 由HTL自动 | 大部分为手动 |
| CSS类命名 | 基于[块元素修饰符](https://getbem.com/)(BEM)表示法的标准化命名约定（自2.0.0版起） | 自定义方案 |
| 对话框定义 | [珊瑚3](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/reference-materials/coral-ui/coralui3/index.html) | Coral 2 +经典UI |
| JSON输出 | [Jackson序列化的Sling模型导出程序](https://sling.apache.org/documentation/bundles/models.html#exporter-framework-since-130) | 默认Sling Servlet |
| 版本控制 | [对于模型和HTL](guidelines.md) | 无 |
| 测试 | 单元测试+集成测试 | 集成测试 |
| 交付 | [通过公共GitHub](https://github.com/adobe/aem-core-wcm-components) | 通过快速入门 |
| License | [Apache许可证](https://www.apache.org/licenses/LICENSE-2.0) | Adobe专有 |
| 贡献 | 通过拉取请求 | 不可能 |
| 辅助功能 | 完全符合[WCAG 2.0 AA标准](https://docs.adobe.com/content/help/zh-Hans/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html) | 仅部分符合[WCAG 2.0 AA标准](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html) |

## 组件列表 {#component-list}

下表列出了可用的核心组件（链接到其API），并指示它们替换的基础组件。

| 核心组件 | 描述 | 已更换基础组件 |
|---|---|---|
| [页面](https://adobe.com/go/aem_cmp_tech_page_v2) | 使用模板编辑器的响应式页面 | `/libs/foundation/components/page /libs/wcm/foundation/components/page` |
| [痕迹导航](https://adobe.com/go/aem_cmp_tech_breadcrumb_v2) | 页面层次结构导航 | `/libs/foundation/components/breadcrumb` |
| [标题](https://adobe.com/go/aem_cmp_tech_title_v2) | H1-H6标题 | `/libs/foundation/components/title /libs/wcm/foundation/components/title` |
| [文本](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/text/v2/text) | 富文本 | `/libs/foundation/components/text /libs/foundation/components/table /libs/wcm/foundation/components/text` |
| [图像](https://adobe.com/go/aem_cmp_tech_image_v2) | 智能和延迟加载最佳呈现版本大小 | `/libs/foundation/components/image /libs/foundation/components/adaptiveimage /libs/foundation/components/logo /libs/foundation/components/mobileimage  /libs/foundation/components/mobilelogo /libs/wcm/foundation/components/image` |
| [列表](https://adobe.com/go/aem_cmp_tech_list_v2) | 页面列表 | `/libs/foundation/components/list /libs/foundation/components/mobilelist /libs/wcm/foundation/components/list` |
| [社交媒体共享](https://adobe.com/go/aem_cmp_tech_sharing_v1) | Facebook和Pinterest共享小组件 | `-` |
| [表单容器](https://adobe.com/go/aem_cmp_tech_form_container_v2) | 响应式表单段落系统 | `/libs/foundation/components/form/start /libs/foundation/components/form/end` |
| [表单文本](https://adobe.com/go/aem_cmp_tech_form_text_v2) | 文本输入字段 | `/libs/foundation/components/form/text /libs/foundation/components/form/password` |
| [表单选项](https://adobe.com/go/aem_cmp_tech_form_options_v2) | 多个选项输入字段 | `/libs/foundation/components/form/checkbox /libs/foundation/components/form/radio /libs/foundation/components/form/dropdown` |
| [隐藏的表单](https://adobe.com/go/aem_cmp_tech_form_hidden_v2) | 隐藏的输入字段 | `/libs/foundation/components/form/hidden` |
| [表单按钮](https://adobe.com/go/aem_cmp_tech_form_button_v2) | 提交或自定义按钮 | `/libs/foundation/components/form/submit` |
| [导航](https://adobe.com/go/aem_cmp_tech_navigation_v1) | 列出嵌套页面层次结构的网站导航组件 | `/libs/foundation/components/topnav /libs/foundation/components/mobiletopnav` |
| [语言导航](https://adobe.com/go/aem_cmp_tech_langnav_v1) | 列出全球语言结构的语言和国家切换器 | `-` |
| [快速搜索](https://adobe.com/go/aem_cmp_tech_search_v1) | 搜索组件，可在下拉菜单中将结果显示为就地建议 | `/libs/foundation/components/search` |
| [Teaser](https://adobe.com/go/aem_cmp_tech_teaser_v1) | 允许内容作者轻松创建Teaser以使用图像、标题或富文本进一步创建内容，并链接到进一步内容或其他操作 | `-` |
| [选项卡](https://adobe.com/go/aem_cmp_tech_tabs_v1) | 允许内容作者在多个选项卡中组织页面内容 | `-` |
| [轮播](https://adobe.com/go/aem_cmp_tech_carousel_v1) | 允许内容作者以旋转的幻灯片轮播组织内容 | `/libs/foundation/components/carousel` |
| [内容片段](https://adobe.com/go/aem_cmp_tech_cf_v1) | 允许显示内容片段 | `-` |
| [内容片段列表](https://adobe.com/go/aem_cmp_tech_cflist_v1) | 允许显示内容片段列表 | `-` |
| [分隔符](https://adobe.com/go/aem_cmp_tech_separator_v1) | 用于分隔页面上的内容 | `-` |
| [折叠](https://adobe.com/go/aem_cmp_tech_accordion_v1) | 在可折叠的折叠面板中组织内容面板 | `-` |
| [容器](https://adobe.com/go/aem_cmp_tech_container_v1) | 在容器内组织组件 | `-` |
| [按钮](https://adobe.com/go/aem_cmp_tech_button_v1) | 在页面上创建按钮 | `-` |
| [下载](https://adobe.com/go/aem_cmp_tech_download_v1) | 向页面添加可下载的资产 | `-` |
| [体验片段](https://adobe.com/go/aem_cmp_tech_xf_v1) | 将体验片段添加到页面 | `/libs/cq/experience-fragments/editor/components/experiencefragment` |
| [嵌入](https://adobe.com/go/aem_cmp_tech_embed_v1) | 在页面中嵌入外部资源 | - |
| [进度条](https://adobe.com/go/aem_cmp_tech_progress_v1) | 以直观的方式表示实现目标的进展 | - |
| [PDF 查看器](https://adobe.com/go/aem_cmp_tech_pdfviewer_v1) | 在页面上显示PDF文档 | - |

### 即将推出的组件 {#upcoming-components}

有关即将推出的核心组件路线图的概述，请参阅GitHub上的[项目wiki](https://github.com/adobe/aem-core-wcm-components/wiki/home)。

## 核心组件升级 {#upgrade-of-core-components}

版本控制组件的一个好处是，它允许将迁移到新AEM版本的过程与迁移到新组件版本的过程分开。 此外，如果有新的组件版本可用，则允许将每个组件单独迁移到新版本。

迁移到新AEM版本不会影响核心组件的工作方式，前提是其版本还支持要迁移到的新AEM版本。 对核心组件进行的自定义也不应受到影响，前提是它们未使用[已弃用或已删除](https://docs.adobe.com/content/help/zh-Hans/experience-manager-cloud-service/release-notes/deprecated-removed-features.html)的API。

迁移到核心组件的新版本也不会影响组件的工作方式，但可能会向页面作者引入新功能，这可能需要模板编辑器进行一些配置，以防不需要默认行为。 但是，可能需要修改自定义，有关更多详细信息，请参阅[自定义核心组件](customizing.md#upgrade-compatibility-of-customizations)页面。
