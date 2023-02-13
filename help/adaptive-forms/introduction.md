---
title: AEM自适应Forms核心组件简介
description: 使用自适应Forms核心组件的灵活性创建引人入胜的注册体验（表单），并借助Adobe Experience Manager的强大功能提供。
role: Architect, Developer, Admin, User
source-git-commit: b378fbd5695f82b8fc9de3a2d53a8387099ae33b
workflow-type: tm+mt
source-wordcount: '1028'
ht-degree: 13%

---


# 自适应Forms核心组件简介 {#adaptive-forms-core-components-introduction}

使用Adobe Experience Manager中的自适应Forms核心组件，您可以利用可用的灵活性和自定义选项，创建引人入胜的注册体验。

## 核心组件  {#overview}

在Adobe Experience Manager(AEM)中，组件是用于创建页面和表单的构建基块。 它们为作者提供了创建和管理内容的简单而强大的方式，同时也为开发人员提供了创建自定义组件所需的灵活性和可扩展性。 这些功能旨在加快开发时间并降低网站和表单的维护成本，灵活且易于定制，以满足网站和表单的特定需求。

核心组件还旨在提供响应性，并支持多种设备，包括台式机、平板电脑和智能手机。 它们还遵循最新的Web标准和最佳实践，使其成为用于创建Web内容的可靠解决方案。

总的说来，核心组件是在AEM中创建和管理Web内容的必不可少的工具，它提供了一个功能强大且灵活的解决方案，有助于减少开发时间和维护成本，同时也为网站访客提供了绝佳的用户体验。

## 自适应Forms核心组件

自适应Forms核心组件是一组24个符合BEM规范的开源组件，这些组件是在Adobe Experience Manager WCM核心组件的基础上构建的。 它们专门用于创建自适应Forms，自适应Adaptive Manager是根据用户的设备、浏览器和屏幕大小而调整的表单。

这些组件可用于通过提供各种表单字段选项（包括文本字段、复选框、下拉菜单等）来创建出众的数据捕获和注册体验。 这些功能还包括验证、条件逻辑和响应式设计等功能，可用于创建用户友好且易于使用的表单。

此外，由于这些组件是开源的，开发人员能够轻松自定义和扩展组件，以满足其组织的特定需求。 此外，这些组件是基于边界元方法构建的，可确保它们具有可扩展性和可维护性。

![](assets/sample-adaptive-form.png)

## 功能 {#features}

