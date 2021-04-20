---
title: AEM 项目原型
description: 基于AEM的应用程序的项目模板
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Administrator
translation-type: tm+mt
source-git-commit: 0e737fc766225e00c6d9f5a4c2240e05b49a9a62
workflow-type: tm+mt
source-wordcount: '1043'
ht-degree: 6%

---


# AEM 项目原型 {#aem-project-archetype}

AEM项目原型是一个Maven模板，可创建基于最小、最佳实践的Adobe Experience Manager(AEM)项目，作为网站的起点。

>[!TIP]
>
>可在GitHub](https://github.com/adobe/aem-project-archetype)上找到最新的AEM项目原型[。

## 资源 {#resources}

* **原型文档(此文档):** 原型体系结构及其不同模块概述。
   * **[使用原型：有关](using.md)** 使用原型和可用模块的更多详细信息
   * **[ui.frontend:](uifrontend.md)** 如何使用前端构建模块
* 以下教程基于此原型：
   * **[WKND站点：了](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)** 解如何开始新网站。
   * **[WKND单页应用程序：了](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html)** 解如何构建可在AEM中完全授权的React或Angular Web应用程序。

## 功能 {#features}

* **最佳实践：** 用Adobe的所有最新推荐做法Bootstrap您的网站。
* **低代码：** 编辑模板、创建内容、部署CSS，站点就可上线了。
* **云就绪：如** 果需要，可 [以将AEM作](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html) 为云服务在几天内上线，并简化可扩展性和维护。
* **调度程序：** 项目只能通过确保速度和安全 [性的](https://docs.adobe.com/content/help/zh-Hans/experience-manager-dispatcher/using/dispatcher.html) Dispatcher配置完成。
* **多站点：如** 果需要，原型可生成多语言和多 [区域设置的内容结构](https://docs.adobe.com/content/help/en/experience-manager-65/administering/introduction/msm.html)。
* **核心组件：** 作者可以使用我们的通用标准化组件集 [创建几乎任何布局](/help/introduction.md)。
* **可编辑的模** 板：几乎可以 [组合任何不带代码的模板](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/page-authoring/template-editor-feature-video-use.html)，并定义作者可以编辑的内容。
* **响应式布局：** 在模板或单个页面上， [定义定义断点](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/responsive-layout.html) 的元素重排方式。
* **Header和Footer：使用** 组件的本地化功能，无需代码即可 [组合和本地化它们](https://docs.adobe.com/content/help/zh-Hans/experience-manager-core-components/using/get-started/localization.html)。
* **样式系统：** 通过允许作者将不同的样式应用于自定义 [组件，](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/style-system.html) 避免构建这些组件。
* **前端构建：前端** 开发人员可以使 [用Webpack、](uifrontend.md#webpack-dev-server) TypeScript和 [SASS模](uifrontend.md) 拟AEM页面并构建客户端库。
* **WebApp-Ready：对** 于使用 [](uifrontend-react.md) Reactor  [Angular的站](uifrontend-angular.md)点 [，请使用](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/headless/spa/developing.html) SPA  [SDK](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html)保留在应用程序创作的上下文中。
* **启用商务：** 对于要将AEM Commerce与商务解决方 [案(](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/commerce/home.html) 如Magentoush the Commerce  [](https://magento.com/) Core Components)集成的项目 [](https://github.com/adobe/aem-core-cif-components)。
* **示例代码：** 签出HelloWorld组件以及示例模型、servlet、过滤器和调度程序。
* **开放源：** 如果某些内容不是应有的，则有助于 [](https://github.com/adobe/aem-core-wcm-components/blob/master/CONTRIBUTING.md) 您的改进！

## 使用

要生成项目，请根据需要调整以下命令行：

```shell
mvn -B archetype:generate \
 -D archetypeGroupId=com.adobe.aem \
 -D archetypeArtifactId=aem-project-archetype \
 -D archetypeVersion=26 \
 -D appTitle="My Site" \
 -D appId="mysite" \
 -D groupId="com.mysite" \
```

* 将[AEM的`aemVersion=cloud`设置为Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html);\
   为[Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams)或内部部署设置`aemVersion=6.5.0`。
仅为非云aem版本添加核心组件依赖关系，因为核心组件是作为Cloud Service提供给AEM的OOTB。
* 调整`appTitle="My Site"`以定义网站标题和组件组。
* 调整`appId="mysite"`以定义Maven artifactId、组件、配置和内容文件夹名称以及客户端库名称。
* 调整`groupId="com.mysite"`以定义Maven groupId和Java源包。
* 查找可用属性的列表，查看是否有更多要调整的属性。

## 可用属性

| 名称 | 默认 | 描述 |
--------------------------|----------------|--------------------
| `appTitle` |  | 应用程序标题将用于网站标题和组件组(例如，`"My Site"`)。 |
| `appId` |  | 技术名称将用于组件、配置和内容文件夹名称以及客户端库名称(例如`"mysite"`)。 |
| `artifactId` | *`${appId}`* | 基Maven伪像ID(例如，`"mysite"`)。 |
| `groupId` |  | 基本Maven组ID(例如，`"com.mysite"`)。 |
| `package` | *`${groupId}`* | Java源包(例如`"com.mysite"`)。 |
| `version` | `1.0-SNAPSHOT` | 项目版本(例如`1.0-SNAPSHOT`)。 |
| `aemVersion` | `cloud` | 目标 AEM版本(对于[AEM，可以`cloud`作为Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html);或`6.5.0`，或`6.4.4`（适用于[Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams)或内部部署）。 |
| `sdkVersion` | `latest` | 当`aemVersion=cloud`可指定[SDK](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/developing/aem-as-a-cloud-service-sdk.html)版本时(例如，`2020.02.2265.20200217T222518Z-200130`)。 |
| `includeDispatcherConfig` | `y` | 根据`aemVersion`（可以是`y`或`n`）的值，为云或AMS/on-premise包含调度程序配置。 |
| `frontendModule` | `general` | 包括一个Webpack前端构建模块，用于生成常规站点的客户端库(可以是`general`或`none`;对于实现[SPA Editor](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/headless/spa/editor-overview.html)的单页应用程序，可以是`angular`或`react`。 |
| `language` | `en` | 用于从(例如，`en`, `deu`)。 |
| `country` | `us` | 用于创建内容结构的国家/地区代码(ISO 3166-1)，例如`US`)。 |
| `singleCountry` | `y` | 包括语言主控的内容结构（可以是`y`或`n`）。 |
| `includeExamples` | `n` | 包括[组件库](https://www.aemcomponents.dev/)示例站点（可以是`y`或`n`）。 |
| `includeErrorHandler` | `n` | 包括一个自定义404响应页，该页将对整个实例全局（可以是`y`或`n`）。 |
| `includeCommerce` | `n` | 包括[CIF核心组件](https://github.com/adobe/aem-core-cif-components)依赖项并生成相应的伪像。 |
| `commerceEndpoint` |  | 仅CIF必需。 要使用的商务系统GraphQL服务的可选端点(例如，`https://hostname.com/grapql`)。 |
| `datalayer` | `y` | 激活与[Adobe客户端数据层](/help/developing/data-layer/overview.md)的集成。 |
| `amp` | `n` | 启用对生成的项目模板的[AMP](/help/developing/amp.md)支持。 |

## 系统要求

| 原型 | AEM as a Cloud Service | AEM 6.5 | AEM 6.4 | Java SE | 马文 |
|---------|---------|---------|---------|---------|---------|
| [26](https://github.com/adobe/aem-project-archetype/releases/tag/aem-project-archetype-26) | 持续 | 6.5.5.0+ | 6.4.8.1+ | 8, 11 | 3.3.9+ |

将[AEM的本地开发环境设置为Cloud ServiceSDK](https://docs.adobe.com/content/help/en/experience-manager-learn/cloud-service/local-development-environment-set-up/overview.html)或为AEM](https://docs.adobe.com/content/help/en/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html)的旧版本设置[。

### 已知问题

在Windows上运行并生成调度程序配置时，您应在提升的命令提示符或Linux的Windows子系统中运行(请参阅[#329](https://github.com/adobe/aem-project-archetype/issues/329))。

在交互模式下执行原型时（没有`-B`参数），具有默认值的属性无法更改，除非最终确认消失，否则将通过在问题中包含具有默认值的属性来重复问题(请参阅
[ARCHETYPE-308](https://issues.apache.org/jira/browse/ARCHETYPE-308)了解详细信息)。

## 进一步阅读{#further-reading}

有关使用原型的详细信息，包括原型的优点、选项及其模块的工作方式，请参阅[使用原型文档。](using.md)
