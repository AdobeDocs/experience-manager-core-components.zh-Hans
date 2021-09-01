---
title: AEM 项目原型
description: 基于AEM的应用程序的项目模板
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: 58994726-9b65-4035-9d45-60b745d577bb
source-git-commit: 5271174f5c325a9793dc155c763054752c7308b8
workflow-type: tm+mt
source-wordcount: '1113'
ht-degree: 5%

---

# AEM 项目原型 {#aem-project-archetype}

AEM项目原型是一个Maven模板，可创建基于最佳实践的、最基础的Adobe Experience Manager(AEM)项目，以作为您网站的起点。

>[!TIP]
>
>最新的AEM项目原型[可在GitHub上找到。](https://github.com/adobe/aem-project-archetype)

## 资源 {#resources}

* **原型文档（本文档）：** 原型架构及其不同模块的概述。
   * **[使用原型：](using.md)** 有关使用原型和可用模块的更多详细信息
   * **[ui.frontend:](uifrontend.md)** 如何使用前端构建模块
* 以下教程基于此原型：
   * **[WKND网站：](https://docs.adobe.com/content/help/zh-Hans/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)** 了解如何启动一个新的网站。
   * **[WKND单页应用程序：](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html)** 了解如何构建可在AEM中完全授权的React或AngularWeb应用程序。

## 功能 {#features}

* **最佳实践：** Bootstrap您的网站，以介绍Adobe的所有最新推荐实践。
* **低代码：** 编辑模板、创建内容、部署CSS，并且您的网站已准备就绪，可上线。
* **云就绪：** 如有需要，请使 [用AEM as a ](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html) Cloud Service在几天内上线，并轻松实现可扩展性和维护。
* **Dispatcher:** 项目只能通过确保速度和安 [全](https://docs.adobe.com/content/help/zh-Hans/experience-manager-dispatcher/using/dispatcher.html) 性的Dispatcher配置完成。
* **多站点：** 如果需要，原型会为多语言和多 [区域设置生成内容结构](https://docs.adobe.com/content/help/en/experience-manager-65/administering/introduction/msm.html)。
* **核心组件：** 作者可以使用我们通用的标准化组件 [集来创建几乎任何布局](/help/introduction.md)。
* **可编辑的模板：** 几乎任何不 [带代码的模板组合](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/page-authoring/template-editor-feature-video-use.html)，并定义允许作者编辑的内容。
* **响应式布局：** 在模板或各个页面上， [定义定义断点](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/responsive-layout.html) 的元素重排方式。
* **页眉和页脚：** 使用组件的本地化功能，无需代码即 [可组合和本地化它们](https://docs.adobe.com/content/help/zh-Hans/experience-manager-core-components/using/get-started/localization.html)。
* **样式系统：** 通过允许作者对自定义组件应用不同的样式， [避免](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/style-system.html) 生成这些组件。
* **前端构建：** 前端开发人员可以使用Webpack、TypeScript和SASS [模拟](uifrontend.md#webpack-dev-server) AEM页 [面并](uifrontend.md) 构建客户端库。
* **WebApp-Ready:** 对于使用ReactorAngular [](uifrontend-react.md) 的 [网站](uifrontend-angular.md)，请使用 [SPA ](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/headless/spa/developing.html) SDK保留 [应用程序的上下文创作](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html)。
* **启用商务：** 对于要将AEM Commerce与商务解决方 [](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/commerce/home.html) 案(如管理商务核心组 [](https://magento.com/) 件)集 [成的项目](https://github.com/adobe/aem-core-cif-components)。
* **示例代码：** 签出HelloWorld组件以及示例模型、Servlet、过滤器和调度程序。
* **开放源：** 如果某些内容不如预期，将为您的改 [](https://github.com/adobe/aem-core-wcm-components/blob/master/CONTRIBUTING.md) 进做出贡献！

## 使用 {#usage}

要生成项目，请根据需要调整以下命令行：

```shell
mvn -B archetype:generate \
 -D archetypeGroupId=com.adobe.aem \
 -D archetypeArtifactId=aem-project-archetype \
 -D archetypeVersion=XX \
 -D appTitle="My Site" \
 -D appId="mysite" \
 -D groupId="com.mysite" \
```

* 将`XX`替换为最新的[原型版本号。](#requirements)
* 将[AEM的`aemVersion=cloud`设置为Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html);\
   为[Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams)或内部部署设置`aemVersion=6.5.0`。
仅会为非云aem版本添加核心组件依赖项，因为为AEM as aCloud Service提供了核心组件OOTB。
* 调整`appTitle="My Site"`以定义网站标题和组件组。
* 调整`appId="mysite"`以定义Maven人为对象ID、组件、配置和内容文件夹名称以及客户端库名称。
* 调整`groupId="com.mysite"`以定义Maven groupId和Java源包。
* 查找可用属性列表，以查看是否需要调整更多属性。

## 可用属性 {#available-properties}

| 名称 | 默认 | 描述 |
|---------------------------|----------------|--------------------|
| `appTitle` |  | 应用程序标题将用于网站标题和组件组(例如，`"My Site"`)。 |
| `appId` |  | 技术名称将用于组件、配置和内容文件夹名称，以及客户端库名称(例如，`"mysite"`)。 |
| `artifactId` | *`${appId}`* | 基本Maven对象ID(例如，`"mysite"`)。 |
| `groupId` |  | 基本Maven组ID(例如，`"com.mysite"`)。 |
| `package` | *`${groupId}`* | Java源包(例如，`"com.mysite"`)。 |
| `version` | `1.0-SNAPSHOT` | 项目版本(例如，`1.0-SNAPSHOT`)。 |
| `aemVersion` | `cloud` | Target AEM版本(对于[AEM as a Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html)，可以为`cloud`;或`6.5.0`，或`6.4.4`（适用于[Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams)或内部部署版）。 |
| `sdkVersion` | `latest` | 当`aemVersion=cloud`可以指定[ SDK](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/developing/aem-as-a-cloud-service-sdk.html)版本时(例如，`2020.02.2265.20200217T222518Z-200130`)。 |
| `includeDispatcherConfig` | `y` | 包含适用于云或AMS/on-premise的调度程序配置，具体取决于`aemVersion`的值（可以是`y`或`n`）。 |
| `frontendModule` | `general` | 包括Webpack前端构建模块，用于为常规站点生成客户端库（可以是`general`或`none`）；可以是`angular`或`react`(对于实施[SPA编辑器](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/headless/spa/editor-overview.html)的单页应用程序)。 |
| `language` | `en` | 语言代码(ISO 639-1)，用于从(例如，`en`, `deu`)。 |
| `country` | `us` | 国家/地区代码(ISO 3166-1)，用于从(例如`US`)。 |
| `singleCountry` | `y` | 包括语言主控的内容结构（可以是`y`或`n`）。 |
| `includeExamples` | `n` | 包括[组件库](https://www.aemcomponents.dev/)示例站点（可以是`y`或`n`）。 |
| `includeErrorHandler` | `n` | 包括一个对整个实例全局的自定义404响应页面（可以是`y`或`n`）。 |
| `includeCommerce` | `n` | 包括[CIF核心组件](https://github.com/adobe/aem-core-cif-components)依赖项并生成相应的工件。 |
| `commerceEndpoint` |  | 仅CIF必需。 要使用的商务系统GraphQL服务的可选端点(例如，`https://hostname.com/grapql`)。 |
| `datalayer` | `y` | 激活与[Adobe客户端数据层](/help/developing/data-layer/overview.md)的集成。 |
| `amp` | `n` | 为生成的项目模板启用[AMP](/help/developing/amp.md)支持。 |
| `enableDynamicMedia` | `n` | 在项目策略设置中启用基础DynamicMedia组件，并在核心图像组件的策略中激活Dynamic Media功能。 |
| `enableSSR` | `n` | 为前端项目启用SSR的选项 |

## 系统要求 {#requirements}

| 原型 | AEM as a Cloud Service | AEM 6.5 | Java SE | 马文 |
|---------|---------|---------|---------|---------|
| [30](https://github.com/adobe/aem-project-archetype/releases/tag/aem-project-archetype-30) | 持续 | 6.5.7.0+ | 8, 11 | 3.3.9+ |

为[AEM as a Cloud ServiceSDK](https://docs.adobe.com/content/help/en/experience-manager-learn/cloud-service/local-development-environment-set-up/overview.html)或为[旧版AEM](https://docs.adobe.com/content/help/en/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html)设置本地开发环境。

### 已知问题 {#known-issues}

在Windows上运行并生成调度程序配置时，您应在提升的命令提示符下或Linux的Windows子系统中运行(请参阅[#329](https://github.com/adobe/aem-project-archetype/issues/329))。

在交互模式下执行原型（不带`-B`参数）时，无法更改具有默认值的属性，除非最终确认被取消，否则将重复问题，方法是在问题中包含具有默认值的属性(请参阅
[ARCHETYPE-308](https://issues.apache.org/jira/browse/ARCHETYPE-308)以了解详细信息)。

使用`File -> New -> Maven Project`启动新项目时，无法在Eclipse中使用此原型，因为后生成脚本`archetype-post-generate.groovy`将因[Eclipse问题而不执行。](https://bugs.eclipse.org/bugs/show_bug.cgi?id=514993) 解决方法是使用上述命令行，然后在Eclipse中使用 `File -> Import -> Existing Maven Project`。

## 进一步阅读 {#further-reading}

有关使用原型（包括原型的好处、选项及其模块的工作方式）的更多详细信息，请参阅[使用原型文档。](using.md)
