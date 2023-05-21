---
title: 使用 AEM 项目原型
description: AEM 项目原型的详细使用说明
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: a3978d8b-4904-42aa-9ee2-9c1f884327bb
source-git-commit: ca61d71a2644465e74249058157d8dea2aa71352
workflow-type: tm+mt
source-wordcount: '2198'
ht-degree: 100%

---

# AEM 项目原型 {#aem-project-archetype}

AEM 项目原型创建最小的基于最佳实践的 Adobe Experience Manager 项目作为您自己的 AEM 项目的起点。使用此原型时必须提供的属性允许您为此项目的所有部分指定名称并控制某些可选功能。

## 为什么使用原型 {#why-use-the-archetype}

利用 AEM 项目原型，您只需按几下键即可构建基于最佳实践的 AEM 项目。通过使用原型，所有部分都已准备就绪，即便生成的项目最小，它也实施了 AEM 的所有[主要功能](#what-you-get)，您只需在其基础上进行构建和扩展。

当然，成功的 AEM 项目涉及很多要素，而使用 AEM 项目原型可以奠定坚实的基础，强烈建议对任何 AEM 项目这样做。

## 快速入门 {#getting-started}

利用项目原型，可以轻松地在 AEM 上开始进行开发。您可以通过多种方式迈出第一步。

* WKND 教程 - 有关在 AEM 上进行开发的精彩介绍（包括如何利用原型），请参阅 [AEM Sites 入门 - WKND 教程](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)中的实际示例，该示例介绍如何使用原型实施简单项目。
* WKND 事件教程 - 如果您特别想知道如何在 AEM 上开发单页面应用程序 (SPA)，请务必查看专门的 [WKND 事件教程](https://helpx.adobe.com/cn/experience-manager/kt/sites/using/getting-started-spa-wknd-tutorial-develop.html)。
* 下载原型并开始创建您自己的项目！- 您可以轻松下载 GitHub 上提供的最新项目原型，并通过[执行以下简单步骤](#how-to-use-the-archetype)来创建第一个项目。

## 使用原型的好处 {#what-you-get}

AEM 项目原型包含以下模块：

* **[core](core.md)**：此模块是一个 Java 捆绑包，它包含所有核心功能（例如 OSGi 服务、侦听器和调度程序）以及与组件相关的 Java 代码（例如 servlet 和请求过滤器）。
* **[it.tests](ittests.md)**：此模块是基于 Java 的集成测试。
* **[ui.apps](uiapps.md)**：此模块包含项目的 `/apps` 和 `/etc` 部分，即 JS 和 CSS clientlibs、组件和模板。
* **[ui.content](uicontent.md)**：此模块包含使用 ui.apps 模块中的组件的示例内容。
* **ui.config**：此模块包含项目的特定于 runmode 的 OSGi 配置。
* **[ui.frontend.general](uifrontend.md)**：**（可选）**&#x200B;此模块包含使用通用型基于 Webpack 的前端构建模块所需的构件。
* **[ui.frontend.react](uifrontend-react.md)**：**（可选）**&#x200B;此模块包含使用原型创建基于 React 的 SPA 项目时所需的构件。
* **[ui.frontend.angular](uifrontend-angular.md)**：**（可选）**&#x200B;此模块包含使用原型创建基于 Angular 的 SPA 项目时所需的构件。
* **[ui.tests](uitests.md)**：此模块包含基于 Selenium 的 UI 测试。
* **all**：此模块是单内容包，它嵌入了所有已编译的模块（捆绑包和内容包），其中包括任何供应商依赖项。
* **analyse**：此模块对项目运行分析，这为部署到 AEM as a Cloud Service 提供了额外的验证。

![](/help/assets/archetype-structure.png)

Maven 中表示的 AEM 原型模块作为表示应用程序、内容和必要的 OSGi 捆绑包的内容包部署到 AEM。

## 如何使用原型 {#how-to-use-the-archetype}

要使用原型，您首先需要创建一个项目，该项目在本地文件结构中生成模块，如[之前所述](#what-you-get)。作为项目生成的一部分，可以定义项目的许多属性，例如项目名称、版本等。

使用 Maven 构建项目会创建可部署到 AEM 的构件（包和 OSGi 捆绑包）。其他 Maven 命令和配置文件可用于将项目构件部署到 AEM 实例。

### 创建项目 {#create-project}

首先，您可以简单地使用 [AEM Eclipse 扩展](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developer-tools/eclipse.html)并遵循“新建项目”向导，然后选择&#x200B;**“AEM 示例多模块项目”**&#x200B;以使用原型的发行版。

当然，您也可以直接调用 Maven。

```shell
mvn -B archetype:generate \
 -D archetypeGroupId=com.adobe.aem \
 -D archetypeArtifactId=aem-project-archetype \
 -D archetypeVersion=XX \
 -D aemVersion=cloud \
 -D appTitle="My Site" \
 -D appId="mysite" \
 -D groupId="com.mysite" \
 -D frontendModule=general \
 -D includeExamples=n
```

* 将 `XX` 设置为最新的 AEM 项目原型的[版本号](https://github.com/adobe/aem-project-archetype/blob/master/VERSIONS.md)。
* 为 [AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html) 设置 `aemVersion=cloud`；\
   为 [Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams) 或内部部署设置 `aemVersion=6.5.0`。
仅为非云 AEM 版本添加核心组件依赖项，因为核心组件是针对 AEM as a Cloud Service 提供的
OOTB。
* 调整 `appTitle="My Site"` 以定义网站标题和组件组。
* 调整 `appId="mysite"` 以定义 Maven artifactId、组件、配置和内容文件夹名称以及客户端库名称。
* 调整 `groupId="com.mysite"` 以定义 Maven groupId 和 Java 源程序包。
* 查找可用属性列表以了解是否还需要调整其他属性。

>[!NOTE]
>
>最佳实践是将 `adobe-public` 配置文件添加到 Maven `settings.xml` 文件，以便自动将 repo.adobe.com 添加到 maven 构建过程。
>
>[可在此处找到](https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-17454.html?lang=zh-Hans)示例 POM。

### 属性 {#properties}

在使用原型创建项目时，以下属性可用。

| 名称 | 默认 | 描述 |
|---------------------------|----------------|--------------------|
| `appTitle` |  | 应用程序标题，将用于网站标题和组件组（例如 `"My Site"`）。 |
| `appId` |  | 技术名称，将用于组件、配置和内容文件夹名称以及客户端库名称（例如，`"mysite"`）。 |
| `artifactId` | *`${appId}`* | 基本 Maven 构件 ID（例如 `"mysite"`）。 |
| `groupId` |  | 基本 Maven 组 ID（例如 `"com.mysite"`）。 |
| `package` | *`${groupId}`* | Java 源程序包（例如 `"com.mysite"`）。 |
| `version` | `1.0-SNAPSHOT` | 项目版本（例如 `1.0-SNAPSHOT`）。 |
| `aemVersion` | `cloud` | 目标 AEM 版本（可以是 [AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html?lang=zh-Hans) 的 `cloud`；或 [Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams) 或内部部署的 `6.5.0` 或 `6.4.4`）。 |
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
| `datalayer` | `y` | 激活与 [Adobe Client Data Layer](/help/developing/data-layer/overview.md) 的集成。 |
| `amp` | `n` | 为生成的项目模板启用 [AMP](/help/developing/amp.md) 支持。 |
| `enableDynamicMedia` | `n` | 在项目策略设置中启用基础 DynamicMedia 组件，并在核心图像组件的策略中激活 Dynamic Media 功能。 |
| `enableSSR` | `n` | 用于为前端项目启用 SSR 的选项 |
| `precompiledScripts` | `n` | 用于从 `ui.apps` [预编译](/help/developing/archetype/precompiled-bundled-scripts.md)服务器端脚本并将它们作为 `ui.apps` 项目中的次捆绑构件附加到版本的选项。`aemVersion` 应设置为 `cloud`。 |

>[!NOTE]
>
> 如果首次在交互模式中执行原型，则无法更改带默认值的属性（有关更多详细信息，请参阅 [ARCHETYPE-308](https://issues.apache.org/jira/browse/ARCHETYPE-308)）。如果最后的属性确认被拒绝并且重复了调查问卷，或在命令行中传递了参数，则可以更改该值（例如 `-DoptionIncludeExamples=n`）。

>[!NOTE]
>
>在 Windows 上运行并生成 Dispatcher 配置时，您应在提升权限的命令提示符下或适用于 Linux 的 Windows 子系统中运行（请参阅[问题 329](https://github.com/adobe/aem-project-archetype/issues/329)）。

### 配置文件 {#profiles}

在运行 `mvn install` 时，生成的 maven 项目支持不同的部署配置文件。

| 配置文件 ID | 描述 |
| --------------------------|------------------------------|
| `autoInstallBundle` | 将带 maven-sling-plugin 的核心捆绑包安装到 felix 控制台 |
| `autoInstallPackage` | 通过包管理器将带 content-package-maven-plugin 的 ui.content 和 ui.apps 内容包安装到本地主机上的默认创作实例（端口 4502）。可使用 `aem.host` 和 `aem.port` 用户定义的属性更改主机名和端口。 |
| `autoInstallPackagePublish` | 通过包管理器将带 content-package-maven-plugin 的 ui.content 和 ui.apps 内容包安装到本地主机上的默认发布实例（端口 4503）。可使用 `aem.host` 和 `aem.port` 用户定义的属性更改主机名和端口。 |
| `autoInstallSinglePackage` | 通过包管理器将带 content-package-maven-plugin 的 `all` 内容包安装到本地主机上的默认创作实例（端口 4502）。可使用 `aem.host` 和 `aem.port` 用户定义的属性更改主机名和端口。 |
| `autoInstallSinglePackagePublish` | 通过包管理器将带 content-package-maven-plugin 的 `all` 内容包安装到本地主机上的默认发布实例（端口 4503）。可使用 `aem.host` 和 `aem.port` 用户定义的属性更改主机名和端口。 |
| `integrationTests` | 在 AEM 实例上运行提供的集成测试（仅针对 `verify` 阶段） |
| `precompiledScripts` | 在将 `precompiledScripts` 属性设置为 `y` 的情况下生成项目时自动定义。该配置文件默认处于活动状态，并在 `ui.apps` 中生成一个带预编译脚本的 OSGi 捆绑包，该包将包含在 `all` 内容包中。可使用 `-DskipScriptPrecompilation=true` 禁用配置文件。 |

### 构建和安装 {#building-and-installing}

要构建在项目根目录中运行的所有模块，请使用以下 Maven 命令。

```shell
mvn clean install
```

如果您有一个正在运行的 AEM 实例，则可以使用以下 Maven 命令构建和打包整个项目并将其部署到 AEM 中。

```shell
mvn clean install -PautoInstallPackage
```

要将它部署到发布实例，请运行此命令。

```shell
mvn clean install -PautoInstallPackagePublish
```

或者，要部署到发布实例，请运行此命令。

```shell
mvn clean install -PautoInstallPackage -Daem.port=4503
```

或者，要仅将捆绑包部署到创作实例，请运行此命令。

```shell
mvn clean install -PautoInstallBundle
```

## 父级 POM {#parent-pom}

项目的根目录 (`<src-directory>/<project>/pom.xml`) 中的 `pom.xml` 被称为父级 POM，可驱动项目的结构并管理项目的依赖项和某些全局属性。

### 全局项目属性 {#global-properties}

父级 POM 的 `<properties>` 部分定义了在 AEM 实例上部署项目所必需的几个全局属性，例如用户名/密码、主机名/端口等。

这些属性设置为部署到本地 AEM 实例，因为这是开发人员最常进行的构建。请注意，有一些属性要部署到创作实例和发布实例。此外，也会在此处将凭据设置为使用 AEM 实例进行身份验证。使用默认 admin:admin 凭据。

设置这些属性以便在部署到更高级别的环境时可以将其覆盖。这样一来，无需更改 POM 文件，并且可通过命令行参数覆盖 `aem.host` 和 `sling.password` 等变量：

```shell
mvn -PautoInstallPackage clean install -Daem.host=production.hostname -Dsling.password=productionpasswd
```

### 模块结构 {#module-structure}

父级 POM 的 `<modules>` 部分定义项目将构建的模块。默认情况下，项目将构建[之前定义的标准模块](#what-you-get)：core、ui.apps、ui.content、ui.tests 和 it.launcher。随着项目的发展，始终可以添加更多模块。

### 依赖项 {#dependencies}

父级 POM 的 `<dependencyManagement>` 部分定义项目中使用的 API 的所有依赖项和版本。应在父级 POM 中管理版本。core 和 ui.apps 等子模块不应包含任何版本信息。

#### Uber-Jar {#uber-jar}

关键依赖项之一是 [AEM Java API Jar](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-as-a-cloud-service-sdk.html)。这将包括所有 AEM API，并且 AEM 版本只有一个依赖项。

>[!NOTE]
>
>作为最佳实践，您应更新 uber-jar 版本以匹配 AEM 的目标版本。例如，如果您计划部署到 AEM 6.4，则应将 uber-jar 的版本更新为 6.4.0。

#### 核心组件 {#core-components}

当然，AEM 项目原型会使用核心组件。

核心组件在默认 runmode 中自动安装到 AEM 中，并由示例 WKND 站点使用。在[生产 runmode](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html#runmodes) (`nosamplecontent`) 中，核心组件不可用。

因此，要在所有部署中利用核心组件，最佳实践是将它们作为 Maven 项目的一部分包含在内。

>[!NOTE]
>
>通常，核心组件的每个版本都会紧跟 AEM 项目原型的版本，以便最新的原型使用最新版本的核心组件。
>
>然而，原型的新版本可能不会直接紧跟核心组件的新版本，因此您可能希望将核心组件的依赖项更新到最新版本。

>[!NOTE]
>
>core.wcm.components.examples 是一组示例页面，用于说明核心组件的示例。作为最佳实践，在部署项目以供生产使用时，您应删除此依赖项和子包包含。

## 测试 {#testing}

项目中包含三个级别的测试，由于这些测试的类型不同，因此它们会通过不同的方式或在不同的位置执行。

* core 模块中的单元测试：此测试展示了捆绑包中包含的代码的经典单元测试。要进行测试，请执行：
   * `mvn clean test`
* 服务器端集成测试：此测试在 AEM 环境中（即 AEM 服务器上）运行单元测试等。要进行测试，请执行：
   * `mvn clean verify -PintegrationTests`
* 客户端 Hobbes.js 测试：这些是基于 JavaScript 的浏览器端测试，用于验证浏览器端的行为。要进行测试，请执行：
   1. 在浏览器中加载 AEM，就像创作页面一样。
   1. 在[开发者模式](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developer-tools/developer-mode.html)中打开页面
   1. 打开左面板并切换到&#x200B;**测试**&#x200B;选项卡。
   1. 找到生成的 **MyName 测试**&#x200B;并运行它们。

## 后续步骤 {#next-steps}

因此，您已构建并安装 AEM 项目原型。现在该做什么？虽然原型很小，但包含根据推荐的最佳实践配置的多个强大 AEM 功能示例。这些示例可引导您如何在项目中利用这些功能。对于任何项目，您可能需要：

* [通过扩展现有核心组件来自定义组件](/help/developing/customizing.md)
* [添加其他模板](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)
* [修改本地化结构](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/preparation.html)
* [了解前端构建模块](uifrontend.md)
