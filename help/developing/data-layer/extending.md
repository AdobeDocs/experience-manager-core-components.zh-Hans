---
title: 扩展 Adobe Client Data Layer
description: Adobe Client Data Layer 可以按照一些基本模式进行扩展
feature: 核心组件，Adobe Client Data Layer
role: Architect, Developer, Admin
exl-id: f3d5555b-4f08-49de-ab0f-dc0fb04aadf8
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: ht
source-wordcount: '282'
ht-degree: 100%

---

# 扩展 Adobe Client Data Layer {#extending-acdl}

您可以使用自定义对话框选项扩展核心组件，这些选项允许内容作者输入与 Data Layer 相关的其他信息。

为了在核心组件提供的 Data Layer 中包括这些字段，您必须扩展能够实施自己特定 Data Layer 方法的组件模型。

## 示例：标题组件 {#example}

像[标题组件](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/Title.java)这样的核心组件能够扩展具有 `getData` 方法（默认返回 [`ComponentData`](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/datalayer/ComponentData.java)）的[组件](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/Title.java)。

`ComponentData` 序列化您的组件可能实施的预定义字段，例如 [`TitleImpl`](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/internal/models/v1/TitleImpl.java) 的 `getDataLayerLinkUrl` 和 `getDataLayerTitle`。

因此，您的自定义 Sling 模型可能具有 `getData` 方法，该方法返回扩展 `ComponentData` 以返回更多字段的对象。

这样做会将 `data-cmp-data-layer` 属性添加到组件的 HTML 元素，还会添加将填充到 Data Layer 的数据 JSON。此时，您可以实施监听此数据或相关事件的脚本。

>[!TIP]
>
>要进一步探讨 Data Layer 的灵活性，请查看相关的集成选项，包括如何为自定义组件启用 Data Layer。
