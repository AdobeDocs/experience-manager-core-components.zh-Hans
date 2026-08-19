---
title: 配置内容AI 搜索组件
description: 内容AI 搜索组件为网站访客提供了创作AI支持的搜索。 了解如何为内容作者启用此组件。
role: Developer, Admin
product_v2:
  - id: c45915cf-e157-4af7-a80d-97b905bcb3a5
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: e2c1b6d3-bb7e-4fe8-8c72-f7b403298e91
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: c18d9e03-ac7d-4811-9c92-3e92ddc70ade
source-git-commit: 865622469555a773138d3ff1b54138f2b76994b0
workflow-type: tm+mt
source-wordcount: 485
ht-degree: 2%

---


# 配置内容AI 搜索组件 {#configure-content-ai-search-component}

内容AI 搜索组件为网站访客提供了创作AI支持的搜索。 了解如何为内容作者启用此组件。

## 先决条件 {#prerequisites}

* 已创建至少一个[内容Source](https://experienceleague.adobe.com/en/docs/experience-manager-content-ai/using/contentsources)，状态为&#x200B;**可用**。
* 在创作和发布上设置的&#x200B;**AEM Content AI客户端** OSGi配置(`ContentAIClientImpl`)，具有有效的API凭据和&#x200B;**默认内容Source**&#x200B;值。 有关如何获取凭据的信息，请参阅文档[设置Adobe Developer Console项目](https://experienceleague.adobe.com/en/docs/experience-manager-content-ai/using/setup-adc-project)。

## 创建代理组件 {#proxy-component}

与所有核心组件一样，建议为AEM附带的默认内容AI 搜索组件创建代理组件。 通过将代理组件中特定于项目的更改保留在`/apps`下，Adobe会自动更新`/libs`下的基础组件，并且项目组件会自动继承这些更新。 有关详细信息，请参阅文档[使用核心组件](/help/get-started/using.md#aemaacs)和[组件指南](/help/developing/guidelines.md)。

## 配置客户端库 {#clientlib}

内容AI 搜索组件不遵循在核心组件中包含客户端库的[标准模式。](/help/developing/including-clientlibs.md) 请按照以下步骤进行操作。

将以下内容添加到项目的页面组件`customheaderlibs.html` （对于CSS）和`customfooterlibs.html` （对于JS）：

```html
<sly data-sly-use.clientLib="/libs/granite/sightly/templates/clientlib.html"
     data-sly-call="${clientLib.css @ categories='core.wcm.components.contentaisearch.v1'}"></sly>
```

如果项目在其上方叠加其自身的品牌样式，则在此类别之后为项目自身的客户端库添加第二个类别。

## 使用内容AI 搜索组件 {#using}

您的内容作者现在可以将内容AI 搜索组件放置到其页面上。 有关详细信息，请参阅文档[内容AI 搜索组件](/help/components/ai-search.md)。

## 组件如何使用内容人工智能 {#how-it-works}

* 标准搜索查询由与Content Source索引相同的检索层提供，从配置的源返回匹配的页面、片段或资源。
* 启用人工智能生成的摘要后，该组件还会调用AEM Content AI生成端点，将响应置于同一索引内容中，并在摘要旁边显示源，以便访客可以验证。
* 由于这两项功能是从同一受管控的内容Source中读取的，因此结果和摘要与当前索引的内容保持一致。 重新运行客户获取（请参阅[控制您的内容源](https://experienceleague.adobe.com/en/docs/experience-manager-content-ai/using/contentsources)）会刷新这两个内容。

## 后续步骤 {#next-steps}

* [控制您的内容源](https://experienceleague.adobe.com/en/docs/experience-manager-content-ai/using/contentsources) — 创建和管理此组件搜索的内容Source。
* [设置Adobe Developer Console项目](https://experienceleague.adobe.com/en/docs/experience-manager-content-ai/using/setup-adc-project) — 获取OSGi Content AI客户端配置使用的凭据。
* [内容人工智能API引用](https://developer.adobe.com/experience-cloud/experience-manager-apis/api/experimental/contentai/) — 了解此组件调用的基础搜索和生成性摘要端点。
