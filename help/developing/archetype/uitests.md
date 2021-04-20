---
title: ui.tests Module of AEM Project Archetype
description: 如何使用AEM Project原型UI测试
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Administrator
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 0%

---


# ui.tests AEM项目原型{#uitests-module}的模块

项目中包含三个测试级别：

* [设备测试](core.md#unit-tests)
* [集成测试](ittests.md)
* UI测试

本文介绍作为ui.tests模块的一部分提供的UI测试。

## 运行UI测试{#running-tests}

要测试，请执行：

```shell
mvn verify -Pui-tests-local-execution
```

执行后，报告和日志可在`target/reports`文件夹中使用。

## 其他选项{#additional-options}

UI测试可以使用许多不同的选项运行，包括针对本地浏览器和作为Docker映像进行无外设测试。 有关详细信息，请参阅ui.tests module](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/ui.tests)的[README.md文件。
