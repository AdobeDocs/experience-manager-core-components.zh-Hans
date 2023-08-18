---
title: 自定义自适应Forms核心组件
description: 了解如何扩展或创建自适应Forms核心组件，以实施为您的组织定制的功能。
role: Architect, Developer, Admin
source-git-commit: 9a80b453d6a6cf7b347128654d3b5e673a063505
workflow-type: tm+mt
source-wordcount: '707'
ht-degree: 4%

---


# 自定义自适应Forms核心组件

通过自定义自适应Forms核心组件，您可以根据特定需求定制现成的功能。 本指南将指导您完成自定义这些组件以创建更加个性化的体验的过程。

## 先决条件

在尝试自定义自适应Forms核心组件之前，

* 了解 [核心组件的架构](customizing.md#customizing-the-markup-customizing-the-markup) 然后通过 [Adobe Experience Manager核心组件官方文档](customizing.md). 这些全面的资源在整个自定义过程中充当您的指南。
* 设置开发环境这可以确保用于更改核心组件的流畅工作流。 在设置开发环境时，请使用基于最新AEM原型项目的AEM原型项目。 根据您的环境，您可以：

   * [为Formsas a Cloud Service设置本地开发环境](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/setup-configure-migrate/setup-local-development-environment.html).
   * [为AEM 6.5 Forms设置本地开发环境](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html?lang=zh-Hans)

## 自定义自适应Forms核心组件

请按照以下步骤修改自适应Forms核心组件的外观、行为和功能。

1. **识别并复制核心组件**

   在配置开发环境时，您已创建一个基于原型的项目。 在AEM原型项目中，标识要自定义的特定核心组件。 标识后，在基于AEM原型的项目中创建一个组件副本。 请将其与其他自适应Forms核心组件保持并行。 此步骤可确保您的自定义操作不会影响原始组件，从而允许您自由进行试验。

1. **自定义复制的组件**

   打开复制的组件，然后根据您的要求开始进行必要的修改：

   * **自定义HTML结构**：定制HTML结构以满足您的设计需求，同时遵循 [BEM（块元素修改量）](https://github.com/adobe/aem-core-wcm-components/wiki/css-coding-conventions) 可维护且可伸缩代码的样式惯例。
   * **更新标签**：更新组件的标签，为自定义版本提供清楚的描述性名称。 请参阅提供的 [OOTB（现成）标签模板](https://github.com/adobe/aem-core-forms-components/blob/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/af-commons/v1/fieldTemplates/label.html) 以保持一致性。
   * **自定义构件**：调整在组件中使用的构件（下拉列表、复选框），使其与您的特定用例保持一致。 请参见 [构件实施示例](https://github.com/adobe/aem-core-forms-components/blob/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/textinput/v1/textinput/textinput.html) 以供参考。
   * **帮助文本和工具提示**：个性化与组件关联的帮助文本或工具提示，为用户提供上下文和指导。 使用 [OOTB帮助文本模板](https://github.com/adobe/aem-core-forms-components/blob/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/af-commons/v1/fieldTemplates/questionMark.html) 作为起点。
   * **数据属性**：在组件的HTML元素中合并所有必需的数据属性。 这些属性对于组件在运行时正常运行至关重要。 请参阅 [文档](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/textinput/v1/textinput) 了解数据属性在自适应Forms核心组件中的作用。

1. **实施后端逻辑**

   如果您的自定义需要后端逻辑，则可以扩展现有Sling模型。 请参阅提供的 [示例](https://github.com/adobe/aem-core-forms-components/blob/master/bundles/af-core/src/main/java/com/adobe/cq/forms/core/components/internal/models/v1/form/TextInputImpl.java) 将所需的功能无缝集成到您的自定义组件中。

1. **配置组件的对话框**

   配置与自定义组件关联的对话框。 使用示例 [组件对话框](https://github.com/adobe/aem-core-forms-components/blob/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/textinput/v1/textinput/_cq_dialog/.content.xml) 在文档中提供，以确保正确管理用户交互和设置。

1. **在本地开发环境中部署和测试组件**

   使用 [maven ，用于构建和部署组件](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/developing/archetype/using.html#building-and-installing) 本地开发环境中的。 部署组件后，创建自适应表单以测试自定义组件。

1. **在生产环境中部署自定义组件**

   在本地开发环境中测试组件后，在生产环境中部署该组件。

