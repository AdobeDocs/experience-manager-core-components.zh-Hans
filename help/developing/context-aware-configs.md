---
title: Sling上下文感知配置和核心组件
description: 核心组件针对某些功能利用Sling上下文感知配置
role: Architect, Developer, Administrator
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 0%

---


# Sling上下文感知配置和核心组件{#sling-context-aware-configurations}

上下文感知配置是Sling](https://sling.apache.org/documentation/bundles/context-aware-configuration/context-aware-configuration.html)的[功能。 它们是与内容资源或资源树相关的配置，并由核心组件利用这些配置来允许站点范围的配置。

## Sling上下文感知配置{#context-aware-configurations}

您的站点可能需要不同站点区域的不同配置，例如某些参数可能共享，需要继承嵌套上下文和全局回退值。 AEM利用Sling上下文感知配置，可实现此功能。

有关AEM中配置的详细信息，请参阅配置和配置浏览器文档。](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/developing/configurations.html)[

## 在核心组件{#core-components}中使用

许多核心组件功能利用上下文感知配置。 所有此类配置都位于以下节点下：

* `/conf/<my-site>/sling:configs/<my-configuration>`

具体配置取决于特定组件或功能。 使用上下文感知配置的核心组件的功能有：

* [PDF查看器组件](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/pdfviewer/v1/pdfviewer#context-aware-config)
* [Adobe客户端数据层](/help/developing/data-layer/overview.md#installation-activation)
* [AMP支持](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)
