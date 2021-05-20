---
title: Sling上下文感知配置和核心组件
description: 核心组件针对某些功能利用Sling上下文感知配置
role: Architect, Developer, Administrator
exl-id: d35210f7-a65d-4768-ab9e-f12ec406da2d
source-git-commit: 8ff36ca143af9496f988b1ca65475497181def1d
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 0%

---

# Sling上下文感知配置和核心组件{#sling-context-aware-configurations}

上下文感知配置是Sling](https://sling.apache.org/documentation/bundles/context-aware-configuration/context-aware-configuration.html)的[功能。 它们是与内容资源或资源树相关的配置，核心组件利用这些配置来允许站点范围的配置。

## Sling上下文感知配置{#context-aware-configurations}

您的网站可能需要针对不同网站区域的不同配置，例如，某些参数可能会共享，需要继承嵌套上下文和全局回退值。 AEM利用Sling上下文感知配置，这种配置可启用这种可能性。

有关AEM中配置的详细信息，请参阅配置和配置浏览器文档。](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/developing/configurations.html)[

## 在核心组件{#core-components}中使用

许多核心组件功能都利用上下文感知配置。 所有此类配置都位于以下节点下：

* `/conf/<my-site>/sling:configs/<my-configuration>`

单个配置取决于特定组件或功能。 使用上下文感知配置的核心组件的功能包括：

* [PDF查看器组件](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/pdfviewer/v1/pdfviewer#context-aware-config)
* [Adobe客户端数据层](/help/developing/data-layer/overview.md#installation-activation)
* [AMP支持](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)
