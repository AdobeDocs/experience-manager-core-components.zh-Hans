---
title: 适用于AngularSPA的前端内部版本
description: 基于Angular的SPA项目的前端构建流程描述
feature: 核心组件、 AEM项目原型
role: Architect, Developer, Administrator
exl-id: 5726e29d-081c-42bb-bf4e-2852043b21d6
source-git-commit: 8ff36ca143af9496f988b1ca65475497181def1d
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 0%

---

# angularSPA {#frontend-angular}的前端内部版本

本文档介绍了在使用原型基于Angular框架创建单页应用程序(SPA)时创建的项目的详细信息。 例如，将`frontendModule`选项设置为`angular`时。

## 概述 {#overview}

此项目已通过[AngularCLI](https://github.com/angular/angular-cli)引导。

此应用程序的构建目的是使用网站的AEM模型。 它将使用[@adobe/cq-angular-editable-components](https://www.npmjs.com/package/@adobe/cq-angular-editable-components)包中的帮助程序组件自动生成布局。

## 脚本 {#scripts}

在项目目录中，可以运行以下命令。

### npm开始{#npm-start}

```
npm start
```

此命令通过从运行于http://localhost:4502的本地AEM实例代理JSON模型，以开发模式运行应用程序。 这假定整个项目已至少部署到AEM一次（项目根目录中的`mvn clean install -PautoInstallPackage`）。

在ui.frontend目录中运行npm启动后，您的应用程序将在浏览器中自动打开(路径： http://localhost:4200/content/${appId}/${country}/${language}/home.html)。 如果进行编辑，页面将重新加载。

如果您收到与CORS相关的错误，您可能需要按如下方式配置AEM:

1. 导航到配置管理器(http://localhost:4502/system/console/configMgr)
1. 打开“AdobeGranite跨源资源共享策略”的配置
1. 使用以下其他值创建新配置：
   * 允许的源：http://localhost:4200
   * 支持的标头：授权
   * 允许的方法：OPTIONS

### npm测试{#npm-test}

```shell
npm test
```

此命令启动Karma测试运行程序。 有关更多信息，请参阅[Angular文档，以了解有关运行测试](https://angular.io/guide/testing)的信息。

### npm运行测试：debug {#npm-run-test-debug}

```shell
npm run test:debug
```

此命令在交互式监视模式下启动Karma测试运行器。

### npm运行内部版本{#npm-run-build}

```shell
npm run build
```

此命令将生产应用程序构建到内部版本文件夹。 它可以在生产模式下捆绑Angular，并优化内部版本以获得最佳性能。 有关更多信息，请参阅[部署](https://angular.io/guide/deployment)的Angular文档。

此外，还使用[aem-clientlib-generator](https://github.com/wcm-io-frontend/aem-clientlib-generator)包从应用程序生成AEM ClientLib。

有关项目原型如何使用AEM ClientLibs的更多信息，请参阅常规[ui.frontend模块文档](uifrontend.md#clientlibs)。

## 浏览器支持{#browser-support}

默认情况下，此项目使用[Browserslist](https://github.com/browserslist/browserslist)的默认选项来标识目标浏览器。 此外，它还包含现代语言功能的填充，以支持旧版浏览器（例如Internet Explorer 11）。 如果不需要支持此类浏览器，则可以删除多填充依赖项和导入。
