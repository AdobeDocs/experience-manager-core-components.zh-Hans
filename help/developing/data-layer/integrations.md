---
title: 集成和Adobe客户端数据层
description: 了解Adobe客户端数据层如何与您的自定义组件集成，以及与Adobe Analytics和Adobe Target的集成如何帮助您深入了解您的网站
translation-type: tm+mt
source-git-commit: ea7a0e08ea1b769b400fce275c8ce7e0db6f9407
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 0%

---


# 与Adobe客户端数据层集成 {#integrations}

Adobe客户端数据层通过提供一种标准化方法来公开和访问任何脚本的任何类型数据，从而减少了对网站进行测试的工作量。

Adobe客户端数据层可以与您的自定义组件集成，与Adobe Analytics和Adobe Target的集成可以帮助您深入了解您的网站。

## 为自定义组件启用数据层 {#enabling-custom-components}

自动向数据层添加自定义组件：

1. 定义需要跟踪的自定义组件模型的属性。
1. 将属性 `data-cmp-data-layer` 添加到自定义组件HTL。 例如， `data-cmp-data-layer="${mycomponent.data.json}"`.

要在每次单击自定义组件的 `cmp:click` 特定元素时自动使事件层触发，请在自定义组件HTL `data-cmp-clickable` 中为要跟踪的元素添加属性。

可 `data-cmp-data-layer-enabled` 以在客户端查询属性以检查数据层是否已启用。

>[!TIP]
>
>有关Adobe客户端数据层与核心组件集成以及如何在自定义组件上启用数据层的更多详细信息，请参 [`DATA_LAYER_INTEGRATION.md`](https://github.com/adobe/aem-core-wcm-components/blob/master/DATA_LAYER_INTEGRATION.md) 阅核心组件存储库中的文件。

## 与Adobe Analytics和Adobe Target集成 {#analytics-target}

与Adobe Analytics和Adobe Target携手，Adobe客户端数据层成为获得数字体验洞察的强大而灵活的工具集的基础。 以下教程引导您完成示例集成。

### 与Adobe Analytics收集页面数据 {#collect-page-data}

了解如何将Adobe客户端数据层的内置功能与AEM核心组件结合使用来收集Adobe Experience Manager Sites某个页面的相关数据。 Experience Platform Launch和Adobe Analytics扩展将用于创建规则以将页面数据发送到Adobe Analytics。

[视图此处的教程。](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/integrations/analytics/collect-data-analytics.html)

### 使用Adobe Analytics跟踪点击的组件 {#track-clicked-components}

将事件驱动型Adobe客户端数据层与AEM核心组件结合使用，跟踪Adobe Experience Manager站点上特定组件的点击情况。 了解如何在Experience Platform Launch中使用规则来监听单击事件、按组件进行筛选，以及使用跟踪链接信标将数据发送到Adobe Analytics。

[视图此处的教程。](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/integrations/analytics/track-clicked-component.html)
