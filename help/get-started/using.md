---
title: 使用核心组件
description: “要在您自己的项目中开始使用核心组件，需要执行三个步骤：下载和安装、创建代理组件、加载核心样式并允许模板上的组件。”
role: Architect, Developer, Administrator, Business Practitioner
exl-id: ee2d25e4-e2b8-4ecc-a62c-f0066de2bf2d
translation-type: tm+mt
source-git-commit: 45a17fe42146516f351f897e85a4a48dcf3aadab
workflow-type: tm+mt
source-wordcount: '977'
ht-degree: 2%

---

# 使用核心组件{#using-core-components}

要在您自己的项目中开始使用核心组件，有四个步骤，具体详见以下各节：

1. [下载和安装](#download-and-install)
1. [创建代理组件](#create-proxy-components)
1. [加载核心样式](#load-the-core-styles)
1. [启用组件](#allow-the-components)

>[!TIP]
>
>有关如何从头开始使用项目设置、核心组件、可编辑模板、客户端库和组件开发进行更多说明，以下多部分教程可能很受关注：\
>[AEM Sites - WKND 教程快速入门](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)

>[!TIP]
>
>如果您使用[AEM项目原型，则根据Adobe的最佳实践建议，](/help/developing/archetype/overview.md)核心组件将自动包含在您的项目中。

## 下载并安装{#download-and-install}

核心组件背后的驱动思想之一是灵活性。 更频繁地发布新版本的核心组件使Adobe能够更灵活地提供新功能。 开发人员反过来可以灵活选择将哪些组件集成到其项目中以及希望更新它们的频率。 这会为AEM和核心组件生成单独的发布流程。

因此，您是以云服务或内部部署形式运行AEM决定安装步骤。

### AEM as a Cloud Service {#aemaacs}

没有第一步！ AEM作为Cloud Service，会自动附带最新版本的核心组件。 正如AEMaCS为您优惠AEM的最新功能一样，AEMaCS会自动使您获得最新版本的核心组件。

在AEMaCS上使用核心组件时，应牢记以下几点：

* 核心组件包含在`/libs`中。
* 如果项目构建管道再次包含核心组件作为`/apps`的一部分，它将在日志中生成警告，并将忽略作为项目的一部分嵌入的版本。
   * 在即将发布的版本中，再次包括核心组件将使管道构建失败。
* 如果您的项目之前在`/apps`和[中包含核心组件，则您可能需要调整您的项目。](/help/developing/overview.md#via-aemaacs)
* 即使核心组件现在位于`/libs`中，也不建议在`/apps`中创建相同路径的任何叠加。 [如果需要自](/help/developing/guidelines.md#proxy-component-pattern) 定义组件的任何方面，应改用代理组件模式。

### AEM 6.5和上一版本{#aem-65}

当在生产模式下启动时（无示例内容），核心组件不是快速启动的一部分。 因此，您的第一步是从GitHub](https://github.com/adobe/aem-core-wcm-components/releases/latest)下载最新发布的内容包，并将其安装到AEM环境。[

可以通过多种方式实现自动化，但在实例上快速安装内容包的最简单方法是使用包管理器；请参阅[安装软件包](https://docs.adobe.com/content/help/en/experience-manager-65/administering/contentmanagement/package-manager.html#installing-packages)。 此外，一旦您还将运行一个发布实例，您需要将该包复制到发布者；请参阅[复制包](https://docs.adobe.com/content/help/en/experience-manager-65/administering/contentmanagement/package-manager.html#replicating-packages)。

## 创建代理组件{#create-proxy-components}

由于[代理组件模式](/help/developing/guidelines.md#proxy-component-pattern)部分中说明的原因，核心组件不得直接从内容中引用。 为避免出现这种情况，它们都属于隐藏的组件组（`.core-wcm`或`.core-wcm-form`），这将阻止它们直接显示在编辑器中。

而是必须创建站点特定的组件，这些组件定义要向页面作者显示的所需组件名称和组，并将每个组件引用核心组件作为其超类型。 这些站点特定的组件有时称为“代理组件”，因为它们不需要包含任何内容并且主要用于定义要用于站点的组件的版本。 但是，在自定义[核心组件](/help/developing/customizing.md)时，这些代理组件在标记和逻辑自定义方面起着至关重要的作用。

因此，对于每个希望用于站点的核心组件，您必须：

1. 在站点的components文件夹中创建相应的代理组件。

   **示**
例在 `/apps/my-site/components` 创建类型的标题节点  `cq:Component`

1. 使用超类型指向相应的核心组件版本。

   **Example添**
加以下属性：\
   `sling:resourceSuperType="core/wcm/components/title/v1/title"`

1. 定义组件的组、标题和（可选）说明。 这些值是特定于项目的，它们指示组件如何向作者公开。

   **示**
例添加以下属性：

   ```shell
   componentGroup="My Site"
   jcr:title="Title"  
   jcr:description="Section Heading"
   ```

例如，查看WKND站点](https://github.com/adobe/aem-guides-wknd/blob/master/ui.apps/src/main/content/jcr_root/apps/wknd/components/title/.content.xml)的[标题组件，它是以这种方式构建的代理组件的一个很好示例。

## 加载核心样式{#load-the-core-styles}

1. 如果尚未完成，请创建一个[客户端库](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/clientlibs.html)，其中包含站点所需的所有CSS和JS文件。
1. 在站点的客户端库上，将依赖项添加到可能需要的核心组件中。 可通过添加`embed`属性来完成此操作。

   例如，要包含所有v1核心组件的客户端库，要添加的属性为：

   ```shell
   embed="[  
   core.wcm.components.image.v1,  
   core.wcm.components.list.v1,  
   core.wcm.components.breadcrumb.v1,  
   core.wcm.components.form.container.v1,  
   core.wcm.components.form.text.v1  
   ]"
   ```

在转到下一部分之前，请确保您的代理组件和客户端库已部署到AEM环境。

## 允许组件{#allow-the-components}

在[模板编辑器](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)中执行以下步骤。

1. 在模板编辑器中，选择布局容器，然后打开其策略。
1. 在允许的组件列表中，选择之前创建的代理组件，这些组件应显示在分配给它们的组件组下。 完成后，应用更改。
1. （可选）对于具有设计对话框的组件，可以预先配置它们。

就这样！ 在从编辑的模板创建的页面中，您现在应可以使用新创建的组件。

**阅读下一篇文章：**

* [自定义核心组件](/help/developing/customizing.md)  — 了解如何设置核心组件的样式和自定义核心组件。
* [组件准则](/help/developing/guidelines.md)  — 了解核心组件的实施模式。
