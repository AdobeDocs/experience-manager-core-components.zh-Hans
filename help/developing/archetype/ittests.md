---
title: it.tests AEM项目原型模块
description: 如何使用AEM项目原型集成测试
feature: 核心组件、 AEM项目原型
role: Architect, Developer, Administrator
exl-id: 0abc0265-3a3f-4323-97e6-3af0c62299ef
source-git-commit: 8ff36ca143af9496f988b1ca65475497181def1d
workflow-type: tm+mt
source-wordcount: '80'
ht-degree: 0%

---

# it.tests AEM项目原型{#ittests-module}的模块

项目包含三个级别的测试：

* [单元测试](core.md#unit-tests)
* 集成测试
* [用户界面测试](uitests.md)

本文介绍了it.tests模块中提供的集成测试。

## 运行集成测试{#running-tests}

服务器端集成测试允许在AEM环境(即AEM服务器)中运行类似单元的测试。 要进行测试，请执行：

```
mvn clean verify -PintegrationTests
```
