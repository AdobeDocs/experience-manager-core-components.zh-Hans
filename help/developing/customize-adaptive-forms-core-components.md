---
title: 自定义自适应表单核心组件
description: 了解扩展或创建自适应表单核心组件以实现为您的组织量身定制的功能。
role: Architect, Developer, Admin
exl-id: f3ab12aa-d48d-47e9-a965-15052cac6f18
source-git-commit: 5994133947ff697f7c866fe61598c58e37e77008
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 100%

---

# 自定义自适应表单核心组件

自定义自适应表单核心组件允许您定制开箱即用的功能以满足您的特定需求。本指南将引导您完成自定义这些组件以创建更加个性化的体验的过程。

{{traditional-aem}}

## 先决条件

在深入定制自适应表单核心组件之前，

* 了解有关[核心组件的架构](customizing.md#customizing-the-markup-customizing-the-markup)并浏览[官方 Adobe Experience Manager 核心组件文档](customizing.md)。这些综合资源可在整个定制过程中为您提供指导。
* 设置您的开发环境，这可以确保对核心组件进行更改的顺利工作流程。设置开发环境时，使用基于最新 AEM Archetype 项目的 AEM Archetype 项目。根据您的环境，您可以：

   * [为 Forms as a Cloud Service 设置本地开发环境](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/setup-configure-migrate/setup-local-development-environment.html?lang=zh-Hans)。
   * [为 AEM 6.5 Forms 设置本地开发环境](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html?lang=zh-Hans)

## 自定义自适应表单核心组件

请按照以下步骤修改自适应表单核心组件的外观、行为和功能。

1. **识别并复制核心组件**

   在配置开发环境时，您已经创建了一个基于 Archetype 的项目。在 AEM Archetype 项目中，标识您想要自定义的特定核心组件。确定后，在基于 AEM Archetype 的项目中创建该组件的副本。使其与其他自适应表单核心组件保持并行。此步骤可确保您的定制工作不会影响原始组件，从而使您可以自由地进行试验。

1. **自定义复制的组件**

   打开复制的组件并开始根据您的要求进行必要的修改：

   * **自定义 HTML 结构**：定制 HTML 结构以满足您的设计需求，同时遵循[BEM（块元素修改器）](https://github.com/adobe/aem-core-wcm-components/wiki/css-coding-conventions)可维护和可扩展代码的样式实践。
   * **更新标签**：更新组件的标签，为定制版本提供清晰的描述性名称。为了一致性，请参考提供的[OOTB（开箱即用）标签模板](https://github.com/adobe/aem-core-forms-components/blob/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/af-commons/v1/fieldTemplates/label.html)。
   * **自定义小组件**：调整组件中使用的小组件（下拉列表、复选框）以符合您的特定用例。查看[示例小组件实施](https://github.com/adobe/aem-core-forms-components/blob/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/textinput/v1/textinput/textinput.html)以供参考。
   * **帮助文本和工具提示**：个性化与组件关联的帮助文本或工具提示，为用户提供上下文和指导。使用[OOTB 帮助文本模板](https://github.com/adobe/aem-core-forms-components/blob/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/af-commons/v1/fieldTemplates/questionMark.html)作为起点。
   * **数据属性**：将所有必要的数据属性合并到组件的 HTML 元素中。这些属性对于组件在运行时的正常运行至关重要。咨询[文档](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/textinput/v1/textinput)了解数据属性在自适应表单核心组件中的角色。

1. **实施后端逻辑**

   如果您的定制需要后端逻辑，您可以扩展现有的吊索模型。参考提供的[示例](https://github.com/adobe/aem-core-forms-components/blob/master/bundles/af-core/src/main/java/com/adobe/cq/forms/core/components/internal/models/v1/form/TextInputImpl.java)，将所需的功能无缝集成到您的定制组件中。

1. **配置组件的对话框**

   配置与您的自定义组件关联的对话框。使用文档中提供的示例[组件对话框](https://github.com/adobe/aem-core-forms-components/blob/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/textinput/v1/textinput/_cq_dialog/.content.xml)，以确保用户交互和设置得到适当管理。

1. **在本地开发环境中部署并测试组件**

   根据您当地的开发环境，使用[Maven 来构建和部署组件](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/developing/archetype/using.html?lang=zh-Hans#building-and-installing)。部署组件后，创建一个自适应表单来测试自定义组件。

1. **在您的生产环境中部署自定义组件**

   在本地开发环境中测试组件后，将组件部署到生产环境中。
