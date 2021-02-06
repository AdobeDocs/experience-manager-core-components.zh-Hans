---
title: 使用核心组件
description: “要在您自己的项目中开始使用核心组件，需要执行三个步骤：下载和安装、创建代理组件、加载核心样式并允许模板上的组件。”
translation-type: tm+mt
source-git-commit: 10090b836397af3c9428f99bba72313263f34596
workflow-type: tm+mt
source-wordcount: '757'
ht-degree: 3%

---


# 使用核心组件{#using-core-components}

要在您自己的项目中开始使用核心组件，有四个步骤，具体请参阅以下各节：

1. [下载和安装](#download-and-install)
1. [创建代理组件](#create-proxy-components)
1. [加载核心样式](#load-the-core-styles)
1. [启用组件](#allow-the-components)

>[!NOTE]
>
>或者，对于如何从头开始使用项目设置、核心组件、可编辑模板、客户端库和组件开发等更多说明，以下多部分教程可能会很受关注：\
>[AEM Sites - WKND 教程快速入门](https://docs.adobe.com/content/help/en/experience-manager-learn/getting-started-wknd-tutorial-develop/overview.html)

## 下载并安装{#download-and-install}

核心组件背后的驱动思想之一是灵活性。 更频繁地发布新版核心组件，使Adobe能够更灵活地提供新功能。 开发人员反过来可以灵活地选择将组件集成到其项目中以及希望更新它们的频率。

因此，在生产模式下（无示例内容）启动时，核心组件不是快速启动的一部分。 因此，您的第一步是从GitHub](https://github.com/adobe/aem-core-wcm-components/releases/latest)下载最新发布的内容包，并将其安装在AEM环境上。[

可以通过多种方式实现自动化，但在实例上快速安装内容包的最简单方法是使用包管理器；请参阅[安装软件包](https://docs.adobe.com/content/help/en/experience-manager-65/administering/contentmanagement/package-manager.html#installing-packages)。 此外，一旦您还运行了发布实例，您需要将该包复制到发布者；请参阅[复制包](https://docs.adobe.com/content/help/en/experience-manager-65/administering/contentmanagement/package-manager.html#replicating-packages)。

## 创建代理组件{#create-proxy-components}

由于[代理组件模式](/help/developing/guidelines.md#proxy-component-pattern)部分中所述的原因，核心组件不能直接从内容中引用。 为避免出现这种情况，它们都属于隐藏的组件组（`.core-wcm`或`.core-wcm-form`），这将阻止它们直接显示在编辑器中。

而是必须创建站点特定的组件，这些组件定义要向页面作者显示的所需组件名称和组，并将每个组件引用到核心组件作为其超级类型。 这些站点特定的组件有时称为“代理组件”，因为它们不需要包含任何内容，并且主要用于定义要用于站点的组件的版本。 但是，在自定义[核心组件](/help/developing/customizing.md)时，这些代理组件在标记和逻辑自定义方面起着重要作用。

因此，对于每个希望用于站点的核心组件，您必须：

1. 在站点的组件文件夹中创建相应的代理组件。

   **示**
例在 `/apps/my-site/components` 创建类型的标题节点下  `cq:Component`

1. 使用超类型指向相应的核心组件版本。

   **示**
例添加以下属性：\
   `sling:resourceSuperType="core/wcm/components/title/v1/title"`

1. 定义组件的组、标题和（可选）说明。 这些值是特定于项目的，并规定如何向作者显示组件。

   **示**
例添加以下属性：

   ```shell
   componentGroup="My Site"
   jcr:title="Title"  
   jcr:description="Section Heading"
   ```

例如，查看WKND站点](https://github.com/adobe/aem-guides-wknd/blob/master/ui.apps/src/main/content/jcr_root/apps/wknd/components/title/.content.xml)的[标题组件，它是以这种方式构建的代理组件的一个很好示例。

## 加载核心样式{#load-the-core-styles}

1. 如果尚未完成，请创建[客户端库](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/clientlibs.html)，其中包含站点所需的所有CSS和JS文件。
1. 在站点的客户端库中，将依赖项添加到可能需要的核心组件。 这是通过添加`embed`属性来完成的。

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

在转到下一节之前，请确保您的代理组件和客户端库已部署到AEM环境。

## 允许组件{#allow-the-components}

在[模板编辑器](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)中执行以下步骤。

1. 在模板编辑器中，选择布局容器，然后打开其策略。
1. 在允许的组件列表中，选择以前创建的代理组件，代理组件应显示在分配给它们的组件组下。 完成后，应用更改。
1. （可选）对于具有设计对话框的组件，可以预先配置它们。

就这样！ 现在，在从已编辑的模板创建的页面中，您应能使用新创建的组件。

**阅读下一篇文章：**

* [自定义核心组件](/help/developing/customizing.md) -了解如何设计核心组件的样式和自定义核心组件。
* [组件准则](/help/developing/guidelines.md) -了解核心组件的实施模式。
