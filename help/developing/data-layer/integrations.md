---
title: 集成和 Adobe Client Data Layer
description: 了解 Adobe 客户端数据层如何与您的自定义组件集成，以及与 Adobe Analytics 和 Adobe Target 的集成如何帮助您洞察自己的网站
feature: Core Components, Adobe Client Data Layer
role: Developer, Admin
exl-id: 503dd3dc-fe95-4a17-83f5-1f0c1960993d
TQID: https://experienceleague.adobe.com/xncfOtz1FNyeH6CjQjg7cSeIonIg2mkBIPUgZvMI7Ww
product_v2: id: c45915cf-e157-4af7-a80d-97b905bcb3a5id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: ae478996-b206-4712-9b0c-dc78a2644453id: d429a63e-ade4-4117-b04e-9b996d1c94ef
subfeature_v2: id: a94e5c13-4138-47ec-b9c8-e804e17aaca2
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 424
ht-degree: 100%

---

# 与 Adobe Client Data Layer 的集成 {#integrations}

Adobe Client Data Layer 通过提供一种标准化方法来公开和访问任何脚本的任何类型的数据，从而减少检测网站所需的工作量。

Adobe 客户端数据层可与您的自定义组件集成，并且与 Adobe Analytics 和 Adobe Target 的集成如何帮助您洞察自己的网站。

## 为自定义组件启用 Data Layer {#enabling-custom-components}

自动将自定义组件添加到 Data Layer：

1. 定义需要跟踪的自定义组件模型的属性。
1. 将 `data-cmp-data-layer` 属性添加到自定义组件 HTL。例如 `data-cmp-data-layer="${mycomponent.data.json}"`.

要自动使 Data Layer 在每次单击自定义组件的特定元素时触发 `cmp:click` 事件，可将 `data-cmp-clickable` 属性添加到要在自定义组件 HTL 中跟踪的元素。

可在客户端查询 `data-cmp-data-layer-enabled` 属性以检查是否已启用 Data Layer。

>[!TIP]
>
>有关 Adobe Client Data Layer 与核心组件的集成以及如何在自定义组件上启用 Data Layer 的其他技术详细信息，请参阅核心组件存储库中的 [`DATA_LAYER_INTEGRATION.md`](https://github.com/adobe/aem-core-wcm-components/blob/master/DATA_LAYER_INTEGRATION.md) 文件。

## 与 Adobe Analytics 和 Adobe Target 集成 {#analytics-target}

Adobe 客户端数据层与 Adobe Analytics 和 Adobe Target 搭配使用，为构建功能非常强大且灵活的工具集奠定了基础，从而洞察您的数字体验。 以下教程将指导您完成示例集成。

### 使用 Adobe Analytics 收集页面数据 {#collect-page-data}

了解如何使用带 AEM 核心组件的 Adobe Client Data Layer 的内置功能来收集有关 Adobe Experience Manager Sites 中页面的数据。 Experience Platform Launch 和 Adobe Analytics 扩展将用于创建规则以将页面数据发送到 Adobe Analytics。

[在此处查看教程。](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/integrations/analytics/collect-data-analytics.html)

### 使用 Adobe Analytics 跟踪单击的组件 {#track-clicked-components}

使用带 AEM 核心组件的事件驱动型 Adobe Client Data Layer 跟踪 Adobe Experience Manager Site 上的特定组件的单击数。 了解如何使用 Experience Platform Launch 中的规则来侦听单击事件、按组件筛选并在带跟踪链接信标的情况下将数据发送到 Adobe Analytics。

[在此处查看教程。](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/integrations/analytics/track-clicked-component.html)
