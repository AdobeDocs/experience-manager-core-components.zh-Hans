---
title: 按钮组件
description: 核心组件按钮组件允许创建和显示按钮。
translation-type: tm+mt
source-git-commit: c186e9ec3944d785ab0376769cf7f2307049a809
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 2%

---


# 按钮组件{#button-component}

核心组件按钮组件允许在页面上配置和显示按钮项。

## 使用 {#usage}

核心组件按钮组件允许在页面中包含按钮。

* 可在“配置”对话框中选择按钮 [的属性](#configure-dialog)。
* 可在设计对话框中定义按钮组件 [的样式](#design-dialog)。

## 版本和兼容性 {#version-and-compatibility}

按钮组件的当前版本为v1,2019年6月在核心组件的2.5.0版中引入了v1，本文档中对此进行了说明。

下表详细列出了组件的所有受支持版本、与组件版本兼容的AEM版本以及指向先前版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM 云服务 |
|--- |--- |---|---|
| v1 | 兼容 | 兼容 | 兼容 |

有关核心组件版本和版本的详细信息，请参阅文档 [核心组件版本](/help/versions.md)。

## 示例组件输出 {#sample-component-output}

要体验“按钮”组件并查看其配置选项以及HTML和JSON输出的示例，请访问组 [件库](https://adobe.com/go/aem_cmp_library_button)。

## 技术详细信息 {#technical-details}

有关“按钮组件”的最 [新技术文档可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_button_v1)。

有关开发核心组件的更多详细信息，请参阅核 [心组件开发人员文档](/help/developing/overview.md)。

## 配置对话框 {#configure-dialog}

配置对话框允许内容作者定义按钮以及按钮的行为和显示方式，以便访客页面。

### 属性选项卡 {#properties-tab}

![按钮组件编辑对话框的属性选项卡](/help/assets/button-edit-properties.png)

* **文本** -按钮上显示的文本
* **链接** -链接到AEM中的内容页面、外部资源或锚点
   * 使用选 **择对话框** ，在AEM中选择路径。
* **图标** -用于在按钮中显示图标的标识符
* **ID** —— 此选项允许控制HTML和数据层中组件的唯一标 [识符](/help/developing/data-layer/overview.md)。
   * 如果留空，则会自动为您生成唯一ID，并可通过检查生成的页面找到该ID。
   * 如果指定了ID，则作者有责任确保它是唯一的。
   * 更改ID可能会影响CSS、JS和数据层跟踪。

### “辅助功能”选项卡 {#accessibility-tab}

![按钮组件编辑对话框的辅助功能选项卡](/help/assets/button-edit-accessibility.png)

在“辅 **助功能** ”选项卡上，可以为组 [件的ARIA辅助功](https://www.w3.org/WAI/standards-guidelines/aria/) 能标签设置值。

* **标签** -组件的ARIA标签属性的值

## 设计对话框 {#design-dialog}

### 样式选项卡 {#styles-tab}

图像组件支持AEM样 [式系统](/help/get-started/authoring.md#component-styling)。
