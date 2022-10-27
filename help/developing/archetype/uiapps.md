---
title: AEM 项目原型的 ui.apps 模块
description: AEM 项目原型的 ui.apps 模块
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: fc63a19a-3253-44ee-96e2-bb5544c2235b
source-git-commit: 19bceb1d8ba07c70798f2e7203db957d3e8b3d03
workflow-type: ht
source-wordcount: '0'
ht-degree: 100%

---

# AEM 项目原型的 ui.apps 模块 {#uiapps-module}

ui.apps maven 模块 (`<src-directory>/<project>/ui.apps`) 包含 `/apps` 下方的站点所需的所有渲染代码。这包括将以名为 [clientlibs 的 AEM 格式存储的 CSS/JS。](uifrontend.md#clientlibs) 这还包括用于渲染动态 HTML 的 HTL 脚本。您可以将 ui.apps 模块视为采用 JCR 的结构的映射，但可通过某种格式存储在文件系统上并提交给源代码控制。

Apache Jackrabbit FileVault 包插件用于将 ui.apps 模块的内容编译为可部署到 AEM 的 AEM 包。在父 pom.xml 中定义插件的全局配置。

## 父级 POM {#parent-pom}

[父级 POM](/help/developing/archetype/using.md#parent-pom) (`<src>/<project>/pom.xml`) 包含 `<plugin>` 部分，其中定义了项目中使用的插件的各种配置。这包括 Jackrabbit FileVault 包插件的 `filterSource` 的配置。`filterSource` 指向 `filter.xml` 文件的位置，该文件用于定义包中包含的 jcr 路径。

除了 Jackrabbit FileVault 包插件之外，还定义了内容包插件，此插件用于将包推送到 AEM。请注意，使用的 `aem.host`、`aem.port`、`vault.user` 和 `vault.password` 的变量对应于同一父级 POM 中定义的全局属性。

## ui.apps/pom.xml {#uiapps-pom}

请注意，core.wcm.components.all 和 core.wcm.components.examples 包作为子包包含在内。这将每次部署核心组件包和 WKND 代码。

core.wcm.components.all 和 core.wcm.components.examples 作为依赖项包含在依赖项列表中。但作为最佳实践，依赖项的版本在此处被忽略并在[父级 pom 文件](/help/developing/archetype/using.md#core-components)中进行管理。

## filter.xml {#filter}

ui.apps 模块的 `filter.xml` 文件位于 `<src>/<project>/ui.apps/src/main/content/META-INF/vault/filter.xml`，并包含将随 ui.apps 包一起包含和安装的路径。
