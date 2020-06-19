---
title: PDF查看器组件
description: PDF查看器组件允许显示PDF文档。
translation-type: tm+mt
source-git-commit: b08fc5ec49126f7be19b7433a3d71de877d9e442
workflow-type: tm+mt
source-wordcount: '644'
ht-degree: 1%

---


# PDF查看器组件 {#pdf-viewer-component}


核心组件PDF查看器组件允许在页面中包含PDF文档。

## 使用 {#usage}

核心组件PDF查看器组件嵌入一个查看器以在页面上显示作为资源存储的PDF文件。

## 版本和兼容性 {#version-and-compatibility}

PDF查看器组件的当前版本为v1,2020年6月随核心组件的2.10.0版引入了v1，该版本在本文档中进行了说明。

下表详细列出了组件的所有受支持版本、与组件版本兼容的AEM版本以及指向先前版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM 云服务 |
|--- |--- |---|---|
| v1 | 兼容 | 兼容 | 兼容 |

有关核心组件版本和版本的详细信息，请参阅文档 [核心组件版本](/help/versions.md)。

## 示例组件输出 {#sample-component-output}

要体验PDF查看器组件以及查看其配置选项以及HTML和JSON输出的示例，请访问组 [件库](https://adobe.com/go/aem_cmp_library_pdfviewer)。

## 技术详细信息 {#technical-details}

有关PDF查看器组件的最新技术文 [档可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_pdfviewer_v1)。

有关开发核心组件的更多详细信息，请参阅核 [心组件开发人员文档](/help/developing/overview.md)。

## 配置对话框 {#configure-dialog}

配置对话框允许内容作者定义查看器以及查看器的行为和显示方式，以便访客页面。

### Configuration Tab {#configuration-tab}

“配置”选项卡允许作者定义应显示的PDF。 该路径可在AEM中定义为资产，或定义为其他资源的绝对路径。

![PDF查看器组件编辑对话框的配置选项卡](/help/assets/pdf-viewer-edit-configuration.png)

### 自定义选项卡 {#customize-tab}

通过“自定义”选项卡，作者可以定义查看器中对读者可用的选项以及查看器的显示方式。

![PDF查看器组件编辑对话框的“自定义”选项卡](/help/assets/pdf-viewer-edit-customize.png)

可用选项的数量取决于 **选定** 的“类型”。

* [完整窗口](#full-window) -查看区域在整个浏览器中呈现。 这最适合于存储和工作效率应用程序。
* [大小容器](#sized-container) -查看区域在整个浏览器中呈现。 这最适合于存储和工作效率应用程序。
* [内嵌](#in-line) -在网页内以行方式呈现的所有PDF页面。 这最适合读取应用程序。

#### 完整窗口 {#full-window}

查看区域在整个浏览器中呈现。 这最适合于存储和工作效率应用程序。

![“自定义PDF查看器组件”编辑对话框的选项卡全窗口选项](/help/assets/pdf-viewer-edit-customize-full.png)

* **默认视图模式** -查看器将如何适合显示该查看器的页面
   * 适合页面
   * 适合宽度
* **全屏** -启用后，查看器将占用视口的全高／全宽。
* **注释工具** -启用注释工具后，即可使用注释工具。
* **左侧面板** -启用后，将显示左侧面板。
* **下载PDF** —— 启用后，将显示下载按钮。
* **打印PDF** —— 启用后，将显示打印按钮。
* **页面控件** -切换页面控件的行为。
   * 停放
   * 取消停放

#### 大小容器 {#sized-container}

查看区域在整个浏览器中呈现。 这最适合于存储和工作效率应用程序。

![自定义PDF查看器组件编辑对话框的制表符大小的容器选项](/help/assets/pdf-viewer-edit-customize-sized-container.png)

* **全屏** -启用后，查看器将占用视口的全高／全宽。
* **下载PDF** —— 启用后，将显示下载按钮。
* **打印PDF** —— 启用后，将显示打印按钮。
* **页面控件** -切换页面控件的行为。
   * 停放
   * 取消停放

#### 联机 {#in-line}

在网页内以行形式呈现的所有PDF页面。 这最适合读取应用程序。

![自定义PDF查看器组件编辑对话框的制表符大小的容器选项](/help/assets/pdf-viewer-edit-customize-inline.png)

* **下载PDF** —— 启用后，将显示下载按钮。
* **打印PDF** —— 启用后，将显示打印按钮。

## 设计对话框 {#design-dialog}

PDF查看器组件没有“设计”对话框。
