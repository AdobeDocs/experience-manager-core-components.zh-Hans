---
title: 目录组件
description: 目录组件根据页面内容中的标题创建目录，以便读者快速浏览页面。
role: Architect, Developer, Admin, User
exl-id: 006adde2-ebff-4e74-8e79-325cccd43e8f
source-git-commit: 8beae61676340e8aafaee469018d865ea7ed934e
workflow-type: tm+mt
source-wordcount: '768'
ht-degree: 100%

---

# 目录组件 {#table-of-contents-component}

目录组件根据页面内容中的标题创建目录，以便读者快速浏览页面。

## 用途 {#usage}

目录组件使网站访问者能够通过基于页面内容标题的高效生成的 ToC 快速浏览页面内容。

* ToC 在服务器端生成。
* 调度程序已完全缓存该缓存，以便快速投放。
* 它适用于页面上的所有组件，而不仅仅是核心组件。

[编辑对话框](#edit-dialog)允许内容作者定义要在目录中使用的标题范围。通过[设计对话框](#design-dialog)，模板作者可以在内容作者向页面添加目录组件时设置标题的默认值，并根据类名限制目录中包含的标题。

## 版本和兼容性 {#version-and-compatibility}

目录组件的当前版本为 v1，在 2022 年 5 月核心组件的 2.20.0 版中引入，本文档对此进行了描述。

下表详细说明了该组件的所有受支持版本、与该组件的版本兼容的 AEM 版本以及指向早期版本文档的链接。

| 组件版本 | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | 兼容 | 兼容 |

有关核心组件版本的更多信息，请参阅文档[核心组件版本](/help/versions.md)。

>[!NOTE]
>
>在 AEM as a Cloud Service 上，您的管理员需要为组件启用过滤器，以使其呈现组件的内容。
>
>[有关更多信息，请参阅该组件的 GitHub 文档](https://adobe.com/go/aem_cmp_tech_tableofcontents_v1_cn)。

### 技术详细信息 {#technical-details}

有关目录组件的最新技术文档[可以在 GitHub 上找到](https://adobe.com/go/aem_cmp_tech_tableofcontents_v1_cn)。

在[核心组件开发人员文档](/help/developing/overview.md)中可找到有关开发核心组件的其他详细信息。

## “编辑”对话框 {#edit-dialog}

编辑对话框允许内容作者定义目录组件应呈现为目录的标题级别范围。

![目录组件的编辑对话框](/help/assets/tableofcontents-edit.png)

**列表类型** – 此选项定义列表是项目符号列表还是编号列表。
* **标题开始级别** – 此选项定义目录组件应呈现的标题的最高级别。
* **标题停止级别** – 此选项定义目录组件应呈现的标题的最低级别。
* **ID** – 利用此选项，可以控制 HTML 和[数据层](/help/developing/data-layer/overview.md)中组件的唯一标识符。
   * 如果留空，系统会自动为您生成一个唯一 ID，可以通过检查结果页面找到该 ID。
   * 如果指定一个 ID，作者有责任确保它是唯一的。
   * 更改此 ID 会对 CSS、JS 和数据层跟踪产生影响。

## “设计”对话框 {#design-dialog}

通过设计对话框，模板作者可以为目录组件的标题范围设置默认值，并根据类名限制目录中包含的标题。

### “属性”选项卡 {#properties-tab}

![快速搜索组件的“设计”对话框](/help/assets/tableofcontents-design.png)

* **限制列表类型** – 此选项定义组件将生成的列表类型。选择此选项将限制内容作者选择其他列表类型的能力。
* **限制开始级别** – 此选项定义了内容作者可以选择用于定义目录的最高标题级别。
* **限制停止级别** – 此选项定义了内容作者可以选择用于定义目录的最低标题级别。
* **包括类名** – 如果设置了此选项，目录组件只会考虑具有指定类名或包含在指定类名元素中的标题。
   * 轻触或单击&#x200B;**添加**&#x200B;图标以添加一个或多个类名。
   * 轻触或单击类名旁边的&#x200B;**删除**&#x200B;图标可将其删除。
* **忽略类名** – 如果设置了此选项，目录组件会忽略具有指定类名或包含在指定类名元素中的标题。
   * 轻触或单击&#x200B;**添加**&#x200B;图标以添加一个或多个类名。
   * 轻触或单击类名旁边的&#x200B;**删除**&#x200B;图标可将其删除。

### 样式选项卡 {#styles-tab}

目录组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。

## Adobe 客户端数据层 {#data-layer}

目录组件支持 [Adobe 客户端数据层](/help/developing/data-layer/overview.md)。
