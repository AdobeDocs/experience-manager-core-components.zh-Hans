---
title: Web优化的图像交付
description: 了解核心组件如何利用AEM Web优化的图像交付功能，更高效地交付图像。
role: Architect, Developer, Admin, User
source-git-commit: 20436ffb5d6a6346738be1e6f5e6e2e8a68e76c9
workflow-type: tm+mt
source-wordcount: '1170'
ht-degree: 0%

---


# Web优化的图像交付 {#web-optimized-image-delivery}

了解核心组件如何利用AEM Web优化的图像交付功能，更高效地交付图像。

>[!NOTE]
>
>Web优化的图像交付服务是2022年6月发布的AEMas a Cloud Service预发布功能，预计7月份将推出GA。
>
>有关AEMaCS预发行功能的更多信息，请参阅此文档 [Adobe Experience Manager as a Cloud Service预发行渠道](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/release-notes/prerelease.html)

##  概述 {#overview}

AEM as a Cloud Service的Web优化图像交付功能，可在 [WebP格式。](https://developers.google.com/speed/webp) WebP平均可将图像的下载大小减小约25%，从而加快页面加载速度。

在核心组件中激活Web优化图像交付非常简单，而且由于所有常用浏览器都支持WebP，因此体验对最终用户是透明的。 他们会注意到的唯一区别是内容加载速度更快！

## 激活核心组件的Web优化图像交付 {#activating}

要启用Web优化的图像交付，请编辑页面模板并只需激活选项 **启用Web优化图像** 的“设计”对话框中 [图像组件。](/help/components/image.md#design-dialog) 此选项适用于图像组件的v1、v2和v3。

如果您不熟悉设计对话框和AEM页面模板， [请查阅此文档。](/help/get-started/authoring.md#pre-configuring-core-components)

![在“设计”对话框中启用Web优化的图像交付](/help/assets/web-optimized-image-delivery.png)

就是这样！图像现在由图像组件以WebP格式交付。

激活Web优化的图像交付后，您可能还希望检查调度程序配置以验证它是否不会阻止对图像服务的请求。 此服务的URL采用以下形式。

```text
/adobe/dynamicmedia/deliver/dm-aid--741ed388-d5f8-4797-8095-10c896dc9f1d/skitouring.jpg?quality=80&preferwebp=true
```

这可以用此正则表达式来推广。

```text
\/adobe\/dynamicmedia\/deliver\/([^:[]|*\/])\/([\w-])\.(gif|png|png8|jpg|pjpg|bjpg|webp|webpll|webply)(?[a-z0-9=&]*)?
```

## 验证WebP交付 {#verifying}

Web优化的图像交付对内容的消费者是透明的，不会影响标记。 最终用户只会注意到加载时间更短。

因此，要观察行为的实际变化，您必须查看页面源。

1. 在AEM中，编辑基于您 [激活的Web优化图像交付](#activating) （对于图像组件）。
1. 在页面编辑器中，选择 **页面信息** 按钮 **查看已发布的项目**.
1. 使用您的浏览器开发人员工具，查看页面源，并查看渲染的标记如何保持不变，但是图像位于 `src` 属性点到 [新图像服务的URL。](#activating)

## 当Web优化图像交付不可用时 {#fallback}

Web优化的图像交付仅在AEMas a Cloud Service中可用。 如果无法使用该功能(例如在内部部署或在本地开发实例上运行AEM 6.5)，则图像交付将回退到使用 [自适应图像Servlet。](/help/developing/adaptive-image-servlet.md)

正如启用Web优化图像交付不会影响标记一样，回退到自适应图像Servlet也不会影响标记，因为 `src` 属性 `img` 元素。

## 常见问题解答 {#faq}

### 为什么在我的环境中没有启用Web优化图像的此类选项？ {#missing-option}

该功能仅在AEMas a Cloud Service上可用。 在本地或本地运行AEM，即图像组件 [掉落](#fallback) 以使用自适应图像Servlet。

### 为何该服务不与本地SDK一起使用？ {#local-sdk}

在上使用AEM SDK `localhost`，图像服务不可用，并且图像呈现 [掉落](#fallback) 以使用自适应图像Servlet。

要使用Web优化的图像交付服务，请将项目部署到AEMaaCS开发环境，以便能够准确测试图像服务与图像服务的行为方式。

### 为什么该服务不适用于我页面上的某些图像？ {#some-images}

图像服务仅适用于位于 `/content/dam` 而且对于直接上传到页面并存储在 `cq:Page` 对象。 此类资产仍将随自适应图像Servlet作为 [后退。](#fallback)

### 为什么该服务会显示质量较差的图像或限制图像的大小？ {#quality}

Web优化图像服务会考虑所有2048像素和更小的图像呈现，并选取最大的图像演绎版作为应用所请求设置（宽度、裁剪、格式、质量等）的基础。

图像服务永远不会放大图像。 因此，这些演绎版定义了图像服务能够交付的最佳大小和质量。 因此，请确保您的资产都具有2048像素的缩放演绎版，如果没有，则重新处理它们。

### 我的图像的URL仍以。JPG或.PNG结尾，而不是.WEBP，并且没有SRCSET属性或PICTURE元素。 这是否真的在使用优化的Web格式？ {#content-negotiation}

为了提供WebP格式，Web优化的图像交付服务使用了一种称为“内容协商”的技术。 这包括返回WebP文件格式，即使在请求JPG或PNG文件扩展名时也是如此，但仅当发出请求的浏览器提供了 `image/webp` HTTP接受标头。 然后，支持此技术的浏览器可以提供此标头，而较旧的浏览器仍将获得JPG或PNG文件格式。

这种技术的优点是 `img` 元素及其属性可以保持不变，这将为现有站点带来最佳兼容性，并确保向web优化图像交付过渡的最顺畅路径。

### 我能否将Web优化的图像交付与我自己的组件结合使用？

可以，自定义组件可以使用Web优化的图像交付服务。 Adobe建议 [扩展图像组件](/help/developing/customizing.md) 在这种情况下。

以下是一个服务界面，可用于帮助生成资产URL。

```
com.adobe.cq.wcm.spi.AssetDelivery.getDeliveryURL(Resource resource, Map<String, Object> parameterMap)
```

此服务将资产资源作为第一个必需参数，并且可以为要应用的所需图像转换（可选映射，其中可能包含以下参数）进行映射。

* `path`  — 要交付的资产ID必须符合模式 `([^:\[\]\|\*\/]+)` (例如： `unicorn–1234`)
* `seoname`  — 要附加到图像URL中的以用户定义的以SEO为中心的名称，可能包含连字符，必须为模式名称 `([\w-]+)` (例如： `my-friend-the-unicorn`)
* `format`  — 所需的图像格式可以 `gif`, `png`, `png8`, `jpg`, `pjpg`, `bjpg`, `webp`, `webpll`, `webply` (例如： `webp`)
* `preferwebp`  — 如果可能，传送WebP输出，忽略 `format` 参数([请参阅关于内容协商的常见问题解答](#content-negotiation))，布尔值(例如： `true`)
* `width`  — 所需的图像分辨率（以像素为单位）必须大于1(例如： `400`)
* `quality`  — 所需的压缩，介于 `1` 和 `100` (例如： `75`)
* `c`  — 所需的图像裁剪坐标、以逗号分隔的像素值(例如： `100,100,400,200`)
* `r`  — 所需的图像旋转可以 `90`, `180`, `270` (例如： `90`)
* `flip`  — 所需的图像翻转，可以 `h`, `v`, `hv` (例如： `h`)

### 新图像服务交付的图像的URL是什么？ {#url}

请参阅上一节 [激活核心组件的Web优化图像交付](#activating) 例如URL和正则表达式。

### 启用Web优化图像后，图像是否无法显示？

不，这不该发生。

* 在HTML中，启用Web优化图像时，标记不会更改，只有图像元素上SCR属性的值会更改。
* 当新图像服务不可用或无法处理所需的图像时，将生成URL [回退到自适应图像Servlet。](#fallback)
* 调度程序规则可能会阻止Web优化的图像服务和 [激活该功能时应选中。](#activating)
