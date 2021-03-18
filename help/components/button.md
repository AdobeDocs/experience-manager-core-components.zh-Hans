---
title: 按钮组件
description: 核心组件按钮组件允许创建和显示按钮。
role: 架构师、开发人员、管理员、业务从业者
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '456'
ht-degree: 3%

---


# 按钮组件{#button-component}

核心组件按钮组件允许在页面上配置和显示按钮项。

## 使用 {#usage}

核心组件按钮组件允许在页面中包含按钮。

* 可在[配置对话框](#configure-dialog)中选择按钮的属性。
* 可在[设计对话框](#design-dialog)中定义按钮组件的样式。

## 版本和兼容性{#version-and-compatibility}

Button Component的当前版本为v1,2019年6月随核心组件版本2.5.0引入了v1，本文档对此进行了说明。

下表详细列出了组件的所有受支持版本、与组件版本兼容的AEM版本，以及指向先前版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | 兼容 | 兼容 | 兼容 |

有关核心组件版本和版本的详细信息，请参阅文档[核心组件版本](/help/versions.md)。

## 示例组件输出{#sample-component-output}

要体验“按钮组件”及其配置选项以及HTML和JSON输出的示例，请访问[组件库](https://adobe.com/go/aem_cmp_library_button)。

## 技术详细信息{#technical-details}

有关“按钮组件[”的最新技术文档可在GitHub](https://adobe.com/go/aem_cmp_tech_button_v1)上找到。

有关开发核心组件的更多详细信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## 配置对话框{#configure-dialog}

通过“配置”对话框，内容作者可以定义按钮，以及按钮的行为和显示方式，以便访客页面。

### 属性选项卡{#properties-tab}

![按钮组件编辑对话框的属性选项卡](/help/assets/button-edit-properties.png)

* **文本**  — 按钮上显示的文本
* **链接**  — 链接到AEM、外部资源或锚点中的内容页面
   * 使用&#x200B;**选择对话框**&#x200B;在AEM中选择路径。
* **图标**  — 用于在按钮中显示图标的标识符
* **ID**  — 此选项允许控制HTML和数据层中组件的唯一 [标识符](/help/developing/data-layer/overview.md)。
   * 如果留空，系统会为您自动生成唯一ID，通过检查生成的页面可以找到它。
   * 如果指定了ID，则作者有责任确保它是唯一的。
   * 更改ID可能会影响CSS、JS和数据图层跟踪。

### 辅助功能选项卡{#accessibility-tab}

![按钮组件编辑对话框的“辅助功能”选项卡](/help/assets/button-edit-accessibility.png)

在&#x200B;**辅助功能**&#x200B;选项卡上，可以为组件的[ARIA辅助功能](https://www.w3.org/WAI/standards-guidelines/aria/)标签设置值。

* **Label**  — 组件的ARIA label属性值

## 设计对话框{#design-dialog}

### 样式选项卡{#styles-tab}

按钮组件支持AEM [样式系统](/help/get-started/authoring.md#component-styling)。

## Adobe客户端数据层{#data-layer}

按钮组件支持[Adobe客户端数据层。](/help/developing/data-layer/overview.md)
