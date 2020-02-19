---
title: 针对React SPA的前端构建
description: 基于React的SPA项目的前端构建流程说明
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

---


# 针对React SPA的前端构建 {#frontend-react}

本文档介绍了在使用原型创建基于React框架的单页应用程序(SPA)时创建的项目的详细信息。 即当您将选项设置为 `frontendModule` 时 `react`。

## 概述 {#overview}

此项目已通过创建 [-反应应用程序启动](https://github.com/facebook/create-react-app)。

此应用程序的构建目的是使用站点的AEM模型。 它将使用 [@adobe/cq-react-editable-components包中的帮助组件自动生成布局](https://www.npmjs.com/package/@adobe/cq-react-editable-components) 。

## 脚本 {#scripts}

在项目目录中，可以运行以下命令：

### npm开始 {#npm-start}

```
npm start
```

此命令通过从运行于http://localhost:4502的本地AEM实例代理JSON模型，在开发模式下运行应用程序。 这假定整个项目已至少部署一次到AEM(在项`mvn clean install -PautoInstallPackage` 目根目录中)。

在ui. `npm start` frontend目 [录中运行后](uifrontend.md) ，您的应用程序将自动在您的浏览器中打开(路径 `http://localhost:3000/content/<appId>/<country>/<language>/home.html`)。 如果进行编辑，页面将重新加载。

如果收到与CORS相关的错误，您可能希望按如下方式配置AEM:

1. 导航到配置管理器(http://localhost:4502/system/console/configMgr)
1. 打开“Adobe Granite跨源资源共享策略”的配置
1. 使用以下附加值创建新配置：
   * 允许的来源：http://localhost:3000
   * 支持的标题：授权
   * 允许的方法：选项

### npm测试 {#npm-test}

```
npm test
```

此命令在交互式观察模式下启动测试运行器。 有关详细 [信息，请参阅有关运行测试的](https://facebook.github.io/create-react-app/docs/running-tests) React文档。

### npm运行内部版本 {#npm-run-build}

```
npm run build
```

此命令将生产应用程序构建到内部版本文件夹。 它捆绑了在生产模式下进行React，并优化了构建以获得最佳性能。 有关详细 [信息，请参阅有关部署的](https://facebook.github.io/create-react-app/docs/deployment) React文档。

此外，使用aem-clientlib-generator包从应用程序 [生成AEM ClientLib](https://github.com/wcm-io-frontend/aem-clientlib-generator) 。

## 浏览器支持 {#browser-support}

默认情况下，此项目使用 [Browserslist](https://github.com/browserslist/browserslist)的默认选项来标识目标浏览器。 此外，它还包含现代语言功能的填充功能以支持旧版浏览器（例如Internet Explorer 11）。 如果不需要支持此类浏览器，则可以删除多填充依赖关系和导入。

## 代码拆分 {#code-splitting}

默认情况下，React应用程序配置为 [使用代码拆](https://webpack.js.org/guides/code-splitting) 分。 构建生产应用程序时，代码将以几个块输出：

```
$ ls build/static/js
2.5b77f553.chunk.js
2.5b77f553.chunk.js.map
main.cff1a559.chunk.js
main.cff1a559.chunk.js.map
runtime~main.a8a9905a.js
runtime~main.a8a9905a.js.map
```

只有在需要时加载区块才能显着提高应用程序性能。

要使此功能与AEM一起使用，应用程序需要能够识别需要从AEM生成的HTML请求哪些JS和CSS文件。 这可以使用asset-manifest.json文件中的“entrypoints”键来实现。 该文件在clientlib.config.js中进行分析，只有entrypoint文件绑定到ClientLib中。 其余文件将放在ClientLib的资源目录中，并将动态请求这些文件，因此仅在实际需要它们时加载。

有关项目原型 [如何使用AEM ClientLibs的更多信息](uifrontend.md#clientlibs) ，请参阅常规ui.frontend模块文档。
