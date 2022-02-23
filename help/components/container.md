---
title: 容器组件
description: 使用核心组件容器组件，可在页面上为多个其他组件创建容器。
role: Architect, Developer, Admin, User
exl-id: 53c7190d-44cb-42ff-bc1a-483c7875bcf8
source-git-commit: 9767a3a10cb9a77f385edc0ac3fb00096c0087af
workflow-type: ht
source-wordcount: '790'
ht-degree: 100%

---

# 容器组件{#container-component}

使用核心组件容器组件，可在页面上为多个其他组件创建容器。

## 用途 {#usage}

使用核心组件容器组件，可在页面上为多个其他组件创建容器，并可用于分组其他组件以及应用通用样式或布局。

* 在[“配置”对话框](#configure-dialog)中可选择容器的属性。
* 将容器组件添加到页面时的默认值可以在[“设计”对话框](#design-dialog)中定义。

## 版本和兼容性 {#version-and-compatibility}

容器组件的当前版本是 v1，此版本随 2019 年 6 月的核心组件发行版本 2.5.0 的发布引入，具体说明见本文。

下表详细说明了该组件的所有受支持版本、与该组件的版本兼容的 AEM 版本以及指向早期版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | 兼容<br>[版本 2.17.4](/help/versions.md) 和更低版本 | 兼容 | 兼容 |

有关核心组件版本的更多信息，请参阅文档[核心组件版本](/help/versions.md)。

## 示例组件输出 {#sample-component-output}

要体验容器组件并查看其配置选项示例以及 HTML 和 JSON 输出，请访问[组件库](https://adobe.com/go/aem_cmp_library_container_cn)。

## 技术详细信息 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_container_v1_cn)有关容器组件的最新技术文档。

在[核心组件开发人员文档](/help/developing/overview.md)中可找到有关开发核心组件的其他详细信息。

## “配置”对话框 {#configure-dialog}

利用“配置”对话框，内容作者可以定义容器项目，以及对于页面访客它会如何表现和显示。

![容器组件的“编辑”对话框](/help/assets/container-edit.png)

* **布局** - 此选项定义容器组件的行为或布局行为。
   * **简单** - 将容器定义为简单的组件集合
   * **响应式网格** - 将容器定义为 [AEM 响应式布局](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/responsive-layout.html)
* **背景颜色** - 定义为自由格式的 RGB 值，或者使用拾色器，[具体取决于配置](#background-tab)
* **背景图像** - 定义容器的背景颜色，[具体取决于配置](#background-tab)
* **ID** - 利用此选项，可以控制 HTML 和 [Data Layer](/help/developing/data-layer/overview.md) 中的组件的唯一标识符。
   * 如果留空，系统会自动为您生成一个唯一 ID，可以通过检查结果页面找到该 ID。
   * 如果指定一个 ID，作者有责任确保它是唯一的。
   * 更改此 ID 会对 CSS、JS 和 Data Layer 跟踪产生影响。

## “设计”对话框 {#design-dialog}

使用“设计”对话框，模板作者可以定义哪些选项可供使用容器组件的内容作者使用。

### “允许的组件”选项卡 {#allowed-components-tab}

**“允许的组件”**&#x200B;选项卡用于定义哪些组件可由内容作者作为项目添加到容器组件。

“允许的组件”选项卡的功能，与[在模板编辑器的布局容器中定义策略和属性时](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)的同名选项卡的功能相同。

### “默认组件”选项卡 {#default-components-tab}

“默认组件”选项卡用于定义在特定资源类型放到容器上时，要向组件中添加哪些组件，类似于[如何在页面模板上定义默认组件](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)。

### “响应式设置”选项卡 {#responsive-settings-tab}

![容器组件的“设计”对话框的“响应式设置”选项卡](/help/assets/container-design-responsive.png)

* **列数** - 定义所生成容器的网格中的列数。

### “背景”选项卡 {#background-tab}

![容器组件的“设计”对话框的“背景”选项卡](/help/assets/container-design-background.png)

* **背景图像**
   * **启用背景图像** - 选择此选项可允许内容作者定义容器的背景图像。
* **背景颜色**
   * **启用背景颜色** - 选择此选项可允许内容作者定义容器的背景颜色。
   * **仅色板** - 选择此选项可仅允许内容作者从预定义的色板中选择容器的背景颜色。
      * 仅在选择了&#x200B;**“启用背景颜色”**&#x200B;时可用
* **允许的色板** - 定义内容作者可从中选择容器背景颜色的预定义颜色
   * 使用&#x200B;**“添加”**&#x200B;按钮可添加预定义的色板。在添加之后，一个条目将添加到列表中，包含以下列：
   * **值** - 通过 RGB 值手动定义颜色
      * 点击或单击拾色器，以通过调整单独的 RGB 值或定义十六进制值，更轻松地选择颜色。
   * **删除** - 点击或单击以删除色板。
   * **重新排列** - 点击或单击并拖动以重新排列色板。

### “样式”选项卡 {#styles-tab}

容器组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。
