---
title: 页面组件 (v2)
description: 页面组件是指可扩展的页面组件，设计用于模板编辑器，允许使用模板编辑器来组装页眉/页脚和结构组件。
role: Architect, Developer, Admin, User
exl-id: e85fe4db-6de4-4a84-a54c-bd07a67efed3
index: n
source-git-commit: 92a3ec273a5be6751c1503835b9c2e5cbd61bb9e
workflow-type: ht
source-wordcount: '618'
ht-degree: 100%

---


# 页面组件 (v2) {#page-component}

页面组件是指可扩展的页面组件，设计用于[模板编辑器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=zh-Hans)，允许使用模板编辑器来组装页眉/页脚和结构组件。

## 用途 {#usage}

页面组件构成了使用核心组件以及可编辑模板设计的所有页面的基础。利用页面组件，可以使用其他核心组件将页眉、页脚和页面结构定义为模板。

使用[“设计”对话框](#design-dialog)，可以为页面定义自定义客户端库。与可从组件直接访问编辑对话框的其他组件不同，由于页面组件是页面本身，其[“编辑”对话框](#edit-dialog)是页面属性窗口。

## 版本和兼容性 {#version-and-compatibility}

本文档介绍了页面组件 v2，此版本随 2018 年 1 月的核心组件发行版本 2.0.0 的发布引入。

>[!CAUTION]
>
>本文档介绍了页面组件 v2。
>
>有关当前版本的页面组件的详细信息，请参阅[页面组件](/help/components/page.md)文档。

## 渐进式 Web 应用程序支持 {#pwa-support}

核心组件的发行版本 2.15.0 引入了对 AEM as a Cloud Service 的内置[渐进式 Web 应用程序 (PWA) 功能的支持。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/enable-pwa.html?lang=zh-Hans)在网站级别使用简单的配置，可以将 AEM 体验转换为 PWA！

### 技术详细信息 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_page_v2_cn)有关页面组件的最新技术文档。

在[核心组件开发人员文档](/help/developing/overview.md)中可找到有关开发核心组件的其他详细信息。

## “编辑”对话框 {#edit-dialog}

由于该组件呈现整个页面，通常位于编辑对话框中的设置可在[页面属性](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html?lang=zh-Hans)窗口中找到。

## “设计”对话框 {#design-dialog}

由于该组件呈现整个页面，在编辑页面模板时，通过&#x200B;**页面信息 -> 页面策略**&#x200B;访问“设计”对话框。

![页面策略](/help/assets/page-policy.png)

>[!NOTE]
>
>在 AEM 的以前版本中，**页面策略**&#x200B;称为&#x200B;**页面设计**。

### “属性”选项卡 {#properties-tab}

使用“页面设计”窗口，您可以定义要加载的客户端库，以及页面的 Web 资源库。

* **客户端库** - 这定义要加载的客户端库类别。JavaScript 添加到正文结尾，CSS 添加到页头。
* **客户端库 JavaScript 页头** - 这定义要在页头中加载的 JavaScript 客户端库类别。
   * 在此处定义并在&#x200B;**客户端库**&#x200B;字段中存在的类别，将在页头而非正文结尾加载 JavaScript。
   * 除非该类别还存在于&#x200B;**客户端库**&#x200B;字段中，否则不加载 CSS。

* **Web 资源客户端库** - 用于提供 favicon 等 Web 资源的客户端库类别。

* **跳到主内容元素选择器** - 用作可访问性功能，以直接跳到页面的主内容。

![页面组件设计对话框](/help/assets/page-design.png)

可以同时为&#x200B;**客户端库**&#x200B;和&#x200B;**客户端库 JavaScript 页头**&#x200B;字段配置库，如下所示：

* 要添加新字段，请单击或点击字段下的&#x200B;**“添加”**&#x200B;按钮。
* 要删除字段，请单击或点击要删除的字段旁边的垃圾桶图标。
* 要重新设置加载顺序，请单击或点击要移动的字段并拖动旁边的手柄。

有关使用客户端库的更多信息，请参阅[使用客户端库](https://helpx.adobe.com/cn/experience-manager/6-5/sites/developing/using/clientlibs.html)。

>[!CAUTION]
>
>为页头单独定义客户端库的功能已在核心组件发行版本 2.2.0 中引入。

### “样式”选项卡 {#styles-tab}

页面组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。

## Adobe Client Data Layer {#data-layer}

页面组件支持 [Adobe Client Data Layer](/help/developing/data-layer/overview.md)。
