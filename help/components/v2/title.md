---
title: 标题组件 (v2)
description: 核心组件标题组件是章节标题组件，具备就地编辑的功能。
role: Architect, Developer, Admin, User
source-git-commit: e5251010ca41025eb2bb56b66164ecf4cc0145c8
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 94%

---


# 标题组件 (v2) {#title-component}

核心组件标题组件是章节标题组件，具备就地编辑的功能。

## 用途 {#usage}

标题组件旨在用作内容章节的标题。可用的标题级别可由模板作者在[“设计”对话框](#design-dialog)中定义。内容编辑者可以在[“编辑”对话框](#edit-dialog)中从可用标题级别选择。为了增加便利性，可以简单地就地编辑标题文本。

## 版本和兼容性 {#version-and-compatibility}

本文档介绍了标题组件的v2，该组件在2018年1月的核心组件版本2.0.0中引入。

>[!CAUTION]
>
>本文档介绍标题组件的v2。
>
>有关当前版本的标题组件的详细信息，请参阅[标题组件](/help/components/title.md)文档。

## 示例组件输出 {#sample-component-output}

要体验标题组件并查看其配置选项示例以及 HTML 和 JSON 输出，请访问[组件库](https://adobe.com/go/aem_cmp_library_title_cn)。

### 技术详细信息 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_title_v2_cn)有关标题组件的最新技术文档。

在[核心组件开发人员文档](/help/developing/overview.md)中可找到有关开发核心组件的其他详细信息。

## “编辑”对话框 {#edit-dialog}

内容作者可以使用“编辑”对话框定义标题文本以及选择标题级别。

* **标题** - 如果为空，则使用页面标题
* **类型/大小** - 定义标题的标题级别
* **链接** - 定义标题将链接到的内容。这可以是内容页面的路径、外部 URL 或页面锚点。
* **ID** - 利用此选项，可以控制 HTML 和[ Data Layer ](/help/developing/data-layer/overview.md)中的组件的唯一标识符。
   * 如果留空，系统会自动为您生成一个唯一 ID，可以通过检查结果页面找到该 ID。
   * 如果指定一个 ID，作者有责任确保它是唯一的。
   * 更改此 ID 会对 CSS、JS 和 Data Layer 跟踪产生影响。

![标题组件的“编辑”对话框](/help/assets/title-edit.png)

>[!NOTE]
>
>为标题定义链接的功能在核心组件发行版本 2.2.0 中引入。

就地编辑器也可以用于编辑标题组件的文本。

![就地编辑标题组件](/help/assets/title-edit-inline.png)

## “设计”对话框 {#design-dialog}

模板作者可以使用“设计”对话框定义内容作者在创建标题组件时具有的默认标题级别。

### “大小”选项卡 {#sizes-tab}

![标题组件的“设计”对话框](/help/assets/title-design.png)

* **为作者允许的类型/大小** - 启用或禁用内容作者在使用标题组件时可用的标题类型。
* **默认类型/大小** - 定义内容作者在将标题组件添加到页面时，将自动分配的标题类型。
* **禁用链接**- 禁用标题组件中对链接的支持，从而不允许内容作者从标题进行链接。

>[!NOTE]
>
>为标题定义链接的功能在核心组件发行版本 2.2.0 中引入。

### “样式”选项卡 {#styles-tab}

标题组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。

## Adobe Client Data Layer {#data-layer}

标题组件支持 [Adobe Client Data Layer](/help/developing/data-layer/overview.md)。
