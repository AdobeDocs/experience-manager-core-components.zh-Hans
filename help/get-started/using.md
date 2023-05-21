---
title: 使用核心组件
description: “要在您自己的项目中启动并运行核心组件，需要执行四个步骤：下载并安装、创建代理组件、加载核心样式和在模板上启用组件。”
role: Architect, Developer, Admin, User
exl-id: ee2d25e4-e2b8-4ecc-a62c-f0066de2bf2d
source-git-commit: 8beae61676340e8aafaee469018d865ea7ed934e
workflow-type: tm+mt
source-wordcount: '1008'
ht-degree: 100%

---

# 使用核心组件{#using-core-components}

要在您自己的项目中启动并运行核心组件，需要执行四个步骤，以下部分中分别详述了这些步骤：

1. [下载并安装](#download-and-install)
1. [创建代理组件](#create-proxy-components)
1. [加载核心样式](#load-the-core-styles)
1. [启用组件](#allow-the-components)

>[!TIP]
>
>要更详细地了解如何从头开始使用项目设置、核心组件、可编辑模板、客户端库和组件开发，以下包含多个部分的教程可能会对您有所帮助：\
>[《AEM Sites 快速入门》 - WKND 教程](https://experienceleague.adobe.com/docs/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)

>[!TIP]
>
>如果您使用 [AEM 项目原型，](/help/developing/archetype/overview.md)核心组件将根据 Adobe 的最佳实践建议自动包含在您的项目中。

## 下载并安装 {#download-and-install}

核心组件背后的驱动理念之一是灵活性。更频繁地发布新版本的核心组件可让 Adobe 更灵活地交付新功能。反过来，开发人员可以灵活地选择要集成到其项目中的组件以及所需的组件更新频率。这将使 AEM 和核心组件具有独立的发布流程。

因此，是运行 AEM as a Cloud service 还是内部部署将决定安装步骤。

### AEM as a Cloud Service {#aemaacs}

没有第一步！AEM as a Cloud Service 自动附带最新版本的核心组件。正如 AEMaaCS 为您提供 AEM 的最新功能一样，AEMaaCS 将自动为您提供最新版本的核心组件。

在 AEMaaCS 上使用核心组件时要记住以下几点：

* 核心组件包含在 `/libs` 中。
* 如果项目构建管道再次将核心组件包含为 `/apps` 的一部分，则会在日志中生成警告，并且将忽略作为项目的一部分嵌入的版本。
   * 在即将发布的版本中，再次包含核心组件将导致管道构建失败。
* 如果项目之前已将核心组件包含在 `/apps` 中，[您可能需要调整您的项目。](/help/developing/overview.md#via-aemaacs)
* 即使核心组件现在位于 `/libs` 中，也建议不要在 `/apps` 中创建同一路径的任何叠加。如果需要自定义组件的任何方面，则应改用[代理组件模式](/help/developing/guidelines.md#proxy-component-pattern)。
* 为了让[目录组件](/help/components/tableofcontents.md)呈现其内容，需要在 OSGi 中配置过滤器。
   * [有关更多信息，请参阅该组件的 GitHub 文档](https://adobe.com/go/aem_cmp_tech_tableofcontents_v1_cn)。

### AEM 6.5 及之前的版本 {#aem-65}

在生产模式（没有示例内容）下启动时，核心组件不是快速入门的一部分。因此，您首先要[从 GitHub 下载最新发布的内容包](https://github.com/adobe/aem-core-wcm-components/releases/latest)并在 AEM 环境中安装此包。

虽然可通过多种方法自动执行此操作，但使用包管理器可最轻松地在实例上快速安装内容包；请参阅[安装包](https://experienceleague.adobe.com/docs/experience-manager-65/administering/contentmanagement/package-manager.html#installing-packages)。此外，一旦您还运行了发布实例，您就需要将该包复制到发布者；请参阅[复制包](https://experienceleague.adobe.com/docs/experience-manager-65/administering/contentmanagement/package-manager.html#replicating-packages)。

## 创建代理组件 {#create-proxy-components}

出于[代理组件模式](/help/developing/guidelines.md#proxy-component-pattern)部分中说明的原因，不得从内容中直接引用核心组件。为了避免出现上述情况，核心组件都属于隐藏组件组（`.core-wcm` 或 `.core-wcm-form`），这将阻止它们直接显示在编辑器中。

相反，必须创建特定于站点的组件，这将定义要显示给页面作者的所需组件名称和组，并将每个组件作为核心组件的超类型。这些特定于站点的组件有时称为“代理组件”，因为它们不需要包含任何内容，并且主要用于定义要用于站点的组件版本。不过，在自定义[核心组件](/help/developing/customizing.md)时，这些代理组件在标记和逻辑自定义方面将发挥重要作用。

因此，对于需用于站点的每个核心组件，您必须：

1. 在站点的 components 文件夹中创建相应的代理组件。

   **示例**
在 `/apps/my-site/components` 下，创建类型为 `cq:Component` 的标题节点

1. 指向带超类型的相应核心组件版本。

   **示例**
添加以下属性：\
   `sling:resourceSuperType="core/wcm/components/title/v1/title"`

1. 定义组件的组、标题和（可选）描述。这些值是特定于项目的，并规定了向作者公开组件的方式。

   **示例**
添加以下属性：

   ```shell
   componentGroup="My Site"
   jcr:title="Title"  
   jcr:description="Section Heading"
   ```

对于实例，查看 [WKND 站点的标题组件](https://github.com/adobe/aem-guides-wknd/blob/master/ui.apps/src/main/content/jcr_root/apps/wknd/components/title/.content.xml)，它是通过此方式构建的代理组件的良好示例。

## 加载核心样式 {#load-the-core-styles}

1. 如果尚未这样做，请创建一个[客户端库](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/clientlibs.html)，该库包含站点所需的所有 CSS 和 JS 文件。
1. 在站点的客户端库上，将依赖项添加到可能需要的核心组件。可添加 `embed` 属性来完成此操作。

   例如，要包含所有 v1 核心组件的客户端库，则要添加的属性为：

   ```shell
   embed="[  
   core.wcm.components.image.v1,  
   core.wcm.components.list.v1,  
   core.wcm.components.breadcrumb.v1,  
   core.wcm.components.form.container.v1,  
   core.wcm.components.form.text.v1  
   ]"
   ```

在转到下一个部分之前，请确保您的代理组件和客户端库已部署到您的 AEM 环境。

## 允许组件 {#allow-the-components}

在[模板编辑器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)中执行以下步骤。

1. 在模板编辑器中，选择“布局容器”，然后打开其策略。
1. 在“允许的组件”列表中，选择之前创建的代理组件，这些组件应显示在为其分配的组件组的下方。完成后，应用更改。
1. （可选）对于具有设计对话框的组件，可以预先配置它们。

就是这样！在从编辑过的模板创建的页面中，您现在应能使用新创建的组件。

**阅读下一篇文章：**

* [自定义核心组件](/help/developing/customizing.md) - 了解如何样式化和自定义核心组件。
* [《组件指南》](/help/developing/guidelines.md) - 了解核心组件的实施模式。
