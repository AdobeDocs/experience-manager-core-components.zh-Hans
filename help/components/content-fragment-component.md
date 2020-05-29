---
title: 内容片段组件
description: 核心组件内容片段组件允许显示内容片段。
translation-type: tm+mt
source-git-commit: c186e9ec3944d785ab0376769cf7f2307049a809
workflow-type: tm+mt
source-wordcount: '659'
ht-degree: 3%

---


# 内容片段组件{#content-fragment-component}

核心组件内容片段组件允许显示内 [容片段](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/content-fragments/content-fragments.html)。

>[!NOTE]
>
>在核心组件的2.4.0版之前，内容片段组件可用作核心组件的扩展，必须单独下载并明确启用。

## 使用 {#usage}

核心组件内容片段组件允许在页面 [中包含内容](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/content-fragments/content-fragments.html) 片段。

* 可以在配置对话框中选择片段及其 [属性](#configure-dialog)。
* 处理特定图像和网格的资源类型可以在设计对话框中 [定义](#design-dialog)。
* 编辑选项将在内容片段编辑器中打 [开所选片段](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/content-fragments/content-fragments-variations.html)。

## 版本和兼容性 {#version-and-compatibility}

内容片段组件的当前版本为v1,2017年10月随核心组件版本1.1.0一起推出，本文档对此进行了说明。

下表详细列出了组件的所有受支持版本、与组件版本兼容的AEM版本以及指向先前版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM 云服务 |
|--- |--- |---|---|
| v1 | 兼容 | 兼容 | 兼容 |

>[!NOTE]
>
>在版本2.4.0之前，内容片段组件位于扩展文件夹中。
>
> `apps/core/wcm/extension/components/contentfragment/v1/contentfragment`
> 
>从2.4.0开始，它已移至以下位置。
>
>`apps/core/wcm/components/contentfragment/v1/contentfragment`
>
>虽然两者都是v1，但从extensions文件夹使用的任何内容片段组件在升级到核心组件的2.4.0版或更高版本时，都需要迁移其相关代理组件才能使用新的资源类型。

有关核心组件版本和版本的详细信息，请参阅文档 [核心组件版本](/help/versions.md)。

## 示例组件输出 {#sample-component-output}

要体验内容片段组件以及查看其配置选项以及HTML和JSON输出的示例，请访问组 [件库](https://adobe.com/go/aem_cmp_library_cf)。

## 技术详细信息 {#technical-details}

有关内容片段组件的最新技术文 [档可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_cf_v1)。

有关开发核心组件的更多详细信息，请参阅核 [心组件开发人员文档](/help/developing/overview.md)。

## 配置对话框 {#configure-dialog}

配置对话框允许内容作者定义要包括的内容片段和该片段的元素。

### 属性选项卡 {#properties-tab}

![内容片段组件](/help/assets/content-fragment-edit-properties.png)

* **内容片段**

   * 所需内容片段的路径
   * 选 **择对话框** ，可用于定位片段

* **显示模式**
   * **单文本元素** -启用选择一个多行文本元素并启用段落控制选项
   * **多个元素** -允许选择所选内容片段的一个或多个元素
* **元素** -要包括的内容片段的元素
* **变体** -要使用的内容片段的变体(默认为主 **体**)

* **段落**

   * **全部** -显示所有段落
   * **范围**

      * 指定应显示的段落范围，以分号分隔
      * 例 `1;3-5;7;9-*` 如，包括1号、3号至5号、7号和9号至最后段落
* **ID** —— 此选项允许控制HTML和数据层中组件的唯一标 [识符](/help/developing/data-layer/overview.md)。
   * 如果留空，则会自动为您生成唯一ID，并可通过检查生成的页面找到该ID。
   * 如果指定了ID，则作者有责任确保它是唯一的。
   * 更改ID可能会影响CSS、JS和数据层跟踪。

### 段落控制选项卡 {#paragraph-control-tab}

选择“多元素”模 **式时** ，此选项卡不可用。

![内容片段组件](/help/assets/content-fragment-edit-paragraph.png)

* **段落** -允许选择所有段落或范围
* **将标题作为自己的段落处理**

## 设计对话框 {#design-dialog}

设计对话框允许模板作者定义用于处理混合媒体图像和响应式网格的资源类型。

![内容片段组件的设计对话框](/help/assets/content-fragment-design.png)

* **内部响应式网格**

   * 用于内部响应式网格的Sling资源类型

