---
title: 预编译的捆绑脚本
description: 了解如何通过 OSGi 捆绑包将组件脚本部署到 Adobe Experience Manager Cloud Service。
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: 3edc388f-01b2-45cc-bd56-f22e5a5a8624
source-git-commit: 554be9539428cd75462a38fc45f1bece04baf066
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 100%

---


# 预编译的捆绑脚本 {#precompiled-bundled-scripts}

AEM as a Cloud Service 支持将 [`ui.apps`](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html?lang=zh-Hans#code-packages-%2F-osgi-bundles) 组件脚本部署为预编译的捆绑脚本。这使开发人员能够在构建时预编译脚本，并将这些脚本打包为 OSGi 捆绑包。

## 通过 OSGi 捆绑包部署预编译的脚本的优势 {#advantages}

将脚本部署为预编译的捆绑脚本有以下好处：

+ 在构建时编译脚本可让开发人员在开发过程的早期发现错误。
+ Java API 脚本依赖项通过 `Import-Package` 和 `Export-Package` 包头明确定义。
+ 对其他资源类型的继承（通过 `sling:resourceSuperType`）和委派（例如，通过 HTL 的 `data-sly-resource` 块元素或通过 `sling:include` JSP 标记）可通过包的元数据进行映射。
+ 可通过类似于 Java API 的方式强制执行资源类型版本控制。

## 预编译和包导入 {#precompilation}

[`htl-maven-plugin`](https://sling.apache.org/components/htl-maven-plugin/index.html) 可以验证 HTL 脚本的语法，也可用于将 HTL 脚本转换为 Java 类。然后将它们添加到 Maven 项目的 `generated-sources` 文件夹，并由 `maven-compiler-plugin` 提取。

可以添加 [`bnd-maven-plugin`](https://github.com/bndtools/bnd/tree/master/maven/bnd-maven-plugin) 来为 Java API 导入生成 OSGi 捆绑包的元数据。

## 继承和委派 {#inheritance-delegation}

OSGi 框架提供了一种强大的方式来定义[需求和功能](https://docs.osgi.org/specification/osgi.core/7.0.0/framework.module.html#framework.module.dependencies)，以表达不同组件之间的契约。它们通过元数据进行描述，并在运行时强制执行。捆绑脚本使用此机制来表达它们的继承关系 (`sling:resourceSuperType`) 以及委托（包括渲染过程中的其他资源类型）。

[scriptingbundle-maven-plugin](https://sling.apache.org/components/scriptingbundle-maven-plugin/bnd.html) 项目中的 `bnd` 插件可用于提取与 [`ui.apps` 所提供的脚本对应的需求和功能。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html?lang=zh-Hans#code-packages-%2F-osgi-bundles) 内容包

## AEM 项目原型支持 {#support}

从版本 31 开始，[AEM 项目原型](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/developing/archetype/using.html?lang=zh-Hans)可用于正确设置 AEM as a Cloud Service 项目，以使用预编译的捆绑脚本。

此外，AEM 项目原型将配置 [AEM as a Cloud Service SDK 构建分析器 Maven 插件](/help/developing/archetype/build-analyzer-maven-plugin.md)，以验证 Java 包级别以及脚本级别的依赖项。
