---
title: AEM 项目原型
description: 基于AEM的应用程序的项目模板
translation-type: tm+mt
source-git-commit: ed8c4609683d8e43ebc6859694ff7b9578fb07ff
workflow-type: tm+mt
source-wordcount: '989'
ht-degree: 6%

---


# AEM 项目原型 {#aem-project-archetype}

AEM Project Archetype是一个Maven模板，它创建基于最小最佳实践的Adobe Experience Manager(AEM)项目，作为网站的起点。

>[!TIP]
>
>最新的AEM Project Archetype [可在GitHub上找到](https://github.com/adobe/aem-project-archetype)。

## 资源 {#resources}

* **原型文档(此文档):** 原型体系结构及其不同模块概述。
   * **[使用原型：](using.md)** 有关使用原型和可用模块的更多详细信息
   * **[ui.frontend:](uifrontend.md)** 如何使用前端构建模块
* 以下教程基于此原型：
   * **[WKND站点：](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)** 了解如何开始新网站。
   * **[WKND单页应用程序：](https://helpx.adobe.com/experience-manager/kt/sites/using/getting-started-spa-wknd-tutorial-develop.html)** 了解如何构建在AEM中完全可授权的React或Angular Web应用程序。

## 功能 {#features}

* **最佳实践：** Bootstrap您的网站，了解Adobe的所有最新推荐做法。
* **低码：** 编辑模板、创建内容、部署CSS，让站点上线。
* **云就绪：** 如果需要， [请将AEM用作Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html) ，在几天内投入使用，并简化可扩展性和维护。
* **调度程序：** 项目只能通过确保速度和安 [全的Dispatcher](https://docs.adobe.com/content/help/zh-Hans/experience-manager-dispatcher/using/dispatcher.html) 配置完成。
* **多站点：** 如果需要，原型为多语言和多 [区域设置生成内容结构](https://docs.adobe.com/content/help/en/experience-manager-65/administering/introduction/msm.html)。
* **核心组件：** 作者可以使用我们的多功能标准化组件集 [创建几乎任何布局](/help/introduction.md)。
* **可编辑模板：** 无需代码 [即可组合几乎任何模板](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/page-authoring/template-editor-feature-video-use.html)，并定义作者可以编辑的内容。
* **响应式布局：** 在模板或单个页面上，定 [义元素如何重排](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/siteandpage/responsive-layout.html) （定义的断点）。
* **页眉和页脚：** 使用组件的本地化功能，无需代码即可将 [其组合并本地化](https://docs.adobe.com/content/help/zh-Hans/experience-manager-core-components/using/get-started/localization.html)。
* **样式系统：** 通过允许作者对自定义组件应用不 [同的样式，避免](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/style-system.html) 构建自定义组件。
* **前端构建：** 前端设备可以 [使用Webpack](uifrontend.md#webpack-dev-server)[、TypeScript和SASS模](uifrontend.md) 拟AEM页面并构建客户端库。
* **WebApp就绪：** 对于使用 [React](uifrontend-react.md) 或Angular的 [站点](uifrontend-angular.md)，请使 [用SPA SDK](https://docs.adobe.com/content/help/en/experience-manager-64/developing/headless/spas/spa-architecture.html) ，在应 [](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html)用程序的上下文创作中保留。
* **示例代码：** 结帐HelloWorld组件，以及示例模型、服务器、过滤器和调度程序。
* **未结来源：** 如果事情不是本该如此，那 [就帮](https://github.com/adobe/aem-core-wcm-components/blob/master/CONTRIBUTING.md) 助您改进！

## 使用

要生成项目，请根据需要调整以下命令行：

```
mvn -B archetype:generate \
 -D archetypeGroupId=com.adobe.granite.archetypes \
 -D archetypeArtifactId=aem-project-archetype \
 -D archetypeVersion=23 \
 -D aemVersion=cloud \
 -D appTitle="My Site" \
 -D appId="mysite" \
 -D groupId="com.mysite" \
 -D frontendModule=general \
 -D includeExamples=n
```

* Set `aemVersion=cloud` for [AEM as a Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html);\
   为 `aemVersion=6.5.0` Adobe [Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams)或内部部署设置。
核心组件依赖关系仅针对非云aem版本添加，因为核心组件是作为Cloud Service提供给AEM的OOTB的。
* 调整 `appTitle="My Site"` 以定义网站标题和组件组。
* 调 `appId="mysite"` 整以定义Maven artifactId、组件、配置和内容文件夹名称以及客户端库名称。
* 调 `groupId="com.mysite"` 整以定义Maven groupId和Java源包。
* 查找可用属性的列表，查看是否有更多要调整的属性。

## 可用属性

| 名称 | 默认 | 描述 |
--------------------------|----------------|--------------------
| `appTitle` |  | 应用程序标题将用于网站标题和组件组(例如， `"My Site"`)。 |
| `appId` |  | 技术名称将用于组件、配置和内容文件夹名称以及客户端库名称(例如， `"mysite"`)。 |
| `artifactId` | *`${appId}`* | 基Maven对象ID(例如， `"mysite"`)。 |
| `groupId` |  | 基本Maven组ID(例如， `"com.mysite"`)。 |
| `package` | *`${groupId}`* | Java源包(例如， `"com.mysite"`)。 |
| `version` | `1.0-SNAPSHOT` | 项目版本(如 `1.0-SNAPSHOT`)。 |
| `aemVersion` | `6.5.0` | 目标AEM版本(可 `cloud` 以 [作为Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html);或 `6.5.0`者 `6.4.4`，或 `6.3.3` 用于 [Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams) 或内部部署)。 |
| `sdkVersion` | `latest` | 当 `aemVersion=cloud` 可 [以指定](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/developing/aem-as-a-cloud-service-sdk.html) SDK版本时(例如， `2020.02.2265.20200217T222518Z-200130`)。 |
| `includeDispatcherConfig` | `y` | 根据值（可以是或），为云或AMS/本地包括调度程序 `aemVersion` 配置 `y` 。 `n` |
| `frontendModule` | `none` | 包括一个Webpack前端构建模块，它生成客户端库(可以是常规 `general` 站点 `none` 或常规站点；可以是 `angular` 或 `react` 用于实施SPA编辑器的单 [页应用程序](https://docs.adobe.com/content/help/en/experience-manager-65/developing/headless/spas/spa-overview.html))。 |
| `languageCountry` | `en_us` | 用于创建内容结构的语言和国家／地区代码(例如， `en_us`)。 |
| `singleCountry` | `y` | 包括语言主控的内容结构( `y`可以是 `n`或)。 |
| `includeExamples` | `y` | 包括 [组件库](https://www.aemcomponents.dev/) 示例站点( `y`可以是或 `n`)。 |
| `includeErrorHandler` | `n` | 包括将对整个实例（可以是或）全局的自定义404响 `y` 应页 `n`面。 |
| `includeCommerce` | `n` | 包括 [CIF核心组件依赖](https://github.com/adobe/aem-core-cif-components) ，并生成相应的伪像。 |
| `commerceEndpoint` |  | 仅CIF必需。 要使用的商务系统GraphQL服务的可选端点(例如， `https://hostname.com/grapql`)。 |
| `datalayer` | `y` | 激活与Adobe客 [户端数据层的集成](/help/developing/data-layer/overview.md)。 |
| `amp` | `n` | 启用 [对生成](/help/developing/amp.md) 的项目模板的AMP支持。 |

## 系统要求

| 原型 | AEM 云服务 | AEM 6.5 | AEM 6.4 | Java SE | 马文 |
---------|---------|---------|---------|---------|---------|---------
| [24](https://github.com/adobe/aem-project-archetype/releases/tag/aem-project-archetype-24) | 持续 | 6.5.5.0+ | 6.4.8.1+ | 8, 11 | 3.3.9+ |

将AEM的本地开发环境 [设置为Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-learn/cloud-service/local-development-environment-set-up/overview.html) SDK或 [旧版AEM的本地开](https://docs.adobe.com/content/help/en/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html)发。

### 已知问题

在Windows上运行并生成调度程序配置时，应在提升的命令提示符或Windows Subsystem for Linux中运行(请参 [阅#329](https://github.com/adobe/aem-project-archetype/issues/329))。

在交互模式(无参数 `-B` )中执行原型时，无法更改具有默认值的属性，除非最终确认消失，否则将通过将具有默认值的属性包含在问题中来重复问题(有关详细信息，请参阅[ARCHETYPE](https://issues.apache.org/jira/browse/ARCHETYPE-308) -308)。

## 进一步阅读 {#further-reading}

有关使用原型的更多详细信息，包括原型的优点、选项及其模块的工作方式，请参 [阅使用原型文档。](using.md)
