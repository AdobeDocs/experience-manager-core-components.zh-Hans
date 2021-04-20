---
title: ui.apps Module of the AEM Project Archetype
description: ui.apps Module of the AEM Project Archetype
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Administrator
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 0%

---


# ui.apps Module of the AEM Project Archetype {#uiapps-module}

ui.apps授权模块(`<src-directory>/<project>/ui.apps`)包括`/apps`下站点所需的所有呈现代码。 这包括将以AEM格式（称为[clientlibs）存储的CSS/JS。](uifrontend.md#clientlibs) 这还包括用于渲染动态HTML的HTL脚本。您可以将ui.apps模块视为JCR中结构的映射，但格式可以存储在文件系统中并提交到源代码控制。

Apache Jackrabbit FileVault包插件用于将ui.apps模块的内容编译为可部署到AEM的AEM包。 插件的全局配置在父pom.xml中定义。

## 父POM {#parent-pom}

[父POM](/help/developing/archetype/using.md#parent-pom) ()`<src>/<project>/pom.xml`包括 `<plugin>` 为项目中使用的插件定义各种配置的部分。这包括Jackrabbit FileVault包插件的`filterSource`配置。 `filterSource`指向用于定义包中包含的jcr路径的`filter.xml`文件的位置。

除Jackrabbit FileVault包插件外，还有内容包插件的定义，用于将包推送到AEM。 请注意，使用`aem.host`、`aem.port`、`vault.user`和`vault.password`的变量与在同一父POM中定义的全局属性相对应。

## ui.apps/pom.xml {#uiapps-pom}

ui.apps pom(`<src>/<project>/ui.apps/pom.xml`)为`filevault-package-maven-plugin`提供`embedded`标记。 `embedded`标记包含编译后的核心包，作为ui.apps包的一部分，并将在其中安装它。

请注意，core.wcm.components.all和core.wcm.components.examples包作为子包包含在内。 这将每次部署核心组件包和WKND代码。

core.wcm.components.all和core.wcm.components.examples作为依赖关系包含在依赖关系列表中。 但是，作为最佳实践，此处会忽略依赖项的版本，并在[父pom文件](/help/developing/archetype/using.md#core-components)中进行管理。

## filter.xml {#filter}

ui.apps模块的`filter.xml`文件位于`<src>/<project>/ui.apps/src/main/content/META-INF/vault/filter.xml`，其中包含将随ui.apps包一起包含和安装的路径。
