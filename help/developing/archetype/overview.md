---
title: AEM 项目原型
description: 基于AEM的应用程序的项目模板
translation-type: tm+mt
source-git-commit: 2faa092a075ab0512e9bd5654884534936c0ad53

---


# AEM 项目原型 {#aem-project-archetype}

AEM Project Archetype是Maven模板，可创建基于最小、最佳实践的Adobe Experience Manager(AEM)项目作为网站的起点。

>[!TIP]
>
>可在GitHub上找到最 [新的AEM Project Archetype](https://github.com/adobe/aem-project-archetype)。

## 资源 {#resources}

* **原型文档(本文档):** 原型体系结构及其不同模块的概述。
   * **[使用原型：](using.md)**有关使用原型和可用模块的更多详细信息
   * **[ui.frontend:](uifrontend.md)**如何使用前端构建模块
* 以下教程基于此原型：
   * **[WKND站点：](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)**了解如何开始新网站。
   * **[WKND单页应用程序：](https://helpx.adobe.com/experience-manager/kt/sites/using/getting-started-spa-wknd-tutorial-develop.html)**了解如何构建在AEM中完全可创作的React或Angular Web应用程序。

## 功能 {#features}

* **最佳实践：** 使用Adobe的所有最新推荐实践引导您的网站。
* **低码：** 编辑模板、创建内容、部署CSS，让站点上线。
* **云就绪：** 如果需要， [可以将AEM用作云服务](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html) ，在几天内上线并简化可扩展性和维护。
* **调度程序：** 项目只能通过确保速度和安全 [性的Dispatcher配置](https://docs.adobe.com/content/help/en/experience-manager-dispatcher/using/dispatcher.html) 完成。
* **多站点：** 如果需要，原型为多语言和多区 [域设置生成内容结构](https://docs.adobe.com/content/help/en/experience-manager-65/administering/introduction/msm.html)。
* **核心组件：** 作者几乎可以使用我们的通用标准化组件集 [创建任何布局](/help/introduction.md)。
* **可编辑的模板：** 无需代码 [即可组合几乎任何模板](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/page-authoring/template-editor-feature-video-use.html)，并定义作者可以编辑的内容。
* **响应式布局：** 在模板或单个页面上，定 [义元素如何重排所定义的断点](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/siteandpage/responsive-layout.html) 。
* **页眉和页脚：** 使用组件的本地化功能，无需代码即可将 [其组合并本地化](https://docs.adobe.com/content/help/zh-Hans/experience-manager-core-components/using/get-started/localization.html)。
* **样式系统：** 通过允许作者对自定义组件应用不 [同的样式](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/style-system.html) ，避免构建这些组件。
* **前端构建：** 前端设备可以 [使用Webpack](uifrontend.md#webpack-dev-server) 、TypeScript和SASS [模拟AEM页面并构建客户端库](uifrontend.md) 。
* **WebApp-Ready:** 对于使用 [React](uifrontend-react.md) 或 [Angular](uifrontend-angular.md)的站点，请使用 [SPA SDK](https://docs.adobe.com/content/help/en/experience-manager-64/developing/headless/spas/spa-architecture.html) ，在应用程序的上 [](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html)下文创作中保留该SPA SDK。
* **示例代码：** 结帐HelloWorld组件，以及示例模型、服务器、过滤器和调度程序。
* **未结来源：** 如果某件事情不是应有的，请 [改进](https://github.com/adobe/aem-core-wcm-components/blob/master/CONTRIBUTING.md) !

## 使用

要生成项目，请根据您的需要调整以下命令行：

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
   为 `aemVersion=6.5.0` Adobe Managed Services [](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams)（或内部部署）设置。
核心组件依赖关系仅针对非云aem版本添加，因为核心组件是作为CloudService为AEM提供的OOTB。
* 调整 `appTitle="My Site"` 以定义网站标题和组件组。
* 调 `appId="mysite"` 整以定义Maven artifactId、组件、配置和内容文件夹名称以及客户端库名称。
* 调 `groupId="com.mysite"` 整以定义Maven groupId和Java源包。
* 查找可用属性的列表，以查看是否有更多要调整的属性。

## 可用属性

| 名称 | 默认 | 描述 |
--------------------------|----------------|--------------------
| `appTitle` |  | 应用程序标题将用于网站标题和组件组(例如， `"My Site"`)。 |
| `appId` |  | 技术名称将用于组件、配置和内容文件夹名称以及客户端库名称(例如， `"mysite"`)。 |
| `artifactId` | *`${appId}`* | 基本Maven对象ID(例如， `"mysite"`)。 |
| `groupId` |  | 基本Maven组ID(例如， `"com.mysite"`)。 |
| `package` | *`${groupId}`* | Java源包(例如， `"com.mysite"`)。 |
| `version` | `1.0-SNAPSHOT` | 项目版本(例如 `1.0-SNAPSHOT`)。 |
| `aemVersion` | `6.5.0` | 目标AEM版本(可 `cloud` 以 [将AEM作为云服务](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html);或 `6.5.0`者 `6.4.4`，或 `6.3.3` 用于 [Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams) 或内部部署)。 |
| `sdkVersion` | `latest` | 当可 `aemVersion=cloud` 以指定 [SDK版本时](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/developing/aem-as-a-cloud-service-sdk.html) (例如， `2020.02.2265.20200217T222518Z-200130`)。 |
| `includeDispatcherConfig` | `y` | 根据值（可以是或），为云或AMS/内部部署包含调度程序 `aemVersion` 配置 `y``n`。 |
| `frontendModule` | `none` | 包括一个Webpack前端构建模块，用于生成客户端库(可以是常规 `general` 站点 `none` 或常规站点；可以是或 `angular` 用 `react` 于实施 [SPA编辑器的单页应用程序](https://docs.adobe.com/content/help/en/experience-manager-65/developing/headless/spas/spa-overview.html))。 |
| `languageCountry` | `en_us` | 用于创建内容结构的语言和国家／地区代码(例如， `en_us`)。 |
| `singleCountry` | `y` | 包括主语言内容结构(可以 `y`是或 `n`)。 |
| `includeExamples` | `y` | 包括组 [件库示例站点](https://www.aemcomponents.dev/) (可以 `y`是或 `n`)。 |
| `includeErrorHandler` | `n` | 包括一个自定义404响应页面，该页面将对整个实例(可以是或 `y` )全局 `n`性。 |

## 系统要求

| 原型 | AEM 云服务 | AEM 6.5 | AEM 6.4 | AEM 6.3 | Java SE | 马文 |
---------|---------|---------|---------|---------|---------|---------
| [23](https://github.com/adobe/aem-project-archetype/releases/tag/aem-project-archetype-23) | 连续 | 6.5.0.0+ | 6.4.4.0+ | 6.3.3.4+ | 8, 11 | 3.3.9+ |

将 [AEM的本地开发环境设置为Cloud Service SDK](https://docs.adobe.com/content/help/en/experience-manager-learn/cloud-service/local-development-environment-set-up/overview.html) ，或 [为旧版AEM设置](https://docs.adobe.com/content/help/en/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html)。

### 已知问题

在Windows上运行并生成调度程序配置时，您应该在提升的命令提示符下运行，或者在Linux的Windows子系统中运行(请参 [阅#329](https://github.com/adobe/aem-project-archetype/issues/329))。

在交互模式(不带参数 `-B` )中执行原型时，除非最终确认消失，否则无法更改具有默认值的属性，该确认会通过将具有默认值的属性包含在问题中来重复问题(有关详细信息，请参阅[ARCHETYPE-308](https://issues.apache.org/jira/browse/ARCHETYPE-308) )。

## 进一步阅读 {#further-reading}

有关使用原型的更多详细信息，包括其优点、选项及其模块的工作方式，请参阅 [使用原型文档。](using.md)