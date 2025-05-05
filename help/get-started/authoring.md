---
title: 通过核心组件创作
description: 在 AEM 中，组件是结构化元素，用于构成所创作的页面内容 - 核心组件提供了灵活且丰富的创作功能。
role: Architect, Developer, Admin, User
exl-id: 56e58303-a178-45ab-b59d-e374c9cf90cf
source-git-commit: 945e1793ae4e959f83960db46d2de4257916fe32
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 100%

---

# 通过核心组件创作

在 Adobe Experience Manager 中，组件是结构化元素，用于构成所创作的页面内容。

核心组件提供了灵活且丰富的创作功能。[WKND 参考网站](https://wknd.site)说明了如何使用核心组件实施丰富的网站体验。

要体验核心组件并查看其配置选项示例以及 HTML 和 JSON 输出，请访问[组件库](https://adobe.com/go/aem_cmp_library_cn)。

对于使用 [AEM 项目原型](/help/developing/archetype/overview.md)在 AEM 项目上实施核心组件，有关面向开发人员的更加深入的信息，请查看 [WKND 教程](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html?lang=zh-Hans)。

>[!NOTE]
>
>核心组件不可直接供作者使用，[开发团队必须先将它们集成到您的环境中](/help/get-started/using.md)。在集成后，可通过[模板编辑器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=zh-Hans)使其可用并进行预配置。

>[!CAUTION]
>
>核心组件[需要 AEM 6.4 或更高版本](/help/versions.md)，并需要使用[可编辑的模板](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=zh-Hans)。它们不适用于经典 UI，也不能用于静态模板。

## 通过核心组件创作 {#authoring-with-core-components}

作为作者，您会发现核心组件具备多种优势，包括：

* 简单易用，并与[页面编辑器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html?lang=zh-Hans)很好地集成

* 具有丰富的功能，可以适应 [WKND 参考网站](https://wknd.site)以及[组件库](https://adobe.com/go/aem_cmp_library_cn)中所述的多种使用案例

* 可通过[模板编辑器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=zh-Hans)进行[预先配置](#pre-configuring-core-components)，以定义可供页面作者使用的功能

* 根据[无障碍指南](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/accessible-content.html?lang=zh-Hans)构建

* 构建用于支持[响应式布局](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/responsive-layout.html?lang=zh-Hans)

* 构建用于支持 [轻松本地化](localization.md)

在[编辑页面](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html?lang=zh-Hans)时，组件在页面编辑器侧面板的&#x200B;**“组件”**&#x200B;选项卡上可用。

组件根据类别分组为组件组，以轻松地排列和筛选组件。组件组名称与组件一起显示在[组件浏览器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html?lang=zh-Hans)中，还可以按组筛选以轻松地查找合适的组件。

>[!NOTE]
>
>默认情况下，核心组件是隐藏组的一部分，在组件浏览器中不可见。
>
>将所需的组件添加到可见组或者自定义这些组，以使其对作者可见。

## 预配置核心组件 {#pre-configuring-core-components}

配置基础组件是开发人员的工作。但是，对于核心组件，模板作者现在可以通过模板编辑器配置大量的功能。

例如，如果某个图像组件不应允许从文件系统上传图像，或者如果某个文本组件只应允许特定段落格式，则可以通过一次简单的单击来启用或禁用这些功能。

有关更多信息，请参阅[创建页面模板](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=zh-Hans)。

### “编辑”和“设计”对话框 {#edit-and-design-dialogs}

由于模板作者可以预配置核心组件来定义模板中允许哪些选项，然后由页面作者进一步配置来定义实际页面内容，因此每个组件可以在两个不同的对话框中具有选项。

|  | 描述 | 控制内容 | 示例 |
|--- |--- |--- |--- |
| **“编辑”对话框** | 在对所放置组件进行正常页面编辑期间，**页面作者**&#x200B;可以修改的选项 | 组件显示的内容及其最终显示在页面上的样式。 | 内容文本的格式化，旋转页面上的图像 |
| **“设计”对话框** | **模板作者**&#x200B;在配置页面模板时可以修改的选项 | 页面作者在编辑组件时可以使用的选项 | 哪些文本格式化选项可用，哪些图像就地选项可用 |

### 组件样式 {#component-styling}

大部分核心组件的样式可以使用 AEM 样式系统定义。

* 模板作者可以在特定组件的“设计”对话框中，定义哪些样式可供该组件使用。
* 然后，内容作者可以在添加组件和创建内容时，选择应用哪些样式。

有关更多详细信息，请参阅[样式系统](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/style-system.html?lang=zh-Hans)文档。

## 开发人员资源 {#developer-resources}

有关核心组件的技术信息，请参阅[开发核心组件](/help/developing/overview.md)开发人员文档。
