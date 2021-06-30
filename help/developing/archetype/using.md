---
title: 使用AEM项目原型
description: AEM项目原型的详细使用说明
feature: 核心组件、 AEM项目原型
role: Architect, Developer, Administrator
exl-id: a3978d8b-4904-42aa-9ee2-9c1f884327bb
source-git-commit: 17081a073998512a52aebfc662f2bc125ca2a2c4
workflow-type: tm+mt
source-wordcount: '2147'
ht-degree: 1%

---

# AEM 项目原型 {#aem-project-archetype}

AEM项目原型创建了一个基于最佳实践的、最基础的Adobe Experience Manager项目，可用作您自己的AEM项目的起点。 使用此原型时必须提供的属性允许您指定此项目所有部分的名称，并控制某些可选功能。

## 为何使用原型 {#why-use-the-archetype}

使用AEM项目原型，您可以在构建基于最佳实践的AEM项目的道路上前进，只需几次击键。 通过使用原型，所有片段都已到位，这样，尽管生成的项目最小，但它已实施AEM的所有[关键功能](#what-you-get)，因此您只需在顶部构建并扩展即可。

当然，成功的AEM项目包含许多元素，但使用AEM项目原型是一个不错的基础，强烈建议对任何AEM项目使用。

## 入门 {#getting-started}

项目原型使得在AEM上开始开发变得非常简单。 您可以通过多种方式执行第一步。

* WKND教程 — 有关在AEM上进行开发（包括如何利用原型）的重要介绍，请参阅[AEM Sites快速入门 — WKND教程](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)，以获取一个实际示例，该示例将指导您逐步使用原型来实施简单项目。
* WKND事件教程 — 如果您对AEM上的单页应用程序(SPA)开发特别感兴趣，请务必查看专用的[WKND事件教程](https://helpx.adobe.com/experience-manager/kt/sites/using/getting-started-spa-wknd-tutorial-develop.html)。
* 自行下载并启动！  — 您可以轻松下载GitHub上提供的当前项目原型，并按照](#how-to-use-the-archetype)下面的简单步骤，通过[创建您的第一个项目。

## 原型的使用 {#what-you-get}

AEM原型由模块组成：

* **[核心](core.md)**:是一个Java包，其中包含所有核心功能（如OSGi服务、侦听器和调度程序），以及与组件相关的Java代码（如servlet和请求过滤器）。
* **[it.tests](ittests.md)**:是基于Java的集成测试。
* **[ui.apps](uiapps.md)**:包含 `/apps` 项 `/etc` 目的和部分，即JS和CSS客户端库、组件和模板。
* **[ui.content](uicontent.md)**:包含使用ui.apps模块中的组件的示例内容。
* **ui.config**:包含项目的特定于运行模式的OSGi配置。
* **[ui.frontend.general](uifrontend.md)**: **（可选）** 包含使用基于Webpack的常规前端生成模块所需的工件。
* **[ui.frontend.react](uifrontend-react.md)**: **（可选）** 包含使用原型创建基于React的SPA项目时所需的工件。
* **[ui.frontend.angular](uifrontend-angular.md)**: **（可选）** 包含使用原型创建基于Angular的SPA项目时所需的工件。
* **[ui.tests](uitests.md)**:包含基于硒的UI测试。
* **全部**:是一个内容包，嵌入所有编译的模块（包和内容包），包括任何供应商依赖项。
* **分析**:对项目运行分析，该分析为部署到AEM as aCloud Service提供了额外验证。

![](/help/assets/archetype-structure.png)

Maven中表示的AEM Archetype模块作为表示应用程序、内容和必要OSGi包的内容包部署到AEM。

## 如何使用原型 {#how-to-use-the-archetype}

要使用原型，您首先需要创建一个项目，该项目将本地文件结构中的模块生成为[之前描述的](#what-you-get)。 在项目生成过程中，可以定义项目的许多属性，如项目名称、版本等。

使用Maven构建项目时，会创建可部署到AEM的工件（包和OSGi包）。 其他Maven命令和配置文件可用于将项目工件部署到AEM实例。

### 创建项目 {#create-project}

要开始使用，您大多可以简单地使用[AEM Eclipse扩展](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developer-tools/eclipse.html)，然后按照“新建项目”向导选择&#x200B;**AEM示例多模块项目**&#x200B;来使用已发布的原型版本。

当然，您也可以直接调用Maven。

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

* 将`XX`设置为最新AEM项目原型的[版本号](https://github.com/adobe/aem-project-archetype/blob/master/VERSIONS.md)。
* 将[AEM的`aemVersion=cloud`设置为Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html);\
   为[Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams)或内部部署设置`aemVersion=6.5.0`。
仅会为非云aem版本添加核心组件依赖项，因为为AEM as a Cloud提供了核心组件OOTB
服务。
* 调整`appTitle="My Site"`以定义网站标题和组件组。
* 调整`appId="mysite"`以定义Maven人为对象ID、组件、配置和内容文件夹名称以及客户端库名称。
* 调整`groupId="com.mysite"`以定义Maven groupId和Java源包。
* 查找可用属性列表，以查看是否需要调整更多属性。

>[!NOTE]
>
>最佳做法是将`adobe-public`配置文件添加到Maven `settings.xml`文件，以便自动将repo.adobe.com添加到Maven构建过程。
>
>此处](https://helpx.adobe.com/experience-manager/kb/SetUpTheAdobeMavenRepository.html)提供了POM [示例。

### 属性 {#properties}

使用原型创建项目时，可以使用以下属性。

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

>[!NOTE]
>
> 如果首次在交互模式下执行原型，则无法更改具有默认值的属性（有关更多详细信息，请参阅[ARCHETYPE-308](https://issues.apache.org/jira/browse/ARCHETYPE-308)）。 当结尾的属性确认被拒绝并重复调查表时，或通过在命令行中传递参数(例如，`-DoptionIncludeExamples=n`)。

>[!NOTE]
>
>在Windows上运行并生成调度程序配置时，您应在提升的命令提示符下或Linux的Windows子系统中运行（请参阅[问题329](https://github.com/adobe/aem-project-archetype/issues/329)）。

### 个人资料 {#profiles}

运行`mvn install`时，生成的Maven项目支持不同的部署配置文件。

| 配置文件ID | 描述 |
| --------------------------|------------------------------|
| `autoInstallBundle` | 将包含maven-sling-plugin的核心包安装到felix控制台 |
| `autoInstallPackage` | 将包含content-package-maven-plugin的ui.content和ui.apps内容包安装到包管理器，以在localhost（端口4502）上默认创作实例。 主机名和端口可以使用`aem.host`和`aem.port`用户定义的属性进行更改。 |
| `autoInstallPackagePublish` | 将包含content-package-maven-plugin的ui.content和ui.apps内容包安装到包管理器，以在localhost（端口4503）上默认发布实例。 主机名和端口可以使用`aem.host`和`aem.port`用户定义的属性进行更改。 |
| `autoInstallSinglePackage` | 将`all`包含content-package-maven-plugin的内容包安装到包管理器，以在localhost（端口4502）上默认创作实例。 主机名和端口可以使用`aem.host`和`aem.port`用户定义的属性进行更改。 |
| `autoInstallSinglePackagePublish` | 将包含content-package-maven-plugin的`all`内容包安装到包管理器，以在localhost（端口4503）上默认发布实例。 主机名和端口可以使用`aem.host`和`aem.port`用户定义的属性进行更改。 |
| `integrationTests` | 在AEM实例上运行提供的集成测试（仅适用于`verify`阶段） |

### 构建和安装 {#building-and-installing}

要构建在项目根目录中运行的所有模块，请使用以下Maven命令。

```shell
mvn clean install
```

如果您有正在运行的AEM实例，则可以构建并打包整个项目，然后使用以下Maven命令将其部署到AEM中。

```shell
mvn clean install -PautoInstallPackage
```

要将其部署到发布实例，请运行此命令。

```shell
mvn clean install -PautoInstallPackagePublish
```

或者，要部署到发布实例，请运行此命令。

```shell
mvn clean install -PautoInstallPackage -Daem.port=4503
```

或者，要仅将包部署到作者，请运行此命令。

```shell
mvn clean install -PautoInstallBundle
```

## 父POM {#parent-pom}

位于项目根目录(`<src-directory>/<project>/pom.xml`)的`pom.xml`称为父POM，它驱动项目结构并管理项目的依赖关系和某些全局属性。

### 全局项目属性 {#global-properties}

父POM的`<properties>`部分定义了对于在AEM实例上部署项目非常重要的几个全局属性，如用户名/密码、主机名/端口等。

这些属性设置为部署到本地AEM实例，因为这是开发人员将执行的最常见内部版本。 请注意，有一些资产可部署到创作实例和发布实例。 这也是将凭据设置为通过AEM实例进行身份验证的地方。 使用默认的管理员：管理员凭据。

已设置这些属性，以便在部署到更高级别的环境时可以覆盖这些属性。 这样，POM文件就不必更改，但诸如`aem.host`和`sling.password`之类的变量可以通过命令行参数来覆盖：

```shell
mvn -PautoInstallPackage clean install -Daem.host=production.hostname -Dsling.password=productionpasswd
```

### 模块结构 {#module-structure}

父POM的`<modules>`部分定义项目将构建的模块。 默认情况下，项目会生成[之前定义的标准模块](#what-you-get):核心、ui.apps、ui.content、ui.tests和it.launcher。 随着项目的不断发展，可以随时添加更多模块。

### 依赖关系 {#dependencies}

父POM的`<dependencyManagement>`部分定义项目中使用的所有API依赖项和版本。 应在父POM中管理版本。 核心和ui.apps等子模块不应包含任何版本信息。

#### Uber-Jar {#uber-jar}

关键依赖项之一是[AEM uber-jar](https://docs.adobe.com/content/help/en/experience-manager-65/developing/devtools/ht-projects-maven.html#ExperienceManagerAPIDependencies)。 这将包括所有AEM API，只包含AEM版本的一个依赖项条目。

>[!NOTE]
>
>作为最佳实践，您应更新uber-jar版本以匹配AEM的目标版本。 例如，如果您计划部署到AEM 6.4，则应将uber-jar的版本更新为6.4.0。

#### 核心组件 {#core-components}

AEM项目原型当然会利用核心组件。

核心组件在默认运行模式下自动安装在AEM中，并由示例WKND站点使用。 在[生产运行模式](https://docs.adobe.com/content/help/en/experience-manager-65/administering/security/production-ready.html)(`nosamplecontent`)中，核心组件不可用。

因此，为了在所有部署中利用核心组件，最佳做法是将它们包含在Maven项目中。

>[!NOTE]
>
>核心组件的每个版本通常后跟一个AEM项目原型版本，以便最新原型使用最新版本的核心组件。
>
>但是，原型的新版本可能不会直接遵循核心组件的新版本，因此您可能希望将对核心组件的依赖项更新到最新版本。

>[!NOTE]
>
>core.wcm.components.examples是一组示例页面，用于说明核心组件的示例。 作为最佳实践，在部署生产用项目时，您应该删除此依赖项和子包包含。

## 测试 {#testing}

项目中包含三个测试级别，由于它们是不同类型的测试，因此会以不同的方式或在不同的位置执行它们。

* 核心单元测试：这显示了对包中包含的代码的经典单元测试。 要进行测试，请执行：
   * `mvn clean test`
* 服务器端集成测试：这些测试在AEM环境(即在AEM服务器上)中运行类似于单元的测试。 要进行测试，请执行：
   * `mvn clean verify -PintegrationTests`
* 客户端Hobbes.js测试：这些是基于JavaScript的浏览器端测试，用于验证浏览器端行为。 要测试，请执行以下操作：
   1. 在浏览器中加载AEM，就像创作页面一样。
   1. 在[开发人员模式](https://docs.adobe.com/content/help/en/experience-manager-65/developing/components/developer-mode.html)中打开页面
   1. 打开左面板，然后切换到&#x200B;**Tests**&#x200B;选项卡。
   1. 找到生成的&#x200B;**MyName测试**&#x200B;并运行它们。

## 后续步骤 {#next-steps}

因此，您已构建并安装AEM项目原型。 现在怎么办？ 原型很小，但包含许多根据推荐的最佳实践配置的强大AEM功能示例。 使用这些说明如何在项目中利用这些功能。 对于您可能需要执行以下操作的任何项目：

* [通过扩展现有核心组件来自定义组件](/help/developing/customizing.md)
* [添加其他模板](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)
* [调整本地化结构](https://docs.adobe.com/content/help/en/experience-manager-65/administering/introduction/tc-prep.html)
* [了解前端构建模块](uifrontend.md)
