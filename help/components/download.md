---
title: 下载组件
description: 核心组件下载组件允许在页面上创建下载选项。
translation-type: tm+mt
source-git-commit: c186e9ec3944d785ab0376769cf7f2307049a809
workflow-type: tm+mt
source-wordcount: '687'
ht-degree: 1%

---


# 下载组件{#download-component}

核心组件下载组件允许在页面上创建下载选项。

## 使用 {#usage}

核心组件下载组件允许在页面中包含下载选项及其关联的资产。

* 可以在[配置对话框](#configure-dialog)中选择下载选项的属性。
* 可以在[设计对话框](#design-dialog)中定义下载组件的默认值。

## 版本和兼容性{#version-and-compatibility}

下载组件的当前版本为v1,2019年6月随核心组件的2.5.0版引入了v1，该版本在本文档中进行了说明。

下表详细列出了组件的所有受支持版本、与组件版本兼容的AEM版本以及指向先前版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | 兼容 | 兼容 | 兼容 |

有关核心组件版本和版本的详细信息，请参阅文档[核心组件版本](/help/versions.md)。

## 示例组件输出{#sample-component-output}

要体验下载组件及其配置选项以及HTML和JSON输出的示例，请访问[组件库](https://adobe.com/go/aem_cmp_library_download)。

## 技术详细信息{#technical-details}

有关下载组件[的最新技术文档可在GitHub](https://adobe.com/go/aem_cmp_tech_download_v1)上找到。

有关开发核心组件的更多详细信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## 配置对话框{#configure-dialog}

配置对话框允许内容作者定义下载项以及下载项的行为和显示方式，以便访客页面。

![下载组件的编辑对话框的资产选项卡](/help/assets/download-edit-asset.png)

### 资产选项卡{#asset-tab}

选择下载资产与[图像组件](image.md)的功能非常相似，同样利用AEM DAM。

* **下载资产**
   * 从[资产浏览器](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html)中删除资产，或点按&#x200B;**浏览**&#x200B;选项，从本地文件系统中上传。
   * 点按或单击&#x200B;**清除**&#x200B;以取消选择当前选定的图像。
   * 点按或单击&#x200B;**编辑**&#x200B;以[在资产编辑器中管理资产](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/manage/manage-digital-assets.html)的演绎版。

### 属性选项卡{#properties-tab}

![下载组件的编辑对话框的属性选项卡](/help/assets/download-edit-properties.png)

* **标题** -显示为下载项的标题
   * **从DAM资产获取标题** -选中此选项后，标题将自动填充DAM资产的标题。
* **描述** -显示为下载项的描述性子标题
   * **从DAM资产获取描述** -选中此选项后，将自动填充DAM资产的描述。
* **操作文本** -显示为下载项的操作文本
   * 从文件系统上传资产时，此字段为必填字段。
   * **内联显示** -选择后，提供的操作文 **本** 将内联显示。
* **ID**  —— 此选项允许控制HTML和数据层中组件的唯一标 [识符](/help/developing/data-layer/overview.md)。
   * 如果留空，则会自动为您生成唯一ID，并可通过检查生成的页面找到该ID。
   * 如果指定了ID，则作者有责任确保它是唯一的。
   * 更改ID可能会影响CSS、JS和数据层跟踪。

## 设计对话框{#design-dialog}

设计对话框允许模板作者定义使用下载组件的内容作者可用的选项。

### 属性选项卡{#properties-tab-design}

![下载组件的“设计”对话框](/help/assets/download-design.png)

* **允许从文件系统上传** -允许内容作者从其本地文件系统中上传资产作为下载资产。
   * 将取消选择默认值。
* **标题类型** -用于下载组件标题的HTML元素。
   * 如果未选择任何值，则默认值为H3。
* **显示文件大小** -选中后，资产的文件大小将显示在下载组件中。
   * 默认值被选中。
* **显示文件格式** -选中后，资产的文件格式将显示在下载组件中。
   * 默认值被选中。
* **显示文件名** -选中后，资产的文件名将显示在下载组件中。
   * 默认值被选中。

### 样式选项卡{#styles-tab}

映像组件支持AEM [样式系统](/help/get-started/authoring.md#component-styling)。
