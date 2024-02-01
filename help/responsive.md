---
title: 核心组件的响应式设计
description: 了解核心组件的响应式设计以及它可能会如何影响您的项目。
role: Architect, Developer, Admin, User
source-git-commit: d39fe0084522f67664203a026340b23d325c1883
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 0%

---


# 核心组件的响应式设计 {#responsive-design}

所有核心组件均设计用于完全响应，确保跨设备无缝体验。 请务必注意，某些高级组件，例如 [轮播，](/help/components/carousel.md) [选项卡，](/help/components/tabs.md) 和 [可折叠项组件、](/help/components/accordion.md) 可能需要在执行项目范围内进行具体考虑，以在所有情况下保持响应能力。

由于这些组件可以表现出响应式行为的方式多种多样，并且在Adobe承诺保持核心组件开箱即用的轻量级后，有意将实施详细响应式方面的责任留给项目。

例如，在窄屏幕上，选项卡组件可以通过将宽选项卡分成新行、允许垂直滚动、将选项卡转换为下拉列表或采用折叠样式来进行调整。 由于实施所有这些行为将对性能造成潜在影响，因此 [clientlibs](/help/developing/including-clientlibs.md#provided) 旨在作为实施者的起点，而不是作为详尽的解决方案。
