---
title: ui.tests AEM Project Archetype模块
description: 如何使用AEM项目原型JUnit测试
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 0%

---


# ui.tests AEM Project Archetype {#uitests-module}的模块

项目包含三个级别的测试：

## 设备测试{#unit-tests}

[核心模块](core.md)中的单元测试显示了捆绑包中包含的代码的经典单元测试。 要进行测试，请执行：

```
mvn clean test
```

## 集成测试{#integration-tests}

服务器端集成测试允许在AEM环境(即AEM服务器)中运行类似单元的测试。 要进行测试，请执行：

```
mvn clean verify -PintegrationTests
```

## 客户端测试{#client-side-tests}

`client-side Hobbes.js`测试是基于JavaScript的浏览器端测试，用于验证浏览器端行为。

要进行测试，在浏览器中查看要测试的AEM页面时，打开左侧面板，在&#x200B;**开发者模式**&#x200B;中打开页面，然后切换至&#x200B;**测试**&#x200B;选项卡，找到生成的&#x200B;**MyName测试**&#x200B;并运行它们。
