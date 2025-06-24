---
title: 下载组件
description: 利用核心组件下载组件，可在页面上创建下载选项。
role: Architect, Developer, Admin, User
exl-id: 48e7ade0-b849-4d1f-b836-51196e5ac507
source-git-commit: dd30def59a8f037864da875ef4c831b11f766e57
workflow-type: tm+mt
source-wordcount: '741'
ht-degree: 100%

---


# 下载组件{#download-component}

利用核心组件下载组件，可在页面上创建下载选项。

{{traditional-aem}}

## 用途 {#usage}

利用核心组件下载组件，可在页面上包括下载选项及其关联的资源。

* 在[“配置”对话框](#configure-dialog)中可选择下载选项的属性。
* 下载组件的默认值可在[“设计”对话框](#design-dialog)中定义。

## 版本和兼容性 {#version-and-compatibility}

下载组件的当前版本是 v2，此版本随 2022 年 2 月的核心组件发行版 2.18.0 的发布引入，具体说明见本文。

下表详细说明了该组件的所有受支持版本、与该组件的版本兼容的 AEM 版本以及指向早期版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|--- |--- |---|---|---|
| v2 | - | 兼容 | 兼容 | 兼容 |
| [v1](v1/download.md) | 兼容 | 兼容 | - | 兼容 |

有关核心组件版本的更多信息，请参阅文档[核心组件版本](/help/versions.md)。

## 示例组件输出 {#sample-component-output}

要体验下载组件并查看其配置选项示例以及 HTML 和 JSON 输出，请访问[组件库](https://adobe.com/go/aem_cmp_library_download_cn)。

## 技术详细信息 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_download_v2_cn)有关下载组件的最新技术文档。

在[核心组件开发人员文档](/help/developing/overview.md)中可找到有关开发核心组件的其他详细信息。

## “配置”对话框 {#configure-dialog}

利用“配置”对话框，内容作者可以定义下载项目，以及对于页面的访客它会如何表现和显示。

![下载组件“编辑”对话框的“资源”选项卡](/help/assets/download-edit-asset.png)

### “资源”选项卡 {#asset-tab}

下载资源的选择与[图像组件](image.md)非常相似，同样利用了 AEM 的 DAM。

* **下载资源**
   * 通过[资源浏览器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html)拖放资源或点击&#x200B;**浏览**&#x200B;选项，以从本地文件系统上传。
   * 点按或单击&#x200B;**“清除”**&#x200B;以取消选择当前选定的图像。
   * 点击或单击&#x200B;**“编辑”**&#x200B;可在资源编辑器中[管理资源的再现](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html)。

### “属性”选项卡 {#properties-tab}

![下载组件“编辑”对话框的“属性”选项卡](/help/assets/download-edit-properties.png)

* **标题** - 为下载项目的显示标题
   * **从 DAM 资源获取标题** - 在选中时，使用 DAM 资源的标题自动填充标题。
* **描述** - 显示为下载项目的描述性子标题
   * **从 DAM 资源获取描述** - 在选中时，使用 DAM 资源的描述自动填充描述。
* **操作文本** - 为下载项目显示的操作文本
   * 从文件系统上传资源时，此字段必填。
   * **显示内联** - 选中时，提供的&#x200B;**操作文本**&#x200B;将显示内联。
* **ID** - 利用此选项，可以控制 HTML 和 [Data Layer](/help/developing/data-layer/overview.md) 中的组件的唯一标识符。
   * 如果留空，系统会自动为您生成一个唯一 ID，可以通过检查结果页面找到该 ID。
   * 如果指定一个 ID，作者有责任确保它是唯一的。
   * 更改此 ID 会对 CSS、JS 和数据层跟踪产生影响。

### “样式”选项卡 {#styles-tab-edit}

![下载组件“编辑”对话框的“样式”选项卡](/help/assets/download-edit-styles.png)

下载组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。

使用下拉菜单选择要应用于该组件的样式。在“编辑”对话框中所做的选择与从组件工具栏中选择的操作效果相同。

必须在[“设计”对话框](#design-dialog)中为此组件配置样式，以便下拉菜单可用。

## “设计”对话框 {#design-dialog}

使用“设计”对话框，模板作者可以定义哪些选项可供使用下载组件的内容作者使用。

### “属性”选项卡 {#properties-tab-design}

![下载组件“设计”对话框](/help/assets/download-design.png)

* **允许从文件系统上传资源** - 允许内容作者从其本地文件系统上传资源作为下载资源。
   * 默认值为未选中。
* **标题类型** - 为下载组件的标题使用的 HTML 元素。
   * 如果未选中值，则默认值为 H3。
* **显示文件大小** - 在选中时，资源的文件大小将显示在下载组件中。
   * 默认值为选中。
* **显示文件格式** - 在选中时，资源的文件格式将显示在下载组件中。
   * 默认值为选中。
* **显示文件名** - 在选中时，资源的文件名将显示在下载组件中。
   * 默认值为选中。

### “样式”选项卡 {#styles-tab}

图像组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。
