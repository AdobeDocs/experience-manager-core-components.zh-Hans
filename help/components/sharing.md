---
title: 社交共享组件
description: 核心组件社交共享组件是一个 Facebook 和 Pinterest 共享小组件。
role: Architect, Developer, Admin, User
exl-id: 8bd53c76-da91-479b-b416-f978682a3d43
index: false
source-git-commit: dd30def59a8f037864da875ef4c831b11f766e57
workflow-type: ht
source-wordcount: '377'
ht-degree: 100%

---


# 社交共享组件{#social-sharing-component}

核心组件社交共享组件是一个 Facebook 和 Pinterest 共享小组件。

>[!NOTE]
>
>社交共享组件已随核心组件[ 2.18.0 版一起弃用。](/help/versions.md)

{{traditional-aem}}

## 用途 {#usage}

社交共享组件将 Facebook 和 Pinterest 共享链接添加到页面。它通常包含在页眉或页脚中。

与其他组件不同，社交共享组件的设置可由模板作者通过[初始页面属性](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)设定，也可由内容作者通过[页面属性](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html)设定。

## 版本和兼容性 {#version-and-compatibility}

社交共享组件的当前版本是 v1，此版本随核心组件 1.0.0 版的发布引入，具体说明见本文。

下表详细说明了该组件的所有支持版本以及与该组件的各个版本兼容的 AEM 版本。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|--- |--- |--- |---|---|
| v1 | 与<br>[版本 2.17.4](/help/versions.md) 和更低版本兼容 | 兼容，已弃用 | 兼容，已弃用 | 兼容，已弃用 |

有关核心组件版本的更多信息，请参阅文档[核心组件版本](/help/versions.md)。

### 技术详细信息 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_sharing_v1_cn)有关共享组件的最新技术文档。

在[核心组件开发人员文档](/help/developing/overview.md)中可找到有关开发核心组件的其他详细信息。

## “编辑”对话框 {#edit-dialog}

![共享组件的“编辑”对话框](/help/assets/sharing-edit.png)

* **ID** - 利用此选项，可以控制 HTML 和 [Data Layer](/help/developing/data-layer/overview.md) 中的组件的唯一标识符。
   * 如果留空，系统会自动为您生成一个唯一 ID，可以通过检查结果页面找到该 ID。
   * 如果指定一个 ID，作者有责任确保它是唯一的。
   * 更改此 ID 会对 CSS、JS 和 Data Layer 跟踪产生影响。

由于共享需要特殊的页眉，因此必须在页面级别启用任何共享。因此，对于内容作者，可通过[页面属性](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html)的“共享”选项卡使用共享组件的编辑选项。

## “设计”对话框 {#design-dialog}

由于共享需要特殊的页眉，因此必须在页面级别启用任何共享。因此，对于模板作者，可通过[初始页面属性](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)使用共享组件的设计选项。
