---
title: 扩展Adobe客户端数据层
description: Adobe客户端数据层可以按照一些基本模式进行扩展
translation-type: tm+mt
source-git-commit: 896ed679ed3351cb309a34b38bf97fe81adc2cfe
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 0%

---


# 扩展Adobe客户端数据层 {#extending-acdl}

您可以使用自定义对话框选项扩展核心组件，这些对话框选项允许内容作者输入与数据层相关的其他信息。

要在核心组件提供的数据层中包含这些字段，必须扩展组件模型，以实现其自己的特定数据层方法。

## 示例：标题组件 {#example}

核心组件(如标题 [组件](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/Title.java) )扩 [展了组件](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/Title.java) ，默认 `getData` 情况下，该组件具有返回的方法 [`ComponentData`。](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/models/datalayer/ComponentData.java)

`ComponentData` 序列化组件可能实现的预定义字段， `getDataLayerLinkUrl` 如 `getDataLayerTitle` 和 [`TitleImpl`。](https://github.com/adobe/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/internal/models/v1/TitleImpl.java)

因此，您的自定义Sling模型可能 `getData` 有一种方法，它返回一个扩展 `ComponentData` 以返回更多字段的对象。

这样，将向组 `data-cmp-data-layer` 件的HTML元素添加一个属性，其中包含将填充到数据层的数据的JSON。 此时，您可以实现侦听此数据或相关事件的脚本。
