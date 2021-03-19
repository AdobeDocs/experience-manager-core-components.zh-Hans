---
title: PDF查看器组件
description: PDF查看器组件允许显示PDF文档。
role: 架构师、开发人员、管理员、业务从业者
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 3%

---


# PDF查看器组件{#pdf-viewer-component}

核心组件PDF查看器组件允许在页面中包含PDF文档。

## 使用 {#usage}

核心组件PDF查看器组件嵌入了查看器，用于在页面上显示作为资源存储的PDF文件。

## 版本和兼容性{#version-and-compatibility}

PDF查看器组件的当前版本为v1,2020年6月随核心组件版本2.10.0引入了v1，本文档对此进行了说明。

下表详细列出了组件的所有受支持版本、与组件版本兼容的AEM版本，以及指向先前版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | 兼容 | 兼容 | 兼容 |

有关核心组件版本和版本的详细信息，请参阅文档[核心组件版本](/help/versions.md)。

## 示例组件输出{#sample-component-output}

要体验PDF查看器组件及其配置选项以及HTML和JSON输出的示例，请访问[组件库](https://adobe.com/go/aem_cmp_library_pdfviewer)。

## 技术详细信息{#technical-details}

有关PDF查看器组件[的最新技术文档可在GitHub](https://adobe.com/go/aem_cmp_tech_pdfviewer_v1)上找到。

有关开发核心组件的更多详细信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

>[!NOTE]
>
>PDF查看器组件利用[Adobe的文档服务API](https://www.adobe.io/apis/documentcloud/dcsdk.html)，并要求管理员配置[上下文感知配置](/help/developing/context-aware-configs.md)以使用这些服务。 有关此配置的[详细信息，请查看组件的技术文档。](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/pdfviewer/v1/pdfviewer#context-aware-config)

## 配置对话框{#configure-dialog}

通过“配置”对话框，内容作者可以定义查看器以及查看器的行为和显示方式，以便访客页面。

### 配置选项卡{#configuration-tab}

“配置”选项卡允许作者定义应显示的PDF。 路径可以在AEM中定义为资产，也可以定义为指向其他资源的绝对路径。

![PDF查看器组件编辑对话框的“配置”选项卡](/help/assets/pdf-viewer-edit-configuration.png)

### 自定义选项卡{#customize-tab}

通过“自定义”选项卡，作者可以定义查看器中可供读者使用的选项以及如何显示查看器。

![“PDF查看器组件”编辑对话框的“自定义”选项卡](/help/assets/pdf-viewer-edit-customize.png)

可用选项的数量取决于所选的&#x200B;**类型**。

* [全窗口](#full-window)  — 查看区域在整个浏览器中呈现。这最适合于存储和工作效率应用程序。
* [大小容器](#sized-container)  — 查看区域在整个浏览器中呈现。这最适合于存储和工作效率应用程序。
* [内嵌](#in-line)  — 在网页中以行方式呈现的所有PDF页面。这最适合读取应用程序。

#### 全屏 {#full-window}

查看区域在整个浏览器中呈现。 这最适合于存储和工作效率应用程序。

![PDF查看器组件的编辑对话框的“自定义”选项卡全窗口选项](/help/assets/pdf-viewer-edit-customize-full.png)

* **默认视图模** 式 — 查看器将如何适合显示该查看器的页面
   * 适应页面
   * 适应宽度
* **全屏**  — 启用后，查看器将占用视口的全高/全宽。
* **注释工具**  — 启用注释工具后，注释工具可用。
* **左侧面板**  — 启用后，将显示左侧面板。
* **下载PDF**  — 启用后，将显示下载按钮。
* **打印PDF**  — 启用后，将显示打印按钮。
* **页面控件**  — 切换页面控件的行为。
   * 停靠
   * 取消停靠

#### 设定了大小的容器 {#sized-container}

查看区域在整个浏览器中呈现。 这最适合于存储和工作效率应用程序。

![自定义PDF查看器组件编辑对话框的制表符大小容器选项](/help/assets/pdf-viewer-edit-customize-sized-container.png)

* **全屏**  — 启用后，查看器将占用视口的全高/全宽。
* **下载PDF**  — 启用后，将显示下载按钮。
* **打印PDF**  — 启用后，将显示打印按钮。
* **页面控件**  — 切换页面控件的行为。
   * 停靠
   * 取消停靠

#### 嵌入式 {#in-line}

所有PDF页面在网页内以行形式呈现。 这最适合读取应用程序。

![自定义PDF查看器组件编辑对话框的制表符大小容器选项](/help/assets/pdf-viewer-edit-customize-inline.png)

* **下载PDF**  — 启用后，将显示下载按钮。
* **打印PDF**  — 启用后，将显示打印按钮。

## 设计对话框{#design-dialog}

PDF查看器组件没有设计对话框。
