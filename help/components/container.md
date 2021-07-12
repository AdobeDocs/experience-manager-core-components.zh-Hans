---
title: 容器组件
description: 核心组件容器组件允许为页面上的多个其他组件创建容器。
role: Architect, Developer, Admin, User
exl-id: 53c7190d-44cb-42ff-bc1a-483c7875bcf8
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '792'
ht-degree: 2%

---

# 容器组件{#container-component}

核心组件容器组件允许为页面上的多个其他组件创建容器。

## 使用 {#usage}

核心组件容器组件允许为页面上的多个其他组件创建容器，并可用于将其他组件分组并应用通用样式或布局。

* 可以在[配置对话框](#configure-dialog)中选择容器的属性。
* 在[设计对话框](#design-dialog)中可定义将容器组件添加到页面时的默认值。

## 版本和兼容性 {#version-and-compatibility}

容器组件的当前版本为v1,2019年6月2.5.0版核心组件中引入了v1，本文档对此进行了描述。

下表详细列出了组件的所有受支持版本、组件版本与之兼容的AEM版本，以及指向以前版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | 兼容 | 兼容 | 兼容 |

有关核心组件版本和版本的更多信息，请参阅文档[核心组件版本](/help/versions.md)。

## 组件输出示例 {#sample-component-output}

要体验容器组件并查看其配置选项以及HTML和JSON输出的示例，请访问[组件库](https://adobe.com/go/aem_cmp_library_container)。

## 技术详细信息 {#technical-details}

有关容器组件[的最新技术文档可在GitHub](https://adobe.com/go/aem_cmp_tech_container_v1)上找到。

有关开发核心组件的更多详细信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## 配置对话框 {#configure-dialog}

配置对话框允许内容作者定义容器项目以及容器项目的行为和显示方式，以供页面访客访问。

![容器组件的编辑对话框](/help/assets/container-edit.png)

* **布局**  — 此选项定义容器组件的行为或布局行为。
   * **简单**  — 将容器定义为组件的简单集合
   * **响应式网格**  — 将容器定义为 [AEM响应式布局](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/responsive-layout.html)
* **背景颜色**  — 可定义为自由格式RGB值，或使用拾色器(具体取决于 [配置)](#background-tab)
* **背景图像**  — 根据配置为容器定义  [背景颜色](#background-tab)
* **ID**  — 利用此选项，可控制HTML和数据层中组件的唯一标识符 [的唯一标识符](/help/developing/data-layer/overview.md)。
   * 如果留为空白，则会自动为您生成唯一ID，并且可以通过检查生成的页面找到该ID。
   * 如果指定了ID，则作者有责任确保该ID是唯一的。
   * 更改ID可能会影响CSS、JS和数据层跟踪。

## “设计”对话框 {#design-dialog}

设计对话框允许模板作者定义内容作者可以使用容器组件的选项。

### 允许的组件选项卡 {#allowed-components-tab}

**允许的组件**&#x200B;选项卡用于定义哪些组件可以作为内容作者添加到容器组件的项目。

当[在模板编辑器中定义布局容器的策略和属性时，允许的组件选项卡的功能与同名的选项卡相同。](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)

### “默认组件”选项卡 {#default-components-tab}

默认组件选项卡用于定义在容器上放置特定资产类型时向组件添加的组件，与在页面模板](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)中定义默认组件的方式类似。[

### 响应设置选项卡 {#responsive-settings-tab}

![容器组件设计对话框的响应设置选项卡](/help/assets/container-design-responsive.png)

* **列**  — 定义生成容器的网格中的列数。

### “背景”选项卡 {#background-tab}

![容器组件“设计”对话框的“背景”选项卡](/help/assets/container-design-background.png)

* **背景图像**
   * **启用背景图像**  — 选择此选项可允许内容作者为容器定义背景图像。
* **背景颜色**
   * **启用背景颜色**  — 选择此选项可允许内容作者为容器定义背景颜色。
   * **仅限色板**  — 选择此选项仅允许内容作者从容器背景颜色的预定义颜色色板中进行选择。
      * 仅当选择&#x200B;**启用背景颜色**&#x200B;时可用
* **允许的色板**  — 定义预定义的颜色，内容作者可以从中选择容器背景颜色
   * 使用&#x200B;**Add**&#x200B;按钮添加预定义的色板。 添加后，会将一个条目添加到列表中，该列包含以下列：
   * **值**  — 通过RGB值手动定义颜色
      * 点按或单击拾色器，通过调整单个RGB值或定义十六进制值，更轻松地选择颜色。
   * **删除**  — 点按或单击以删除色板。
   * **重新排列**  — 点按或单击并拖动以重新排列样本的顺序。

### “样式”选项卡 {#styles-tab}

容器组件支持AEM [样式系统](/help/get-started/authoring.md#component-styling)。
