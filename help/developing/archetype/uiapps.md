---
title: aem Project Archetype的ui.apps模块
description: aem Project Archetype的ui.apps模块
translation-type: tm+mt
source-git-commit: a427c2ade8cca69de8e2b59fc3afb4405342909c
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 0%

---


# aem Project Archetype {#uiapps-module}的ui.apps模块

ui.apps授权模块(`<src-directory>/<project>/ui.apps`)包括`/apps`下的站点所需的所有呈现代码。 这包括将以AEM格式存储的CSS/JS，该格式名为[clientlibs。](uifrontend.md#clientlibs) 这还包括用于呈现动态HTML的HTL脚本。您可以将ui.apps模块视为JCR中结构的映射，但其格式可以存储在文件系统中并提交到源代码控制。

Apache Jackrabbit FileVault包插件用于将ui.apps模块的内容编译为可部署到AEM的AEM包。 插件的全局配置在父pom.xml中定义。

## 父POM {#parent-pom}

[父POM](/help/developing/archetype/using.md#parent-pom) (`<src>/<project>/pom.xml`)包 `<plugin>` 括定义项目中使用的插件的各种配置的部分。这包括Jackrabbit FileVault包插件的`filterSource`配置。 `filterSource`指向用于定义包中包含的jcr路径的`filter.xml`文件的位置。

除Jackrabbit FileVault包插件外，还定义了内容包插件，用于将包推入AEM。 请注意，`aem.host`、`aem.port`、`vault.user`和`vault.password`的变量与在同一父POM中定义的全局属性相对应。

## ui.apps/pom.xml {#uiapps-pom}

ui.apps pom(`<src>/<project>/ui.apps/pom.xml`)提供`filevault-package-maven-plugin`的`embedded`标记。 `embedded`标记包含编译后的核心包，它是ui.apps包的一部分，将安装在其中。

请注意，core.wcm.components.all和core.wcm.components.examples包都作为子包包含在内。 这将每次部署核心组件包和WKND代码。

core.wcm.components.all和core.wcm.components.examples作为依赖关系包含在依赖关系列表中。 但是，作为最佳实践，此处忽略依赖项的版本，并在[父pom文件](/help/developing/archetype/using.md#core-components)中进行管理。

## filter.xml {#filter}

ui.apps模块的`filter.xml`文件位于`<src>/<project>/ui.apps/src/main/content/META-INF/vault/filter.xml`，其中包含随ui.apps包一起包含和安装的路径。
