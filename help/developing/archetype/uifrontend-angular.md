---
title: Angular SPA 的前端构建
description: 对基于 Angular 的 SPA 项目的前端构建流程描述
feature: 核心组件，AEM 项目原型
role: Architect, Developer, Admin
exl-id: 5726e29d-081c-42bb-bf4e-2852043b21d6
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: ht
source-wordcount: '409'
ht-degree: 100%

---

# Angular SPA 的前端构建 {#frontend-angular}

此文档说明了使用原型创建基于 Angular 框架的单页应用程序 (SPA) 时，创建项目的详细信息。即在将 `frontendModule` 选项设置为 `angular` 时。

## 概述 {#overview}

此项目使用 [Angular CLI](https://github.com/angular/angular-cli) 引导。

构建此应用程序是为了使用网站的 AEM 模型。它会使用 [@adobe/cq-angular-editable-components](https://www.npmjs.com/package/@adobe/cq-angular-editable-components) 程序包的帮助程序组件自动生成布局。

## 脚本 {#scripts}

在项目目录中，可以运行以下命令。

### npm start {#npm-start}

```
npm start
```

此命令通过从在 http://localhost:4502 运行的本地 AEM 实例代理 JSON 模型，在开发模式下运行应用程序。这假定整个项目已至少部署到 AEM 一次（项目根中的 `mvn clean install -PautoInstallPackage`）。

在 ui.frontend 目录中运行 npm start 之后，应用程序将自动在浏览器中打开（位于路径 http://localhost:4200/content/${appId}/${country}/${language}/home.html）。如果进行编辑，页面将重新加载。

如果您收到了与 CORS 相关的错误，可能需要如下所示配置 AEM：

1. 导航到 Configuration Manager (http://localhost:4502/system/console/configMgr)
1. 打开“Adobe Granite 跨源资源共享策略”的配置
1. 使用以下其他值创建新配置：
   * 允许的源：http://localhost:4200
   * 支持的标头：Authorization
   * 允许的方法：OPTIONS

### npm test {#npm-test}

```shell
npm test
```

此命令启动 Karma 测试运行程序。有关更多信息，请参阅[有关运行测试的 Angular 文档](https://angular.io/guide/testing)。

### npm run test:debug {#npm-run-test-debug}

```shell
npm run test:debug
```

此命令在交互式观察模式下启动 Karma 测试运行程序。

### npm run build {#npm-run-build}

```shell
npm run build
```

此命令在构建文件夹中构建用于生产的应用程序。它在生产模式下捆绑 Angular，并优化构建以实现最佳性能。有关更多信息，请参阅[有关部署的 Angular 文档](https://angular.io/guide/deployment)。

此外，使用 [aem-clientlib-generator](https://github.com/wcm-io-frontend/aem-clientlib-generator) 程序包从应用程序生成了 AEM ClientLib。

有关项目原型如何使用 AEM ClientLibs 的更多信息，请参阅常规 [ui.frontend 模块文档](uifrontend.md#clientlibs)。

## 浏览器支持 {#browser-support}

默认情况下，此项目使用 [Browserslist](https://github.com/browserslist/browserslist) 的默认选项来标识目标浏览器。此外，它包括用于现代语言功能的 polyfill 以支持较早的浏览器（例如，Internet Explorer 11）。如果不需要支持这些浏览器，可以删除 polyfill 依赖关系和导入。
