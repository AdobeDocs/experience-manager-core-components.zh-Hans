---
title: React SPA 的前端构建
description: 对基于 React 的 SPA 项目的前端构建流程的描述
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: dd8ef13a-9686-47a9-b6af-e486ff10c4d8
source-git-commit: 0eea0cd65063c739e5b405b0380b73962a858e48
workflow-type: tm+mt
source-wordcount: '512'
ht-degree: 100%

---

# React SPA 的前端构建 {#frontend-react}

此文档说明了使用原型创建基于 React 框架的单页面应用程序 (SPA) 时，创建项目的详细信息。即在将 `frontendModule` 选项设置为 `react` 时。

## 概述 {#overview}

使用 [create-react-app](https://github.com/facebook/create-react-app) 引导此项目。

构建此应用程序是为了使用网站的 AEM 模型。它会使用 [@adobe/cq-react-editable-components](https://www.npmjs.com/package/@adobe/aem-react-editable-components) 程序包的帮助程序组件自动生成布局。

## 脚本 {#scripts}

在项目目录中，可以运行以下命令：

### npm start {#npm-start}

```shell
npm start
```

此命令通过从在 http://localhost:4502 运行的本地 AEM 实例代理 JSON 模型，在开发模式下运行应用程序。这假定整个项目已至少部署到 AEM 一次（项目根中的 `mvn clean install -PautoInstallPackage`）。

在 [ui.frontend](uifrontend.md) 目录中运行 `npm start` 之后，应用程序将自动在浏览器中打开（位于路径 `http://localhost:3000/content/<appId>/<country>/<language>/home.html`）。如果进行编辑，页面将重新加载。

如果您收到了与 CORS 相关的错误，可能需要如下所示配置 AEM：

1. 导航到 Configuration Manager (http://localhost:4502/system/console/configMgr)
1. 打开“Adobe Granite 跨源资源共享策略”的配置
1. 使用以下其他值创建新配置：
   * 允许的源：http://localhost:3000
   * 支持的标头：Authorization
   * 允许的方法：OPTIONS

### npm test {#npm-test}

```shell
npm test
```

此命令在交互式观察模式下启动测试运行程序。有关更多信息，请参阅[有关运行测试的 React 文档](https://facebook.github.io/create-react-app/docs/running-tests)。

### npm run build {#npm-run-build}

```shell
npm run build
```

此命令在构建文件夹中构建用于生产的应用程序。它在生产模式下捆绑 React，并优化构建以实现最佳性能。有关更多信息，请参阅[有关部署的 React 文档](https://facebook.github.io/create-react-app/docs/deployment)。

此外，使用 [aem-clientlib-generator](https://github.com/wcm-io-frontend/aem-clientlib-generator) 程序包从应用程序生成了 AEM ClientLib。

## 浏览器支持 {#browser-support}

默认情况下，此项目使用 [Browserslist](https://github.com/browserslist/browserslist) 的默认选项来标识目标浏览器。此外，它包括用于现代语言功能的 polyfill 以支持较早的浏览器（例如，Internet Explorer 11）。如果不需要支持这些浏览器，可以删除 polyfill 依赖关系和导入。

## 代码拆分 {#code-splitting}

React 应用程序配置为默认使用[代码拆分](https://webpack.js.org/guides/code-splitting)。在为生产构建应用程序时，代码将输出为多个块：

```shell
$ ls build/static/js
2.5b77f553.chunk.js
2.5b77f553.chunk.js.map
main.cff1a559.chunk.js
main.cff1a559.chunk.js.map
runtime~main.a8a9905a.js
runtime~main.a8a9905a.js.map
```

只有在需要时才加载块可以显著提升应用程序性能。

要使此功能可用于 AEM，应用程序需要能够识别应该从 AEM 生成的 HTML 请求哪些 JS 和 CSS 文件。在 asset-manifest.json 文件中使用“entrypoints”键可以做到这一点。此文件在 clientlib.config.js 中解析，只有 entrypoint 文件捆绑到 ClientLib。剩余的文件在 ClientLib 资源目录中替换并且动态请求，因此仅在实际需要这些文件时才加载。

有关项目原型如何使用 AEM ClientLibs 的更多信息，请参阅常规 [ui.frontend 模块文档](uifrontend.md#clientlibs)。
