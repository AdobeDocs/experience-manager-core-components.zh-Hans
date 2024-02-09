---
title: AEM 项目原型
description: 了解 AEM 项目原型，它用作基于 AEM 的应用程序的模板。
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: 58994726-9b65-4035-9d45-60b745d577bb
source-git-commit: 8940285f4c5e5870b6a135dac674f06e4c1d8b5a
workflow-type: ht
source-wordcount: '527'
ht-degree: 100%

---


# AEM 项目原型 {#aem-project-archetype}

AEM 项目原型是一个 Maven 模板，它创建最小的基于最佳实践的 Adobe Experience Manager (AEM) 项目作为您网站的起点。本文档概述了原型的优点和一般用法。详细的技术说明和文档可以在原型 GitHub 存储库中找到。

>[!TIP]
>
>最新的 AEM 项目原型和相关技术文档[可以在 GitHub 上找到](https://github.com/adobe/aem-project-archetype)。

## 为什么使用原型 {#why-use-the-archetype}

利用 AEM 项目原型，您只需按几下键即可构建基于最佳实践的 AEM 项目。通过使用原型，所有部分都已准备就绪，即便生成的项目最小，它也实施了 AEM 的所有[主要功能](/help/developing/archetype/using.md#what-you-get)，您只需在其基础上进行构建和扩展。

当然，[成功的 AEM 项目](/help/developing/success.md)涉及很多要素，而使用 AEM 项目原型可以奠定坚实的基础，强烈建议对任何 AEM 项目这样做。

## 功能 {#features}

* **最佳实践：**&#x200B;使用 Adobe 的所有最新推荐实践引导您的网站。
* **少量代码：**&#x200B;编辑您的模板、创建内容、部署您的 CSS，您的网站就可以上线了。
* **云就绪：**&#x200B;如果需要，使用 [AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html) 在几天内上线并简化可扩展性和维护。
* **Dispatcher：**&#x200B;只能通过可确保速度和安全性的 [Dispatcher 配置](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/dispatcher.html)完成项目。
* **多站点：**&#x200B;如果需要，原型将为[多语言和多区域设置](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/msm/overview.html)生成内容结构。
* **核心组件：**&#x200B;作者可以使用我们通用的[标准化组件集](/help/introduction.md)创建几乎任何布局。
* **可编辑模板：**&#x200B;收集几乎任何[不带代码的模板](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/page-authoring/template-editor-feature-video-use.html)，并定义作者可编辑的内容。
* **响应式布局：**&#x200B;在模板或单个页面上，为定义的断点[定义元素的重排方式](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/get-started/localization.html)。
* **页眉和页脚：**&#x200B;收集页眉和页脚，并使用[组件的本地化功能](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/get-started/localization.html)将其本地化而不是使用代码。
* **样式系统：**&#x200B;通过允许作者向自定义组件[应用不同的样式](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/project-archetype/style-system.html)来避免构建这些组件。
* **前端构建**：前端开发人员可以[使用 Webpack、TypeScript 和 SASS ](front-end.md)模拟 AEM 页面和构建客户端库。
* **Web 应用程序就绪**：对于使用 React 或 Angular 的网站，使用 [SPA 开发工具包](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/hybrid/developing.html)保持[应用程序的上下文中创作](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html)。
* **启用 Commerce：**&#x200B;对于要将 [AEM Commerce](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content-and-commerce/home.html) 与 [Magento](https://magento.com/) 等商业解决方案集成的项目，使用 [Commerce 核心组件](https://github.com/adobe/aem-core-cif-components)。
* **示例代码：**&#x200B;查看 HelloWorld 组件以及示例模型、servlet、过滤器和调度程序。
* **开源：**&#x200B;如果有出错的地方，请[做出](https://github.com/adobe/aem-core-wcm-components/blob/master/CONTRIBUTING.md)您的改进！

## 深入阅读 {#further-reading}

* **[AEM 项目原型 GitHub](https://github.com/adobe/aem-project-archetype)** - 有关原型的完整用法和技术详细信息
* **[使用原型](using.md)** - 概述如何在项目中使用原型以及生成的结果模块
* **[使用 AEM 项目原型进行前端开发](front-end.md)** - 如何使用原型的前端模块
* **以下教程基于该原型：**
   * **[WKND 网站](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)** - 了解如何启动全新的网站。
   * **[WKND 单页面应用程序](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/spa-editor/spa-editor-framework-feature-video-use.html)** - 了解如何构建可完全在 AEM 中创作的 React 或 Angular Web 应用程序。
