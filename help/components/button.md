---
title: 按钮组件
description: 核心组件按钮组件允许创建和显示按钮。
role: Architect, Developer, Administrator, Business Practitioner
exl-id: e17efd1d-90d4-497a-9e7d-45934d81bc28
source-git-commit: 8ff36ca143af9496f988b1ca65475497181def1d
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 3%

---

# 按钮组件{#button-component}

核心组件按钮组件允许在页面上配置和显示按钮项目。

## 使用 {#usage}

核心组件按钮组件允许在页面上包含按钮。

* 可以在[配置对话框](#configure-dialog)中选择按钮的属性。
* 可以在[设计对话框](#design-dialog)中定义按钮组件的样式。

## 版本和兼容性{#version-and-compatibility}

按钮组件的当前版本为v1，该版本于2019年6月随核心组件2.5.0版引入，在本文档中进行了描述。

下表详细列出了组件的所有受支持版本、组件版本与之兼容的AEM版本，以及指向以前版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | 兼容 | 兼容 | 兼容 |

有关核心组件版本和版本的更多信息，请参阅文档[核心组件版本](/help/versions.md)。

## 组件输出示例{#sample-component-output}

要体验按钮组件并查看其配置选项以及HTML和JSON输出的示例，请访问[组件库](https://adobe.com/go/aem_cmp_library_button)。

## 技术详细信息{#technical-details}

有关按钮组件[的最新技术文档可在GitHub](https://adobe.com/go/aem_cmp_tech_button_v1)上找到。

有关开发核心组件的更多详细信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## 配置对话框{#configure-dialog}

配置对话框允许内容作者定义按钮以及按钮的行为和显示方式，以供页面访客访问。

### 属性选项卡{#properties-tab}

![按钮组件编辑对话框的属性选项卡](/help/assets/button-edit-properties.png)

* **文本**  — 要在按钮上显示的文本
* **链接**  — 链接到AEM、外部资源或锚点中的内容页面
   * 使用&#x200B;**选择对话框**&#x200B;在AEM中选择路径。
* **图标**  — 在按钮中显示图标的标识符
* **ID**  — 利用此选项，可控制HTML和数据层中组件的唯一标识符 [的唯一标识符](/help/developing/data-layer/overview.md)。
   * 如果留为空白，则会自动为您生成唯一ID，并且可以通过检查生成的页面找到该ID。
   * 如果指定了ID，则作者有责任确保该ID是唯一的。
   * 更改ID可能会影响CSS、JS和数据层跟踪。

### 辅助功能选项卡{#accessibility-tab}

![按钮组件编辑对话框的辅助功能选项卡](/help/assets/button-edit-accessibility.png)

在&#x200B;**辅助功能**&#x200B;选项卡上，可以为组件的[ARIA辅助功能](https://www.w3.org/WAI/standards-guidelines/aria/)标签设置值。

* **标签**  — 组件的ARIA标签属性的值

## 设计对话框{#design-dialog}

### 样式选项卡{#styles-tab}

按钮组件支持AEM [样式系统](/help/get-started/authoring.md#component-styling)。

## Adobe客户端数据层{#data-layer}

按钮组件支持[Adobe客户端数据层。](/help/developing/data-layer/overview.md)
