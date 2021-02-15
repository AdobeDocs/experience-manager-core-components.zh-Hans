---
title: it.tests Module of AEM Project Archetype
description: 如何使用AEM项目原型集成测试
translation-type: tm+mt
source-git-commit: 9d737b31efc8c346775ea5296f7599295af07cf1
workflow-type: tm+mt
source-wordcount: '75'
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
