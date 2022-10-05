---
title: AEM 项目原型
description: 基于 AEM 的应用程序的项目模板
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: 58994726-9b65-4035-9d45-60b745d577bb
source-git-commit: c817592207868284d6d9cc1c8bc0405aa50f8957
workflow-type: tm+mt
source-wordcount: '1192'
ht-degree: 98%

---

# AEM 项目原型 {#aem-project-archetype}

AEM 项目原型是一个 Maven 模板，它创建最小的基于最佳实践的 Adobe Experience Manager (AEM) 项目作为您网站的起点。

>[!TIP]
>
>[在 GitHub 上可找到](https://github.com/adobe/aem-project-archetype)最新的 AEM 项目原型。

## 资源 {#resources}

* **原型文档（本文档）：**&#x200B;原型架构及其不同模块的概述。
   * **[使用原型：](using.md)**&#x200B;有关使用原型和可用模块的更多详细信息
   * **[ui.frontend：](uifrontend.md)**&#x200B;如何使用前端构建模块
* **以下教程基于此原型：**
   * **[WKND 网站：](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)**&#x200B;了解如何启动全新的网站。
   * **[WKND 单页面应用程序：](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html)**&#x200B;了解如何构建可完全在 AEM 中创作的 React 或 Angular Web 应用程序。

## 功能 {#features}

* **最佳实践：**&#x200B;使用 Adobe 的所有最新推荐实践引导您的网站。
* **少量代码：**&#x200B;编辑您的模板、创建内容、部署您的 CSS，您的网站就可以上线了。
* **云就绪：**&#x200B;如果需要，使用 [AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html) 在几天内上线并简化可扩展性和维护。
* **Dispatcher：**&#x200B;只能通过可确保速度和安全性的 [Dispatcher 配置](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/dispatcher.html)完成项目。
* **多站点：**&#x200B;如果需要，原型将为[多语言和多区域设置](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/msm/overview.html)生成内容结构。
* **核心组件：**&#x200B;作者可以使用我们通用的[标准化组件集](/help/introduction.md)创建几乎任何布局。
* **可编辑模板：**&#x200B;收集几乎任何[不带代码的模板](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/page-authoring/template-editor-feature-video-use.html)，并定义作者可编辑的内容。
* **响应式布局：**&#x200B;在模板或单个页面上，为定义的断点[定义元素的重排方式](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/get-started/localization.html)。
* **页眉和页脚：**&#x200B;收集页眉和页脚，并使用[组件的本地化功能](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/get-started/localization.html)将其本地化而不是使用代码。
* **样式系统：**&#x200B;通过允许作者向自定义组件[应用不同的样式](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/project-archetype/style-system.html)来避免构建这些组件。
* **前端构建：**&#x200B;前端开发人员可以使用 Webpack、TypeScript 和 SASS [模拟 AEM 页面](uifrontend.md#webpack-dev-server)和[构建客户端库](uifrontend.md)。
* **Web 应用程序就绪：**&#x200B;对于使用 [React](uifrontend-react.md) 或 [Angular](uifrontend-angular.md) 的网站，使用 [SPA 开发工具包](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/hybrid/developing.html)保持[应用程序的上下文中创作](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html)。
* **启用 Commerce：**&#x200B;对于要将 [AEM Commerce](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content-and-commerce/home.html) 与 [Magento](https://magento.com/) 等商业解决方案集成的项目，使用 [Commerce 核心组件](https://github.com/adobe/aem-core-cif-components)。
* **示例代码：**&#x200B;查看 HelloWorld 组件以及示例模型、servlet、过滤器和调度程序。
* **开源：**&#x200B;如果有出错的地方，请[做出](https://github.com/adobe/aem-core-wcm-components/blob/master/CONTRIBUTING.md)您的改进！

## 用途 {#usage}

要生成项目，请调整以下命令行以满足您的需求：

```shell
mvn -B archetype:generate \
 -D archetypeGroupId=com.adobe.aem \
 -D archetypeArtifactId=aem-project-archetype \
 -D archetypeVersion=XX \
 -D appTitle="My Site" \
 -D appId="mysite" \
 -D groupId="com.mysite" \
```

* 将 `XX` 替换为最新的[原型版本号。](#requirements)
* 为 [AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html) 设置 `aemVersion=cloud`；\
   为 [Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams) 或内部部署设置 `aemVersion=6.5.0`。
仅为非云 AEM 版本添加核心组件依赖项，因为核心组件是针对 AEM as a Cloud Service 提供的 OOTB。
* 调整 `appTitle="My Site"` 以定义网站标题和组件组。
* 调整 `appId="mysite"` 以定义 Maven artifactId、组件、配置和内容文件夹名称以及客户端库名称。
* 调整 `groupId="com.mysite"` 以定义 Maven groupId 和 Java 源程序包。
* 查找可用属性列表以了解是否还需要调整其他属性。

## 可用属性 {#available-properties}

| 名称 | 默认 | 描述 |
|---------------------------|----------------|--------------------|
| `appTitle` |  | 应用程序标题，将用于网站标题和组件组（例如 `"My Site"`）。 |
| `appId` |  | 技术名称，将用于组件、配置和内容文件夹名称以及客户端库名称（例如，`"mysite"`）。 |
| `artifactId` | *`${appId}`* | 基本 Maven 构件 ID（例如 `"mysite"`）。 |
| `groupId` |  | 基本 Maven 组 ID（例如 `"com.mysite"`）。此值必须是[有效的 Java 包名称。](https://docs.oracle.com/javase/specs/jls/se6/html/packages.html#7.7) |
| `package` | *`${groupId}`* | Java 源程序包（例如 `"com.mysite"`）。 |
| `version` | `1.0-SNAPSHOT` | 项目版本（例如 `1.0-SNAPSHOT`）。 |
| `aemVersion` | `cloud` | 目标 AEM 版本（可以是 [AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html) 的 `cloud`；或 [Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams) 或内部部署的 `6.5.0` 或 `6.4.4`）。 |
| `sdkVersion` | `latest` | 在为 `aemVersion=cloud` 时，可指定[开发工具包](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-as-a-cloud-service-sdk.html)版本（例如 `2020.02.2265.20200217T222518Z-200130`）。 |
| `includeDispatcherConfig` | `y` | 包括用于云或 AMS/内部部署的 Dispatcher 配置，具体取决于 `aemVersion` 的值（可以是 `y` 或 `n`）。 |
| `frontendModule` | `general` | 包含一个生成客户端库的 Webpack 前端构建模块（可以是面向常规站点的 `general` 或 `none`；可以是面向实施 [SPA 编辑器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/hybrid/editor-overview.html)的单页面应用程序的 `angular` 或 `react`）。 |
| `language` | `en` | 从中创建内容结构的语言代码 (ISO 639-1)（例如 `en`、`deu`）。 |
| `country` | `us` | 从中创建内容结构的国家/地区代码 (ISO 3166-1)（例如 `US`）。 |
| `singleCountry` | `y` | 包含语言主导的内容结构（可以是 `y` 或 `n`）。 |
| `includeExamples` | `n` | 包含[组件库](https://www.aemcomponents.dev/)示例站点（可以是 `y` 或 `n`）。 |
| `includeErrorHandler` | `n` | 包含将为整个实例全局设置的自定义 404 响应页面（可以是 `y` 或 `n`）。 |
| `includeCommerce` | `n` | 包含 [CIF 核心组件](https://github.com/adobe/aem-core-cif-components)依赖项并生成相应的构件。 |
| `commerceEndpoint` |  | 仅对于 CIF 是必需的。要使用的商务系统 GraphQL 服务的可选端点（例如 `https://hostname.com/grapql`）。 |
| `includeFormscommunications` | `n` | 包括 [Forms 核心组件](https://github.com/adobe/aem-core-forms-components)依赖项、模板、表单数据模型、主题，并为 Forms 通信程序生成相应的伪像。 |
| `includeFormsenrollment` | `n` | 包括 [Forms 核心组件](https://github.com/adobe/aem-core-forms-components)依赖项、模板、表单数据模型、主题，并为 Forms 注册程序生成相应的伪像。 |
| `sdkFormsVersion` | `latest` | When `aemVersion=cloud` 和 `includeFormsenrollment=y` 或 `includeFormscommunications=y`，可以指定Forms SDK版本(例如， `2020.12.17.02`)。 |
| `datalayer` | `y` | 激活与 [Adobe Client Data Layer](/help/developing/data-layer/overview.md) 的集成。 |
| `amp` | `n` | 为生成的项目模板启用 [AMP](/help/developing/amp.md) 支持。 |
| `enableDynamicMedia` | `n` | 在项目策略设置中启用基础 DynamicMedia 组件，并在核心图像组件的策略中激活 Dynamic Media 功能。 |
| `enableSSR` | `n` | 用于为前端项目启用 SSR 的选项 |
| `precompiledScripts` | `n` | 用于从 `ui.apps` [预编译](/help/developing/archetype/precompiled-bundled-scripts.md)服务器端脚本并将它们作为 `ui.apps` 项目中的次捆绑构件附加到版本的选项。`aemVersion` 应设置为 `cloud`。 |
| `includeFormsheadless` | `n` | 包括 [Forms核心组件](https://github.com/adobe/aem-core-forms-components) 依赖关系， `ui.frontend.react.forms.af`和无头工件。 |

## 系统要求 {#requirements}

| 原型 | AEM as a Cloud Service | AEM 6.5 | Java SE | Maven |
|---------|---------|---------|---------|---------|
| [39](https://github.com/adobe/aem-project-archetype/releases/tag/aem-project-archetype-39) | 连续 | 6.5.7.0+ | 8, 11 | 3.3.9+ |

为 [AEM as a Cloud Service SDK](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/local-development-environment-set-up/overview.html) 或[旧版本的 AEM](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html) 设置本地开发环境。

### 已知问题 {#known-issues}

在 Windows 上运行并生成 Dispatcher 配置时，您应在提升权限的命令提示符下或适用于 Linux 的 Windows 子系统中运行（请参阅 [#329](https://github.com/adobe/aem-project-archetype/issues/329)）。

在交互模式下执行原型（不带 `-B` 参数）时，无法更改带默认值的属性，除非取消最终确认，这随后会在问题中包含带默认值的属性来重复问题（有关详细信息，请参阅
[ARCHETYPE-308](https://issues.apache.org/jira/browse/ARCHETYPE-308)）。

在使用 `File -> New -> Maven Project` 开始新项目时，无法在 Eclipse 中使用此原型，因为 [Eclipse 问题导致无法执行后生成脚本 `archetype-post-generate.groovy`。](https://bugs.eclipse.org/bugs/show_bug.cgi?id=514993)解决方法是使用上面的命令行，然后在 Eclipse 中，使用 `File -> Import -> Existing Maven Project`。

## 深入阅读 {#further-reading}

有关使用原型的更多详细信息，包括其好处、选项及其模块的工作方式，请参阅[使用原型文档。](using.md)
