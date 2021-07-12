---
title: AEM项目原型的ui.apps模块
description: AEM项目原型的ui.apps模块
feature: 核心组件、 AEM项目原型
role: Architect, Developer, Admin
exl-id: fc63a19a-3253-44ee-96e2-bb5544c2235b
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 0%

---

# AEM项目原型的ui.apps模块 {#uiapps-module}

ui.apps maven模块(`<src-directory>/<project>/ui.apps`)包含`/apps`下站点所需的所有渲染代码。 这包括将以名为[clientlibs的AEM格式存储的CSS/JS。](uifrontend.md#clientlibs) 这还包括用于渲染动态HTML的HTL脚本。您可以将ui.apps模块视为JCR中结构的映射，但其格式可以存储在文件系统中并提交到源代码控制。

Apache Jackrabbit FileVault包插件用于将ui.apps模块的内容编译到可部署到AEM的AEM包中。 插件的全局配置在父pom.xml中定义。

## 父POM {#parent-pom}

[父POM](/help/developing/archetype/using.md#parent-pom) (`<src>/<project>/pom.xml`)包括为 `<plugin>` 项目中使用的插件定义各种配置的部分。这包括Jackrabbit FileVault包插件的`filterSource`配置。 `filterSource`指向`filter.xml`文件的位置，该文件用于定义包中包含的jcr路径。

除了Jackrabbit FileVault包插件之外，还是内容包插件的定义，用于随后将包推送到AEM。 请注意，使用的变量包括`aem.host`、`aem.port`、`vault.user`和`vault.password`，这些变量与同一父POM中定义的全局属性相对应。

## ui.apps/pom.xml {#uiapps-pom}

ui.apps pom(`<src>/<project>/ui.apps/pom.xml`)为`filevault-package-maven-plugin`提供`embedded`标记。 `embedded`标记包含编译的核心包，该核心包将作为ui.apps包的一部分，并且将在其中安装。

请注意，core.wcm.components.all和core.wcm.components.examples包作为子包包含在内。 这样每次都会部署核心组件包和WKND代码。

core.wcm.components.all和core.wcm.components.examples作为依赖项列表中的依赖项包含在内。 但是，作为最佳实践，此处忽略了依赖项的版本，并在[父pom文件](/help/developing/archetype/using.md#core-components)中进行管理。

## filter.xml {#filter}

ui.apps模块的`filter.xml`文件位于`<src>/<project>/ui.apps/src/main/content/META-INF/vault/filter.xml`，其中包含将随ui.apps包一起包含和安装的路径。
