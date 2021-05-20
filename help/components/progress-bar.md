---
title: 进度条组件
description: 进度条组件以可视方式表示实现目标的进度
role: Architect, Developer, Administrator, Business Practitioner
exl-id: 47afc5a6-ac57-4b6c-92c4-015ca956a20b
source-git-commit: 8ff36ca143af9496f988b1ca65475497181def1d
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 3%

---

# 进度条组件{#progress-bar-component}

核心组件进度条组件以可视方式表示目标的进度。

## 使用 {#usage}

进度条组件允许内容作者通过定义完成百分比来轻松创建进度条，从而直观地显示目标进度。

## 版本和兼容性{#version-and-compatibility}

进度条组件的当前版本为v1，该版本于2020年5月随核心组件2.9.0版引入，在本文档中进行了描述。

下表详细列出了组件的所有受支持版本、组件版本与之兼容的AEM版本，以及指向以前版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|---|
| v1 | 兼容 | 兼容 | 兼容 |

## 组件输出示例{#sample-component-output}

要体验进度条组件并查看其配置选项以及HTML和JSON输出的示例，请访问[组件库](https://adobe.com/go/aem_cmp_library_progressbar)。

### 技术详细信息{#technical-details}

有关进度条组件[的最新技术文档可在GitHub](https://adobe.com/go/aem_cmp_tech_progress_v1)上找到。

有关开发核心组件的更多详细信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## 配置对话框{#configure-dialog}

![进度条组件的编辑对话框](/help/assets/progress-bar-edit.png)

* **完成**  — 进度以百分比表示
* **ID**  — 利用此选项，可控制HTML和数据层中组件的唯一标识符 [的唯一标识符](/help/developing/data-layer/overview.md)。
   * 如果留为空白，则会自动为您生成唯一ID，并且可以通过检查生成的页面找到该ID。
   * 如果指定了ID，则作者有责任确保该ID是唯一的。
   * 更改ID可能会影响CSS、JS和数据层跟踪。

## 设计对话框{#design-dialog}

设计对话框允许模板作者定义应用于进度条组件的样式。

### 样式选项卡{#styles-tab}

进度条组件支持AEM [样式系统](/help/get-started/authoring.md#component-styling)。

## Adobe客户端数据层{#data-layer}

进度条组件支持[Adobe客户端数据层。](/help/developing/data-layer/overview.md)
