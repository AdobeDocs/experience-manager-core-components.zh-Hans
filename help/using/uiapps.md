---
title: ui.apps模块(AEM Project Archetype)
seo-title: ui.apps模块(AEM Project Archetype)
description: ui.apps模块(AEM Project Archetype)
seo-description: ui.apps模块(AEM Project Archetype)
contentOwner: 博纳特
content-type: 参考文件
topic-tags: 核心组件
translation-type: tm+mt
source-git-commit: 3c37b57eb72d1d662cdbd41ca54cdc592919203c

---


# ui.apps模块(AEM Project Archetype) {#uiapps-module}

ui.apps授权模块(`<src-directory>/<project>/ui.apps`)包括下方站点所需的所有渲染代码 `/apps`。 这包括将以称为clientlibs的AEM格式存储的CSS/JS。 这还包括用于呈现动态HTML的HTL脚本。 您可以将ui.apps模块看作JCR中结构的映射，但格式可以存储在文件系统上并提交到源控件。

Apache Jackrabbit fileVault包插件用于将ui.apps模块的内容编译为可部署到AEM的AEM包。 插件的全局配置在父pom.xml中定义。

## 父POM {#parent-pom}

[父POM](archetype.md#parent-pom) (`<src>/<project>/pom.xml`)包括 `<plugin>` 为项目中使用的插件定义各种配置的部分。 这包括Jackrabbit fileVault包插 `filterSource` 件的配置。 这 `filterSource` 些参数指向用于定 `filter.xml` 义包中包含的jcr路径的文件的位置。

除了Jackrabbit fileVault包插件外，还定义了内容包插件，用于将包推送到AEM中。 请注意， `aem.host`、 `aem.port`、 `vault.user`和的变量 `vault.password` 被使用，它们对应于在同一个父POM中定义的全局属性。

## ui.apps/pom.xml {#uiapps-pom}

ui.apps pom(`<src>/<project>/ui.apps/pom.xml`)为 `embedded` 提供标记 `filevault-package-maven-plugin`。 标 `embedded` 记包含编译后的核心包，它是ui.apps包的一部分，并将安装在其中。

请注意，core.wcm.components.all和core.wcm.components.examples包都作为子包包含在内。 这将每次部署核心组件包和WKND代码。

core.wcm.components.all和core.wcm.components.examples作为依赖关系包含在依赖关系列表中。 但是，作为最佳实践，此处忽略依赖项的版本，并在父pom文件中 [进行管理](archetype.md#core-components)。

## filter.xml {#filter}

ui. `filter.xml` apps模块的文件位于，并 `<src>/<project>/ui.apps/src/main/content/META-INF/vault/filter.xml` 包含将随ui.apps包一起包含和安装的路径。
