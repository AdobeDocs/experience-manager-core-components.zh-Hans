---
title: Web 优化图像投放
description: 了解核心组件如何利用 AEM as a Cloud Service 的 Web 优化图像投放功能来更有效地投放图像。
role: Architect, Developer, Admin, User
exl-id: 6080ab8b-f53c-4d5e-812e-16889da4d7de
source-git-commit: d8c8f4c3395313b21f56fd7d98175924287c367c
workflow-type: tm+mt
source-wordcount: '1023'
ht-degree: 97%

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

激活 Web 优化图像投放后，您可能还希望检查调度程序配置以验证它是否不会阻止对图像服务的请求。 此服务的 URL 采用以下形式。

```text
/adobe/dynamicmedia/deliver/dm-aid--741ed388-d5f8-4797-8095-10c896dc9f1d/skitouring.jpg?quality=80&preferwebp=true
```

这可以用此正则表达式来推广。

```text
\/adobe\/dynamicmedia\/deliver\/([^:[]|*\/])\/([\w-])\.(gif|png|png8|jpg|pjpg|bjpg|webp|webpll|webply)(?[a-z0-9=&]*)?
```

## 验证 WebP 投放 {#verifying}

Web 优化图像投放对内容的消费者是透明的，不会影响标记。 最终用户只会注意到加载时间更短。

因此，要观察行为的实际变化，您必须查看页面源。

1. 在 AEM 中，编辑基于模板的页面，您在该模板中为图像组件[激活了 Web 优化图像投放](#activating)。
1. 在页面编辑器中，选择左上角的&#x200B;**页面信息**&#x200B;按钮，然后选择&#x200B;**查看已发布**。
1. 使用您的浏览器开发工具，查看页面源代码并查看呈现的标记如何保持不变，但 `src` 属性中的图像指向[新图像服务的 URL。](#activating)

## 当 Web 优化图像投放不可用时 {#fallback}

Web 优化图像投放仅在 AEM as a Cloud Service 中可用。 如果无法使用该功能(例如在内部部署或在本地开发实例上运行 AEM 6.5)，则图像投放将回退到使用[自适应图像 Servlet。](/help/developing/adaptive-image-servlet.md)

正如启用 Web 优化图像投放不会影响标记一样，回退到自适应图像 Servlet 也不会影响标记，因为只有 `img` 元素的 `src` 属性中的 URL 发生了变化。

## 常见问题解答 {#faq}

### 为什么在我的环境中未启用 Web 优化图像的此类选项？ {#missing-option}

该功能仅在 AEM as a Cloud Service 上可用。 在本地运行或内部部署 AEM，图像组件[ 回退](#fallback)以使用自适应图像 Servlet。

### 为何该服务不与本地 SDK 一起使用？ {#local-sdk}

在 `localhost` 上使用 AEM SDK 时，图像服务不可用，图像渲染[退回](#fallback)以使用自适应图像 Servlet。

要使用 Web 优化图像投放服务，请将项目部署到 AEMaaCS 开发环境，以便能够准确测试图像服务与图像服务的行为方式。

### 为什么该服务不适用于我页面上的某些图像？ {#some-images}

图片服务仅适用于位于 `/content/dam` 下的资产，不适用于直接上传到页面并存储在 `cq:Page` 对象下的图片。 此类资产仍将作为[回退的](#fallback)自适应图像 Servlet 投放。

### 为什么该服务会显示质量较差的图像或限制图像的大小？ {#quality}

Web 优化图像服务会考虑所有 2048 像素和更小的图像呈现，并选取最大的图像演绎版作为应用所请求设置（宽度、裁切、格式、质量等）的基础。

图像服务永远不会放大图像。 因此，这些演绎版定义了图像服务能够投放的最佳大小和质量。 因此，请确保您的资产都具有 2048 像素的缩放演绎版，如果没有，则重新处理它们。

### 我的图片的 URL 仍然以 .JPG 或 .PNG 结尾，而不是 .WEBP，并且没有 SRCSET 属性或 PICTURE 元素。 这是否真的在使用优化的 Web 格式？ {#content-negotiation}

为了提供 WebP 格式，Web 优化图像投放服务使用了一种称为“内容协商”的技术。 这包括返回 WebP 文件格式，即使在请求 JPG 或 PNG 文件扩展名时也是如此，但仅当发出请求的浏览器提供了 `image/webp` HTTP 接受标头。 然后，支持此技术的浏览器可以提供此标头，而较旧的浏览器仍将获得 JPG 或 PNG 文件格式。

这种技术的优点是`img`元素及其属性可以保持不变，这将为现有站点带来最佳兼容性，并确保向 web 优化图像投放过渡的最顺畅路径。

### 我能否将 Web 优化图像投放与我自己的组件结合使用？

可以，自定义组件可以使用 Web 优化图像投放服务。 在这种情况下，Adobe 建议[扩展图像组件](/help/developing/customizing.md)。

以下是一个服务界面，可用于帮助生成资产 URL。

```
com.adobe.cq.wcm.spi.AssetDelivery.getDeliveryURL(Resource resource, Map<String, Object> parameterMap)
```

**请注意，并非通过在AEM Sites CS上运行的核心组件构建的直接URL嵌入体验，违反了Media Library许可条款。**

### 新图像服务投放的图像的 URL 是什么？ {#url}

有关示例 URL 和正则表达式，请参阅上一节[为核心组件激活 Web 优化图像投放](#activating)。

### 启用 Web 优化图像后，图像是否无法显示？

不，这不该发生。

* 在 HTML 中，启用 Web 优化图像时，标记不会更改，只有图像元素上 SRC 属性的值会更改。
* 每当新的图像服务不可用或无法处理所需的图像时，生成的 URL 将[回退到自适应图像 Servlet。](#fallback)
* 调度程序规则可能会阻止网络优化的图像服务，激活该功能时应检查[。](#activating)