|  |  |
|---|---|
| 可以即刻投入使用 | 自适应Forms核心组件是24个强大的WCM组件。 |
| 云就绪 | 可用  [AEM Formsas a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/home.html). |
| 可以通用 | 这些组件表示通用概念，Forms作者可以使用这些概念来组合几乎任何布局。 |
| 可配置 | 模板级别 [内容策略](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developing/full-stack/components-templates/templates.html?lang=zh-Hans#content-policies) 定义允许使用或不使用的功能。 |
| 可访问 | 它们提供ARIA标签，支持键盘导航([已知问题](https://github.com/adobe/aem-core-wcm-components/issues?utf8=✓&amp;q=is%3Aissue+is%3Aopen+accessibility+in%3Atitle))，以及用于屏幕阅读器等辅助技术的文本。 |
| 主题表 | 这些组件实施[样式系统](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/features/style-system.html?lang=zh-Hans)，且标记遵循 [BEM CSS 约定](https://getbem.com/)。 |
| 可自定义 | 可利用几种模式来轻松进行自定义设置（从调整 HTML 到高级功能重用）。 |
| 版本控制 | [版本控制策略](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-policies)可确保核心组件在改进可能影响您的内容时不会中断您的网站。 |
| 开源 | 如果某件事不如应有，请贡献您的改进。 |

<!-- comply with [WCAG 2.1 standard](https://www.w3.org/TR/WCAG21/), -->


## 好处 {#benefits}

数据捕获体验对于潜在客户生成和注册至关重要，而自适应Forms核心组件为创建针对数据捕获进行优化的表单提供了功能强大的解决方案。 使用核心组件创建这些体验与基础组件相关的一些原因包括：

* **GitHub上的可用性和全面的文档**:AEM自适应Forms核心组件是开源组件，可在GitHub上获取，同时还提供了完整的文档。 这样，开发人员便可以更轻松地了解组件及其工作方式，并为开发做出贡献。 的 [aemcomponents.dev](https://www.aemcomponents.dev/) 网站也是一个宝贵的资源，开发人员可以在其中查看各个组件的实际操作情况并访问详细文档。

* **BEM造型模型**:核心组件遵循BEM（块元素修饰符）模型来进行样式设置，该模型是一种建立良好且广泛使用的CSS组织方法。 这样，开发人员就可以更轻松地了解样式的组织方式，以及如何根据自己的特定需求对样式进行修改。

* **不依赖第三方库**:核心组件的一个优势是它们不依赖于第三方JavaScript库，包括JQuery和下划线。 这样可以更快、更轻巧地集成组件，并更轻松地集成到现有AEM实施中。

* **将重点放在性能和辅助功能上**:核心组件构建时考虑了性能和辅助功能，这反映在其高Google灯塔和Web生命体系得分中。 这样，开发人员便于创建无障碍且高性能的网页，在当今的数字环境中，这越来越重要。

* **站点30模板和主题中的表单组件**:核心组件支持站点30模板和主题中的表单组件，从而更便于开发人员在AEM中创建和自定义表单。

* **更易于设置样式**:与基础组件相比，核心组件的样式更简单。 主题创建过程与站点类似，能够从父站点页面继承相同的主题/CSS。 此外，样式的BEM模型使您更容易理解和修改样式。

* **辅助功能**:自适应Forms核心组件支持无障碍标准和准则，以确保残障人士（包括使用屏幕阅读器等辅助技术的残障人士）可以使用表单


<!-- >, such as  [WCAG 2.1 standard](https://www.w3.org/TR/WCAG21/), to ensure that forms can be used by people with disabilities, including those using assistive technologies such as screen readers.

*   **Alignment with AEM Sites**: The Core Components are designed to be more aligned with AEM Sites, making it easier for Sites users to adopt and use them without having to learn anything new. The components use the same front-end pipeline as Sites, making it easier to style and modify their appearance. 

<!-- Additionally, the following points further illustrate this alignment:

    *   **Authoring experience inline with Page editor**: The Core Components have an authoring experience that is inline with the Sites editor, with dialogs and other experiences similar to the Page editor. This makes it easier for Sites users to create and manage forms within the familiar context of the Sites editor.

    *   **Inline form editing in Sites editor**: The Core Components allow  inline form editing within the Sites editor, avoiding the need to switch back and forth between editors. This streamlines the authoring experience and makes it easier to create and manage forms.

    *   **Inheriting Sites features in Forms**: Forms authored within a Sites page inherit the same features as Sites. This provides a seamless and integrated experience for creating and managing forms within the context of AEM Sites 
    
    <!--including Multi Site Manager, the ability to use Sites components within a form for static content, support for scheduled publish/unpublish, form translation aligned with Sites translation, versioning, and targeting -->



## 要求 {#requirements}

自适应Forms核心组件具有以下要求。

| AEM | AEM Forms附加组件 | 核心组件 |
|---|---|---|
| AEM as a Cloud Service | Forms — 数字注册 | [2.20.8](/help/versions.md) 和更高版本 |


## 自适应Forms核心组件 {#components}

您可以使用 [自适应Forms编辑器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html) 创建基于核心组件的自适应Forms。 自适应Forms核心组件的当前版本具有以下列出的组件。

* 折叠
* 按钮
* 复选框组
* 日期选取器
* 下拉列表
* 电子邮件输入
* 表单容器
* 文件附件
* 页脚
* 标题
* 水平选项卡
* 图像
* 数字输入
* 窗格容器
* 单选按钮
* 重置按钮
* 提交按钮
* 电话输入
* 文本输入
* 文本
* 标题
* 向导

