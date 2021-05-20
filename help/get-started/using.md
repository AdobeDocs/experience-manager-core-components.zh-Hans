---
title: 使用核心组件
description: “要在您自己的项目中启动并运行核心组件，需遵循以下三个步骤：下载并安装、创建代理组件、加载核心样式，以及允许模板上的组件。”
role: Architect, Developer, Administrator, Business Practitioner
exl-id: ee2d25e4-e2b8-4ecc-a62c-f0066de2bf2d
source-git-commit: 45a17fe42146516f351f897e85a4a48dcf3aadab
workflow-type: tm+mt
source-wordcount: '977'
ht-degree: 2%

---

# 使用核心组件{#using-core-components}

要在您自己的项目中启动并运行核心组件，需执行四个步骤，具体步骤在以下各节中各自详细介绍：

1. [下载并安装](#download-and-install)
1. [创建代理组件](#create-proxy-components)
1. [加载核心样式](#load-the-core-styles)
1. [启用组件](#allow-the-components)

>[!TIP]
>
>有关如何开始使用项目设置、核心组件、可编辑模板、客户端库和组件开发等更广泛的说明，可能需要使用以下多部分教程：\
>[AEM Sites - WKND 教程快速入门](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)

>[!TIP]
>
>如果您使用[AEM项目原型，则根据Adobe的最佳实践建议，](/help/developing/archetype/overview.md)核心组件会自动包含在您的项目中。

## 下载并安装{#download-and-install}

核心组件背后的驱动思想之一是灵活性。 通过更频繁地发布核心组件的新版本，Adobe能够更灵活地提供新功能。 开发人员反过来也可以灵活地选择将哪些组件集成到其项目中，以及希望更新这些组件的频率。 这会为AEM和核心组件生成单独的发布流程。

因此，无论您是运行AEM as a Cloud Service还是内部部署，都会确定安装步骤。

### AEM as a Cloud Service {#aemaacs}

没有步骤一！ AEM as a Core Components会自动附带最新版本的核心组件。 正如AEMaCS为您提供AEM的最新功能一样，AEMaCS会自动使您了解最新版本的核心组件。

在AEMaCS上使用核心组件时，请牢记以下几点：

* 核心组件包含在`/libs`中。
* 如果项目构建管道再次将核心组件包含在`/apps`中，则该管道将在日志中生成警告，并将忽略作为项目一部分嵌入的版本。
   * 在即将发布的版本中，再次包括核心组件将会失败管道生成。
* 如果您的项目之前在`/apps`中包含核心组件，则您可能需要调整项目。](/help/developing/overview.md#via-aemaacs)[
* 即使核心组件现在位于`/libs`中，也不建议在`/apps`中创建同一路径的任何叠加。 [如果需要自](/help/developing/guidelines.md#proxy-component-pattern) 定义组件的任何方面，则应使用代理组件模式。

### AEM 6.5和之前的{#aem-65}

在生产模式下启动（不含示例内容）时，核心组件不是快速启动的一部分。 因此，您的第一步是从GitHub](https://github.com/adobe/aem-core-wcm-components/releases/latest)下载最新发布的内容包，并将其安装在您的AEM环境中。[

有多种方法可以自动执行此操作，但在实例上快速安装内容包的最简单方法是使用包管理器；请参阅[安装软件包](https://docs.adobe.com/content/help/en/experience-manager-65/administering/contentmanagement/package-manager.html#installing-packages)。 此外，一旦您还将运行一个发布实例，则需要将该包复制到发布者；请参阅[复制包](https://docs.adobe.com/content/help/en/experience-manager-65/administering/contentmanagement/package-manager.html#replicating-packages)。

## 创建代理组件{#create-proxy-components}

由于[代理组件模式](/help/developing/guidelines.md#proxy-component-pattern)部分中所述的原因，核心组件不得直接从内容中引用。 为了避免这种情况，它们都属于隐藏的组件组（`.core-wcm`或`.core-wcm-form`），这将阻止它们直接在编辑器中显示。

而是必须创建特定于站点的组件，这些组件定义要向页面作者显示的所需组件名称和组，并将每个组件作为其超级类型引用到核心组件。 这些特定于站点的组件有时称为“代理组件”，因为它们不需要包含任何内容，主要用于定义要用于站点的组件版本。 但是，在自定义[核心组件](/help/developing/customizing.md)时，这些代理组件在标记和逻辑自定义方面起着至关重要的作用。

因此，对于网站所需的每个核心组件，您必须：

1. 在站点的组件文件夹中创建相应的代理组件。

   ****
示例在 `/apps/my-site/components` 创建类型的标题节点下  `cq:Component`

1. 指向具有超类型的相应核心组件版本。

   ****
示例添加以下属性：\
   `sling:resourceSuperType="core/wcm/components/title/v1/title"`

1. 定义组件的组、标题和（可选）描述。 这些值特定于项目，并指示组件如何向作者显示。

   ****
示例添加以下属性：

   ```shell
   componentGroup="My Site"
   jcr:title="Title"  
   jcr:description="Section Heading"
   ```

例如，查看WKND站点](https://github.com/adobe/aem-guides-wknd/blob/master/ui.apps/src/main/content/jcr_root/apps/wknd/components/title/.content.xml)的[标题组件，这是通过这种方式构建的代理组件的一个很好示例。

## 加载核心样式{#load-the-core-styles}

1. 如果尚未创建，请创建一个[客户端库](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/clientlibs.html)，其中包含网站所需的所有CSS和JS文件。
1. 在网站的客户端库中，将依赖项添加到可能需要的核心组件中。 可通过添加`embed`属性来完成此操作。

   例如，要包含所有v1核心组件的客户端库，则要添加的属性将为：

   ```shell
   embed="[  
   core.wcm.components.image.v1,  
   core.wcm.components.list.v1,  
   core.wcm.components.breadcrumb.v1,  
   core.wcm.components.form.container.v1,  
   core.wcm.components.form.text.v1  
   ]"
   ```

在转到下一部分之前，请确保已将您的代理组件和客户端库部署到AEM环境。

## 允许组件{#allow-the-components}

在[模板编辑器](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)中执行以下步骤。

1. 在模板编辑器中，选择布局容器，然后打开其策略。
1. 在允许的组件列表中，选择之前创建的代理组件，代理组件应显示在分配给它们的组件组下。 完成后，应用更改。
1. 或者，对于具有设计对话框的组件，可以预配置它们。

就这样！ 现在，在通过编辑的模板创建的页面中，您应该能够使用新创建的组件。

**阅读下一篇文章：**

* [自定义核心组件](/help/developing/customizing.md)  — 了解如何设置核心组件的样式和自定义核心组件。
* [组件准则](/help/developing/guidelines.md)  — 了解核心组件的实施模式。
