---
title: AEM as a Cloud ServiceSDK Build Analyzer Maven插件
description: 有关本地Maven内部版本分析器插件的文档
feature: 核心组件、 AEM项目原型
role: Architect, Developer, Admin
exl-id: de26b310-a294-42d6-a0db-91f6036a328c
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '510'
ht-degree: 4%

---

# AEM as a Cloud ServiceSDK Build Analyzer Maven插件 {#maven-analyzer-plugin}

AEM as a Cloud ServiceSDK构建分析器Maven插件可分析各种内容包项目的结构。

有关如何将Maven插件包含在AEM Maven项目中的信息，请参阅[Maven插件文档](https://github.com/adobe/aemanalyser-maven-plugin/blob/main/aemanalyser-maven-plugin/README.md)。

>[!NOTE]
>
>建议您更新Maven项目，以引用Maven中央存储库中插件的最新版本，该版本位于：https://repo1.maven.org/maven2/com/adobe/aem/aemanalyser-maven-plugin/

该插件使用最新的可用SDK，而不是项目中配置的SDK。

下表描述了在此步骤中执行的分析程序。<!-- Note that some are executed in the local SDK, while others are only executed during the Cloud Manager pipeline deployment. -->

| 模块 | 函数、示例和疑难解答 | 本地SDK | Cloud Manager |
|---|---|---|---|
| `api-regions-exportsimports` | 检查所有OSGi包是否都有其Import-Package声明符合Maven项目中其他包含包的Export-package声明。 错误将如下所示： <p> </p> `[ERROR] org.acme:mybundle:0.0.1-SNAPSHOT: Bundle org.acme:mybundle:0.0.1-SNAPSHOT is importing package(s) org.acme.foo in start level 20 but no bundle is exporting these for that start level.`<p> </p>要进行故障诊断，请查看提供包的包是否包含在部署中，或者查看要导出的包清单，以确定使用的是错误名称还是错误版本。 | 是 | 是 |
| `requirements-capabilities` | 检查Maven项目中包含的其他包的功能声明是否满足OSGI包中的所有要求声明。 错误将如下所示： <p> </p> `[ERROR] org.acme:mybundle:0.0.1-SNAPSHOT: Artifact org.acme:mybundle:0.0.1-SNAPSHOT requires org.foo.bar in start level 20 but no artifact is providing a matching capability in this start level.`<p> </p> 要进行故障诊断，请查看预期声明功能以确定缺少该功能的包清单，或检查要求包的清单以查看其中的要求是否正确。 | 是 | 是 |
| `bundle-content` | 如果包中包含使用Sling-Initial-Content指定的初始内容，则会发出警告，在AEM作为Cloud Service群集环境中，这会出现问题。 警告如下所示： <p> </p> `[WARNING] org.acme:mybundle:0.0.1-SNAPSHOT: Found initial content : [/]` <p> </p>要对将初始内容转换为重新指向语句进行故障诊断，请参阅重新指向文档。 | 是 | 是 |
| `bundle-resources` | 如果包包含使用Sling-Bundle-Resources标头指定的资源，则会发出警告，该资源在AEM中作为Cloud Service群集环境存在问题。 警告如下所示：<p> </p> `[WARNING] org.acme:mybundle:0.0.1-SNAPSHOT: Found bundle resources : [/libs/sling/explorer!/resources/explorer]`<p> </p> 要对将资源转换为重新指向语句进行故障诊断，请参阅[重新指向文档](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html?lang=en#repo-init)。 | 是 | 是 |
| `api-regions`<p> </p>`api-regions-check-order`<p> </p>`api-regions-dependencies`<p> </p>`api-regions-duplicates` | 这些分析程序会检查与[内容包到特征模型转换过程](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html?lang=en#deploying)相关的一些详细信息，该过程会创建符合Sling特征模型的工件。 任何错误都应报告给Adobe客户支持。 | 是 | 是 |
| `api-regions-crossfeature-dups` | 验证客户OSGi包没有覆盖AEM作为Cloud Service公共API的导出包声明<p> </p>`[WARNING] org.acme:mybundle:0.0.1-SNAPSHOT: Package overlap found between region global and bundle org.acme:mybundle:0.0.1.SNAPSHOT which comes from feature: [org.acme:myproject.analyse:slingosgifeature:0.0.1-SNAPSHOT]. Both export package: com.day.util`<p> </p>要修复此问题，请停止导出AEM公共API中包含的包。 | 是 | 是 |
| `repoinit` | 检查所有重新指向部分的语法 | 是 | 是 |
| `bundle-nativecode` | 验证OSGI包是否未安装本机代码。 | 是 | 是 |
| `configuration-api` | 验证重要的OSGi配置。 <p> </p> `Configuration org.apache.felix.webconsole.internal.servlet.OsgiManager: Configuration is not allowed (com.mysite:mysite.all:1.0.0-SNAPSHOT\|com.mysite:mysite.ui.config:1.0.0-SNAPSHOT)` | 是 | 是 |
| `region-deprecated-api` | 检查是否使用了[已弃用的api](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/deprecated-apis.html) <p> </p>`[WARNING] com.mysite:mysite.core:1.0.0-SNAPSHOT: Usage of deprecated package found : org.apache.sling.settings : Avoid these features at runtime: run modes, file system access (com.mysite:mysite.all:1.0.0-SNAPSHOT)` | 是 | 是 |

