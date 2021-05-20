---
title: 集成和Adobe客户端数据层
description: 了解Adobe客户端数据层如何与您的自定义组件集成，以及与Adobe Analytics和Adobe Target的集成如何帮助您深入了解您的网站
feature: 核心组件，Adobe客户端数据层
role: Architect, Developer, Administrator
exl-id: 503dd3dc-fe95-4a17-83f5-1f0c1960993d
source-git-commit: 8ff36ca143af9496f988b1ca65475497181def1d
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 0%

---

# 与Adobe客户端数据层集成 {#integrations}

Adobe客户端数据层通过提供标准化方法来公开和访问任何脚本的任何类型的数据，从而减少了对网站进行测试的工作量。

Adobe客户端数据层可以与您的自定义组件集成，并且与Adobe Analytics和Adobe Target的集成可以帮助您深入了解您的网站。

## 为自定义组件启用数据层{#enabling-custom-components}

要自动将自定义组件添加到数据层，请执行以下操作：

1. 定义需要跟踪的自定义组件模型的属性。
1. 将`data-cmp-data-layer`属性添加到自定义组件HTL。 例如`data-cmp-data-layer="${mycomponent.data.json}"`。

要使数据层在每次单击自定义组件的特定元素时自动触发`cmp:click`事件，请将`data-cmp-clickable`属性添加到自定义组件HTL中要跟踪的元素。

可以在客户端查询`data-cmp-data-layer-enabled`属性，以检查数据层是否已启用。

>[!TIP]
>
>有关Adobe客户端数据层与核心组件集成以及如何在自定义组件上启用数据层的进一步技术详细信息，请参阅核心组件存储库中的[`DATA_LAYER_INTEGRATION.md`](https://github.com/adobe/aem-core-wcm-components/blob/master/DATA_LAYER_INTEGRATION.md)文件。

## 与Adobe Analytics和Adobe Target集成{#analytics-target}

与Adobe Analytics和Adobe Target相配合，Adobe客户端数据层成为一套非常强大且灵活的工具的基础，可用于洞察您的数字体验。 以下教程将指导您完成示例集成。

### 使用Adobe Analytics {#collect-page-data}收集页面数据

了解如何将Adobe客户端数据层的内置功能与AEM核心组件结合使用来收集有关Adobe Experience Manager Sites中某个页面的数据。 Experience Platform Launch和Adobe Analytics扩展将用于创建规则以将页面数据发送到Adobe Analytics。

[请在此处查看教程。](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/integrations/analytics/collect-data-analytics.html)

### 使用Adobe Analytics {#track-clicked-components}跟踪已单击的组件

将事件驱动的Adobe客户端数据层与AEM核心组件结合使用，跟踪Adobe Experience Manager网站上特定组件的单击情况。 了解如何在Experience Platform Launch中使用规则来监听点击事件、按组件进行过滤，以及通过跟踪链接信标将数据发送到Adobe Analytics。

[请在此处查看教程。](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/integrations/analytics/track-clicked-component.html)
