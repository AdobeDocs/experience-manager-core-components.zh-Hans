---
title: 容器组件
description: 核心组件容器组件允许为页面上的多个其他组件创建容器。
translation-type: tm+mt
source-git-commit: 65f900ad6759206a13f2bda6169900f62d968d8d

---


# 容器组件{#container-component}

核心组件容器组件允许为页面上的多个其他组件创建容器。

## 使用情况 {#usage}

核心组件容器组件允许为页面上的多个其他组件创建容器，并可用于对其他组件进行分组和应用通用样式或布局。

* 可以在配置对话框中选择容器 [的属性](#configure-dialog)。
* 将容器组件添加到页面时的默认值可以在设计对话框中 [定义](#design-dialog)。

## 版本和兼容性 {#version-and-compatibility}

容器组件的当前版本为v1,v1是在2019年6月随核心组件版本2.5.0一起引入的，本文档对此进行了说明。

下表详细列出了组件的所有受支持版本、与组件版本兼容的AEM版本，以及指向先前版本的文档的链接。

| 组件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM作为云服务 |
|--- |--- |--- |---|---|
| v1 | 兼容 | 兼容 | 兼容 | 兼容 |

有关核心组件版本和版本的详细信息，请参阅文档核 [心组件版本](versions.md)。

## 示例组件输出 {#sample-component-output}

要体验容器组件及其配置选项的示例以及HTML和JSON输出，请访问组件 [库](https://adobe.com/go/aem_cmp_library_container)。

## 技术详细信息 {#technical-details}

有关“容器组件”的最新技 [术文档可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_container_v1)。

有关开发核心组件的更多详细信息，请参阅核 [心组件开发人员文档](developing.md)。

## 配置对话框 {#configure-dialog}

配置对话框允许内容作者定义容器项以及容器项的行为和对页面访客的显示方式。

![](assets/screen-shot-2019-06-21-13.59.26.png)

* **布局** -此选项定义容器组件的行为或布局行为。
   * **简单** -将容器定义为组件的简单集合
   * **响应式网格** -将容器定义为 [AEM响应式布局](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/responsive-layout.html)
* **ID** —— 使用此选项可定义要应用到组件的HTML ID属性。
* **背景颜色** -可定义为自由形式的RGB值，或者使用拾色器(具体取决于 [配置)](#background-tab)
* **背景图像** -根据配置定义容器的 [背景颜色](#background-tab)

## 设计对话框 {#design-dialog}

设计对话框允许模板作者定义使用容器组件的内容作者可用的选项。

### 允许的组件选项卡 {#allowed-components-tab}

允 **许的组件** (Allowed Components)选项卡用于定义哪些组件可以作为内容作者添加到容器组件的项目。

在模板编辑器中定义布局容器的策略和属性时，“允许的组件”选项卡 [的功能与同名选项卡的功能相同。](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)

### 默认组件选项卡 {#default-components-tab}

默认组件选项卡用于定义在容器上丢弃特定资产类型时添加到组件的组件，与在页面模板上定义默认组件的 [方式类似](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)。

### 响应式设置选项卡 {#responsive-settings-tab}

![](assets/screen-shot-2019-06-21-09.33.03.png)

* **列** -定义生成容器网格中的列数。

### 背景选项卡 {#background-tab}

![](assets/screen-shot-2019-06-21-09.42.42.png)

* **背景图像**
   * **启用背景图像** -选择此选项可使内容作者能够为容器定义背景图像。
* **背景颜色**
   * **启用背景颜色** -选择此选项可使内容作者能够为容器定义背景颜色。
   * **仅限色板** -选择此选项可仅允许内容作者从预定义的容器背景颜色色板中进行选择。
      * 仅当选择“启 **用背景颜色** ”时可用
* **允许的色板** -定义预定义的颜色，内容作者可以从中选择容器背景颜色
   * 使用“ **添加** ”按钮可添加预定义的色板。 添加后，一个条目将添加到列表，其中包含以下列：
   * **值** -通过RGB值手动定义颜色
      * 点按或单击拾色器，通过调整单个RGB值或定义十六进制值更轻松地选择颜色。
   * **删除** -点按或单击以删除色板。
   * **重新排列** -点按或单击并拖动以重新排列色板的顺序。

### 样式选项卡 {#styles-tab}

容器组件支持AEM样 [式系统](authoring.md#component-styling)。
