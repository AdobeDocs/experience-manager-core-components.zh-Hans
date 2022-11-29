---
title: 电子邮件核心组件简介
description: 使用电子邮件核心组件的灵活性创建吸引人的电子邮件内容，并利用 Adobe Campaign 的强大功能进行交付。
role: Architect, Developer, Admin, User
exl-id: 0a411f28-bd6a-4bad-b473-6bc27c1d1055
source-git-commit: 33976c0e745ad091a142109f70541f01a31edc5b
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 88%

---


# 电子邮件核心组件简介 {#email-core-components-introduction}

使用电子邮件核心组件的灵活性创建吸引人的电子邮件内容，并利用 Adobe Campaign 的强大功能进行交付。

## 概述 {#overview}

电子邮件核心组件建立在与核心组件相同的强大基础之上。 这些组件支持对电子邮件内容进行简单灵活的拖放式创作，然后可以使用 Adobe Campaign 的强大功能将其交付给您的受众。

## 好处 {#benefits}

电子邮件是品牌体验和客户历程的一部分。 借助电子邮件核心组件，您的作者可以在 AEM 中制作电子邮件内容，提供一致的品牌体验，从而提高内容速度。

* 就像使用核心组件创作页面一样，电子邮件核心组件允许作者在没有技术知识的情况下组装电子邮件，同时确保他们遵循品牌指南。
* 资产和内容重用功能还鼓励作者遵循品牌指南并优化内容创建过程。

## 功能 {#features}

* 核心电子邮件组件基于[核心组件](/help/introduction.md)，因此还支持[可编辑模板](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=zh-Hans)和[样式系统。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/features/style-system.html?lang=zh-Hans)
* 有[十个电子邮件优化的生产就绪组件](#components)创作电子邮件内容。
* 由于插入了 [Adobe Campaign变量](campaign-variables.md) 在大多数对话框字段中。
* 灵活 [分段组件](/help/email/components/segmentation.md) 允许对内容进行高级分段。
* 由于[CSS 样式内联、](https://github.com/adobe/aem-core-email-components/wiki/CSS-Styles-Inliner: — 技术文档)[HTML 属性内联、](https://github.com/adobe/aem-core-email-components/wiki/HTML-Inliner)和 [HTML 清理器，](https://github.com/adobe/aem-core-email-components/wiki/HTML-Sanitizing)核心电子邮件组件提供了最佳的电子邮件友好型 HTML 输出。
* 您可以在 `/content` 以下的任何位置创建电子邮件内容。
* 电子邮件核心组件是[开源的。](https://github.com/adobe/aem-core-email-components)

## 要求 {#requirements}

电子邮件核心组件具有以下要求。

| AEM | Adobe Campaign | 核心组件 |
|---|---|---|
| AEM 6.5.14.0+<br>内部部署或AMS。 | Adobe Campaign Classic<br>Adobe Campaign Standard | [版本2.21.2](/help/versions.md)+ |

>[!NOTE]
>
>由于 AEM as a Cloud Service 不支持 Adobe Campaign 集成，因此 AEM as a Cloud Service 也不支持电子邮件核心组件。

## 电子邮件组件 {#components}

当前版本的电子邮件核心组件具有以下组件。

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

有关安装电子邮件核心组件的详细信息，请参阅[使用电子邮件核心组件](using.md)文档。
