---
title: 标题组件
description: 核心组件标题组件是具有就地编辑功能的章节标题组件。
translation-type: tm+mt
source-git-commit: 4813748bcfa83ce7c73e81d4e4d445ecc8215d26
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 3%

---


# 标题组件{#title-component}

核心组件标题组件是具有就地编辑功能的章节标题组件。

## 使用 {#usage}

标题组件可用作内容部分的标题或标题。 可用标题级别可由模板作者在设计对话框中 [定义](#design-dialog)。 内容编辑器可以从编辑对话框的可用标题级别 [中进行选择](#edit-dialog)。 为了更方便，还可以对标题文本进行简单的就地编辑。

## 版本和兼容性 {#version-and-compatibility}

标题组件的当前版本为v2,2018年1月随核心组件版本2.0.0引入v2，该版本在本文档中进行了说明。

下表详细列出了组件的所有受支持版本、与组件版本兼容的AEM版本以及指向先前版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM 云服务 |
|---|---|---|---|
| v2 | 兼容 | 兼容 | 兼容 |
| [v1](v1/title-v1.md) | 兼容 | 兼容 | - |

有关核心组件版本和版本的详细信息，请参阅文档 [核心组件版本](/help/versions.md)。

## 示例组件输出 {#sample-component-output}

要体验标题组件以及查看其配置选项以及HTML和JSON输出的示例，请访问组 [件库](https://adobe.com/go/aem_cmp_library_title)。

### 技术详细信息 {#technical-details}

有关标题组件的最新技 [术文档，请访问GitHub](https://adobe.com/go/aem_cmp_tech_title_v2)。

有关开发核心组件的更多详细信息，请参阅核 [心组件开发人员文档](/help/developing/overview.md)。

## Edit Dialog {#edit-dialog}

通过编辑对话框，内容作者可以定义标题文本并选择标题级别。

* **标题** -如果为空，则将使用页面标题
* **类型／大小** -定义标题的标题级别
* **链接** -定义标题将链接到的内容。 这可以是内容页面、外部URL或页面锚点的路径。
* **ID** —— 此选项允许控制HTML和数据层中组件的唯一标 [识符](/help/developing/data-layer/overview.md)。
   * 如果留空，则会自动为您生成唯一ID，并可通过检查生成的页面找到该ID。
   * 如果指定了ID，则作者有责任确保它是唯一的。
   * 更改ID可能会影响CSS、JS和数据层跟踪。

![标题组件的编辑对话框](/help/assets/title-edit.png)

>[!NOTE]
>
>核心组件版本2.2.0引入了定义标题链接的功能。

就地编辑器还可用于编辑标题组件的文本。

![标题组件的就地编辑](/help/assets/title-edit-inline.png)

## 设计对话框 {#design-dialog}

设计对话框允许模板作者定义标题组件在内容作者创建时将具有的默认标题级别。

### “大小”选项卡 {#sizes-tab}

![标题组件的设计对话框](/help/assets/title-design.png)

* **作者允许的类型** /大小——启用或禁用内容作者在使用标题组件时可用的标题类型。
* **默认类型**/大小——定义在内容作者将标题组件添加到页面时将自动分配的标题类型。
* **禁用链接**-禁用标题组件中链接的支持，以禁止内容作者从标题中进行链接。

>[!NOTE]
>
>核心组件版本2.2.0引入了定义标题链接的功能。

### 样式选项卡 {#styles-tab}

标题组件支持AEM [样式系统](/help/get-started/authoring.md#component-styling)。
