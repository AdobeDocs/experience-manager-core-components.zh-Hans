---
title: 使用核心组件
description: “要在您自己的项目中开始使用核心组件，需要执行三个步骤：下载和安装、创建代理组件、加载核心样式并允许模板上的组件。”
translation-type: tm+mt
source-git-commit: 945381996db443c227aa31f0aacb963071165681

---


# 使用核心组件{#using-core-components}

要在您自己的项目中启动 [并运行核心组件](developing.md) ，有四个步骤，具体步骤如下各节中详细介绍：

1. [下载和安装](#download-and-install)
1. [创建代理组件](#create-proxy-components)
1. [加载核心样式](#load-the-core-styles)
1. [启用组件](#allow-the-components)

>[!NOTE]
>
>或者，有关如何从头开始使用项目设置、核心组件、可编辑模板、客户端库和组件开发的更多说明，以下多部分教程可能会受到关注：\
>[AEM Sites入门- WKND教程](wknd-tutorial.md)

## 下载和安装 {#download-and-install}

核心组件背后的驱动思想之一是灵活性。 通过更频繁地发布新版核心组件，Adobe在提供新功能方面更加灵活。 开发人员也可以灵活选择将组件集成到其项目中以及希望更新它们的频率。

因此，在生产模式下启动时，核心组件不是快速启动的一部分（没有示例内容）。 因此，您的第一步是从GitHub [下载最新发布的内容包](https://github.com/adobe/aem-core-wcm-components/releases/latest) ，并将其安装在AEM环境中。

可以通过多种方式实现自动化，但在实例上快速安装内容包的最简单方法是使用包管理器；请参 [阅安装包](https://docs.adobe.com/content/help/en/experience-manager-65/administering/contentmanagement/package-manager.html#installing-packages)。 此外，一旦您的发布实例也在运行，您需要将该包复制到发布者；请参阅 [复制包](https://docs.adobe.com/content/help/en/experience-manager-65/administering/contentmanagement/package-manager.html#replicating-packages)。

<!-- 

Comment Type: annotation
Last Modified By: ims-author-CE1E2CE451D1F0680A490D45@AdobeID
Last Modified Date: 2017-04-17T16:42:59.142-0400

Should we be promoting embedding the core-component package as an artifact in a customer application, reasoning as follows: 1) a customer application is required to leverage core components (at a minimum, proxy components must be defined) 2) a customer application must be updated to leverage new versions of core components (since it requires adjusting the sling:resourceSuperType to point at the new version of the component) It seems the only time theres an advantage to installing a release directly is if a bug-fix (non version-changing) release of core-components is cut, and it doesnt coincide with an application deployment. WDYT? For example, recommend doing this for ACS Commons which has a similar use-case (https://adobe-consulting-services.github.io/acs-aem-commons/pages/maven.html) We can of course keep the instructions for manually deploying, since some will want to do this, or the bug-fix use-case will appear.

 -->

## 创建代理组件 {#create-proxy-components}

由于“代理组件模 [式”部分中所述的原因](guidelines.md#proxy-component-pattern) ，核心组件不得直接从内容中引用。 为避免出现这种情况，它们都属于隐藏的组件组( `.core-wcm` 或 `.core-wcm-form`)，这将阻止它们直接显示在编辑器中。

而是必须创建站点特定的组件，这些组件定义要向页面作者显示的所需组件名称和组，并将每个组件引用到核心组件作为其超类型。 这些站点特定的组件有时称为“代理组件”，因为它们不需要包含任何内容并且主要用于定义要用于站点的组件的版本。 但是，在自定义核 [心组件时](customizing.md)，这些代理组件在标记和逻辑自定义方面起着重要作用。

因此，对于每个希望用于站点的核心组件，您必须：

1. 在站点的组件文件夹中创建一个相应的代理组件。

   **示例**&#x200B;在 `/apps/my-site/components` 创建类型的标题节点下 `cq:Component`

1. 使用超类型指向相应的核心组件版本。

   **示例**&#x200B;添加以下属性：\
   `sling:resourceSuperType="core/wcm/components/title/v1/title"`

1. 定义组件的组、标题和（可选）说明。 这些值是特定于项目的，它们指示组件如何向作者公开。

   **示例**&#x200B;添加以下属性：

   ```shell
   componentGroup="My Site"
   jcr:title="Title"  
   jcr:description="Section Heading"
   ```

例如，查看We. [Retail参考站点的标题组件](https://github.com/Adobe-Marketing-Cloud/aem-sample-we-retail/blob/master/ui.apps/src/main/content/jcr_root/apps/weretail/components/content/title/.content.xml)，它是这样构建的代理组件的一个很好的示例。

## 加载核心样式 {#load-the-core-styles}

<!-- 

Comment Type: annotation
Last Modified By: ims-author-CE1E2CE451D1F0680A490D45@AdobeID
Last Modified Date: 2017-04-17T16:57:16.414-0400

Styles is odd in that most Core Components do not have CSS; very few even have structural CSS (breadcrumbs, list) It may be more apt to title this section: Load the Core JavaScript and CSS or Load the Core Client Libraries ?

 -->

<!-- 

Comment Type: annotation
Last Modified By: ims-author-CE1E2CE451D1F0680A490D45@AdobeID
Last Modified Date: 2017-04-17T17:41:37.115-0400

This section seems to cover the "sites" clientlibs for core components; Do we need a section for ensuring the editor clientlibs are loaded in the Page Editor? Pending: https://github.com/Adobe-Marketing-Cloud/aem-core-wcm-components/issues/15

 -->

<!-- 

Comment Type: annotation
Last Modified By: cotescu
Last Modified Date: 2018-03-09T10:45:52.812-0500

Load the Core Client Libraries sounds way better

 -->

1. 如果尚未完成，请创建一 [个客户端库](https://docs.adobe.com/content/help/en/experience-manager-65/developing/introduction/clientlibs.html) ，其中包含站点所需的所有CSS和JS文件。
1. 在站点的客户端库上，将依赖项添加到可能需要的核心组件。 这是通过添加属性来完 `embed` 成的。

   例如，要包含所有v1核心组件的客户端库，要添加的属性应为：

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

## 允许组件 {#allow-the-components}

在模板编辑器中执行以 [下步骤](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)。

1. 在模板编辑器中，选择布局容器，然后打开其策略。
1. 在允许的组件列表中，选择以前创建的代理组件，代理组件应显示在分配给它们的组件组下。 完成后，应用更改。
1. （可选）对于具有设计对话框的组件，可以预配置这些组件。

够了！ 在从已编辑的模板创建的页面中，您现在应能使用新创建的组件。

**阅读下一篇文章：**

* [自定义核心组件](customizing.md) -了解如何设计核心组件的样式和自定义核心组件。
* [组件准则](guidelines.md) -了解核心组件的实施模式。
