---
title: 自适应图像 Servlet
description: 了解核心组件如何使用自适应图像 Servlet 来投放图像，以及如何优化其使用。
role: Architect, Developer, Admin, User
exl-id: d9199d51-6f09-4000-9525-afc30474437e
source-git-commit: dd07fa714a23759d43ca491232674d88bc7bf88e
workflow-type: ht
source-wordcount: '254'
ht-degree: 100%

---

# 自适应图像 Servlet {#adaptive-image-servlet}

了解核心组件如何使用自适应图像 Servlet 来投放图像，以及如何优化其使用。

## 自适应图像 Servelt 还是 Web 优化图像投放？ {#options}

图像核心组件可以使用两种方法来传送图像。

* 默认为自适应图像 Servlet。
* [优化了 Web 的图像投放](/help/developing/web-optimized-image-delivery.md)可供 AEMaaCS 使用，并平均将下载大小减少 25%。

本文档介绍了默认的自适应图像 Servlet。

## 概述 {#overview}

默认情况下，图像组件使用核心组件的自适应图像 Servlet 来传送图像。 [自适应图像 Servlet](https://github.com/adobe/aem-core-wcm-components/wiki/The-Adaptive-Image-Servlet) 负责图像处理和流式传输，可由开发人员在其[核心组件的自定义设置](/help/developing/customizing.md)中使用。

## 优化演绎版选择 {#optimizing-rendition-selection}

自适应图像 Servlet 将尝试针对请求的图像大小和类型选择最佳演绎版。建议同步定义 DAM 演绎版和图像组件所允许的宽度，以便自适应图像 Servlet 执行尽可能少的处理。

这将提高性能并避免底层图像处理库无法正确处理某些图像。

## 使用最后修改的标头 {#last-modified}

自适应图像 Servlet 支持通过 `Last-Modified` 标头进行有条件请求，但是 `Last-Modified` 标头的缓存[需要在 Dispatcher 中启用](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html?lang=zh-Hans#caching-http-response-headers)。

[AEM 项目原型](/help/developing/archetype/overview.md)的示例 Dispatcher 配置已经包含此配置。
