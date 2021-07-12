---
title: AEM项目原型的核心模块
description: AEM项目原型的核心模块
feature: 核心组件、 AEM项目原型
role: Architect, Developer, Admin
exl-id: 49e80d8c-2b41-4c42-b45e-c2e3b4b16a59
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 0%

---

# AEM项目原型的核心模块 {#core-module}

核心Maven模块(`<src-directory>/<project>/core`)包含实施所需的所有Java代码。 该模块将打包所有Java代码并作为OSGi包部署到AEM实例。

`<src-directory>/<project>/core/pom.xml`中定义的Maven包插件负责将Java代码编译到可由AEM OSGi容器识别的OSGi包中。 请注意，这是定义Sling模型位置的位置。

尽管在上级环境中，核心包需要独立于ui.apps模块进行部署的情况很少，但直接部署核心包在本地开发/测试期间非常有用。 Maven Sling插件允许将核心包部署到AEM，以直接利用`autoInstallBundle`配置文件（如[父POM](/help/developing/archetype/using.md#parent-pom)中定义）。

```shell
mvn -PautoInstallBundle clean install
```

成功执行后，您应该能够在`http://<host>:<port>/system/console/bundles`中看到“包”控制台。

##  单元测试 {#unit-tests}

核心模块中的单元测试显示包中包含的代码的经典单元测试。 要进行测试，请执行：

```shell
mvn clean test
```
