---
title: AEM Project Archetype的核心模块
seo-title: AEM Project Archetype的核心模块
description: AEM Project Archetype的核心模块
seo-description: AEM Project Archetype的核心模块
contentOwner: bohnert
content-type: reference
topic-tags: core-components
translation-type: tm+mt
source-git-commit: ca7a47d8ac91516659c115a3f27c09f0ee4b8b33

---


# AEM Project Archetype的核心模块 {#core-module}

核心主模块(`<src-directory>/<project>/core`)包括实现所需的所有Java代码。 该模块将打包所有Java代码并作为OSGi Bundle部署到AEM实例。

中定义的Maven Bundle插件负责将 `<src-directory>/<project>/core/pom.xml` Java代码编译为OSGi包，AEM的OSGi容器可以识别该包。 请注意，这是定义Sling模型位置的位置。

虽然在高级环境中需要独立于ui.apps模块部署核心包的情况很少，但直接部署核心包在本地开发／测试过程中很有用。 Maven Sling插件允许将核心捆绑包直接部署到AEM，以利用父POM中 `autoInstallBundle` 定义的配置 [文件](overview.md#parent-pom)。

```
mvn -PautoInstallBundle clean install
```

成功执行后，您应可以在上查看Bundles Console `http://<host>:<port>/system/console/bundles`。
