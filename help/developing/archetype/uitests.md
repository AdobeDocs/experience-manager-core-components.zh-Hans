---
title: ui.tests AEM Project Archetype模块
description: 如何使用AEM Project原型JUnit测试
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

---


# ui.tests AEM项目原型模块 {#uitests-module}

项目中包含三个级别的测试：

## 单元测试 {#unit-tests}

核心模块中的单元测 [试显示](core.md) ，包中包含的代码的经典单元测试。 要测试，请执行：

```
mvn clean test
```

## 集成测试 {#integration-tests}

服务器端集成测试允许在AEM环境（即AEM服务器）中运行类似单元的测试。 要测试，请执行：

```
mvn clean verify -PintegrationTests
```

## 客户端测试 {#client-side-tests}

这些 `client-side Hobbes.js` 测试是基于JavaScript的浏览器端测试，用于验证浏览器端行为。

要进行测试，在浏览器中查看要测试的AEM页面时，打开左侧面板以“ **Developer** ”模式打开页面，切换至“ **Tests** ”选项卡，找到生成的“ **MyName测试** ”并运行它们。
