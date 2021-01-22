---
title: AEM作为Cloud ServiceSDK构建Analyzer Maven插件
description: 本地Maven构建分析器插件的文档
translation-type: tm+mt
source-git-commit: 42a9dcd64ed8a9c70ec0f72dac50bf88111b703b
workflow-type: tm+mt
source-wordcount: '470'
ht-degree: 3%

---


# AEM作为Cloud ServiceSDK构建分析器主插件{#maven-analyzer-plugin}

AEM作为Cloud ServiceSDK构建分析器主插件，可分析各种内容包项目的结构。

有关如何将插件包含在AEM maven项目中的信息，请参阅[ Maven插件文档](https://github.com/adobe/aemanalyser-maven-plugin/blob/main/aemanalyser-maven-plugin/README.md)。

>[!NOTE]
>
>建议您更新Maven项目，以引用Maven中央存储库中的插件的最新版本，位于以下位置：https://repo1.maven.org/maven2/com/adobe/aem/aemanalyser-maven-plugin/

下表描述了作为此步骤一部分执行的分析器。<!-- Note that some are executed in the local SDK, while others are only executed during the Cloud Manager pipeline deployment. -->

| 模块 | 功能、示例和疑难解答 | 本地SDK | Cloud Manager |
|---|---|---|---|
| `api-regions-exportsimports` | 检查所有OSGI包是否都具有其Import-Package声明，该声明由Maven项目中其他包含包的Export-package声明所满足。 错误的外观如下： <p> </p> `[ERROR] org.acme:mybundle:0.0.1-SNAPSHOT: Bundle org.acme:mybundle:0.0.1-SNAPSHOT is importing package(s) org.acme.foo in start level 20 but no bundle is exporting these for that start level.`<p> </p>要进行疑难解答，请查看提供软件包的捆绑包是否包含在部署中，或者查看您希望导出的捆绑包清单以确定使用的是错误名称还是错误版本。 | 是 | 是 |
| `requirements-capabilities` | 检查在OSGI捆绑包中所做的所有要求声明是否由Maven项目中包含的其他捆绑包的功能声明来满足。 错误的外观如下： <p> </p> `[ERROR] org.acme:mybundle:0.0.1-SNAPSHOT: Artifact org.acme:mybundle:0.0.1-SNAPSHOT requires org.foo.bar in start level 20 but no artifact is providing a matching capability in this start level.`<p> </p> 要进行故障排除，请查看您希望声明的功能以确定缺少该包的原因的捆绑清单，或检查需要捆绑的清单以确认其中的要求正确。 | 是 | 是 |
| `bundle-content` | 如果捆绑包包含用Sling-Initial-Content指定的初始内容，则发出警告，在AEM中，这是作为Cloud Service群集环境的问题。 警告如下所示： <p> </p> `[WARNING] org.acme:mybundle:0.0.1-SNAPSHOT: Found initial content : [/]` <p> </p>要对将初始内容转换为重新指向语句进行疑难解答，请参阅重新指向文档。 | 是 | 是 |
| `bundle-resources` | 如果捆绑包包含用Sling-Bundle-Resources头指定的资源，则发出警告，在AEM中，这是作为Cloud Service群集环境的问题。 警告如下所示：<p> </p> `[WARNING] org.acme:mybundle:0.0.1-SNAPSHOT: Found bundle resources : [/libs/sling/explorer!/resources/explorer]`<p> </p> 要对将资源转换为重新指向语句进行疑难解答，请参阅[重新指向文档](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html?lang=en#repo-init)。 | 是 | 是 |
| `api-regions`<p> </p>`api-regions-check-order`<p> </p>`api-regions-dependencies`<p> </p>`api-regions-duplicates` | 这些分析器检查与特征模型转换过程[相关的一些细节，该过程会产生符合Sling特征模型的伪像。 ](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html?lang=en#deploying)任何错误都应报告给Adobe客户支持。 | 是 | 是 |
| `api-regions-crossfeature-dups` | 验证客户OSGI捆绑包没有覆盖AEM作为Cloud Service公共API的导出包声明<p> </p>`[WARNING] org.acme:mybundle:0.0.1-SNAPSHOT: Package overlap found between region global and bundle org.acme:mybundle:0.0.1.SNAPSHOT which comes from feature: [org.acme:myproject.analyse:slingosgifeature:0.0.1-SNAPSHOT]. Both export package: com.day.util`<p> </p>要修复问题，请停止导出属于AEM public API的包。 | 是 | 是 |
| `repoinit` | 检查所有重新指向节的语法 | 是 | 是 |
| `bundle-nativecode` | 验证OSGI包未安装本机代码。 | 是 | 是 |