---
title: AEM 项目原型的 it.tests 模块
description: 如何使用 AEM 项目原型集成测试
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: 0abc0265-3a3f-4323-97e6-3af0c62299ef
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 100%

---

# AEM 项目原型的 it.tests 模块 {#ittests-module}

项目中包含三个级别的测试：

* [单元测试](core.md#unit-tests)
* 集成测试
* [UI 测试](uitests.md)

本文介绍了作为 it.tests 模块的一部分提供的集成测试。

## 运行集成测试 {#running-tests}

服务器端集成测试允许在 AEM 环境中（即 AEM 服务器上）运行单元测试等。要进行测试，请执行：

```
mvn clean verify -PintegrationTests
```
