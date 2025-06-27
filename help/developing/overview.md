---
title: 开发核心组件
description: 核心组件提供可靠且可扩展的基本组件，这些组件提供了丰富的功能、连续交付、组件版本控制、现代化实施、精简标记以及内容的 JSON 导出。
role: Architect, Developer, Admin
exl-id: 0f79cac1-a3b0-487e-90be-0bd8263d3912
source-git-commit: 5994133947ff697f7c866fe61598c58e37e77008
workflow-type: ht
source-wordcount: '1130'
ht-degree: 100%

---

# 开发核心组件 {#developing-core-components}

核心组件提供可靠且可扩展的基本组件，这些组件提供了丰富的功能、连续交付、组件版本控制、现代化实施、精简标记以及内容的 JSON 导出。

{{traditional-aem}}

## 如何使用核心组件获得成功 {#how-to-succeed}

核心组件的功能强大、灵活且易于使用和自定义。[遵循几个关键准则](success.md)将确保成功实施带核心组件的项目。

## 迁移到核心组件

任何新项目应该使用核心组件实施。但是，现有组件通常具有广泛的基础组件实施。

### 从基础组件迁移 {#from-foundation}

对现有项目进行较大的变动（例如，品牌再造或者整体重构）通常会提供迁移到核心组件的机会。为了协助此迁移，Adobe 提供了多种迁移工具，以鼓励采用核心组件和最新的 AEM 技术。

