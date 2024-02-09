---
title: 使用 AEM 项目原型
description: 了解如何使用 AEM 项目原型，来创建最小的基于最佳实践的 Adobe Experience Manager 项目作为您自己的 AEM 项目的起点。
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: a3978d8b-4904-42aa-9ee2-9c1f884327bb
source-git-commit: bd92a5d1884056ca7b44ea28e5817d8bde10a4d9
workflow-type: ht
source-wordcount: '1092'
ht-degree: 100%

---


# 使用 AEM 项目原型 {#using-the-archetype}

本文档解释如何使用 AEM 项目原型，来创建最小的基于最佳实践的 Adobe Experience Manager 项目作为您自己的 AEM 项目的起点。

本文档侧重介绍一般使用模式以及原型能够为您做什么。有关详细的构建选项和技术说明，请参阅原型的 GitHub 存储库中的文档。

>[!TIP]
>
>最新的 AEM 项目原型和相关技术文档[可以在 GitHub 上找到](https://github.com/adobe/aem-project-archetype)。

## 快速入门 {#getting-started}

利用项目原型，可以轻松地在 AEM 上开始进行开发。您可以通过多种方式使用原型迈出第一步。

* **WKND 教程** - 有关在 AEM 上进行开发的精彩介绍（包括如何利用原型），请参阅 [AEM Sites 入门 - WKND 教程](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)中的实际示例，该示例介绍如何使用原型实施简单项目。
* **WKND 事件教程** - 如果您特别想知道如何在 AEM 上开发单页面应用程序 (SPA)，请务必查看专门的 [WKND 事件教程](https://helpx.adobe.com/cn/experience-manager/kt/sites/using/getting-started-spa-wknd-tutorial-develop.html)。
* **开始创建您自己的项目！** - 您可以轻松下载 [GitHub 上提供的当前项目原型](https://github.com/adobe/aem-project-archetype)，并开始创建您的第一个项目。

## 如何使用原型 {#how-to-use-the-archetype}

使用原型的第一步是创建一个项目，该项目在本地文件结构中生成[模块](#what-you-get)。在生成项目过程中，可以定义项目的许多属性，例如项目名称、版本、启用各种选项等。

>[!TIP]
>
>每当您构建原型时，它还会生成一系列自述文件，其中包含每个模块的技术细节和用法，如[下面的链接](#what-you-get)所示。

使用 Maven 构建项目会创建可部署到 AEM 的构件（包和 OSGi 捆绑包）。其他 Maven 命令和配置文件可用于将项目构件部署到 AEM 实例。

## 使用原型的好处 {#what-you-get}

原型由模块组成，所有模块都是在使用原型时自动创建的。

* **[core](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/core)**：此模块是一个 Java 捆绑包，它包含所有核心功能（例如 OSGi 服务、侦听器和调度程序）以及与组件相关的 Java 代码（例如 servlet 和请求过滤器）。
* **[it.tests](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/it.tests)**：此模块是基于 Java 的集成测试。
* **[ui.apps](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.apps)**：此模块包含项目的 `/apps` 和 `/etc` 部分，即 JS 和 CSS clientlib、组件和模板。
* **[ui.content](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.content)**：此模块包含使用 ui.apps 模块中的组件的示例内容。
* **[ui.config](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.config)**：此模块包含项目的特定于 runmode 的 OSGi 配置。
* **[ui.frontend.general](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.frontend.general)**：（可选）此模块包含使用通用型基于 Webpack 的前端构建模块所需的构件。
* **[ui.frontend.react](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.frontend.react)****：（可选）**&#x200B;此模块包含使用原型创建基于 React 的 SPA 项目时所需的构件（是否使用取决于构建参数）。
* **[ui.frontend.angular](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.frontend.angular)****：（可选）**&#x200B;此模块包含使用原型创建基于 Angular 的 SPA 项目时所需的构件（是否使用取决于构建参数）。
* **[ui.tests](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.tests)**：此模块包含基于 Selenium 的 UI 测试。
* **[all](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/all)**：此模块是单内容包，它嵌入了所有已编译的模块（捆绑包和内容包），其中包括任何供应商依赖项。
* **[dispatcher.ams](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/dispatcher.ams)**：此模块包含 AMS/内部部署项目的基本 Dispatcher 配置（是否使用取决于构建参数）。
* **[dispatcher.cloud](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/dispatcher.cloud)**：此模块包含 AEMaaCS 项目的基本 Dispatcher 配置（是否使用取决于构建参数）。

![内容包组织](/help/assets/content-package-organization.png)

Maven 中表示的原型模块作为表示应用程序、内容和必要的 OSGi 捆绑包的内容包部署到 AEM。

## 父级 POM {#parent-pom}

项目的根目录 (`<src-directory>/<project>/pom.xml`) 中的 `pom.xml` 被称为父级 POM，可驱动项目的结构并管理项目的依赖项和某些全局属性。

### 全局项目属性 {#global-properties}

父级 POM 的 `<properties>` 部分定义了在 AEM 实例上部署项目所必需的几个全局属性，例如用户名/密码、主机名/端口等。

这些属性设置为部署到本地 AEM 实例，因为这是开发人员最常进行的构建。请注意，有一些属性要部署到创作实例和发布实例。此外，也会在此处将凭据设置为使用 AEM 实例进行身份验证。使用默认 `admin:admin` 凭据。

设置这些属性以便在部署到更高级别的环境时可以将其覆盖。这样一来，无需更改 POM 文件，并且可通过命令行参数覆盖 `aem.host` 和 `sling.password` 等变量：

```shell
mvn -PautoInstallPackage clean install -Daem.host=production.hostname -Dsling.password=productionpasswd
```

### 模块结构 {#module-structure}

父级 POM 的 `<modules>` 部分定义项目将构建的模块。默认情况下，项目将构建[之前定义的标准模块。](#what-you-get)随着项目的发展，始终可以添加更多模块。

### 依赖项 {#dependencies}

父级 POM 的 `<dependencyManagement>` 部分定义项目中使用的 API 的所有依赖项和版本。应在父级 POM 中管理版本。子模块不应包含任何版本信息。

#### Uber-Jar {#uber-jar}

关键依赖项之一是 [AEM Java API Jar。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-as-a-cloud-service-sdk.html)这将包括所有 AEM API，并且 AEM 版本只有一个依赖项。

>[!NOTE]
>
>作为最佳实践，您应更新 uber-jar 版本以匹配 AEM 的目标版本。例如，如果您计划部署到 AEM 6.5，则应将 uber-jar 的版本更新到 6.5.X，其中 `X` 表示最新的服务包。

#### 核心组件 {#core-components}

当然，原型会使用[核心组件。](/help/introduction.md)因此，要在所有部署中利用核心组件，最佳实践是将它们作为 Maven 项目的一部分包含在内。

core.wcm.components.examples 是一组示例页面，用于说明核心组件的示例。作为最佳实践，在部署项目以供生产使用时，您应删除此依赖项和子包包含。

>[!NOTE]
>
>核心组件和原型作为单独的 GitHub 项目进行维护，因此它们的版本有所不同。
>
>原型的每个版本都将利用发布时可用的最新版本的核心组件。但是，您可能希望手动更新对核心组件的依赖关系。

## 测试 {#testing}

项目中包含三个级别的测试，由于这些测试的类型不同，因此它们会通过不同的方式或在不同的位置执行。

* **[单元测试](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/core)** - 对捆绑包中包含的代码进行经典的单元测试
* **[集成测试](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/it.tests)** - 服务器端集成测试，在 AEM 环境中（即 AEM 服务器上）运行单元测试等
* **[UI 测试](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.tests)** - 基于 Selenium 的浏览器端测试，用于验证浏览器端行为
