---
title: 核心组件的响应式设计
description: 了解核心组件的响应式设计以及它如何影响您的项目。
role: Architect, Developer, Admin, User
source-git-commit: d39fe0084522f67664203a026340b23d325c1883
workflow-type: ht
source-wordcount: '174'
ht-degree: 100%

---


# 核心组件的响应式设计 {#responsive-design}

所有核心组件均设计为完全响应式，确保跨设备的无缝体验。值得注意的是，一些高级组件（例如[轮播](/help/components/carousel.md)、[选项卡](/help/components/tabs.md)和[折叠组件](/help/components/accordion.md)）可能需要在实施项目的背景下进行具体考虑，以便在所有条件下保持响应能力。

鉴于这些组件可以通过多种方式展示响应式行为，并且 Adobe 致力于保持核心组件方便开箱即用，因此有意将实现详细响应方面的责任留给了项目。

例如，在窄屏幕上，选项卡组件可以通过将宽选项卡分成新行、允许垂直滚动、将选项卡转换为下拉菜单或采用折叠样式进行调整。由于实施所有这些行为会对性能产生潜在影响，[clientlib](/help/developing/including-clientlibs.md#provided) 旨在作为实施者的起点，而不是详尽的解决方案。
