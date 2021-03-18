---
title: AEM项目原型的核心模块
description: AEM项目原型的核心模块
feature: 核心组件、 AEM项目原型
role: 架构师、开发人员、管理员
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 0%

---


# AEM项目原型{#core-module}的核心模块

核心主模块(`<src-directory>/<project>/core`)包括实现所需的所有Java代码。 该模块将打包所有Java代码并作为OSGi Bundle部署到AEM实例。

`<src-directory>/<project>/core/pom.xml`中定义的Maven Bundle插件负责将Java代码编译为可由AEM OSGi容器识别的OSGi包。 请注意，这是定义Sling模型位置的位置。

虽然核心捆绑包需要独立于高级环境中的ui.apps模块进行部署的情况很少，但直接部署核心捆绑包在本地开发/测试过程中非常有用。 Maven Sling插件允许将核心包直接部署到AEM，以利用[父POM](/help/developing/archetype/using.md#parent-pom)中定义的`autoInstallBundle`用户档案。

```shell
mvn -PautoInstallBundle clean install
```

成功执行后，您应能在`http://<host>:<port>/system/console/bundles`看到Bundles控制台。

##  设备测试{#unit-tests}

核心模块中的单元测试将展示捆绑包中包含的代码的经典单元测试。 要测试，请执行：

```shell
mvn clean test
```
