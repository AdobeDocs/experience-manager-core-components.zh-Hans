---
title: 电子邮件核心组件简介
description: 利用电子邮件核心组件的灵活性创建引人入胜的电子邮件内容，并借助Adobe Campaign的强大功能进行交付。
role: Architect, Developer, Admin, User
hidefromtoc: true
index: false
source-git-commit: 8bebe3ca036557f3f7c6b8ec0e65d6d104d5ffae
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 电子邮件核心组件简介 {#email-core-components-introduction}

利用电子邮件核心组件的灵活性创建引人入胜的电子邮件内容，并借助Adobe Campaign的强大功能进行交付。

## 概述 {#overview}

电子邮件核心组件构建于核心组件的相同强大基础之上。 它们允许对电子邮件内容进行简单而灵活的拖放创作，随后，这些内容可通过Adobe Campaign的强大功能交付给受众。

## 好处 {#benefits}

电子邮件是品牌体验和客户历程的一部分。 借助电子邮件核心组件，作者可以在AEM中创作电子邮件内容，从而提供一致的品牌体验，从而提高内容速度。

* 与使用核心组件创作页面一样，电子邮件核心组件允许作者在没有技术知识的情况下组合电子邮件，同时确保他们遵循品牌策略准则。
* 重复使用资产和内容的功能还鼓励作者遵循品牌策略准则并优化内容创建过程。

## 功能 {#features}

* 核心电子邮件组件基于 [核心组件、](/help/introduction.md) 因此也支持 [可编辑的模板](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=zh-Hans) 和 [样式系统。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/features/style-system.html?lang=zh-Hans)
* 有 [十个电子邮件优化的生产就绪组件](#components) 创作电子邮件内容。
* 由于在大多数对话框字段中插入了Adobe Campaign变量，核心电子邮件组件提供了高级个性化。
* 灵活的分段组件允许对内容进行高级分段。
* 核心电子邮件组件可通过 [CSS样式内嵌件、](https://github.com/adobe/aem-core-email-components/wiki/CSS-Styles-Inliner) [HTML属性内线，](https://github.com/adobe/aem-core-email-components/wiki/HTML-Inliner) 和 [HTML消毒剂。](https://github.com/adobe/aem-core-email-components/wiki/HTML-Sanitizer)
* 您可以在下面的任意位置创建电子邮件内容 `/content`.
* 电子邮件核心组件包括 [打开源。](https://github.com/adobe/aem-core-email-components)

## 要求 {#requirements}

电子邮件核心组件具有以下要求。

| AEM | Adobe Campaign | 核心组件 |
|---|---|---|
| AEM 6.5.x.y（内部部署或AMS） | Adobe Campaign Classic vX<br>或<br>Adobe Campaign Standard | [X版](/help/versions.md) 或更高 |

>[!NOTE]
>
>由于AEMas a Cloud Service不支持Adobe Campaign集成，因此AEMas a Cloud Service也不支持电子邮件核心组件。

## 电子邮件组件 {#components}

电子邮件核心组件的当前版本具有以下组件。

* [页面](components/page.md)
* [容器](components/container.md)
* [标题](components/title.md)
* [文本](components/text.md)
* [图像](components/image.md)
* [按钮](components/button.md)
* [Teaser](components/teaser.md)
* [体验片段](components/experience-fragment.md)
* [内容片段](components/content-fragment.md)
* [分段](components/segmentation.md)

## 安装和使用 {#installation-usage}

请参阅 [使用电子邮件核心组件](using.md) 有关安装电子邮件核心组件的详细信息的文档。
