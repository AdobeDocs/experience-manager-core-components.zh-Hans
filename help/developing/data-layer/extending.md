---
title: 扩展Adobe客户端数据层
description: Adobe客户端数据层可以按照一些基本模式进行扩展
feature: 核心组件，Adobe客户端数据层
role: 架构师、开发人员、管理员
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 0%

---


# 扩展Adobe客户端数据层{#extending-acdl}

您可以使用自定义对话框选项扩展核心组件，这些对话框选项允许内容作者输入与数据层相关的其他信息。

要在核心组件提供的数据层中包含这些字段，必须扩展组件的模型，以实现其自己的特定数据层方法。

## 示例：标题组件{#example}

类似[标题组件](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/Title.java)的核心组件扩展了[组件](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/Title.java)，该组件具有`getData`方法，默认情况下返回[`ComponentData`。](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/datalayer/ComponentData.java)

`ComponentData` 序列化您的组件可能实现的预定义字段， `getDataLayerLinkUrl` 如 `getDataLayerTitle` 和 [`TitleImpl`。](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/internal/models/v1/TitleImpl.java)

因此，您的自定义Sling模型可能具有`getData`方法，该方法返回扩展`ComponentData`以返回更多字段的对象。

执行此操作后，将向组件的HTML元素添加`data-cmp-data-layer`属性，其中包含将填充到数据层的数据的JSON。 此时，您可以实现侦听此数据或相关事件的脚本。

>[!TIP]
>
>要进一步探索数据层的灵活性，请查看集成选项，包括如何为自定义组件启用数据层。
