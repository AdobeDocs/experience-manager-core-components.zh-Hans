---
title: Sling 上下文感知配置和核心组件
description: 核心组件为特定功能使用 Sling 上下文感知配置
role: Architect, Developer, Admin
exl-id: d35210f7-a65d-4768-ab9e-f12ec406da2d
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: ht
source-wordcount: '200'
ht-degree: 100%

---

# Sling 上下文感知配置和核心组件 {#sling-context-aware-configurations}

上下文感知配置是 [Sling 的功能](https://sling.apache.org/documentation/bundles/context-aware-configuration/context-aware-configuration.html)。这些是与内容资源或资源树相关的配置，由核心组件用于允许网站范围的配置。

## Sling 上下文感知配置 {#context-aware-configurations}

对于不同网站区域，您的网站可能需要不同的配置，例如，某些可能共享的参数需要集成嵌套上下文和全局回退值。AEM 利用 Sling 上下文感知配置实现了这种可能性。

有关 AEM 中配置的详细信息，[请参阅配置和配置浏览器文档](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/developing/configurations.html)。

## 在核心组件中使用 {#core-components}

多种核心组件功能利用上下文感知配置。所有此类配置位于以下节点下：

* `/conf/<my-site>/sling:configs/<my-configuration>`

单独的配置取决于特定组件或功能。使用上下文感知配置的核心组件的功能包括：

* [PDF 查看器组件](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/pdfviewer/v1/pdfviewer#context-aware-config)
* [Adobe Client Data Layer](/help/developing/data-layer/overview.md#installation-activation)
* [AMP 支持](https://github.com/adobe/aem-core-wcm-components/tree/master/extensions/amp)