[AEM 现代化工具](https://opensource.adobe.com/aem-modernize-tools/)可以轻松地实现下列转换：

* 静态模板到可编辑模板
* 设计配置到策略
* 基础组件到核心组件
* 经典 UI 到触控式 UI

有关这些工具用法的更多信息，[请参阅相应文档](https://opensource.adobe.com/aem-modernize-tools/)。

>[!NOTE]
>
>AEM 现代化工具是社区合作的结果，并非由 Adobe 提供支持或担保。

## 通过移动到 AEM as a Cloud Service 进行迁移 {#via-aemaacs}

由于 AEM as a Cloud Service 自动随最新版本的核心组件提供，在您从内部部署 AEM 安装迁移时，您需要在项目 `pom.xml` 文件中删除与核心组件的任何依赖关系。

您的代理组件仍然像以前一样工作，因为代理指向必需的超类型，而超类型路径中有版本。通过这种方法，只需要删除依赖关系，就可以使核心组件像内部部署一样在 AEMaaCS 中工作。

与任何其他 AEMaaCS 项目一样，您还需要将依赖关系添加到 AEM SDK jar。这并非特定于核心组件，但是必需的。

```xml
<dependency>
   <groupId>com.adobe.aem</groupId>
   <artifactId>aem-sdk-api</artifactId>
</dependency>
```

有关 AEMaaCS 项目的更多信息，请参阅文档 [AEM 项目结构](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html)。

## 核心组件支持 {#core-component-support}

核心组件是 AEM 的一个组成部分，依原样提供支持，并作为“快速入门”的一部分提供，须遵循相同的条款和条件。

与其他 AEM 产品功能一样，一般规则是：首先宣布组件将弃用，并且最早从以下 AEM 发行版本中删除。这为客户提供了至少一个发行周期的时间，在停止支持之前移到组件的新版本。

每个组件的版本都清楚地声明了其支持的 AEM 版本。当某个 AEM 版本不再受到支持时，该版本 AEM 的核心组件也不再受到支持。

有关组件自定义项支持的详细信息，请参阅[自定义核心组件](customizing.md)页面。


## 技术功能 {#technical-capabilities}

下表概述了核心组件与基础组件的不同之处。

有关创作功能的详细信息以及可以预配置它们的选项，[请参阅有关它们的创作页面](/help/get-started/authoring.md)。

| **功能** | **核心组件** | **基础组件** |
|-----|---|---|
| 逻辑实施 | Java POJO 和 [Sling 模型](https://sling.apache.org/documentation/bundles/models.html)注释 | JSP 代码 |
| 标记定义 | [HTML 模板语言](https://experienceleague.adobe.com/docs/experience-manager-htl/using/overview.html) (HTL) 语法 | JSP 代码 |
| XSS 净化 | 由 HTL 自动执行 | 大部分手动 |
| CSS 类命名 | 基于 [Block Element Modifier](https://getbem.com/) (BEM) 表示法（截止到发行版本 2.0.0）的标准化命名约定 | 自定义架构 |
| 对话框定义 | [Coral 3](https://helpx.adobe.com/cn/experience-manager/6-5/sites/developing/using/reference-materials/coral-ui/coralui3/index.html) | Coral 2 + 经典 UI |
| JSON 输出 | [Sling 模型导出器和 Jackson 序列化](https://sling.apache.org/documentation/bundles/models.html#exporter-framework-since-130) | 默认 Sling Servlet |
| 版本控制 | [用于模型和 HTL](guidelines.md) | 无 |
| 测试 | 单元测试 + 集成测试 | 集成测试 |
| 交付 | [通过公开 GitHub](https://github.com/adobe/aem-core-wcm-components) | 通过 Quickstart |
| 许可 | [Apache 许可](https://www.apache.org/licenses/LICENSE-2.0) | Adobe 专有 |
| 参与 | 通过拉取请求 | 不可能 |
| 辅助功能 | 与 [WCAG 2.0 AA 标准](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html)完全兼容 | 仅与 [WCAG 2.0 AA 标准](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html)部分兼容 |

## 组件列表 {#component-list}

下表列出了可用的核心组件、其 API 的链接，并说明了它们取代的基础组件。

| 核心组件 | 描述 | 取代的基础组件 |
|---|---|---|
| [页面](https://adobe.com/go/aem_cmp_tech_page_v2_cn) | 响应式页面，与模板编辑器配合使用 | `/libs/foundation/components/page /libs/wcm/foundation/components/page` |
| [痕迹导航](https://adobe.com/go/aem_cmp_tech_breadcrumb_v2_cn) | 页面层次结构导航 | `/libs/foundation/components/breadcrumb` |
| [标题](https://adobe.com/go/aem_cmp_tech_title_v2_cn) | H1-H6 标题 | `/libs/foundation/components/title /libs/wcm/foundation/components/title` |
| [文本](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/text/v2/text) | 富文本 | `/libs/foundation/components/text /libs/foundation/components/table /libs/wcm/foundation/components/text` |
| [图像](https://adobe.com/go/aem_cmp_tech_image_v2_cn) | 智能和延迟加载优化再现大小 | `/libs/foundation/components/image /libs/foundation/components/adaptiveimage /libs/foundation/components/logo /libs/foundation/components/mobileimage  /libs/foundation/components/mobilelogo /libs/wcm/foundation/components/image` |
| [列表](https://adobe.com/go/aem_cmp_tech_list_v2_cn) | 页面的列表 | `/libs/foundation/components/list /libs/foundation/components/mobilelist /libs/wcm/foundation/components/list` |
| [社交媒体共享](https://adobe.com/go/aem_cmp_tech_sharing_v1_cn) | Facebook 和 Pinterest 共享小组件 | `-` |
| [表单容器](https://adobe.com/go/aem_cmp_tech_form_container_v2_cn) | 响应式表单段落系统 | `/libs/foundation/components/form/start /libs/foundation/components/form/end` |
| [表单文本](https://adobe.com/go/aem_cmp_tech_form_text_v2_cn) | 文本输入字段 | `/libs/foundation/components/form/text /libs/foundation/components/form/password` |
| [表单选项](https://adobe.com/go/aem_cmp_tech_form_options_v2_cn) | 多选输入字段 | `/libs/foundation/components/form/checkbox /libs/foundation/components/form/radio /libs/foundation/components/form/dropdown` |
| [表单隐藏](https://adobe.com/go/aem_cmp_tech_form_hidden_v2_cn) | 隐藏的输入字段 | `/libs/foundation/components/form/hidden` |
| [表单按钮](https://adobe.com/go/aem_cmp_tech_form_button_v2_cn) | 提交或自定义按钮 | `/libs/foundation/components/form/submit` |
| [导航](https://adobe.com/go/aem_cmp_tech_navigation_v1_cn) | 列出嵌套页面层次结构的网站导航组件 | `/libs/foundation/components/topnav /libs/foundation/components/mobiletopnav` |
| [语言导航](https://adobe.com/go/aem_cmp_tech_langnav_v1_cn) | 列出全球语言结构的语言和国家/地区切换器 | `-` |
| [快速搜索](https://adobe.com/go/aem_cmp_tech_search_v1_cn) | 在下拉菜单中将结果显示为就地建议的搜索组件 | `/libs/foundation/components/search` |
| [Teaser](https://adobe.com/go/aem_cmp_tech_teaser_v1_cn) | 允许内容作者轻松地创建 Teaser 以进一步让内容使用图像、标题或富文本，并将其链接到进一步的内容或其他操作 | `-` |
| [选项卡](https://adobe.com/go/aem_cmp_tech_tabs_v1_cn) | 允许内容作者在多个选项卡中整理页面内容 | `-` |
| [轮盘](https://adobe.com/go/aem_cmp_tech_carousel_v1_cn) | 允许内容作者将内容排列在旋转的幻灯片轮盘中 | `/libs/foundation/components/carousel` |
| [内容片段](https://adobe.com/go/aem_cmp_tech_cf_v1_cn) | 允许显示内容片段 | `-` |
| [内容片段列表](https://adobe.com/go/aem_cmp_tech_cflist_v1_cn) | 允许显示内容片段列表 | `-` |
| [分隔符](https://adobe.com/go/aem_cmp_tech_separator_v1_cn) | 分隔页面上的内容 | `-` |
| [折叠](https://adobe.com/go/aem_cmp_tech_accordion_v1_cn) | 在可隐藏的折叠中排列内容面板 | `-` |
| [容器](https://adobe.com/go/aem_cmp_tech_container_v1_cn) | 在容器中排列组件 | `-` |
| [按钮](https://adobe.com/go/aem_cmp_tech_button_v1_cn) | 在页面上创建按钮 | `-` |
| [下载](https://adobe.com/go/aem_cmp_tech_download_v1_cn) | 将可下载的资源添加到页面 | `-` |
| [体验片段](https://adobe.com/go/aem_cmp_tech_xf_v1_cn) | 将体验片段添加到页面 | `/libs/cq/experience-fragments/editor/components/experiencefragment` |
| [嵌入](https://adobe.com/go/aem_cmp_tech_embed_v1_cn) | 在页面中嵌入外部资源 | - |
| [进度条](https://adobe.com/go/aem_cmp_tech_progress_v1_cn) | 提供向目标进展的可视化表示形式 | - |
| [PDF 查看器](https://adobe.com/go/aem_cmp_tech_pdfviewer_v1_cn) | 在页面上呈现 PDF 文档 | - |

## 核心组件升级 {#upgrade-of-core-components}

版本化组件的一个优点是，它允许将迁移到新 AEM 版本与迁移到新组件版本分隔开。此外，如果有新组件版本可用，它允许单独地将各个组件迁移到新版本。

迁移到新 AEM 版本不会影响核心组件的工作方式，前提是其版本也支持正在迁移到的新 AEM 版本。提供给核心组件使用的自定义项，只要不使用已经[弃用或删除](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/deprecated-removed-features.html)的 API，也不应受影响。

迁移到核心组件的新版本也不会影响组件的工作方式，但是可能会向页面作者引入新功能，在默认行为不符合需要时，可能需要模板编辑者进行一些配置。但是可能需要适应自定义项，有关详细信息，请参阅[自定义核心组件](customizing.md#upgrade-compatibility-of-customizations)页面。
