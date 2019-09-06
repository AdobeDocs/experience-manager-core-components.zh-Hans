---
title: 按钮组件
seo-title: 按钮组件
description: 'null'
seo-description: 核心组件按钮组件允许创建和显示按钮。
uuid: ec807de9-f76 c-4850-9e-c3 e439 a1 d626
contentOwner: 用户
content-type: 引用
topic-tags: 创作
products: SG_ EXPERIENCE MANAGER/CORECOMMPANES-new
discoiquuid: f093f58e-9755-4a4f-803a-ab93 a50 e6870
translation-type: tm+mt
source-git-commit: d37cde072dea612ccb55ad31b4aaf42f17839cb4

---


# 按钮组件{#button-component}

核心组件按钮组件允许在页面上配置和显示按钮项目。

## 使用情况 {#usage}

核心组件按钮组件允许在页面上包含按钮。

* 可以在 [配置对话框](#configure-dialog)中选择按钮的属性。
* 可以在 [设计对话框中定义按钮组件的样式](#design-dialog)。

## 版本和兼容性 {#version-and-compatibility}

Button组件的当前版本是v1，它是在2019年月发行的核心组件中引入的，该版本在文档中进行了介绍。

下表详细说明了组件的所有支持版本、组件版本的AEM版本以及以前版本的文档链接。

| 组件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |---|
| v1 | 兼容 | 兼容 | 兼容 |

有关核心组件版本和版本的更多信息，请参阅文档 [核心组件版本](versions.md)。

## 示例组件输出 {#sample-component-output}

要体验按钮组件以及查看其配置选项的示例以及HTML和JSON输出，请访问 [组件库](http://opensource.adobe.com/aem-core-wcm-components/library/button.html)。

## 技术详细信息 {#technical-details}

有关按钮组件 [的最新技术文档，请参阅GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/button/v1/button)。

有关开发核心组件的更多详细信息，请参阅 [核心组件开发人员文档](developing.md)。

## 配置对话框 {#configure-dialog}

配置对话框允许内容作者定义按钮及其行为，并为访客显示页面。

### 属性选项卡 {#properties-tab}

![](assets/screen-shot-2019-08-29-12.19.32.png)

* **文本** -要在按钮上显示的文本
* **链接** -链接到AEM中的内容页面、外部资源或锚点
   * 使用 **选择对话框** 在AEM中选择路径。
* **图标** -用于在按钮中显示图标的标识符

### 辅助功能选项卡 {#accessibility-tab}

![](assets/screen-shot-2019-08-29-12.19.43.png)

在 **辅助功能** 选项卡上，可以为组件设置 [AIR辅助功能](https://www.w3.org/WAI/standards-guidelines/aria/) 标签的值。

* **标签** -组件的ARRIA标签属性的值

## 设计对话框 {#design-dialog}

### 样式选项卡 {#styles-tab}

图像组件支持AEM [Style System](authoring.md#component-styling)。
