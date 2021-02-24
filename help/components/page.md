---
title: 页面组件
description: 页面组件是一个可扩展的页面组件，旨在与模板编辑器一起使用，并允许使用模板编辑器组合页面页眉/页脚和结构组件。
translation-type: tm+mt
source-git-commit: 2748fea0aca82b1262585b3f8c191f61607f7735
workflow-type: tm+mt
source-wordcount: '691'
ht-degree: 3%

---


# 页面组件{#page-component}

页面组件是一个可扩展的页面组件，设计用于与[模板编辑器](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)一起使用，并允许使用模板编辑器组合页面页眉/页脚和结构组件。

## 使用 {#usage}

页面组件构成了使用核心组件以及可编辑模板设计的所有页面的基础。 通过使用页面组件，页眉、页脚和页面结构可以使用其他核心组件定义为模板。

使用[设计对话框](#design-dialog)，可以为页面定义自定义客户端库。 与具有可直接从组件访问的编辑对话框的其他组件不同，由于页面组件是页面本身，因此页面组件的[编辑对话框](#edit-dialog)是页面属性窗口。

## 渐进式Web应用程序支持{#pwa-support}

核心组件版本2.15.0引入了对页面组件中AEM内置[渐进式Web应用程序(PWA)功能](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/enable-pwa.html)的支持。 通过站点级别的简单配置，将您的AEM体验转变为PWA!

## 版本和兼容性{#version-and-compatibility}

页面组件的当前版本为v2,2018年1月随核心组件版本2.0.0引入了v2，本文档对此进行了说明。

下表详细列出了组件的所有受支持版本、与组件版本兼容的AEM版本，以及指向先前版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|---|
| v2 | 兼容 | 兼容 | 兼容 |
| [v1](v1/page-v1.md) | 兼容 | 兼容 | - |

有关核心组件版本和版本的详细信息，请参阅文档[核心组件版本](/help/versions.md)。

### 技术详细信息{#technical-details}

有关页面组件[的最新技术文档可在GitHub](https://adobe.com/go/aem_cmp_tech_page_v2)上找到。

有关开发核心组件的更多详细信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## 编辑对话框{#edit-dialog}

由于组件表示整个页面，因此通常在编辑对话框中的设置会显示在[页面属性](https://docs.adobe.com/content/help/zh-Hans/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html)窗口中。

## 设计对话框{#design-dialog}

由于组件表示整个页面，因此在编辑页面模板时，可通过&#x200B;**页面信息 — >页面策略**&#x200B;访问设计对话框。

![页面策略](/help/assets/page-policy.png)

>[!NOTE]
>
>在AEM的早期版本中，**页面策略**&#x200B;称为&#x200B;**页面设计**。

### 属性选项卡{#properties-tab}

使用“页面设计”窗口，您可以定义要加载的客户端库以及页面的Web资源库。

* **客户端库**  — 定义要加载的客户端库类别。JavaScript将添加在正文末尾，CSS将添加到页面标题。
* **客户端库JavaScript页面头**  — 定义要在页面头中加载的JavaScript客户端库类别。
   * 此处定义的&#x200B;**Client Libraries**&#x200B;字段中也存在的类别将加载到页面头中，而不是在body结尾。
   * 除非&#x200B;**客户端库**&#x200B;字段中也存在类别，否则不会加载CSS。

* **Web资源客户端库**  — 用于提供Web资源（如收藏夹）的客户端库类别。

* **跳至主内容元素选择器**  — 用作辅助功能，可直接跳至页面的主内容

![“页面组件设计”对话框](/help/assets/page-design.png)

可以为&#x200B;**客户端库**&#x200B;和&#x200B;**客户端库JavaScript页面头**&#x200B;字段配置库，如下所示：

* 要添加新字段，请单击或点按字段下方的&#x200B;**添加**&#x200B;按钮。
* 要删除字段，请单击或点按要删除的字段旁边的垃圾桶图标。
* 要重新排列加载顺序，请单击或点按并拖动要移动的字段旁边的手柄。

有关使用客户端库的详细信息，请参阅[使用客户端库](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/clientlibs.html)。

>[!CAUTION]
>
>在核心组件版本2.2.0中引入了为页面头单独定义客户端库的功能。

### 样式选项卡{#styles-tab}

页面组件支持AEM [样式系统](/help/get-started/authoring.md#component-styling)。

## Adobe客户端数据层{#data-layer}

页面组件支持[Adobe客户端数据层。](/help/developing/data-layer/overview.md)
