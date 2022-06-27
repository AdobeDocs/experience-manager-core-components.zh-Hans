---
title: 目录组件
description: 目录组件会根据页面内容中的标题创建一个ToC，以便读者快速导航页面。
role: Architect, Developer, Admin, User
exl-id: 006adde2-ebff-4e74-8e79-325cccd43e8f
source-git-commit: 394a8b968d7bcde7e766ed719c5914ec5cb60744
workflow-type: tm+mt
source-wordcount: '759'
ht-degree: 22%

---

# 目录组件 {#table-of-contents-component}

目录组件会根据页面内容中的标题创建一个ToC，以便读者快速导航页面。

## 用途 {#usage}

目录组件使网站访客能够根据页面内容的标题，通过高效生成的ToC快速导航页面内容。

* ToC在服务器端生成。
* 调度程序已完全缓存该缓存，以便快速交付。
* 它适用于页面上的所有组件，而不仅仅是核心组件。

的 [编辑对话框](#edit-dialog) 允许内容作者定义要在ToC中使用的标题范围。 使用 [设计对话框](#design-dialog)，则当内容作者将目录组件添加到页面时，模板作者可以设置标题的默认值，并根据类名限制ToC中包含的标题。

## 版本和兼容性 {#version-and-compatibility}

目录组件的当前版本为v1，该版本于2022年5月随核心组件2.20.0版引入，在本文档中进行了描述。

下表详细说明了该组件的所有受支持版本、与该组件的版本兼容的 AEM 版本以及指向早期版本文档的链接。

| 组件版本 | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | 兼容 | 兼容 |

有关核心组件版本的更多信息，请参阅文档[核心组件版本](/help/versions.md)。

## 示例组件输出 {#sample-component-output}

要体验目录组件并查看其配置选项以及HTML和JSON输出的示例，请访问 [组件库](https://adobe.com/go/aem_cmp_library_tableofcontents).

### 技术详细信息 {#technical-details}

有关目录组件的最新技术文档 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_tableofcontents_v1).

在[核心组件开发人员文档](/help/developing/overview.md)中可找到有关开发核心组件的其他详细信息。

## “编辑”对话框 {#edit-dialog}

编辑对话框允许内容作者定义目录组件应作为ToC呈现的标题级别范围。

![目录组件的编辑对话框](/help/assets/tableofcontents-edit.png)

**列表类型**  — 此选项定义列表应为项目符号列表还是编号列表。
* **标题开始级别**  — 此选项定义目录组件应呈现的最高级别标题。
* **标题停止级别**  — 此选项定义目录组件应呈现的最低级别标题。
* **ID** - 利用此选项，可以控制 HTML 和 [Data Layer](/help/developing/data-layer/overview.md) 中的组件的唯一标识符。
   * 如果留空，系统会自动为您生成一个唯一 ID，可以通过检查结果页面找到该 ID。
   * 如果指定一个 ID，作者有责任确保它是唯一的。
   * 更改此 ID 会对 CSS、JS 和 Data Layer 跟踪产生影响。

## “设计”对话框 {#design-dialog}

使用设计对话框，模板作者可以设置目录组件标题范围的默认值，并根据类名限制ToC中包含的标题。

### “属性”选项卡 {#properties-tab}

![快速搜索组件的“设计”对话框](/help/assets/tableofcontents-design.png)

* **限制列表类型**  — 此选项定义组件将生成的列表类型。 选择此选项会限制内容作者选择其他列表类型的能力。
* **限制开始级别**  — 此选项定义内容作者为定义ToC而可选择的最高标题级别。
* **限制停止级别**  — 此选项定义内容作者为定义ToC而可以选择的最低标题级别。
* **包括类名称**  — 如果设置此选项，则目录组件将只考虑具有指定类名称或包含在指定类名称元素中的标题。
   * 点按或单击 **添加** 图标以添加一个或多个类名称。
   * 点按或单击 **删除** 类名称旁边的图标以将其删除。
* **忽略类名称**  — 如果设置此选项，则目录组件将忽略具有指定类名称或包含在指定类名称元素中的标题。
   * 点按或单击 **添加** 图标以添加一个或多个类名称。
   * 点按或单击 **删除** 类名称旁边的图标以将其删除。

### “样式”选项卡 {#styles-tab}

目录组件支持AEM [样式系统](/help/get-started/authoring.md#component-styling).

## Adobe Client Data Layer {#data-layer}

目录组件支持 [Adobe客户端数据层。](/help/developing/data-layer/overview.md)
