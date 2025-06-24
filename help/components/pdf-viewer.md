---
title: PDF 查看器组件
description: 利用 PDF 查看器组件可显示 PDF 文档。
role: Architect, Developer, Admin, User
exl-id: deb635f5-2b73-4e7a-9838-3a941e39e898
source-git-commit: dd30def59a8f037864da875ef4c831b11f766e57
workflow-type: tm+mt
source-wordcount: '685'
ht-degree: 100%

---


# PDF 查看器组件 {#pdf-viewer-component}

利用核心组件 PDF 查看器组件，可以在页面上包含 PDF 文档。

{{traditional-aem}}

## 用途 {#usage}

核心组件 PDF 查看器组件嵌入了一个查看器，以在页面上显示作为资源存储的 PDF 文件。

## 版本和兼容性 {#version-and-compatibility}

PDF 查看器组件的当前版本是 v1，此版本随 2020 年 6 月的核心组件发行版本 2.10.0 的发布引入，具体说明见本文。

下表详细说明了该组件的所有受支持版本、与该组件的版本兼容的 AEM 版本以及指向早期版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|--- |--- |---|---|---|
| v1 | 与<br>[版本 2.17.4](/help/versions.md) 和更低版本兼容 | 兼容 | 兼容 | 兼容 |

有关核心组件版本的更多信息，请参阅文档[核心组件版本](/help/versions.md)。

## 示例组件输出 {#sample-component-output}

要体验 PDF 查看器组件并查看其配置选项示例以及 HTML 和 JSON 输出，请访问[组件库](https://adobe.com/go/aem_cmp_library_pdfviewer_cn)。

## 技术详细信息 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_pdfviewer_v1_cn)有关 PDF 查看器组件的最新技术文档。

在[核心组件开发人员文档](/help/developing/overview.md)中可找到有关开发核心组件的其他详细信息。

>[!NOTE]
>
>PDF 查看器组件利用 [Adobe Document Services API](https://www.adobe.io/apis/documentcloud/dcsdk.html)，并要求管理员配置[上下文感知配置](/help/developing/context-aware-configs.md)以使用这些服务。查看组件的技术文档以了解[此配置的详细信息](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/pdfviewer/v1/pdfviewer#context-aware-config)。

## “配置”对话框 {#configure-dialog}

利用“配置”对话框，内容作者可以定义查看器，以及对于页面的访客它会如何表现和显示。

### “配置”选项卡 {#configuration-tab}

利用“配置”选项卡，作者可以定义应该显示哪个 PDF。路径可以定义为 AEM 中的资源或者是其他资源的绝对路径。

![PDF 查看器组件的“编辑”对话框的“配置”选项卡](/help/assets/pdf-viewer-edit-configuration.png)

### “自定义”选项卡 {#customize-tab}

利用“自定义”选项卡，内容作者可以定义在查看器中向读者显示的选项，以及应该如何展示查看器。

![PDF 查看器组件的“编辑”对话框的“自定义”选项卡](/help/assets/pdf-viewer-edit-customize.png)

可用选项的数量取决于所选的&#x200B;**类型**。

* [完整窗口](#full-window) - 查看区域在整个浏览器中渲染。此选项最适合存储和生产力应用程序。
* [根据容器调整大小](#sized-container) - 查看区域在整个浏览器中渲染。此选项最适合存储和生产力应用程序。
* [嵌入式](#in-line) - 所有 PDF 页面在网页中嵌入显示。此选项最适合阅读应用程序。

#### 完整窗口 {#full-window}

查看区域在整个浏览器中渲染。此选项最适合存储和生产力应用程序。

![PDF 查看器组件的“自定义”选项卡的“完整窗口”选项](/help/assets/pdf-viewer-edit-customize-full.png)

* **默认查看模式** - 查看器在显示时将如何适应页面
   * 适应页面
   * 适应宽度
* **全屏** - 在启用时，查看器将占据视区的完整高度/宽度。
* **注释工具** - 启用时，注释工具可用。
* **左侧面板** - 启用时，将显示左侧面板。
* **下载 PDF** - 启用时，将显示下载按钮。
* **打印 PDF** - 启用时，将显示打印按钮。
* **页面控件** - 切换页面控件的行为。
   * 停靠
   * 取消停靠

#### 根据容器调整大小 {#sized-container}

查看区域在整个浏览器中渲染。此选项最适合存储和生产力应用程序。

![PDF 查看器组件的“自定义”选项卡的“根据容器调整大小”选项](/help/assets/pdf-viewer-edit-customize-sized-container.png)

* **全屏** - 在启用时，查看器将占据视区的完整高度/宽度。
* **下载 PDF** - 启用时，将显示下载按钮。
* **打印 PDF** - 启用时，将显示打印按钮。
* **页面控件** - 切换页面控件的行为。
   * 停靠
   * 取消停靠

#### 嵌入式 {#in-line}

所有 PDF 页面在网页中内联显示。此选项最适合阅读应用程序。

![PDF 查看器组件的“自定义”选项卡的“根据容器调整大小”选项](/help/assets/pdf-viewer-edit-customize-inline.png)

* **下载 PDF** - 启用时，将显示下载按钮。
* **打印 PDF** - 启用时，将显示打印按钮。

## “设计”对话框 {#design-dialog}

PDF 查看器组件没有“设计”对话框。
