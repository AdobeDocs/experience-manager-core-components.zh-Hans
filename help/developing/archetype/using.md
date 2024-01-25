---
title: 使用 AEM 项目原型
description: 了解如何使用AEM项目原型创建基于最佳实践的、最基础的Adobe Experience Manager项目，作为您自己的AEM项目的起点。
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: a3978d8b-4904-42aa-9ee2-9c1f884327bb
source-git-commit: bd92a5d1884056ca7b44ea28e5817d8bde10a4d9
workflow-type: tm+mt
source-wordcount: '1092'
ht-degree: 33%

---


# 使用 AEM 项目原型 {#using-the-archetype}

本文档介绍如何使用AEM项目原型来创建最小的基于最佳实践的Adobe Experience Manager项目，作为您自己的AEM项目的起点。

它侧重于常规使用模式以及原型对您的作用。 有关详细的构建选项和技术说明，请参阅原型的GitHub存储库中的文档。

>[!TIP]
>
>最新的AEM项目原型和相关技术文档 [在GitHub上可找到。](https://github.com/adobe/aem-project-archetype)

## 快速入门 {#getting-started}

利用项目原型，可以轻松地在 AEM 上开始进行开发。您可以通过多种方式迈出使用原型的第一步。

* **WKND教程**  — 有关在AEM上进行开发的精彩介绍，包括如何利用原型，请参见 [AEM Sites快速入门 — WKND教程](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html) 举一个实际示例，向您介绍如何使用原型实施简单项目。
* **wknd事件教程**  — 如果您特别想知道如何在AEM上开发单页应用程序(SPA)，请务必查看一下专门的 [WKND事件教程。](https://helpx.adobe.com/cn/experience-manager/kt/sites/using/getting-started-spa-wknd-tutorial-develop.html)
* **你自己开始吧！**  — 您可轻松下载 [GitHub上可用的当前项目原型](https://github.com/adobe/aem-project-archetype) 并自行创建您的第一个项目。

## 如何使用原型 {#how-to-use-the-archetype}

使用原型的第一个步骤是创建一个项目，该项目会生成 [模块](#what-you-get) 在本地文件结构中。 作为项目生成的一部分，可以定义项目的许多属性，例如项目名称、版本、启用各种选项等。

>[!TIP]
>
>无论何时构建原型，它都会生成一系列自述文件，为您提供每个模块的技术细节和使用情况，如 [链接如下。](#what-you-get)

使用 Maven 构建项目会创建可部署到 AEM 的构件（包和 OSGi 捆绑包）。其他 Maven 命令和配置文件可用于将项目构件部署到 AEM 实例。

## 使用原型的好处 {#what-you-get}

原型由模块组成，所有模块均在使用原型时自动创建。

* **[核心](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/core)** 是一个Java捆绑包，它包含所有核心功能（如OSGi服务、侦听器和调度程序）以及与组件相关的Java代码（如servlet和请求过滤器）。
* **[it.tests](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/it.tests)** 是基于Java的集成测试。
* **[ui.apps](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.apps)** 包含 `/apps` 和 `/etc` 项目的各个部分，即JS和CSS clientlibs、组件和模板。
* **[ui.content](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.content)** 包含使用ui.apps模块中的组件的示例内容。
* **[ui.config](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.config)** 包含项目的运行模式特定的OSGi配置。
* **[ui.frontend.general](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.frontend.general)** 包含使用通用型基于Webpack的前端构建模块所需的构件（可选）。
* **[ui.frontend.react](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.frontend.react)** **（可选）** 包含使用原型创建基于React的SPA项目时所需的构件（可选，具体取决于构建参数）。
* **[ui.frontend.angular](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.frontend.angular)** **（可选）** 包含使用原型创建基于Angular的SPA项目时所需的构件（可选，取决于构建参数）。
* **[ui.tests](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.tests)** 包含基于Selenium的UI测试。
* **[所有](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/all)** 是一个内容包，它嵌入了所有编译的模块（捆绑包和内容包），其中包括任何供应商依赖项。
* **[dispatcher.ams](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/dispatcher.ams)** 包含AMS/内部部署项目的基本Dispatcher配置（可选，具体取决于构建参数）。
* **[dispatcher.cloud](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/dispatcher.cloud)** 包含AEMaaCS项目的基本Dispatcher配置（可选，具体取决于构建参数）。

![内容包组织](/help/assets/content-package-organization.png)

Maven中表示的原型的模块作为表示应用程序、内容和必要的OSGi捆绑包的内容包部署到AEM。

## 父级 POM {#parent-pom}

项目的根目录 (`<src-directory>/<project>/pom.xml`) 中的 `pom.xml` 被称为父级 POM，可驱动项目的结构并管理项目的依赖项和某些全局属性。

### 全局项目属性 {#global-properties}

父级 POM 的 `<properties>` 部分定义了在 AEM 实例上部署项目所必需的几个全局属性，例如用户名/密码、主机名/端口等。

这些属性设置为部署到本地 AEM 实例，因为这是开发人员最常进行的构建。请注意，有一些属性要部署到创作实例和发布实例。此外，也会在此处将凭据设置为使用 AEM 实例进行身份验证。默认 `admin:admin` 已使用凭据。

设置这些属性以便在部署到更高级别的环境时可以将其覆盖。这样一来，无需更改 POM 文件，并且可通过命令行参数覆盖 `aem.host` 和 `sling.password` 等变量：

```shell
mvn -PautoInstallPackage clean install -Daem.host=production.hostname -Dsling.password=productionpasswd
```

### 模块结构 {#module-structure}

父级 POM 的 `<modules>` 部分定义项目将构建的模块。默认情况下，项目会生成 [之前定义的标准模块。](#what-you-get) 随着项目的发展，始终可以添加更多模块。

### 依赖项 {#dependencies}

父级 POM 的 `<dependencyManagement>` 部分定义项目中使用的 API 的所有依赖项和版本。应在父POM中管理版本。 子模块不应包含任何版本信息。

#### Uber-Jar {#uber-jar}

关键依赖项之一是 [AEM Java API Jar。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-as-a-cloud-service-sdk.html) 这将包括所有AEM API，并且AEM版本只有一个依赖项。

>[!NOTE]
>
>作为最佳实践，您应更新 uber-jar 版本以匹配 AEM 的目标版本。例如，如果您计划部署到AEM 6.5，则应将uber-jar的版本更新为6.5.X，其中 `X` 是最新的service pack。

#### 核心组件 {#core-components}

当然，原型将利用 [核心组件。](/help/introduction.md) 因此，要在所有部署中利用核心组件，最佳实践是将它们作为Maven项目的一部分包含在内。

core.wcm.components.examples 是一组示例页面，用于说明核心组件的示例。作为最佳实践，在部署项目以供生产使用时，您应删除此依赖项和子包包含。

>[!NOTE]
>
>核心组件和原型作为单独的GitHub项目进行维护，因此它们的版本不同。
>
>原型的每个版本都将利用发布时最新版本的核心组件。 但是，您可能希望手动更新对核心组件的依赖关系。

## 测试 {#testing}

项目中包含三个级别的测试，由于这些测试的类型不同，因此它们会通过不同的方式或在不同的位置执行。

* **[单元测试](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/core)**  — 捆绑包中包含的代码的经典单元测试
* **[集成测试](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/it.tests)**  — 在AEM环境中(即AEM服务器上)运行单元测试的服务器端集成测试
* **[UI测试](https://github.com/adobe/aem-project-archetype/tree/develop/src/main/archetype/ui.tests)**  — 基于Selenium的浏览器端测试，用于验证浏览器端行为
