---
title: AEM 项目原型的 ui.content 模块
description: AEM 项目原型的 ui.content 模块
feature: 核心组件，AEM 项目原型
role: Architect, Developer, Admin
exl-id: af019cd8-c733-4b53-bb57-321dd9451178
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: ht
source-wordcount: '223'
ht-degree: 100%

---

# AEM 项目原型的 ui.content 模块 {#uicontent-module}

ui.content maven 模块 (`<src-directory>/<project>/ui.content`) 包含 `/content` 和 `/conf` 下的基准内容和配置。ui.content 编译到 AEM 包中的方式与 ui.apps 非常相似。主要不同在于，存储在 ui.content 中的节点可以直接在 AEM 实例上修改。这包括页面、DAM 资源和可编辑模板。ui.content 模块可用于存储干净实例的示例内容和/或创建一些要在源代码控制中管理的基准配置。

## filter.xml {#filter}

ui.content 模块的 `filter.xml` 文件位于 `<src>/<project>/ui.content/src/main/content/META-INF/vault/filter.xml`，并包含将随 ui.content 包一起包含和安装的路径。请注意，路径中添加了 `mode="merge"` 属性。这确保了使用代码部署来部署的配置不会自动覆盖已在 AEM 实例上直接创作的内容或配置。

## ui.content/pom.xml

ui.content 模块与 ui.apps 模块相似，使用的是 FileVault 包插件。但是，ui.content pom (`<src>/<project>/ui.content/pom.xml`) 包括名为 `acHandling` 的额外属性，该属性设置为 `merge_preserve`。包括此项是因为 ui.content 模块包括访问控制列表 (ACL)，这些权限确定谁能够编辑模板。要将这些 ACL 导入 AEM，需要 `acHandling` 属性。
