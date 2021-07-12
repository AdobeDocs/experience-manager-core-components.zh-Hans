---
title: PDF查看器组件
description: PDF查看器组件允许显示PDF文档。
role: Architect, Developer, Admin, User
exl-id: deb635f5-2b73-4e7a-9838-3a941e39e898
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '705'
ht-degree: 3%

---

# PDF查看器组件 {#pdf-viewer-component}

核心组件PDF查看器组件允许在页面上包含PDF文档。

## 使用 {#usage}

核心组件PDF查看器组件嵌入了一个查看器，以在页面上显示作为资产存储的PDF文件。

## 版本和兼容性 {#version-and-compatibility}

PDF查看器组件的当前版本为v1，该版本于2020年6月随核心组件2.10.0版引入，在本文档中进行了描述。

下表详细列出了组件的所有受支持版本、组件版本与之兼容的AEM版本，以及指向以前版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | 兼容 | 兼容 | 兼容 |

有关核心组件版本和版本的更多信息，请参阅文档[核心组件版本](/help/versions.md)。

## 组件输出示例 {#sample-component-output}

要体验PDF查看器组件并查看其配置选项以及HTML和JSON输出的示例，请访问[组件库](https://adobe.com/go/aem_cmp_library_pdfviewer)。

## 技术详细信息 {#technical-details}

有关PDF查看器组件[的最新技术文档，请参阅GitHub](https://adobe.com/go/aem_cmp_tech_pdfviewer_v1)。

有关开发核心组件的更多详细信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

>[!NOTE]
>
>PDF查看器组件利用[Adobe的Document Services API](https://www.adobe.io/apis/documentcloud/dcsdk.html)，并要求管理员配置[上下文感知配置](/help/developing/context-aware-configs.md)以使用这些服务。 有关此配置的[详细信息，请查看组件的技术文档。](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/pdfviewer/v1/pdfviewer#context-aware-config)

## 配置对话框 {#configure-dialog}

配置对话框允许内容作者定义查看器及其行为方式和页面访客的显示方式。

### “配置”选项卡 {#configuration-tab}

“配置”选项卡允许作者定义应显示的PDF。 该路径可以定义为AEM中的资产或其他资源的绝对路径。

![PDF查看器组件编辑对话框的“配置”选项卡](/help/assets/pdf-viewer-edit-configuration.png)

### 自定义选项卡 {#customize-tab}

“自定义”选项卡允许作者定义查看器中向读者提供的选项以及查看器的显示方式。

![PDF查看器组件编辑对话框的自定义选项卡](/help/assets/pdf-viewer-edit-customize.png)

可用选项的数量取决于所选的&#x200B;**类型**。

* [全窗口](#full-window)  — 查看区域在完整浏览器中呈现。这最适合存储和生产效率应用。
* [大小容器](#sized-container)  — 查看区域在整个浏览器中呈现。这最适合存储和生产效率应用。
* [内嵌](#in-line)  — 在网页中以线条呈现的所有PDF页面。这最适合读取应用程序。

#### 全屏 {#full-window}

查看区域在整个浏览器中呈现。 这最适合存储和生产效率应用。

![PDF查看器组件编辑对话框的自定义选项卡全窗口选项](/help/assets/pdf-viewer-edit-customize-full.png)

* **默认视图模式**  — 查看器在显示页面时的大小
   * 适应页面
   * 适应宽度
* **全屏**  — 启用后，查看器将占用视区的全高/全宽。
* **注释工具**  — 启用注释工具后，即可使用注释工具。
* **左侧面板**  — 启用后，将显示左侧面板。
* **下载PDF**  — 启用后，将显示下载按钮。
* **打印PDF**  — 启用后，将显示打印按钮。
* **页面控件**  — 切换页面控件的行为。
   * 停靠
   * 取消停靠

#### 设定了大小的容器 {#sized-container}

查看区域在整个浏览器中呈现。 这最适合存储和生产效率应用。

![PDF查看器组件编辑对话框的自定义选项卡大小容器选项](/help/assets/pdf-viewer-edit-customize-sized-container.png)

* **全屏**  — 启用后，查看器将占用视区的全高/全宽。
* **下载PDF**  — 启用后，将显示下载按钮。
* **打印PDF**  — 启用后，将显示打印按钮。
* **页面控件**  — 切换页面控件的行为。
   * 停靠
   * 取消停靠

#### 嵌入式 {#in-line}

所有PDF页面在网页中以行形式呈现。 这最适合读取应用程序。

![PDF查看器组件编辑对话框的自定义选项卡大小容器选项](/help/assets/pdf-viewer-edit-customize-inline.png)

* **下载PDF**  — 启用后，将显示下载按钮。
* **打印PDF**  — 启用后，将显示打印按钮。

## “设计”对话框 {#design-dialog}

PDF查看器组件没有“设计”对话框。
