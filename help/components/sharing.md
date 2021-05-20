---
title: 社交共享组件
description: 核心组件社交共享组件是一个Facebook和Pinterest共享小组件。
role: Architect, Developer, Administrator, Business Practitioner
exl-id: 8bd53c76-da91-479b-b416-f978682a3d43
source-git-commit: 8ff36ca143af9496f988b1ca65475497181def1d
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 7%

---

# 社交共享组件{#social-sharing-component}

核心组件社交共享组件是一个Facebook和Pinterest共享小组件。

## 使用 {#usage}

社交共享组件会将Facebook和Pinterest共享链接添加到页面。 它通常包含在页眉或页脚中。

与其他组件不同，社交共享组件的设置由模板作者通过[初始页面属性](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)完成，而内容作者则通过[页面属性](https://docs.adobe.com/content/help/zh-Hans/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html)完成。

## 版本和兼容性{#version-and-compatibility}

社交共享组件的当前版本为v1，该版本在核心组件的1.0.0版中引入，在本文档中进行了描述。

下表详细列出了组件的所有受支持版本以及与组件版本兼容的AEM版本。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v1 | 兼容 | 兼容 | 兼容 |

有关核心组件版本和版本的更多信息，请参阅文档[核心组件版本](/help/versions.md)。

## 组件输出示例{#sample-component-output}

要体验社交共享组件并查看其配置选项以及HTML和JSON输出的示例，请访问[组件库](https://adobe.com/go/aem_cmp_library_sharing)。

### 技术详细信息{#technical-details}

有关共享组件[的最新技术文档，请参阅GitHub](https://adobe.com/go/aem_cmp_tech_sharing_v1)。

有关开发核心组件的更多详细信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## 编辑对话框{#edit-dialog}

![共享组件的编辑对话框](/help/assets/sharing-edit.png)

* **ID**  — 利用此选项，可控制HTML和数据层中组件的唯一标识符 [的唯一标识符](/help/developing/data-layer/overview.md)。
   * 如果留为空白，则会自动为您生成唯一ID，并且可以通过检查生成的页面找到该ID。
   * 如果指定了ID，则作者有责任确保该ID是唯一的。
   * 更改ID可能会影响CSS、JS和数据层跟踪。

由于共享需要特殊的页面标题，因此必须在页面级别启用任何共享。 因此，对于内容作者，可通过共享选项卡[页面属性](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html)访问共享组件的其他编辑选项。

## 设计对话框{#design-dialog}

由于共享需要特殊的页面标题，因此必须在页面级别启用任何共享。 因此，对于模板作者，共享组件的设计选项可通过[初始页面属性](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)获得。
