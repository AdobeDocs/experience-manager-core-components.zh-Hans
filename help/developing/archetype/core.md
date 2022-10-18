---
title: AEM 项目原型的核心模块
description: AEM 项目原型的核心模块
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: 49e80d8c-2b41-4c42-b45e-c2e3b4b16a59
source-git-commit: 531a7858dd26d32ef189c459c5e7035b6ae0b524
workflow-type: ht
source-wordcount: '182'
ht-degree: 100%

---

# AEM 项目原型的核心模块 {#core-module}

核心 maven 模块 (`<src-directory>/<project>/core`) 包含实施所需的所有 Java 代码。该模块将打包所有 Java 代码并将它作为 OSGi 捆绑包部署到 AEM 实例。

`<src-directory>/<project>/core/pom.xml` 中定义的 Maven 捆绑包插件负责将 Java 代码编译成可由 AEM 的 OSGi 容器识别的 OSGi 捆绑包。请注意，将在此位置定义 Sling 模型。

虽然在上层环境中很少需要独立于 ui.apps 模块部署核心捆绑包，但在本地开发/测试期间直接部署核心捆绑包会很有用。利用 Maven Sling 插件，可以将核心捆绑包直接部署到使用 `autoInstallBundle` 配置文件的 AEM 中，如[父 POM](/help/developing/archetype/using.md#parent-pom) 中所定义。

```shell
mvn -PautoInstallBundle clean install
```

在成功执行此操作后，您应能够在 `http://<host>:<port>/system/console/bundles` 上看到捆绑包控制台。

## 单元测试 {#unit-tests}

核心模块中的单元测试展示了捆绑包中包含的代码的经典单元测试。要进行测试，请执行：

```shell
mvn clean test
```
