---
title: 标题组件
description: 核心组件标题组件是可进行就地编辑的区域标题组件。
role: Architect, Developer, Admin, User
exl-id: 393af72c-549f-4609-afb0-2712f827b549
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 3%

---

# 标题组件{#title-component}

核心组件标题组件是可进行就地编辑的区域标题组件。

## 使用 {#usage}

标题组件将用作内容部分的标题或标题。 可用的标题级别可由模板作者在[设计对话框](#design-dialog)中定义。 内容编辑器可以从[编辑对话框](#edit-dialog)的可用标题级别中进行选择。 为了方便起见，还提供了标题文本的简单就地编辑功能。

## 版本和兼容性 {#version-and-compatibility}

标题组件的当前版本为v2，该版本于2018年1月随核心组件2.0.0版引入，在本文档中进行了描述。

下表详细列出了组件的所有受支持版本、组件版本与之兼容的AEM版本，以及指向以前版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|---|
| v2 | 兼容 | 兼容 | 兼容 |
| [v1](v1/title-v1.md) | 兼容 | 兼容 | - |

有关核心组件版本和版本的更多信息，请参阅文档[核心组件版本](/help/versions.md)。

## 组件输出示例 {#sample-component-output}

要体验标题组件并查看其配置选项以及HTML和JSON输出的示例，请访问[组件库](https://adobe.com/go/aem_cmp_library_title)。

### 技术详细信息 {#technical-details}

有关标题组件[的最新技术文档，请参阅GitHub](https://adobe.com/go/aem_cmp_tech_title_v2)。

有关开发核心组件的更多详细信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## 编辑对话框 {#edit-dialog}

编辑对话框允许内容作者定义标题文本并选择标题级别。

* **标题**  — 如果为空，则将使用页面标题
* **类型/大小**  — 定义标题的标题级别
* **链接**  — 定义标题要链接到的内容。这可以是内容页面、外部URL或页面锚点的路径。
* **ID**  — 利用此选项，可控制HTML和数据层中组件的唯一标识符 [的唯一标识符](/help/developing/data-layer/overview.md)。
   * 如果留为空白，则会自动为您生成唯一ID，并且可以通过检查生成的页面找到该ID。
   * 如果指定了ID，则作者有责任确保该ID是唯一的。
   * 更改ID可能会影响CSS、JS和数据层跟踪。

![标题组件的编辑对话框](/help/assets/title-edit.png)

>[!NOTE]
>
>核心组件版本2.2.0中引入了为标题定义链接的功能。

就地编辑器还可用于编辑标题组件的文本。

![标题组件的就地编辑](/help/assets/title-edit-inline.png)

## “设计”对话框 {#design-dialog}

设计对话框允许模板作者定义标题组件在由内容作者创建时将具有的默认标题级别。

### “大小”选项卡 {#sizes-tab}

![标题组件的设计对话框](/help/assets/title-design.png)

* **作者允许的类型/大小**  — 启用或禁用内容作者在使用标题组件时可用的标题类型。
* **默认类型/大小** — 定义在内容作者将标题组件添加到页面时将自动分配的标题类型。
* **禁用链接** — 禁用对标题组件中链接的支持，以禁止内容作者从标题中进行链接。

>[!NOTE]
>
>核心组件版本2.2.0中引入了为标题定义链接的功能。

### “样式”选项卡 {#styles-tab}

标题组件支持AEM [样式系统](/help/get-started/authoring.md#component-styling)。

## Adobe客户端数据层 {#data-layer}

标题组件支持[Adobe客户端数据层。](/help/developing/data-layer/overview.md)
