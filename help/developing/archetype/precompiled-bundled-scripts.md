---
title: 预编译捆绑脚本
description: 了解如何通过OSGi包将组件脚本部署到Adobe Experience ManagerCloud Service。
source-git-commit: 56464decc8d6ae3cef68d62bfe459bceda0539ef
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 0%

---

# 预编译捆绑脚本

AEM as aCloud Service支持将[`ui.apps`](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html#code-packages-%2F-osgi-bundles)组件脚本部署为预编译的捆绑脚本。 这允许开发人员在构建时预编译其脚本，并将它们打包为OSGi包。

## 通过OSGi包部署预编译脚本的优势

将脚本部署为预编译的捆绑脚本具有以下好处：

+ 在生成时编译脚本允许开发人员在开发过程中尽早发现错误
+ 通过`Import-Package`和`Export-Package`包标头明确定义Java API脚本依赖项
+ 继承（通过`sling:resourceSuperType`）和委派给其他资源类型（例如，通过HTL的`data-sly-resource`块元素或通过`sling:include` JSP标记）可以通过包的元数据进行映射
+ 资源类型版本控制的实施方式与Java API类似

## 预编译和包导入

[`htl-maven-plugin`](https://sling.apache.org/components/htl-maven-plugin/index.html)可以验证HTL脚本的语法，但也可以将其用于将HTL脚本传输到Java类中。 然后，这些值会添加到您Maven项目的`generated-sources`文件夹中，并由`maven-compiler-plugin`选取。

可以添加[`bnd-maven-plugin`](https://github.com/bndtools/bnd/tree/master/maven/bnd-maven-plugin)以生成用于Java API导入的OSGi包元数据。

## 继承和委派

OSGi框架为定义[要求和功能](https://docs.osgi.org/specification/osgi.core/7.0.0/framework.module.html#framework.module.dependencies)提供了一种有效的方法，用于表示不同组件之间的合同。 这些量度通过元数据进行描述，并在运行时强制执行。 捆绑的脚本使用此机制来表示其继承关系(`sling:resourceSuperType`)以及委派（包括渲染过程中的其他资源类型）。

[scriptingbundle-maven-plugin](https://sling.apache.org/components/scriptingbundle-maven-plugin/bnd.html)项目中的`bnd`插件可用于提取与[`ui.apps`](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html#code-packages-%2F-osgi-bundles)内容包提供的脚本对应的要求和功能。

## AEM项目原型支持

从版本31开始，可以使用[AEM项目原型](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/developing/archetype/using.html)正确将AEM设置为Cloud Service项目，以使用预编译的捆绑脚本。 此外，AEM项目原型还将[AEM配置为Cloud ServiceSDK构建分析器Maven插件](/help/developing/archetype/build-analyzer-maven-plugin.md)，以验证Java包级别和脚本级别的依赖关系。
