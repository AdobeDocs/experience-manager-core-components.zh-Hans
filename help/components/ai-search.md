---
title: 内容AI 搜索组件
description: 内容AI 搜索组件为网站访客提供了创作AI支持的搜索。
role: Developer, Admin, User
product_v2:
  - id: c45915cf-e157-4af7-a80d-97b905bcb3a5
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: e2c1b6d3-bb7e-4fe8-8c72-f7b403298e91
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: e721e8b9469646300432b87d42bfb742aaf5f3fb
workflow-type: tm+mt
source-wordcount: 805
ht-degree: 16%

---


# 内容AI 搜索组件 {#content-ai-search-component}

内容AI 搜索组件为网站访客提供了创作AI支持的搜索。

{{traditional-aem}}

## 用途 {#usage}

内容AI 搜索组件允许访客直接从页面搜索[内容Source](https://experienceleague.adobe.com/zh-hans/docs/experience-manager-content-ai/using/contentsources)，并可以选择查看人工智能生成的生成结果摘要。 它将标准全文/语义搜索框与可切换的&#x200B;**显示由AEM Content AI提供支持的AI生成的摘要**&#x200B;面板相结合。

[编辑对话框](#edit-dialog)允许内容作者定义搜索的内容范围、搜索行为和生成设置。 由于模板级别没有可用设置，因此没有“设计”对话框。

>[!NOTE]
>
>要使用内容AI 搜索组件，您必须有权访问内容人工智能Source，并且管理员必须为您的项目启用该组件。 有关详细信息，请参阅文档[配置内容AI 搜索组件](/help/developing/ai-search.md)。

## 版本和兼容性 {#version-and-compatibility}

内容AI 搜索组件的当前版本是v1，此版本随2026年7月的核心组件发行版2.32.0的发布引入，具体说明见本文。

下表详细说明了该组件的所有受支持版本、与该组件的版本兼容的 AEM 版本以及指向早期版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|---|---|---|---|---|
| v1 | - | - | - | 正在进行 |

有关核心组件版本的更多信息，请参阅文档[核心组件版本。](/help/versions.md)

## 示例组件输出 {#sample-component-output}

要体验内容AI 搜索组件并查看其配置选项示例以及HTML和JSON输出，请访问[组件库。](https://adobe.com/go/aem_cmp_library_ai_search)

## 技术详细信息 {#technical-details}

在GitHub上可找到有关内容AI 搜索组件[的最新技术文档。](https://adobe.com/go/aem_cmp_tech_ai_search_v1_cn)

在[核心组件开发人员文档](/help/developing/overview.md)中可找到有关开发核心组件的其他详细信息。

## “编辑”对话框 {#edit-dialog}

利用“编辑”对话框，内容作者可以定义搜索的内容范围、搜索行为和创成设置。 由于模板级别没有可用设置，因此没有“设计”对话框。

### “内容范围”选项卡 {#content-scope}

![编辑对话框的“内容范围”选项卡](/help/assets/content-ai-search-edit-content-scope.png)

* **ID** — 此选项允许控制HTML和[Data Layer.](/help/developing/data-layer/overview.md)中组件的唯一标识符
  * 如果留空，系统会自动为您生成一个唯一 ID，可以通过检查结果页面找到该 ID。
  * 如果指定一个 ID，作者有责任确保它是唯一的。
  * 更改此 ID 会对 CSS、JS 和 Data Layer 跟踪产生影响。
* **内容Source类型** — 此字段定义内容源的类型。 选择类型后，将会使用匹配的源填充&#x200B;**内容Source**&#x200B;下拉列表。
  * **ACQUISITION** — 用于通过抓取/客户获取管道索引的公共、匿名访问源的默认值
  * **AEM_AUTHOR** — 其内容是从AEM创作实例摄取的Content-AI端源
  * **AEM_PUBLISH** — 从AEM发布实例摄取其内容的Content-AI端源
  * **CUSTOM** — 在AEM自己的引入管道之外注册的源
* **内容源** — 这将定义此组件搜索的内容Source。
  * 可用条目与已存在且&#x200B;**可用**&#x200B;的内容源匹配，并且与&#x200B;**内容Source类型**&#x200B;中设置的类型匹配
  * 有关详细信息，请参阅文档[设置和管理您的内容人工智能源](https://experienceleague.adobe.com/zh-hans/docs/experience-manager-content-ai/using/contentsources)。

### “搜索行为”选项卡 {#search-behavior}

![编辑对话框的“搜索行为”选项卡](/help/assets/content-ai-search-edit-search-behavior.png)

* **结果布局** — 此选项定义如何向访客显示搜索结果。
  * **卡片** — 此选项以网格格式显示结果。
  * **列表** — 此选项以列表格式显示结果。
* **结果大小** — 定义每个搜索请求获取的结果数。
  * 默认值为 `12`。
  * 当有其他匹配项可用时，访客可以加载更多结果。
* **占位符文本** — 这是访客进入搜索查询之前在空搜索输入字段中显示的文本。

### “生成搜索”选项卡 {#generative-search}

编辑对话框的![生成搜索选项卡](/help/assets/content-ai-search-edit-generative-search.png)

* **向访客显示生成性摘要切换** — 取消选中时，访客无法更改是否显示AI摘要。
  * 默认值为启用。
* **默认显示生成摘要** — 此选项控制人工智能生成的摘要的面向访客切换的默认状态。
  * 默认值为启用。
* **GenSearch错误回退** — 定义搜索应如何行为或错误。
  * **仅结果（隐藏错误）** — 如果出现错误，则仅显示返回的结果，而不显示错误和不重试按钮。 这是默认值。
  * **使用重试显示错误** — 如果出现错误，则使用重试按钮显示错误。
  * **仅显示错误消息** — 如果出现错误，则仅显示错误消息，不显示结果。
