---
title: AEM项目原型的ui.apps模块
description: AEM项目原型的ui.apps模块
translation-type: tm+mt
source-git-commit: 6f7166c46940ed451721e0760d565d58efe412ab
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 0%

---


# AEM项目原型的ui.apps模块 {#uiapps-module}

ui.apps授权模块()`<src-directory>/<project>/ui.apps`包括下方站点所需的所有渲染代码 `/apps`。 这包括将以称为clientlibs的AEM格式存储的CSS/JS。 这还包括用于呈现动态HTML的HTL脚本。 您可以将ui.apps模块视为JCR中结构的映射，但其格式可以存储在文件系统中并提交到源代码控制。

Apache Jackrabbit FileVault包插件用于将ui.apps模块的内容编译为可部署到AEM的AEM包。 插件的全局配置在父pom.xml中定义。

## 父POM {#parent-pom}

[父POM](/help/developing/archetype/using.md#parent-pom) (`<src>/<project>/pom.xml`)包括 `<plugin>` 为项目中使用的插件定义各种配置的部分。 这包括Jackrabbit FileVault包 `filterSource` 插件的配置。 指 `filterSource` 向用于定义包 `filter.xml` 中包含的jcr路径的文件的位置。

除Jackrabbit FileVault包插件外，还定义了内容包插件，用于将包推入AEM。 请注意， `aem.host`、 `aem.port`、 `vault.user`和的变 `vault.password` 量会与在同一父POM中定义的全局属性相对应。

## ui.apps/pom.xml {#uiapps-pom}

ui.apps pom()`<src>/<project>/ui.apps/pom.xml`提供 `embedded` 了标签 `filevault-package-maven-plugin`。 标 `embedded` 签包含作为ui.apps包的一部分的已编译核心包，以及安装它的位置。

请注意，core.wcm.components.all和core.wcm.components.examples包都作为子包包含在内。 这将每次部署核心组件包和WKND代码。

core.wcm.components.all和core.wcm.components.examples作为依赖关系包含在依赖关系列表中。 但是，作为最佳实践，此处忽略依赖项的版本，并在父pom文 [件中进行管理](/help/developing/archetype/using.md#core-components)。

## filter.xml {#filter}

ui. `filter.xml` apps模块的文件位于， `<src>/<project>/ui.apps/src/main/content/META-INF/vault/filter.xml` 其中包含随ui.apps包一起包含和安装的路径。
