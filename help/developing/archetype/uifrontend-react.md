---
title: 针对SPA的前端构建
description: 基于React的SPA项目的前端构建流程描述
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a
workflow-type: tm+mt
source-wordcount: '512'
ht-degree: 0%

---


# React SPA的前端构建{#frontend-react}

本文档介绍了在使用原型创建基于React框架的单页应用程序(SPA)时创建的项目的详细信息。 例如，将`frontendModule`选项设置为`react`时。

## 概述 {#overview}

此项目由[create-react-app](https://github.com/facebook/create-react-app)引导。

此应用程序的构建目的是使用站点的AEM模型。 它将使用[@adobe/cq-react-editable-components](https://www.npmjs.com/package/@adobe/cq-react-editable-components)包中的帮助组件自动生成布局。

## 脚本 {#scripts}

在项目目录中，可以运行以下命令：

### npm开始{#npm-start}

```
npm start
```

此命令通过从运行于http://localhost:4502的本地AEM实例代理JSON模型，在开发模式下运行应用程序。 这假定整个项目已至少部署一次（`mvn clean install -PautoInstallPackage`在项目根目录中）。

在[ui.frontend](uifrontend.md)目录中运行`npm start`后，您的应用程序将自动在您的浏览器中打开（路径`http://localhost:3000/content/<appId>/<country>/<language>/home.html`）。 如果您进行编辑，页面将重新加载。

如果收到与CORS相关的错误，您可能需要按如下方式配置AEM::

1. 导航到Configuration Manager(http://localhost:4502/system/console/configMgr)
1. 打开“AdobeGranite跨来源资源共享策略”的配置
1. 使用以下附加值创建新配置：
   * 允许的来源:http://localhost:3000
   * 支持的标题：授权
   * 允许的方法：OPTIONS

### npm test {#npm-test}

```
npm test
```

此命令在交互式监视模式下启动测试运行器。 有关详细信息，请参阅[有关运行测试的React文档](https://facebook.github.io/create-react-app/docs/running-tests)。

### npm run build {#npm-run-build}

```
npm run build
```

此命令将生产应用程序构建到内部版本文件夹。 它捆绑在生产模式中的React并优化构建以获得最佳性能。 有关详细信息，请参阅[有关部署](https://facebook.github.io/create-react-app/docs/deployment)的React文档。

此外，使用[aem-clientlib-generator](https://github.com/wcm-io-frontend/aem-clientlib-generator)包从应用程序生成AEM ClientLib。

## 浏览器支持{#browser-support}

默认情况下，此项目使用[浏览器列表](https://github.com/browserslist/browserslist)的默认选项来标识目标浏览器。 此外，它还包含现代语言功能的填充功能，以支持旧版浏览器（例如Internet Explorer 11）。 如果不需要支持此类浏览器，则可以删除填充依赖关系和导入。

## 代码拆分{#code-splitting}

默认情况下，React应用程序配置为使用[代码拆分](https://webpack.js.org/guides/code-splitting)。 构建生产应用程序时，代码将以几个块输出：

```
$ ls build/static/js
2.5b77f553.chunk.js
2.5b77f553.chunk.js.map
main.cff1a559.chunk.js
main.cff1a559.chunk.js.map
runtime~main.a8a9905a.js
runtime~main.a8a9905a.js.map
```

仅在需要时加载区块可显着提高应用程序性能。

要使此功能与AEM配合使用，应用程序需要能够识别需要从AEM生成的HTML请求哪些JS和CSS文件。 这可以使用asset-manifest.json文件中的“entrypoints”键实现。 文件在clientlib.config.js中进行分析，只有entrypoint文件被绑定到ClientLib中。 其余文件将放在ClientLib的资源目录中，并将动态请求，因此仅在实际需要时加载。

有关项目原型如何使用AEM ClientLibs的更多信息，请参阅一般[ui.frontend模块文档](uifrontend.md#clientlibs)。
