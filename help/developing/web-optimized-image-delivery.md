---
title: Web 优化图像投放
description: 了解核心组件如何利用 AEM as a Cloud Service 的 Web 优化图像投放功能来更有效地投放图像。
role: Architect, Developer, Admin, User
exl-id: 6080ab8b-f53c-4d5e-812e-16889da4d7de
source-git-commit: eb1822cb41a849695afb5125745ed5f78e3e70a4
workflow-type: tm+mt
source-wordcount: '1061'
ht-degree: 100%

---

# Web 优化图像投放 {#web-optimized-image-delivery}

了解核心组件如何利用 AEM as a Cloud Service 的 Web 优化图像投放功能来更有效地投放图像。

## 概述 {#overview}

AEM as a Cloud service 的 Web 优化图像投放功能以 [WebP 格式从 DAM 投放图像资产。](https://developers.google.com/speed/webp) WebP 平均可将图像的下载大小减小约 25%，从而加快页面加载速度。

在核心组件中激活 Web 优化图像投放非常简单，而且由于所有常用浏览器都支持 WebP，因此体验对最终用户是透明的。 他们会注意到的唯一区别是内容加载速度更快！

## 激活核心组件的 Web 优化图像投放 {#activating}

要启用 Web 优化图像投放，请编辑页面模板并只需激活选项&#x200B;**启用 Web 优化图像**&#x200B;的“设计”对话框中[图像组件。](/help/components/image.md#design-dialog) 此选项适用于图像组件的 v1、v2 和 v3。

如果您不熟悉设计对话框和 AEM 页面模板，[请查阅此文档。](/help/get-started/authoring.md#pre-configuring-core-components)

![在“设计”对话框中启用 Web 优化图像投放](/help/assets/web-optimized-image-delivery.png)

就是这样！图像现在由图像组件以 WebP 格式投放。

激活 Web 优化图像投放后，您可能希望检查调度程序配置以验证它是否不会阻止对图像投放服务的请求。有关详细信息，请参阅[本常见问题条目](#failure-to-deliver)。

## 验证 WebP 投放 {#verifying}

Web 优化的图像投放对于内容的消费者来说是透明的。最终用户只会注意到加载时间更短。因此，要观察行为的任何实际变化，您必须检查浏览器中所渲染图像的内容类型。所有现代浏览器都支持 WebP。您可以参考[本网站](https://caniuse.com/webp)，了解有关浏览器支持的详细信息。

1. 在 AEM 中，编辑基于模板的页面，您在该模板中为图像组件[激活了 Web 优化图像投放](#activating)。
1. 在页面编辑器中，选择左上角的&#x200B;**页面信息**&#x200B;按钮，然后选择&#x200B;**查看已发布**。
1. 打开浏览器的开发人员工具并选择网络选项卡。
1. 重新加载页面并查找加载图像的 HTTP 请求，然后检查浏览器收到的图像的内容类型。

## 当 Web 优化图像投放不可用时 {#fallback}

Web 优化图像投放仅在 AEM as a Cloud Service 中可用。 如果无法使用该功能(例如在内部部署或在本地开发实例上运行 AEM 6.5)，则图像投放将回退到使用[自适应图像 Servlet。](/help/developing/adaptive-image-servlet.md)

回退到自适应图像 Servlet 会更改页面源中 `img` 元素的 `src` 属性。

## 常见问题解答 {#faq}

### 为什么在我的环境中未启用 Web 优化图像的此类选项？ {#missing-option}

该功能仅在 AEM as a Cloud Service 上可用。 在本地运行或内部部署 AEM，图像组件[ 回退](#fallback)以使用自适应图像 Servlet。

### 为何该服务不与本地 SDK 一起使用？ {#local-sdk}

在 `localhost` 上使用 AEM SDK 时，图像服务不可用，图像渲染[退回](#fallback)以使用自适应图像 Servlet。

要使用 Web 优化图像投放服务，请将项目部署到 AEMaaCS 开发环境，以便能够准确测试图像服务与图像服务的行为方式。

### 为什么该服务不适用于我页面上的某些图像？ {#some-images}

图片服务仅适用于位于 `/content/dam` 下的资产，不适用于直接上传到页面并存储在 `cq:Page` 对象下的图片。 此类资产仍将作为[回退的](#fallback)自适应图像 Servlet 投放。

### 为什么该服务会显示质量较差的图像或限制图像的大小？ {#quality}

处理 `/content/dam` 下的图像资源时，AEM as a Cloud Service 环境会生成不同尺寸的优化呈现。Web 优化图像服务将分析图像核心组件请求的宽度，考虑原始图像和 2048 像素和更小的所有呈现，并选择其中最大的图像（在图像服务可以处理的大小和尺寸限制内，当前为 50 MB 和 `12k`x`12k`）作为基础，应用请求的设置（宽度、裁切、格式、质量等）。

为了保持输出的保真度，图像服务不会放大图像。上述呈现定义了图像服务能够投放的最佳质量。由于您通常无法影响原始图像资源的大小和/或尺寸，因此请确保您的图像资源都具有 2048 像素的缩放呈现，如果没有，请重新处理它们。

### 我的图片的 URL 仍然以 .JPG 或 .PNG 结尾，而不是 .WEBP，并且没有 SRCSET 属性或 PICTURE 元素。 这是否真的在使用优化的 Web 格式？ {#content-negotiation}

为了提供 WebP 格式，Web 优化图像投放服务执行[服务器驱动的内容协商。](https://developer.mozilla.org/en-US/docs/Web/HTTP/Content_negotiation#server-driven_content_negotiation)这有助于根据客户端公布的功能选择图像的最佳输出格式，从而允许图像投放服务忽略文件扩展名。

利用内容协商的优点是，未声明支持 WebP 的浏览器仍将获得 JPG 或 PNG 文件格式，而无需对页面标记进行任何更改。这为现有网站提供了最佳兼容性，并保证以最顺畅的可能方式过渡到 Web 优化的图像投放。

### 我能否将 Web 优化图像投放与我自己的组件结合使用？

可以，自定义组件可使用 Web 优化的图像投放服务（通过[扩展图像组件](/help/developing/customizing.md)构建这些自定义组件）。

以下是可用于帮助生成资源 URL 的服务借口。

```
com.adobe.cq.wcm.spi.AssetDelivery.getDeliveryURL(Resource resource, Map<String, Object> parameterMap)
```

>[!WARNING]
>
>将 URL 直接嵌入到并非通过上述 SPI（在 AEM as a Cloud Service Sites 上提供）构建的体验中违反了[媒体库使用条款](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/assets/admin/medialibrary.html?lang=en#use-media-library)。

### 启用 Web 优化图像后，图像是否无法显示？ {#failure-to-deliver}

否，由于以下原因，这种情况绝对不应该发生。

* 在 HTML 中，启用 Web 优化图像时，标记不会更改，只有图像元素上 `src` 属性的值会更改。
* 每当新的图像服务不可用或无法处理所需的图像时，生成的 URL 将[回退到自适应图像 Servlet](#fallback)。

但是，Dispatcher 规则可能会阻止 Web 优化的图像投放服务。图像投放服务的 URL 以 `/adobe` 开头，并检查 Dispatcher 日志中是否有被拒绝的请求，如[这里所述](https://experienceleague.adobe.com/docs/experience-manager-learn/ams/dispatcher/common-logs.html#filter-rejects)，这样应该有助于解决将图像投放到浏览器时遇到的任何故障。
