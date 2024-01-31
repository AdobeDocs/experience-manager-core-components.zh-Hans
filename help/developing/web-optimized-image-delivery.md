---
title: Web 优化图像投放
description: 了解核心组件如何利用 AEM as a Cloud Service 的 Web 优化图像投放功能来更有效地投放图像。
role: Architect, Developer, Admin, User
exl-id: 6080ab8b-f53c-4d5e-812e-16889da4d7de
source-git-commit: 7325751541d463eb9744b1e4a72fd64611f74d55
workflow-type: tm+mt
source-wordcount: '1056'
ht-degree: 54%

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

激活Web优化图像投放后，您可能需要检查Dispatcher配置以验证它是否不会阻止对图像投放服务的请求。 请参阅 [此常见问题解答条目](#failure-to-deliver) 以了解更多信息。

## 验证 WebP 投放 {#verifying}

网络优化图像投放对内容的消费者是透明的。 最终用户只会注意到加载时间变快。 因此，要观察行为的任何实际变化，您必须检查浏览器中渲染图像的内容类型。 所有现代浏览器都支持WebP。 您可以引用 [此网站](https://caniuse.com/webp) 以了解有关浏览器支持的详细信息。

1. 在 AEM 中，编辑基于模板的页面，您在该模板中为图像组件[激活了 Web 优化图像投放](#activating)。
1. 在页面编辑器中，选择左上角的&#x200B;**页面信息**&#x200B;按钮，然后选择&#x200B;**查看已发布**。
1. 打开浏览器的开发人员工具，然后选择“网络”选项卡。
1. 重新加载页面，并查找加载图像的HTTP请求，然后检查浏览器收到的图像的内容类型。

## 当 Web 优化图像投放不可用时 {#fallback}

Web 优化图像投放仅在 AEM as a Cloud Service 中可用。 如果无法使用该功能(例如在内部部署或在本地开发实例上运行 AEM 6.5)，则图像投放将回退到使用[自适应图像 Servlet。](/help/developing/adaptive-image-servlet.md)

回退到自适应图像Servlet会更改 `src` 的属性 `img` 页面源中的元素。

## 常见问题解答 {#faq}

### 为什么在我的环境中未启用 Web 优化图像的此类选项？ {#missing-option}

该功能仅在 AEM as a Cloud Service 上可用。 在本地运行或内部部署 AEM，图像组件[ 回退](#fallback)以使用自适应图像 Servlet。

### 为何该服务不与本地 SDK 一起使用？ {#local-sdk}

在 `localhost` 上使用 AEM SDK 时，图像服务不可用，图像渲染[退回](#fallback)以使用自适应图像 Servlet。

要使用 Web 优化图像投放服务，请将项目部署到 AEMaaCS 开发环境，以便能够准确测试图像服务与图像服务的行为方式。

### 为什么该服务不适用于我页面上的某些图像？ {#some-images}

图片服务仅适用于位于 `/content/dam` 下的资产，不适用于直接上传到页面并存储在 `cq:Page` 对象下的图片。 此类资产仍将作为[回退的](#fallback)自适应图像 Servlet 投放。

### 为什么该服务会显示质量较差的图像或限制图像的大小？ {#quality}

当图像资产位于 `/content/dam` 处理，AEMas a Cloud Service的环境会生成不同维度的优化演绎版。 Web优化图像服务会分析图像核心组件请求的宽度，考虑原始图像以及所有2048像素或更小的演绎版，并选取那些图像服务可以处理的最大尺寸(在大小和尺寸限制之内，当前为50 MB， `12k`x`12k`)作为将应用所请求设置（宽度、裁切、格式、质量等）的基础。

为了保持输出的保真度，图像服务不放大图像。 上述演绎版定义了图像服务能够投放的最佳质量。 由于您通常无法影响原始图像资源的大小和/或尺寸，因此请确保您的图像资源都具有2048像素的缩放演绎版，如果没有，则重新处理它们。

### 我的图片的 URL 仍然以 .JPG 或 .PNG 结尾，而不是 .WEBP，并且没有 SRCSET 属性或 PICTURE 元素。 这是否真的在使用优化的 Web 格式？ {#content-negotiation}

为了提供WebP格式，Web优化图像投放服务将执行 [服务器驱动的内容协商。](https://developer.mozilla.org/en-US/docs/Web/HTTP/Content_negotiation#server-driven_content_negotiation) 这有助于根据客户端广告化功能选择图像的最佳输出格式，从而使图像投放服务忽略文件扩展名。

利用内容协商的优势在于，不广告支持WebP的浏览器仍会获得JPG或PNG文件格式，而无需更改页面的标记。 这样可以为现有站点提供最佳兼容性，并确保以最顺畅的方式过渡到Web优化图像投放。

### 我能否将 Web 优化图像投放与我自己的组件结合使用？

可以，自定义组件可使用 Web 优化的图像投放服务（通过[扩展图像组件](/help/developing/customizing.md)构建这些自定义组件）。

以下是可用于帮助生成资源 URL 的服务借口。

```
com.adobe.cq.wcm.spi.AssetDelivery.getDeliveryURL(Resource resource, Map<String, Object> parameterMap)
```

>[!WARNING]
>
>未通过上述SPI构建的直接URL嵌入体验(可在AEMas a Cloud Service站点上获得)违反了 [Media Library使用条款](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/assets/admin/medialibrary.html?lang=en#use-media-library).

### 启用 Web 优化图像后，图像是否无法显示？ {#failure-to-deliver}

不，由于以下原因，这种情况绝不应该发生。

* 在HTML中，启用Web优化图像时，标记不会更改，只会更改 `src` 图像元素上的属性发生更改。
* 每当新的图像服务不可用或无法处理所需的图像时，生成的 URL 将[回退到自适应图像 Servlet。](#fallback)
* Dispatcher规则可能会阻止Web优化的图像投放服务。 图像投放服务的URL开头为 `/adobe`，并检查 [已拒绝请求的Dispatcher日志](https://experienceleague.adobe.com/docs/experience-manager-learn/ams/dispatcher/common-logs.html#filter-rejects) 应该有助于排除在将图像交付给浏览器时遇到的任何故障。
