---
title: 使用AEM Project Archetype
description: AEM Project Archetype的详细使用说明
translation-type: tm+mt
source-git-commit: 794408e8b643de2234664e69e59e1108cf286cd7
workflow-type: tm+mt
source-wordcount: '2057'
ht-degree: 1%

---


# AEM 项目原型 {#aem-project-archetype}

AEM Project Archetype创建基于最佳实践的最小化Adobe Experience Manager项目，作为您自己的AEM项目的起点。 使用此原型时必须提供的属性允许您指定此项目所有部分的名称，并控制某些可选特征。

## 为何使用原型{#why-use-the-archetype}

使用AEM Project Archetype，您只需按键几次，即可踏上构建基于最佳实践的AEM项目的道路。 通过使用原型，所有部分都已到位，这样，尽管最终的项目是最小的，它已经实现了AEM的所有[关键功能](#what-you-get)，这样您只需在顶部构建并扩展。

当然，在AEM项目中有许多成功的元素，但使用AEM项目原型是可靠的基础，强烈建议任何AEM项目都使用。

## 入门 {#getting-started}

项目原型使得在AEM上开始开发变得很容易。 您可以通过多种方式执行第一步。

* WKND教程——有关在AEM上进行开发（包括如何利用原型）的精彩介绍，请参阅[AEM Sites入门- WKND教程](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)，以获得一个实际示例，该示例将指导您逐步使用原型来实施一个简单的项目。
* WKND事件教程——如果您对AEM上的单页应用程序(SPA)开发特别感兴趣，请务必查看专用的[WKND事件教程](https://helpx.adobe.com/experience-manager/kt/sites/using/getting-started-spa-wknd-tutorial-develop.html)。
* 自行下载和开始! -您可以轻松下载GitHub上提供的当前项目原型，并按照[下面的简单步骤创建您的第一个项目。](#how-to-use-the-archetype)

## 原型{#what-you-get}的使用

AEM Archetype由模块组成：

* **[核心](core.md)**:是一个Java捆绑包，它包含所有核心功能(如OSGi服务、监听器和调度程序)，以及与组件相关的Java代码(如servlet和request过滤器)。
* **[ui.apps](uiapps.md)**:包含 `/apps` 项 `/etc` 目的和部分，即JS和CSS客户端库、组件、模板、运行模式特定配置以及Hobbes测试。
* **[ui.content](uicontent.md)**:包含使用ui.apps模块中的组件的示例内容。
* **[ui.tests](uitests.md)**:是一个Java包，包含服务器端执行的JUnit测试。此捆绑包不会部署到生产上。
* **ui.launcher**:包含将ui.tests捆绑包（和依赖捆绑包）部署到服务器并触发远程JUnit执行的粘胶代码。
* **[ui.frontend.general](uifrontend.md)**: **（可选）** 包含使用基于Webpack的常规前端构建模块所需的伪像。
* **[ui.frontend.react](uifrontend-react.md)**: **（可选）** 包含使用原型创建基于React的SPA项目时所需的伪像。
* **[ui.frontend.angular](uifrontend-angular.md)**: **（可选）** 包含使用原型创建基于角度的SPA项目时所需的伪像。

![](/help/assets/archetype-structure.png)

在Maven中表示的AEM Archetype的模块作为表示应用程序、内容和必需OSGi包的内容包部署到AEM。

## 如何使用原型{#how-to-use-the-archetype}

要使用原型，您首先需要创建一个项目，该项目在本地文件结构中生成[之前描述的](#what-you-get)模块。 在项目生成过程中，可以定义项目的许多属性，如项目名称、版本等。

使用Maven构建项目可创建可部署到AEM的对象（包和OSGi包）。 其他Maven命令和用户档案可用于将项目对象部署到AEM实例。

### 创建项目 {#create-project}

要开始使用，您最简单的方法是使用[AEM Eclipse扩展](https://docs.adobe.com/content/help/en/experience-manager-65/developing/devtools/aem-eclipse.html)并按照“新建项目”向导选择&#x200B;**AEM示例多模块项目**&#x200B;来使用已发布版本的原型。

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

* 将`XX`设置为最新AEM Project Archetype的[版本号](https://github.com/adobe/aem-project-archetype/blob/master/VERSIONS.md)。
* 将[AEM的`aemVersion=cloud`设置为Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html);\
   为[Adobe Managed Services](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams)或内部部署设置`aemVersion=6.5.0`。
核心组件依赖关系仅针对非云aem版本添加，因为核心组件是作为云为AEM提供的OOTB
服务。
* 调整`appTitle="My Site"`以定义网站标题和组件组。
* 调整`appId="mysite"`以定义Maven artifactId、组件、配置和内容文件夹名称以及客户端库名称。
* 调整`groupId="com.mysite"`以定义Maven groupId和Java源包。
* 查找可用属性的列表，查看是否有更多要调整的属性。

>[!NOTE]
>
>最好将`adobe-public`用户档案添加到Maven `settings.xml`文件，以便自动将repo.adobe.com添加到主构建过程。
>
>此处](https://helpx.adobe.com/experience-manager/kb/SetUpTheAdobeMavenRepository.html)可找到示例POM [。

### 属性 {#properties}

在使用原型创建项目时，可以使用以下属性。

| 名称 | 默认 | 描述 |
--------------------------|----------------|--------------------
| `appTitle` |  | 应用程序标题将用于网站标题和组件组(例如，`"My Site"`)。 |
| `appId` |  | 技术名称将用于组件、配置和内容文件夹名称以及客户端库名称(例如，`"mysite"`)。 |
| `artifactId` | *`${appId}`* | 基Maven对象ID(例如，`"mysite"`)。 |
| `groupId` |  | 基本Maven组ID(例如，`"com.mysite"`)。 |
| `package` | *`${groupId}`* | Java源包(例如，`"com.mysite"`)。 |
| `version` | `1.0-SNAPSHOT` | 项目版本(如`1.0-SNAPSHOT`)。 |
| `aemVersion` | `6.5.0` | 目标AEM版本(对于`cloud`AEM，可以是[Cloud Service;或](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/landing/home.html)，或`6.5.0`（适用于`6.4.4`Adobe Managed Services[或内部部署）。](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/dispatcher.ams) |
| `sdkVersion` | `latest` | 当`aemVersion=cloud`可以指定[ SDK](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/developing/aem-as-a-cloud-service-sdk.html)版本时(例如，`2020.02.2265.20200217T222518Z-200130`)。 |
| `includeDispatcherConfig` | `y` | 根据`aemVersion`的值（可以是`y`或`n`），为云或AMS/on-premise包括调度程序配置。 |
| `frontendModule` | `none` | 包括一个Webpack前端构建模块，它为常规站点生成客户端库(可以是`general`或`none`;对于实现[SPA Editor](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/headless/spa/introduction.html)的单页应用程序，可以是`angular`或`react`。 |
| `languageCountry` | `en_us` | 用于创建内容结构的语言和国家／地区代码(例如，`en_us`)。 |
| `singleCountry` | `y` | 包括语言主控的内容结构（可以是`y`或`n`）。 |
| `includeExamples` | `y` | 包括[组件库](https://www.aemcomponents.dev/)示例站点（可以是`y`或`n`）。 |
| `includeErrorHandler` | `n` | 包括一个自定义404响应页，该页将对整个实例全局（可以是`y`或`n`）。 |

>[!NOTE]
>
> 如果原型首次以交互模式执行，则无法更改具有默认值的属性（有关详细信息，请参阅[ARCHETYPE-308](https://issues.apache.org/jira/browse/ARCHETYPE-308)）。 当结束时的属性确认被拒绝并且调查表被重复时，或者通过在命令行中传递参数(例如，`-DoptionIncludeExamples=n`)。

>[!NOTE]
>
>在Windows上运行并生成调度程序配置时，您应在提升的命令提示符或Linux的Windows子系统中运行（请参阅[期刊329](https://github.com/adobe/aem-project-archetype/issues/329)）。

### 个人资料 {#profiles}

运行`mvn install`时，生成的主项目支持不同的部署用户档案。

| 用户档案ID | 描述 |
--------------------------|------------------------------
| `autoInstallBundle` | 将带有maven-sling-plugin的核心捆绑包安装到felix控制台 |
| `autoInstallPackage` | 将包含content-package-maven-plugin的ui.content和ui.apps内容包安装到包管理器，以在localhost上默认创作实例，端口为4502。 主机名和端口可以使用`aem.host`和`aem.port`用户定义的属性进行更改。 |
| `autoInstallPackagePublish` | 将包含content-package-maven-plugin的ui.content和ui.apps内容包安装到包管理器，以在localhost上默认发布实例，端口4503。 主机名和端口可以使用`aem.host`和`aem.port`用户定义的属性进行更改。 |
| `autoInstallSinglePackage` | 将`all`内容包和content-package-maven-plugin安装到包管理器，以在localhost上安装默认的作者实例，端口为4502。 主机名和端口可以使用`aem.host`和`aem.port`用户定义的属性进行更改。 |
| `autoInstallSinglePackagePublish` | 将`all`内容包和content-package-maven-plugin安装到包管理器，以在localhost上安装默认发布实例，端口为4503。 主机名和端口可以使用`aem.host`和`aem.port`用户定义的属性进行更改。 |
| `integrationTests` | 在AEM实例上运行提供的集成测试（仅针对`verify`阶段） |

### 构建和安装{#building-and-installing}

要构建在项目根目录中运行的所有模块，请使用以下Maven命令。

```shell
mvn clean install
```

如果您有正在运行的AEM实例，则可以构建并打包整个项目，然后使用以下Maven命令部署到AEM中。

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

项目(`<src-directory>/<project>/pom.xml`)根部的`pom.xml`称为父POM，它驱动项目结构并管理依赖项和项目的特定全局属性。

### 全局项目属性{#global-properties}

父POM的`<properties>`部分定义了对AEM实例上的项目部署非常重要的几个全局属性，如用户名／口令、主机名／端口等。

这些属性设置为部署到本地AEM实例，因为这是开发人员将执行的最常见的构建。 请注意，存在要部署到作者实例和发布实例的属性。 此外，还将凭据设置为与AEM实例进行身份验证。 使用默认管理员：管理员凭据。

设置这些属性，以便在部署到更高级别环境时可以覆盖它们。 这样，POM文件就不必更改，但诸如`aem.host`和`sling.password`之类的变量可以通过命令行参数被覆盖：

```shell
mvn -PautoInstallPackage clean install -Daem.host=production.hostname -Dsling.password=productionpasswd
```

### 模块结构{#module-structure}

父POM的`<modules>`部分定义项目将构建的模块。 默认情况下，项目会生成[以前定义的标准模块](#what-you-get):核心、ui.apps、ui.content、ui.tests和it.launcher。 随着项目的发展，可以始终添加更多模块。

### 依赖关系 {#dependencies}

父POM的`<dependencyManagement>`部分定义项目中使用的所有API的依赖项和版本。 版本应在父POM中管理。 核心和ui.apps等子模块不应包含任何版本信息。

#### Uber-Jar {#uber-jar}

关键依赖项之一是[AEM uber-jar](https://docs.adobe.com/content/help/en/experience-manager-65/developing/devtools/ht-projects-maven.html#ExperienceManagerAPIDependencies)。 这将包括所有AEM API，只包含AEM版本的一个依赖项。

>[!NOTE]
>
>作为最佳实践，您应更新uber-jar版本以匹配AEM的目标版本。 例如，如果您计划部署到AEM 6.4，则应将uber-jar的版本更新到6.4.0。

#### 核心组件 {#core-components}

AEM Project Archetype当然利用核心组件。

核心组件自动安装在AEM的默认运行模式中，并由示例WKND站点使用。 在[生产运行模式](https://docs.adobe.com/content/help/en/experience-manager-65/administering/security/production-ready.html)(`nosamplecontent`)中，核心组件不可用。

因此，为了在所有部署中利用核心组件，最好将其纳入Maven项目。

>[!NOTE]
>
>每个版本的核心组件通常随后都会发布AEM Project Archetype，这样最新的原型就会使用最新版本的核心组件。
>
>但是，新版本的原型可能不会直接遵循新版本的核心组件，因此您可能希望将对核心组件的依赖性更新到最新版本。

>[!NOTE]
>
>core.wcm.components.examples是一组示例页面，用于说明核心组件的示例。 作为最佳实践，在为生产用途部署项目时，应删除此依赖项和子包包含。

## 测试 {#testing}

项目中包含三个测试级别，由于它们是不同类型的测试，因此它们以不同的方式或在不同位置执行。

* 核心单元测试：它展示捆绑包中包含的代码的经典单元测试。 要进行测试，请执行：
   * `mvn clean test`
* 服务器端集成测试：这些测试在AEM-环境(即AEM服务器)中运行类似单元的测试。 要进行测试，请执行：
   * `mvn clean verify -PintegrationTests`
* 客户端Hobbes.js测试：这些是基于JavaScript的浏览器端测试，用于验证浏览器端行为。 测试：
   1. 在浏览器中加载AEM，就像创作页面一样。
   1. 在[开发者模式](https://docs.adobe.com/content/help/en/experience-manager-65/developing/components/developer-mode.html)中打开页面
   1. 打开左面板并切换到&#x200B;**测试**&#x200B;选项卡。
   1. 找到生成的&#x200B;**MyName测试**&#x200B;并运行它们。

## 后续步骤{#next-steps}

因此，您已经构建并安装了AEM Project Archetype。 现在怎么办？ 原型很小，但包含许多根据推荐最佳实践配置的强大AEM功能的示例。 使用这些功能可以指示您如何在项目中利用这些功能。 对于您可能需要的任何项目：

* [通过扩展现有核心组件来自定义组件](/help/developing/customizing.md)
* [添加其他模板](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)
* [调整本地化结构](https://docs.adobe.com/content/help/en/experience-manager-65/administering/introduction/tc-prep.html)
* [了解前端构建模块](uifrontend.md)
