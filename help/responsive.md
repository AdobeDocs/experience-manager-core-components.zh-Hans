---
title: 核心组件的响应式设计
description: 了解核心组件的响应式设计以及它如何影响您的项目。
role: Developer, Admin, User
exl-id: c0eff174-6803-4b44-aeb1-eae3bc8a36ea
TQID: https://experienceleague.adobe.com/wUpRlK8WxDuQzmFJFWAwFZUY-1fo9qOOgbOn-GEwBok
product_v2: id: c45915cf-e157-4af7-a80d-97b905bcb3a5id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 73aa5234ac63fa3be99feebce448bb6722513838
workflow-type: tm+mt
source-wordcount: 178
ht-degree: 100%

---

# 核心组件的响应式设计 {#responsive-design}

所有核心组件均设计为完全响应式，确保跨设备的无缝体验。 值得注意的是，一些高级组件（例如[轮播](/help/components/carousel.md)、[选项卡](/help/components/tabs.md)和[折叠组件](/help/components/accordion.md)）可能需要在实施项目的背景下进行具体考虑，以便在所有条件下保持响应能力。

鉴于这些组件可以通过多种方式展示响应式行为，并且 Adobe 致力于保持核心组件方便开箱即用，因此有意将实现详细响应方面的责任留给了项目。

例如，在窄屏幕上，选项卡组件可以通过将宽选项卡分成新行、允许垂直滚动、将选项卡转换为下拉菜单或采用折叠样式进行调整。 由于实施所有这些行为会对性能产生潜在影响，[clientlib](/help/developing/including-clientlibs.md#provided) 旨在作为实施者的起点，而不是详尽的解决方案。
