---
title: 下载组件
description: 核心组件下载组件允许在页面上创建下载选项。
translation-type: tm+mt
source-git-commit: 65f900ad6759206a13f2bda6169900f62d968d8d

---


# 下载组件{#download-component}

核心组件下载组件允许在页面上创建下载选项。

## 使用情况 {#usage}

核心组件下载组件允许在页面中包含下载选项及其关联的资产。

* 可以在配置对话框中选择下载选项的 [属性](#configure-dialog)。
* 可在设计对话框中定义下载组件的 [默认值](#design-dialog)。

## 版本和兼容性 {#version-and-compatibility}

下载组件的当前版本为v1,v1是2019年6月随核心组件版本2.5.0引入的，本文档对此进行了说明。

下表详细列出了组件的所有受支持版本、与组件版本兼容的AEM版本，以及指向先前版本的文档的链接。

| 组件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM作为云服务 |
|--- |--- |--- |---|---|
| v1 | 兼容 | 兼容 | 兼容 | 兼容 |

有关核心组件版本和版本的详细信息，请参阅文档核 [心组件版本](versions.md)。

## 示例组件输出 {#sample-component-output}

要体验下载组件以及查看其配置选项的示例以及HTML和JSON输出，请访问组 [件库](https://adobe.com/go/aem_cmp_library_download)。

## 技术详细信息 {#technical-details}

有关下载组件的最新技术文 [档可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_download_v1)。

有关开发核心组件的更多详细信息，请参阅核 [心组件开发人员文档](developing.md)。

## 配置对话框 {#configure-dialog}

配置对话框允许内容作者定义下载项以及下载项的行为和对页面访客的显示方式。

![](assets/screen-shot-2019-06-17-09.49.14.png)

### 资产选项卡 {#asset-tab}

选择的下载资产与图像组件的功能非常相似 [](image.md) ，并且同样利用AEM的DAM。

* **下载资产**
   * 从资产浏览器中 [拖放资产](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html) ，或点 **按浏览选项** ，以从本地文件系统上传。
   * 点按或单 **击清除** ，以取消选择当前选定的图像。
   * 点按或单 **击编辑** , [以在资产编辑器中管理资产的演绎版](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/manage/manage-digital-assets.html) 。

### 属性选项卡 {#properties-tab}

![](assets/screen-shot-2019-06-17-09.49.51.png)

* **标题** -显示为下载项的标题
   * **从DAM资产获取标题** -选中后，标题将自动填充DAM资产的标题。
* **说明** -显示为下载项的描述性子标题
   * **从DAM资产获取描述** -选择此选项后，将自动填充DAM资产的描述。
* **操作文本** -显示为下载项的操作文本
   * 从文件系统上传资产时，此字段为必填字段。
   * **内联显示** -选择后，提供的操作文 **本将内联显示** 。

## 设计对话框 {#design-dialog}

设计对话框允许模板作者定义使用下载组件的内容作者可用的选项。

### 属性选项卡 {#properties-tab-design}

![](assets/screen-shot-2019-06-17-10.04.31.png)

* **默认操作文本** -定义作者将下载 **** 组件添加到页面时提供的默认操作文本。
* **允许从文件系统上传** -允许内容作者从其本地文件系统中将资产上传为下载资产。
   * 将取消选择默认值。
* **标题类型** -用于下载组件标题的HTML元素。
   * 如果未选择任何值，则默认值为H3。
* **显示文件大小** -选择后，资产的文件大小将显示在下载组件中。
   * 将选择默认值。
* **显示文件格式** -选择后，资产的文件格式将显示在下载组件中。
   * 将选择默认值。
* **显示文件名** -选择后，资产的文件名将显示在下载组件中。
   * 将选择默认值。

### 样式选项卡 {#styles-tab}

图像组件支持AEM样 [式系统](authoring.md#component-styling)。
