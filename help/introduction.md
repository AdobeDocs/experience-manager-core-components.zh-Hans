---
title: 核心组件简介
description: '获取核心组件问题的解决方案，并允许其他人在 AEM 中创作元素。 '
role: Architect, Developer, Admin, User
exl-id: d294db22-4cb0-48a4-9366-03fda5b8bb8e
source-git-commit: c572a2f5ab4e975e0ef467ab071fd25b373be18b
workflow-type: tm+mt
source-wordcount: '927'
ht-degree: 100%

---

# 核心组件简介{#core-components-introduction}

在 Adobe Experience Manager 中，组件是结构化元素，用于构成所创作的页面内容。组件一直是 AEM 体验的一个基本元素，它使页面的创建过程变得简便但功能强大，使开发人员对组件的开发变得灵活且可扩展。

核心组件是一组用于 AEM 的标准化网站内容管理 (WCM) 组件，可加快开发速度并降低网站的维护成本。

## 资源 {#resources}

* **[组件库：](https://www.adobe.com/go/aem_cmp_library_cn)**&#x200B;一组用于查看组件的各种配置的示例。
* **组件文档（此文档）：**&#x200B;对于开发人员和作者，包含有关每个组件的详细信息。
* **[核心组件 GitHub 存储库：](https://github.com/adobe/aem-core-wcm-components)**&#x200B;对于开发人员，包含每个组件和项目下载的详细信息。
* 开始使用：
   * **[使用核心组件获得成功：](/help/developing/success.md)**&#x200B;在任何将使用核心组件的项目开始之前要考虑的指南。
   * **[WKND 教程：](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)**&#x200B;有关构建新站点的两日教程。
   * **[Summit 教程：](https://expleague.azureedge.net/labs/L767/index.html)**&#x200B;有关构建新站点的两小时教程（来自 US Summit 2019 的实验室）。
   * **[Gems 网络研讨会：](https://helpx.adobe.com/cn/experience-manager/kt/eseminars/gems/AEM-Core-Components.html)**&#x200B;核心组件导览（于 2018 年 12 月录制）。

## 功能 {#features}

|  |  |
|---|---|
| 可以即刻投入使用 | 核心组件是 30 个经过充分测试、广泛使用且性能出色的强大组件。 |
| 云就绪 | 无论是在 [AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html)、[Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams) 上还是内部部署，这些组件都能运行。 |
| 可以通用 | 这些组件代表了作者可用来设计几乎任何布局的通用概念。 |
| 可配置 | 模板级[内存策略](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/full-stack/components-templates/templates.html#content-policies)定义页面作者可以使用或无法使用的功能。 |
| 可跟踪 | [Adobe Client Data Layer 集成](/help/developing/data-layer/overview.md)允许全方位跟踪访客体验。 |
| 可访问 | 它们符合 [WCAG 2.1 标准](https://www.w3.org/TR/WCAG21/)，提供 ARIA 标签，并支持键盘导航（[已知问题](https://github.com/adobe/aem-core-wcm-components/issues?utf8=✓&amp;q=is%3Aissue+is%3Aopen+accessibility+in%3Atitle)）。 |
| SEO 友好 | HTML 输出是语义的，并提供 [schema.org](https://schema.org) 微数据注释。 |
| WebApp 就绪 | [简化的 JSON 输出](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/development/develop-sling-model-exporter.html)允许客户端渲染，并且仍可进行[上下文内编辑](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html)。 |
| AMP 支持 | 组件已内置[对 AMP 标准的支持，](/help/developing/amp.md)可加快移动体验。 |
| 设计套件 | 利用 [Adobe XD UI 套件](https://experienceleague.adobe.com/docs/experience-manager-learn/assets/AEM-CoreComponents-UI-Kit.xd)，设计人员可以创建随后可[按需样式化](https://github.com/adobe/aem-guides-wknd/releases/download/aem-guides-wknd-0.0.2/AEM_UI-kit-WKND.xd)的线框。 |
| 可主题化 | 这些组件实施[样式系统](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/features/style-system.html)，且标记遵循 [BEM CSS 约定](http://getbem.com/)。 |
| 可自定义 | 可利用几种模式来[轻松进行自定义设置](developing/customizing.md)（从调整 HTML 到高级功能重用）。 |
| 版本控制 | [版本控制策略](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-policies)可确保核心组件在改进可能影响您的内容时不会中断您的网站。 |
| 可本地化 | 智能引用解析允许特定组件自动查找和[自动渲染对应的本地化内容](get-started/localization.md)。 |
| 开源 | 如果有出错的地方，请[做出您的改进！](https://github.com/adobe/aem-core-wcm-components/blob/master/CONTRIBUTING.md) |

## 组件 {#the-components}

当前版本的核心组件具有以下组件。

### 模板组件 {#template-components}

* [页面](components/page.md)
* [导航](components/navigation.md)
* [语言导航](components/language-navigation.md)
* [痕迹导航](components/breadcrumb.md)
* [快速搜索](components/quick-search.md)
* [目录](components/tableofcontents.md)

### 页面创作组件 {#page-authoring-components}

* [标题](components/title.md)
* [文本](components/text.md)
* [图像](components/image.md)
* [按钮](components/button.md)
* [Teaser](components/teaser.md)
* [下载](components/download.md)
* [列表](components/list.md)
* [体验片段](components/experience-fragment.md)
* [内容片段](components/content-fragment-component.md)
* [内容片段列表](components/content-fragment-list.md)
* [嵌入](components/embed.md)
* [社交媒体共享](components/sharing.md)
* [分隔符](components/separator.md)
* [进度条](components/progress-bar.md)
* [PDF 查看器](components/pdf-viewer.md)

### 容器组件 {#container-components}

* [容器](components/container.md)
* [轮盘](components/carousel.md)
* [选项卡](components/tabs.md)
* [折叠](components/accordion.md)

### 表单组件 {#form-components}

* [表单容器](components/forms/form-container.md)
* [表单文本](components/forms/form-text.md)
* [表单选项](components/forms/form-options.md)
* [表单隐藏](components/forms/form-hidden.md)
* [表单按钮](components/forms/form-button.md)

>[!NOTE]
>
>核心组件不可直接供作者使用，[开发团队必须先将它们集成到您的环境中](get-started/using.md)。在集成后，可通过[模板编辑器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)使其可用并进行预配置。

>[!NOTE]
>
>个别核心组件的某些版本可能仅与特定版本的 AEM 兼容。
>
>有关兼容性信息，请参阅特定组件对应的帮助页面（可在上文中的列表中点击相应链接），或参考[核心组件版本](versions.md)文档以了解更多信息。

## 系统要求 {#system-requirements}

| 核心组件发行版本 | AEM as a Cloud Service | AEM 6.5 补丁级别 | Java SE 版本 | Maven 版本 |
|---------|---------|---------|---------|---------|
| [2.20.0](https://github.com/adobe/aem-core-wcm-components/releases/tag/core.wcm.components.reactor-2.20.0) | 连续 | 6.5.10.0+ * | 8, 11 | 3.3.9+ |

>[!NOTE]
>
>(*) 自版本 2.11.0 开始，需要 `org.apache.sling.models.impl` 版本 1.4.12 或更高版本（由于 [SLING-8781](https://issues.apache.org/jira/browse/SLING-8781)）。这会在将来的 Service Pack 中为 AEM 6.4 和 6.5 提供。在此之前，Sling 模型捆绑包将包含在 `core.wcm.components.all` 包中。

有关以前的核心组件版本的要求，请参阅[核心组件版本](versions.md)。

核心组件要求使用[可编辑模板](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/page-authoring/template-editor-feature-video-use.html)，并且不支持经典 UI 和静态模板。如果需要，请检查 [AEM 现代化工具](https://opensource.adobe.com/aem-modernize-tools/pages/tools.html)以使用这些现代化 AEM 功能更新您的项目。

要设置本地开发环境，请查看[此 AEM as a Cloud Service 开发工具包概述](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/local-development-environment-set-up/overview.html)或适用于[旧版 AEM](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html) 的本文档。

>[!TIP]
>
>核心组件自动成为 AEM as a Cloud Service 的一部分，并且您始终拥有最新版本的核心组件。
>
>有关如何在 AEMaaCS 中和内部部署开始使用核心组件的更多信息，请参阅[使用核心组件](/help/get-started/using.md)文档。
