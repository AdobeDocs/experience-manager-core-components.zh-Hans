---
title: 内容片段组件
description: 利用核心组件内容片段组件，可以显示内容片段。
role: Architect, Developer, Admin, User
exl-id: 551ff2a1-f8db-490c-84a3-4255b364fc83
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: ht
source-wordcount: '673'
ht-degree: 100%

---

# 内容片段组件{#content-fragment-component}

利用核心组件内容片段组件，可以显示[内容片段](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/content-fragments/content-fragments.html)。

>[!NOTE]
>
>在版本 2.4.0 的核心组件之前，内容片段组件作为核心组件的扩展提供，并且必须单独下载并明确启用。

## 用途 {#usage}

利用核心组件内容片段组件，可以包含页面上的[内容片段](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/content-fragments/content-fragments.html)。

* 可在[“配置”对话框](#configure-dialog)中选择片段及其属性。
* 可在[“设计”对话框](#design-dialog)中定义用于处理特定图像的资源类型。
* 编辑选项将在[内容片段编辑器](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/content-fragments/content-fragments-variations.html)中打开选定的片段。

## 版本和兼容性 {#version-and-compatibility}

内容片段组件的当前版本是 v1，此版本随 2017 年 10 月的核心组件 1.1.0 版的发布引入，具体说明见本文。

下表详细说明了该组件的所有受支持版本、与该组件的版本兼容的 AEM 版本以及指向早期版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | 兼容 | 兼容 | 兼容 |

>[!NOTE]
>
>在版本 2.4.0 之前，内容片段组件位于 extensions 文件夹中。
>
> `apps/core/wcm/extension/components/contentfragment/v1/contentfragment`
> 
>从版本 2.4.0 开始，该组件已移至以下位置。
>
>`apps/core/wcm/components/contentfragment/v1/contentfragment`
>
>虽然两者都是 v1，但在升级到版本 2.4.0 或更高版本的核心组件时，从 extensions 文件夹中使用的任何内容片段组件都需要迁移其相关代理组件才能使用新的资源类型。

有关核心组件版本的更多信息，请参阅文档[核心组件版本](/help/versions.md)。

## 示例组件输出 {#sample-component-output}

要体验内容片段组件并查看其配置选项示例以及 HTML 和 JSON 输出，请访问[组件库](https://adobe.com/go/aem_cmp_library_cf_cn)。

## 技术详细信息 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_cf_v1_cn)有关内容片段组件的最新技术文档。

在[核心组件开发人员文档](/help/developing/overview.md)中可找到有关开发核心组件的其他详细信息。

## “配置”对话框 {#configure-dialog}

利用“配置”对话框，内容作者可以定义要包含的内容片段及其元素。

### “属性”选项卡 {#properties-tab}

![内容片段组件](/help/assets/content-fragment-edit-properties.png)

* **内容片段**

   * 所需内容片段的路径
   * **“选择”对话框**&#x200B;可用于定位片段

* **显示模式**
   * **单个文本元素** - 允许选择一个多行文本元素并启用段落控制选项
   * **多个元素** - 允许选择选定的内容片段的一个或多个元素
* **元素** - 要包含的内容片段的一个或多个元素
* **变体** - 要使用的内容片段的变体（默认为 **Master**）

* **段落**

   * **全部** - 显示所有段落
   * **范围**

      * 指定应显示的段落的范围（用分号分隔）
      * 例如，如果为 `1;3-5;7;9-*`，则包含第一段、第三段到第五段、第七段、第九段到最后一段
* **ID** - 利用此选项，可以控制 HTML 和 [Data Layer](/help/developing/data-layer/overview.md) 中的组件的唯一标识符。
   * 如果留空，系统会自动为您生成一个唯一 ID，可以通过检查结果页面找到该 ID。
   * 如果指定一个 ID，作者有责任确保它是唯一的。
   * 更改此 ID 会对 CSS、JS 和 Data Layer 跟踪产生影响。

### “段落控制”选项卡 {#paragraph-control-tab}

在选择&#x200B;**多个元素**&#x200B;模式时，此选项卡不可用。

![内容片段组件](/help/assets/content-fragment-edit-paragraph.png)

* **段落** - 允许选择所有段落或一个范围
* **将标题处理为它们自己的段落**

## “设计”对话框 {#design-dialog}

利用“设计”对话框，模板作者可以定义用于处理混合媒体图像和响应式网格的资源类型。

![内容片段组件“设计”对话框](/help/assets/content-fragment-design.png)

* **内部响应式网格**

   * 用于内部响应式网格的 Sling 资源类型

## Adobe Client Data Layer {#data-layer}

内容片段组件支持 [Adobe Client Data Layer](/help/developing/data-layer/overview.md)。
