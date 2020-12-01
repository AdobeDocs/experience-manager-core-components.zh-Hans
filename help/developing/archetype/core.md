---
title: AEM项目原型的核心模块
description: AEM项目原型的核心模块
translation-type: tm+mt
source-git-commit: 6f7166c46940ed451721e0760d565d58efe412ab
workflow-type: tm+mt
source-wordcount: '159'
ht-degree: 0%

---


# AEM项目原型{#core-module}的核心模块

核心主模块(`<src-directory>/<project>/core`)包括实现所需的所有Java代码。 该模块将打包所有Java代码并作为OSGi Bundle部署到AEM实例。

`<src-directory>/<project>/core/pom.xml`中定义的Maven Bundle插件负责将Java代码编译为可由AEM OSGi容器识别的OSGi包。 请注意，这是定义Sling模型位置的位置。

虽然在高级环境中需要独立于ui.apps模块部署核心捆绑包的情况很少，但直接部署核心捆绑包在本地开发／测试过程中很有用。 Maven Sling插件允许将核心包直接部署到AEM，以利用[父POM](/help/developing/archetype/using.md#parent-pom)中定义的`autoInstallBundle`用户档案。

```
mvn -PautoInstallBundle clean install
```

成功执行后，您应能在`http://<host>:<port>/system/console/bundles`看到Bundles控制台。
