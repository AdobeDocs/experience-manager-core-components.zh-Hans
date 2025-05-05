---
title: AEM as a Cloud Service SDK 构建分析器 Maven 插件
description: 本地 Maven 构建分析器插件文档
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: de26b310-a294-42d6-a0db-91f6036a328c
source-git-commit: eafbe18b13830edde3535fbb67d9ef62b7d045f3
workflow-type: ht
source-wordcount: '656'
ht-degree: 100%

---

# AEM as a Cloud Service SDK 构建分析器 Maven 插件 {#maven-analyzer-plugin}

AEM as a Cloud Service SDK 构建分析器 Maven 插件分析各种内容包项目的结构。

有关如何将其包括在 AEM maven 项目中的信息，请参阅 [Maven 插件文档](https://github.com/adobe/aemanalyser-maven-plugin/blob/main/aemanalyser-maven-plugin/README.md)。

>[!NOTE]
>
>建议您更新 Maven 项目，以在以下位置引用 [Maven 中央存储库](https://repo1.maven.org/maven2/com/adobe/aem/aemanalyser-maven-plugin/)中该插件的最新版本。

该插件使用最新可用的 SDK 而不是在项目中配置的 SDK。

下表描述了在此步骤中执行的分析器。<!-- Note that some are executed in the local SDK, while others are only executed during the Cloud Manager pipeline deployment. -->

| 模块 | 函数、示例和疑难解答 | 本地 SDK | Cloud Manager |
|---|---|---|---|
| `api-regions-exportsimports` | 检查所有 OSGi 捆绑的 Import-Package 声明，是否由 Maven 项目中包含的其他捆绑的 Export-package 声明满足。错误可能类似下面这样： <p> </p> `[ERROR] org.acme:mybundle:0.0.1-SNAPSHOT: Bundle org.acme:mybundle:0.0.1-SNAPSHOT is importing package(s) org.acme.foo in start level 20 but no bundle is exporting these for that start level.`<p> </p>要排除问题，请查看提供包的捆绑是否包括在部署中，或者查看您预期导出的捆绑的清单，以确定使用的名称或版本是否有错。 | 是 | 是 |
| `bundle-unversioned-packages` | 检查 OSGi 捆绑包是否指定了带有导出包声明的版本和带有导入包声明的版本范围。错误可能类似下面这样： <p> </p> `[ERROR] org.acme:mybundle:0.0.1-SNAPSHOT: Bundle org.acme:mybundle:0.0.1-SNAPSHOT is exporting package org.acme.foo without a version.`<p> </p>要进行故障排除，请确保在该程序包中添加 `package-info.java`，指定要导出的版本。 | 是 | 是 |
| `requirements-capabilities` | 检查 OSGi 捆绑提出的所有要求声明，是否由 Maven 项目中包含的其他捆绑的功能声明满足。错误可能类似下面这样： <p> </p> `[ERROR] org.acme:mybundle:0.0.1-SNAPSHOT: Artifact org.acme:mybundle:0.0.1-SNAPSHOT requires org.foo.bar in start level 20 but no artifact is providing a matching capability in this start level.`<p> </p> 要排除问题，请查看您预期会声明功能的捆绑的清单，以确定捆绑为什么缺失，或者检查所需捆绑的清单，以查看其中的要求是否正确。 | 是 | 是 |
| `bundle-resources` | 如果某个捆绑包含使用 Sling-Bundle-Resources 标头指定的资源，而这些资源在 AEM as a Cloud Service 集群环境中有问题，则会提出警告。警告可能类似下面这样：<p> </p> `[WARNING] org.acme:mybundle:0.0.1-SNAPSHOT: Found bundle resources : [/libs/sling/explorer!/resources/explorer]`<p> </p> 要排除问题，请参阅 [Repoinit 文档](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html?lang=zh-hans#repo-init)将资源转化为 repoinit 语句。 | 是 | 是 |
| `api-regions`<p> </p>`api-regions-check-order`<p> </p>`api-regions-dependencies`<p> </p>`api-regions-duplicates` | 这些分析器检查与[内容包向功能模型转换流程](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html?lang=zh-hans#deploying)相关的一些详细信息，这些流程会创建遵守 Sling 功能模型的构件。任何错误都应报告给 Adobe 客户支持。 | 是 | 是 |
| `api-regions-crossfeature-dups` | 验证客户的 OSGi 捆绑没有会覆盖 AEM as a Cloud Service 的公共 API 的 Export-package 声明<p> </p>`[WARNING] org.acme:mybundle:0.0.1-SNAPSHOT: Package overlap found between region global and bundle org.acme:mybundle:0.0.1.SNAPSHOT which comes from feature: [org.acme:myproject.analyse:slingosgifeature:0.0.1-SNAPSHOT]. Both export package: com.day.util`<p> </p>要修复，请停止导出属于 AEM 公共 API 的包。 | 是 | 是 |
| `repoinit` | 检查所有 repoinit 部分的语法 | 是 | 是 |
| `bundle-nativecode` | 确保 OSGi 捆绑没有安装原生代码。 | 是 | 是 |
| `configuration-api` | 验证重要 OSGi 配置。 <p> </p> `Configuration org.apache.felix.webconsole.internal.servlet.OsgiManager: Configuration is not allowed (com.mysite:mysite.all:1.0.0-SNAPSHOT\|com.mysite:mysite.ui.config:1.0.0-SNAPSHOT)` | 是 | 是 |
| `region-deprecated-api` | 检查是否使用了[已弃用的 api](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/deprecated-apis.html?lang=zh-hans) <p> </p>`[WARNING] com.mysite:mysite.core:1.0.0-SNAPSHOT: Usage of deprecated package found : org.apache.sling.settings : Avoid these features at runtime: run modes, file system access (com.mysite:mysite.all:1.0.0-SNAPSHOT)` | 是 | 是 |
| `artifact-rules` | 验证包和内容包等依赖项以防止构件中出现已知问题。<p> </p>`[WARNING] [artifact-rules] com.adobe.acs:acs-aem-commons-bundle:5.0.4: Use at least version 5.0.10 (com.mysite:mysite.all:1.0.0-SNAPSHOT)` | 是 | 是 |
| `aem-env-var` | 根据[变量命名指南](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/configuring-osgi.html?lang=zh-Hans#variable-naming)检查环境变量。<p> </p>`[ERROR] Configuration org.apache.felix.webconsole.internal.servlet.OsgiManager: Value for property 'port' must not use env vars prefixed with INTERNAL_ or ADOBE_ (com.mysite1:my-site-1.all:1.0.0-SNAPSHOT\|com.mysite1:my-site-1.ui.config:1.0.0-SNAPSHOT)` | 是 | 是 |
| `content-package-validation` | 运行 FileVault 验证器。默认情况下，启用了 jackrabbit docviewparser，用于检查将在部署期间安装的包中 xml 的结构良好的内容语法。<p> </p>`[main] WARN org.apache.sling.feature.analyser.task.impl.CheckContentPackages - ValidationViolation: "jackrabbit-docviewparser: Invalid XML found: The reference to entity "se" must end with the ';' delimiter.", filePath=jcr_root/apps/somename/configs/com.adobe.test.Invalid.xml, nodePath=/apps/somename/configs/com.adobe.test.Invalid`<p> </p>要修复此问题，请查看分析器命名的文件以了解 xml 问题。 | 是 | 是 |
| `aem-provider-type` | 检查应用程序代码是否实现或扩展了 AEM（产品）的“ProviderType”接口/类，请参阅 [CQBP-84](https://experienceleague.adobe.com/docs/experience-manager-cloud-manager/using/how-to-use/custom-code-quality-rules.html?lang=zh-hans#product-apis-annotated-with-providertype-should-not-be-implemented-or-extended-by-customers) | 是 | 是 |
| `configurations-basic` | 检查 OSGi 配置是否存在常见错误，例如未为“service.ranking”属性指定正确的类型。 | 是 | 是 |

{style="table-layout:auto"}

## 已知问题

以下是使用构建分析器 Maven 插件时出现的已知问题的列表。

### 无法在本地 SDK 中执行构建分析器 Maven 插件

在将本地 SDK 与低于 `1.1.2` 的构建分析器 Maven 插件结合使用时，运行该插件可能会导致以下错误。在此情况下，请将您的项目更新到该插件的最新版本。

```txt
[ERROR] Failed to execute goal com.adobe.aem:aemanalyser-maven-plugin:1.1.0:analyse (default-analyse) on project mysite.analyse: Execution default-analyse of goal com.adobe.aem:aemanalyser-maven-plugin:1.1.0:analyse failed: arraycopy: source index -1 out of bounds for char[65536] -> [Help 1]
```

如果您已使用 AEM 项目原型设置项目，请确保调整根 Maven `pom.xml` 中的属性，如下所示。

```xml
   ...
   <properties>
      ...
      <aemanalyser.version>1.1.2</aemanalyser.version> <!-- Make sure to use the latest release -->
      ...
   </properties>
```
