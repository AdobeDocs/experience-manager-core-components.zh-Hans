---
title: 使用核心组件
seo-title: 使用核心组件
description: 'null'
seo-description: “要在您自己的项目中使用核心组件，需要执行以下三个步骤：下载和安装、创建代理组件、加载核心样式以及允许模板上的组件”。
uuid: a ef2acf-8226-4510-838b-f5 fae196 f9 f1
contentOwner: 用户
content-type: 引用
topic-tags: developing
products: SG_ EXPERIENCE MANAGER/CORECOMMPANES-new
discoiquuid: 1703a171-830c-477e-a34 f-99caba841 ec4
disttype: dist5
gnavtheme: 浅色
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 632d6abb1f13667cc0457152268d50af3bfabfc4

---


# 使用核心组件{#using-core-components}

要在您自己的项目中与 [核心组件](developing.md) 一起运行并运行，有四个步骤，具体部分如下所示：

1. [下载和安装](#download-and-install)
1. [创建代理组件](#create-proxy-components)
1. [加载核心样式](#load-the-core-styles)
1. [启用组件](#allow-the-components)

>[!NOTE]
>
>或者，对于如何从项目设置、可编辑模板、客户端库和组件开发开始从零开始的更多说明，以下多部分教程可能会很感兴趣：\
>[AEM Sites入门- WKD教程](wknd-tutorial.md)

## 下载和安装 {#download-and-install}

核心组件背后的一个驱动力是灵活性。更频繁地释放新版本的核心组件通常使得Adobe能够更灵活地交付新功能。开发人员可以灵活地在其中选择集成到项目中，以及他们希望更新它们的频率。

因此，核心组件不是在生产模式下开始时快速启动的核心组件(不含示例内容)。因此，您的第一步是 [从GitHub下载最新发布的内容包，](https://github.com/adobe/aem-core-wcm-components/releases/latest) 并将其安装在AEM环境中。

有多种方法可以实现这一点，但在实例上快速安装内容包的最简单方法是使用包管理器；请参阅 [安装包](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/package-manager.html)。此外，一旦您还将运行发布实例，您需要将该包复制到publisher；请参阅 [复制包](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/package-manager.html)。

<!-- 

Comment Type: annotation
Last Modified By: ims-author-CE1E2CE451D1F0680A490D45@AdobeID
Last Modified Date: 2017-04-17T16:42:59.142-0400

Should we be promoting embedding the core-component package as an artifact in a customer application, reasoning as follows: 1) a customer application is required to leverage core components (at a minimum, proxy components must be defined) 2) a customer application must be updated to leverage new versions of core components (since it requires adjusting the sling:resourceSuperType to point at the new version of the component) It seems the only time theres an advantage to installing a release directly is if a bug-fix (non version-changing) release of core-components is cut, and it doesnt coincide with an application deployment. WDYT? For example, recommend doing this for ACS Commons which has a similar use-case (https://adobe-consulting-services.github.io/acs-aem-commons/pages/maven.html) We can of course keep the instructions for manually deploying, since some will want to do this, or the bug-fix use-case will appear.

 -->

## 创建代理组件 {#create-proxy-components}

出于 [在“代理组件模式](guidelines.md#proxy-component-pattern) ”部分中说明的原因，核心组件不得直接从内容中引用。为避免这种情况，它们都属于隐藏的组件组( `.core-wcm` 或 `.core-wcm-form`)，这会阻止它们直接在编辑器中显示。

而是必须创建站点特定组件，它定义要向页面作者显示的所需组件名称和组，并将每个组件作为其超类型引用到核心组件。这些站点特定的组件有时称为“代理组件”，因为它们无需包含任何内容，而且主要用于定义要用于站点的组件版本。但是，自定义 [核心组件](customizing.md)时，这些代理组件对于标记和逻辑自定义起着至关重要的作用。

因此，对于需要用于站点的每个核心组件，您必须：

1. 在站点的组件文件夹中创建相应的代理组件。

   **下例**`/apps/my-site/components` 创建类型的标题节点 `cq:Component`

1. 指向具有super-type的相应核心组件版本。

   **示例**添加以下属性：\
   `sling:resourceSuperType="core/wcm/components/title/v1/title"`

1. 定义组件的组、标题和可选描述。这些值是特定于项目的，并决定组件如何向作者公开。

   **示例**添加以下属性：

   ```shell
   componentGroup="My Site"
   jcr:title="Title"  
   jcr:description="Section Heading"
   ```

例如，查看We. Retail参考站点 [](https://github.com/Adobe-Marketing-Cloud/aem-sample-we-retail/blob/master/ui.apps/src/main/content/jcr_root/apps/weretail/components/content/title/.content.xml)的标题组件，它是一个构建方式的一个很好的代理组件示例。

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

1. 如果尚未完成，则创建一个 [客户端库](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/clientlibs.html) ，其中包含您的站点所需的所有CSS和JS文件。
1. 在站点的客户端库上，向可能需要的核心组件添加依赖关系。通过添加 `embed` 属性来完成此操作。

   例如，要包括所有v核心组件的客户端库，要添加的属性是：

   ```shell
   embed="[  
   core.wcm.components.image.v1,  
   core.wcm.components.list.v1,  
   core.wcm.components.breadcrumb.v1,  
   core.wcm.components.form.container.v1,  
   core.wcm.components.form.text.v1  
   ]"
   ```

请确保您的代理组件和客户端库已部署到AEM环境，然后转到下一部分。

## 允许组件 {#allow-the-components}

以下步骤在 [模板编辑器](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)中执行。

1. 在模板编辑器中，选择布局容器，然后打开其策略。
1. 在允许组件列表中，选择之前创建的代理组件，该组件应显示在分配给它们的组件组下方。完成后，应用更改。
1. 或者，对于具有设计对话框的组件，可以预配置这些组件。

就是这样！在已编辑的模板中创建的页面中，您现在应当能够使用新创建的组件。

**阅读下一步：**

* [自定义核心组件](customizing.md) -了解如何样式和自定义核心组件。
* [组件指南](guidelines.md) -了解核心组件的实施模式。
