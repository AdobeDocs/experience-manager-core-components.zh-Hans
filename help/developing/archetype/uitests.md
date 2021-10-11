---
title: AEM 项目原型的 ui.tests 模块
description: 如何使用 AEM 项目原型 UI 测试
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: eb3c9b34-f10e-410f-bcf3-34f94f124c7c
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: ht
source-wordcount: '112'
ht-degree: 100%

---

# AEM 项目原型的 ui.tests 模块 {#uitests-module}

项目中包含三个级别的测试：

* [单元测试](core.md#unit-tests)
* [集成测试](ittests.md)
* UI 测试

本文介绍了作为 ui.tests 模块的一部分提供的 UI 测试。

## 运行 UI 测试 {#running-tests}

要进行测试，请执行：

```shell
mvn verify -Pui-tests-local-execution
```

在执行之后，在 `target/reports` 文件夹中提供了报告和日志。

## 其他选项 {#additional-options}

可以使用许多不同的选项运行 UI 测试，包括对本地浏览器的无标题测试以及作为 Docker 镜像进行测试。有关更多信息，请参阅 [ui.tests 模块的 README.md](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype/ui.tests) 文件。
