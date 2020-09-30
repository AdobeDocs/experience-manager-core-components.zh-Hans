---
title: 社交共享组件
description: 核心组件社交共享组件是Facebook和Pinterest共享构件。
translation-type: tm+mt
source-git-commit: 4813748bcfa83ce7c73e81d4e4d445ecc8215d26
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 2%

---


# 社交共享组件{#social-sharing-component}

核心组件社交共享组件是Facebook和Pinterest共享构件。

## 使用 {#usage}

社交共享组件会添加Facebook和Pinterest共享链接至页面。 它通常包含在页眉或页脚中。

与其他组件不同，社交共享组件的设置由模板作者通过初始页面属 [性完成](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html) ，而内容作者通过页面 [属性完成](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html)。

## 版本和兼容性 {#version-and-compatibility}

社交共享组件的当前版本为v1，它是随核心组件版本1.0.0引入的，本文档中对此进行了说明。

下表详细列出了组件的所有受支持版本以及与组件版本兼容的AEM版本。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM 云服务 |
|--- |--- |--- |---|
| v1 | 兼容 | 兼容 | 兼容 |

有关核心组件版本和版本的详细信息，请参阅文档 [核心组件版本](/help/versions.md)。

## 示例组件输出 {#sample-component-output}

要体验社交共享组件并查看其配置选项以及HTML和JSON输出的示例，请访问组 [件库](https://adobe.com/go/aem_cmp_library_sharing)。

### 技术详细信息 {#technical-details}

有关共享组件的最新技 [术文档，请访问GitHub](https://adobe.com/go/aem_cmp_tech_sharing_v1)。

有关开发核心组件的更多详细信息，请参阅核 [心组件开发人员文档](/help/developing/overview.md)。

## Edit Dialog {#edit-dialog}

![共享组件的编辑对话框](/help/assets/sharing-edit.png)

* **ID** —— 此选项允许控制HTML和数据层中组件的唯一标 [识符](/help/developing/data-layer/overview.md)。
   * 如果留空，则会自动为您生成唯一ID，并可通过检查生成的页面找到该ID。
   * 如果指定了ID，则作者有责任确保它是唯一的。
   * 更改ID可能会影响CSS、JS和数据层跟踪。

由于共享需要特殊的页面标题，因此必须在页面级别启用任何共享。 因此，对于内容作者，可以通过页面属性的共享选项卡使用共享组件的其他 [编辑选项](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html)。

## 设计对话框 {#design-dialog}

由于共享需要特殊的页面标题，因此必须在页面级别启用任何共享。 因此，对于模板作者，共享组件的设计选项可通过初始页 [面属性使用](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)。
