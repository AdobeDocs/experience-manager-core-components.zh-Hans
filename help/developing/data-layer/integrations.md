---
title: 集成和Adobe客户端数据层
description: 了解Adobe客户端数据层如何与您的自定义组件集成，以及与Adobe Analytics和Adobe Target的集成如何帮助您深入了解您的网站
feature: 核心组件，Adobe客户端数据层
role: 架构师、开发人员、管理员
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 0%

---


# 与Adobe客户端数据层{#integrations}集成

Adobe客户端数据层通过提供一种标准化方法来公开和访问任何脚本的任何类型数据，从而减少了对网站进行仪表化的工作。

Adobe客户端数据层可与您的自定义组件集成，与Adobe Analytics和Adobe Target的集成可以帮助您获得对网站的洞察。

## 为自定义组件{#enabling-custom-components}启用数据层

要自动向数据层添加自定义组件，请执行以下操作：

1. 定义需要跟踪的自定义组件模型的属性。
1. 将`data-cmp-data-layer`属性添加到自定义组件HTL。 例如，`data-cmp-data-layer="${mycomponent.data.json}"`。

要使数据层在每次单击自定义组件的特定元素时自动触发`cmp:click`事件，请在自定义组件HTL中向要跟踪的元素添加`data-cmp-clickable`属性。

可以在客户端查询`data-cmp-data-layer-enabled`属性，以检查数据层是否已启用。

>[!TIP]
>
>有关将Adobe客户端数据层与核心组件集成以及如何在自定义组件上启用数据层的更多技术详细信息，请参阅核心组件存储库中的[`DATA_LAYER_INTEGRATION.md`](https://github.com/adobe/aem-core-wcm-components/blob/master/DATA_LAYER_INTEGRATION.md)文件。

## 与Adobe Analytics和Adobe Target集成{#analytics-target}

与Adobe Analytics和Adobe Target相配，Adobe客户端数据层成为获得数字体验洞察的强大而灵活的工具集的基础。 以下教程引导您完成示例集成。

### 使用Adobe Analytics {#collect-page-data}收集页面数据

了解如何将Adobe客户端数据层的内置功能与AEM核心组件结合使用，以在Adobe Experience Manager Sites中收集有关某个页面的数据。 Experience Platform Launch和Adobe Analytics扩展将用于创建规则以将页面数据发送到Adobe Analytics。

[视图此处的教程。](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/integrations/analytics/collect-data-analytics.html)

### 使用Adobe Analytics {#track-clicked-components}跟踪已点击的组件

将事件驱动型Adobe客户端数据层与AEM核心组件结合使用，跟踪Adobe Experience Manager站点上特定组件的单击情况。 了解如何在Experience Platform Launch中使用规则来监听点击事件、按组件过滤以及使用跟踪链接信标将数据发送到Adobe Analytics。

[视图此处的教程。](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/integrations/analytics/track-clicked-component.html)
