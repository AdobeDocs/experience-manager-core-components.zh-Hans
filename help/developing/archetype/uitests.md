---
title: AEM项目原型的ui.test模块
description: 如何使用AEM项目原型UI测试
feature: 核心组件、 AEM项目原型
role: Architect, Developer, Admin
exl-id: eb3c9b34-f10e-410f-bcf3-34f94f124c7c
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 0%

---

# ui.tests AEM项目原型模块 {#uitests-module}

项目包含三个级别的测试：

* [单元测试](core.md#unit-tests)
* [集成测试](ittests.md)
* 用户界面测试

本文介绍了作为ui.tests模块一部分提供的UI测试。

## 运行UI测试 {#running-tests}

要进行测试，请执行：

```shell
mvn verify -Pui-tests-local-execution
```

执行后，`target/reports`文件夹中提供了报告和日志。

## 其他选项 {#additional-options}

UI测试可以使用多种不同的选项来运行，包括针对本地浏览器和作为Docker图像进行无头测试。 有关详细信息，请参阅ui.tests模块](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/ui.tests)的[README.md文件。
