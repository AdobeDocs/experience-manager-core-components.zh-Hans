---
title: 扩展 Adobe Client Data Layer
description: Adobe Client Data Layer 可以按照一些基本模式进行扩展
feature: Core Components, Adobe Client Data Layer
role: Developer, Admin
exl-id: f3d5555b-4f08-49de-ab0f-dc0fb04aadf8
TQID: 'https://experienceleague.adobe.com/67YSpRfwNRMDgcBARHKLz51-Er6xb4vp1rXX0r0sbfE'
product_v2:
  - id: c45915cf-e157-4af7-a80d-97b905bcb3a5
    internal-label: Experience Manager Sites
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: d9d38edd-df1b-480c-8f5e-72b62576f390
    internal-label: Site and page features
  - id: d429a63e-ade4-4117-b04e-9b996d1c94ef
    internal-label: Integrations
subfeature_v2:
  - id: c43ff1f6-5a6d-4e8c-b3cc-6bdb3fa6e092
    internal-label: Core components
  - id: a94e5c13-4138-47ec-b9c8-e804e17aaca2
    internal-label: Adobe Client Data Layer
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
source-git-commit: 025b8134f7675b4515f4586910a94a2732bfa2ee
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 100%
---
# 扩展 Adobe Client Data Layer {#extending-acdl}

您可以使用自定义对话框选项扩展核心组件，这些选项允许内容作者输入与 Data Layer 相关的其他信息。

为了将这些字段包含在核心组件提供的数据层中，您必须扩展实现了其自身特定数据层方法的组件模型。

## 示例：标题组件 {#example}

像[标题组件](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/Title.java)这样的核心组件能够扩展具有 `getData` 方法（默认返回 [`ComponentData`](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/datalayer/ComponentData.java)）的[组件](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/Title.java)。

`ComponentData` 序列化您的组件可能实施的预定义字段，例如 [`TitleImpl`](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/internal/models/v1/TitleImpl.java) 的 `getDataLayerLinkUrl` 和 `getDataLayerTitle`。

因此，您的自定义 Sling 模型可能具有 `getData` 方法，该方法返回扩展 `ComponentData` 以返回更多字段的对象。

这样做会将 `data-cmp-data-layer` 属性添加到组件的 HTML 元素，还会添加将填充到 Data Layer 的数据 JSON。 此时，您可以实施监听这些数据或相关事件的脚本。

>[!TIP]
>
>要进一步探讨 Data Layer 的灵活性，请查看相关的集成选项，包括如何为自定义组件启用 Data Layer。
