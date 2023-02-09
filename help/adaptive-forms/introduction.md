---
title: AEM自适应Forms核心组件简介
description: 使用自适应Forms核心组件的灵活性创建引人入胜的注册体验（表单），并借助Adobe Experience Manager的强大功能提供。
role: Architect, Developer, Admin, User
source-git-commit: 781cf351ef52cbb56ff33c2674c8af591c81a30e
workflow-type: tm+mt
source-wordcount: '1069'
ht-degree: 13%

---


# 自适应Forms核心组件简介 {#adaptive-forms-core-components-introduction}

使用Adobe Experience Manager中的自适应Forms核心组件，您可以利用可用的灵活性和自定义选项，创建引人入胜的注册体验。

## 核心组件  {#overview}

在Adobe Experience Manager(AEM)中，组件是用于创建页面和表单的构建基块。 它们为作者提供了创建和管理内容的简单而强大的方式，同时也为开发人员提供了创建自定义组件所需的灵活性和可扩展性。

核心组件是一组预建的标准化WCM组件，旨在加快网站的开发时间并降低网站维护成本。 这些组件包括文本字段、图像、视频等内容。 这些功能设计得灵活，可轻松自定义以满足网站的特定需求。

核心组件还旨在提供响应性，并支持多种设备，包括台式机、平板电脑和智能手机。 它们还遵循最新的Web标准和最佳实践，使其成为用于创建Web内容的可靠解决方案。

此外，核心组件构建为可与AEM的其他部分无缝协作，使作者和开发人员能够以更少的工作量和更少的时间创建更具吸引力的交互式表单。

总的说来，核心组件是在AEM中创建和管理Web内容的必不可少的工具，它提供了一个功能强大且灵活的解决方案，有助于减少开发时间和维护成本，同时也为网站访客提供了绝佳的用户体验。

在Adobe Experience Manager中，组件是构成所创作页面和表单内容的结构元素。 组件一直是AEM体验的一个基本元素，它使页面和表单的创建变得简单但功能强大，并且对开发人员而言，组件的开发也变得灵活和可扩展。 核心组件是一组标准化的Web内容管理(WCM)组件，可加快开发时间并降低网站维护成本。

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
| 可访问 | 他们遵守 [WCAG 2.1标准](https://www.w3.org/TR/WCAG21/)，提供ARIA标签，支持键盘导航([已知问题](https://github.com/adobe/aem-core-wcm-components/issues?utf8=✓&amp;q=is%3Aissue+is%3Aopen+accessibility+in%3Atitle))，以及用于屏幕阅读器等辅助技术的文本。 |
| 可主题化 | 这些组件实施[样式系统](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/features/style-system.html?lang=zh-Hans)，且标记遵循 [BEM CSS 约定](http://getbem.com/)。 |
| 可自定义 | 可利用几种模式来轻松进行自定义设置（从调整 HTML 到高级功能重用）。 |
| 版本控制 | [版本控制策略](https://github.com/adobe/aem-core-wcm-components/wiki/Versioning-policies)可确保核心组件在改进可能影响您的内容时不会中断您的网站。 |
| 开源 | 如果某件事不如应有，请贡献您的改进。 |

## 好处 {#benefits}

数据捕获体验对于潜在客户生成和注册至关重要，而自适应Forms核心组件为创建针对数据捕获进行优化的表单提供了功能强大的解决方案。 使用核心组件创建这些体验的一些原因包括：

* **自定义**:自适应Forms核心组件允许开发人员轻松自定义表单组件（如文本字段、复选框和下拉菜单）的外观和行为，以满足特定要求。

* **辅助功能**:自适应Forms核心组件支持无障碍标准和准则，例如  [WCAG 2.1标准](https://www.w3.org/TR/WCAG21/)，以确保残障人士（包括使用屏幕阅读器等辅助技术的残障人士）能够使用表单。

* **一致的表单**:通过使用自适应Forms核心组件，开发人员可以创建外观一致的表单，从而更便于用户理解和填写表单，从而提高参与度并改善用户体验。

* **WYSIWYG编辑器**:AEM Forms提供用户友好界面，易于使用WYSIWYG编辑器来使用这些组件创建自适应表单。 它允许表单作者创建和编辑表单，而无需知道如何进行代码。 它还包含一个可视化规则编辑器，可帮助您轻松创建基于规则的操作并实施复杂的逻辑，以便自动执行表单行为，而无需编写代码。

* **条件逻辑**:自适应Forms核心组件支持使用条件逻辑，这意味着可以根据用户输入的值更改表单组件的外观或行为。 例如，某些字段可以隐藏，或根据在其他字段中所做的选择设为必填字段。

* **数据验证**:自适应Forms核心组件提供内置数据验证功能，允许开发人员确保用户输入的数据符合特定条件，如最小和最大长度、所需值和特定格式。

## 要求 {#requirements}

自适应Forms核心组件具有以下要求。

| AEM | AEM Forms附加组件 | 核心组件 |
|---|---|---|
| AEM as a Cloud Service | Forms — 数字注册 | [2.20.8](/help/versions.md) 和更高版本 |


## 自适应Forms核心组件 {#components}

自适应Forms核心组件的当前版本具有以下组件。

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

