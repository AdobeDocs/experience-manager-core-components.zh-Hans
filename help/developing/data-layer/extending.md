---
title: 扩展Adobe客户端数据层
description: Adobe客户端数据层可以按照一些基本模式进行扩展
feature: 核心组件，Adobe客户端数据层
role: Architect, Developer, Administrator
exl-id: f3d5555b-4f08-49de-ab0f-dc0fb04aadf8
source-git-commit: 8ff36ca143af9496f988b1ca65475497181def1d
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 0%

---

# 扩展Adobe客户端数据层{#extending-acdl}

您可以使用自定义对话框选项扩展核心组件，该对话框选项允许内容作者输入与数据层相关的其他信息。

要在核心组件提供的数据层中包含这些字段，必须扩展组件的模型以实施其自己的特定数据层方法。

## 示例：标题组件 {#example}

诸如[标题组件](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/Title.java)之类的核心组件扩展了[组件](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/Title.java)，该组件具有默认返回[`ComponentData`的`getData`方法。](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/datalayer/ComponentData.java)

`ComponentData` 序列化组件可能实施的预定义字段， `getDataLayerLinkUrl` 如 `getDataLayerTitle` 和 [`TitleImpl`。](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/internal/models/v1/TitleImpl.java)

因此，您的自定义Sling模型可能具有`getData`方法，该方法会返回一个扩展为`ComponentData`以返回更多字段的对象。

为此，会向组件的HTML元素添加`data-cmp-data-layer`属性，该元素包含要填充到数据层的数据的JSON。 此时，您可以实施用于侦听此数据或相关事件的脚本。

>[!TIP]
>
>要进一步探索数据层的灵活性，请查看有关集成选项的信息，包括如何为自定义组件启用数据层。
