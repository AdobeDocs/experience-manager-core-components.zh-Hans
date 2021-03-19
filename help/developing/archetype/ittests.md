---
title: it.tests Module of AEM Project Archetype
description: 如何使用AEM项目原型集成测试
feature: 核心组件、 AEM项目原型
role: 架构师、开发人员、管理员
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '83'
ht-degree: 0%

---


# it.tests AEM Project Archetype {#ittests-module}的模块

项目中包含三个测试级别：

* [设备测试](core.md#unit-tests)
* 集成测试
* [UI测试](uitests.md)

本文描述了it.tests模块中可用的集成测试。

## 运行集成测试{#running-tests}

服务器端集成测试允许在AEM-环境(即AEM服务器)中运行类似于单元的测试。 要测试，请执行：

```
mvn clean verify -PintegrationTests
```
