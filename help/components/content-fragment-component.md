---
title: 内容片段组件
description: 核心组件内容片段组件允许显示内容片段。
role: Architect, Developer, Administrator, Business Practitioner
exl-id: 551ff2a1-f8db-490c-84a3-4255b364fc83
source-git-commit: 8ff36ca143af9496f988b1ca65475497181def1d
workflow-type: tm+mt
source-wordcount: '673'
ht-degree: 5%

---

# 内容片段组件{#content-fragment-component}

核心组件内容片段组件允许显示[内容片段](https://docs.adobe.com/content/help/zh-Hans/experience-manager-cloud-service/assets/content-fragments/content-fragments.html)。

>[!NOTE]
>
>在核心组件2.4.0版之前，内容片段组件可用作核心组件的扩展，并且必须单独下载并明确启用。

## 使用 {#usage}

核心组件内容片段组件允许在页面上包含[内容片段](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/content-fragments/content-fragments.html)。

* 可在[配置对话框](#configure-dialog)中选择片段及其属性。
* 可在[设计对话框](#design-dialog)中定义用于处理某些图像和网格的资源类型。
* 编辑选项将在[内容片段编辑器](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/content-fragments/content-fragments-variations.html)中打开选定的片段。

## 版本和兼容性{#version-and-compatibility}

内容片段组件的当前版本为v1，该版本于2017年10月随核心组件1.1.0版引入，在本文档中进行了描述。

下表详细列出了组件的所有受支持版本、组件版本与之兼容的AEM版本，以及指向以前版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | 兼容 | 兼容 | 兼容 |

>[!NOTE]
>
>在版本2.4.0之前，内容片段组件位于扩展文件夹中。
>
> `apps/core/wcm/extension/components/contentfragment/v1/contentfragment`
> 
>从2.4.0开始，已将其移至以下位置。
>
>`apps/core/wcm/components/contentfragment/v1/contentfragment`
>
>尽管两者都是v1，但是从扩展文件夹中使用的任何内容片段组件在升级到核心组件版本2.4.0或更高版本时，都需要迁移其相关的代理组件才能使用新的资源类型。

有关核心组件版本和版本的更多信息，请参阅文档[核心组件版本](/help/versions.md)。

## 组件输出示例{#sample-component-output}

要体验内容片段组件并查看其配置选项以及HTML和JSON输出的示例，请访问[组件库](https://adobe.com/go/aem_cmp_library_cf)。

## 技术详细信息{#technical-details}

有关内容片段组件[的最新技术文档可在GitHub](https://adobe.com/go/aem_cmp_tech_cf_v1)上找到。

有关开发核心组件的更多详细信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## 配置对话框{#configure-dialog}

配置对话框允许内容作者定义要包含的内容片段和该片段的元素。

### 属性选项卡{#properties-tab}

![内容片段组件](/help/assets/content-fragment-edit-properties.png)

* **内容片段**

   * 所需内容片段的路径
   * **选择对话框**&#x200B;可用于查找片段

* **显示模式**
   * **单个文本元素**  — 启用一个多行文本元素的选择，并启用段落控制选项
   * **多个元素**  — 允许选择选定内容片段的一个或多个元素
* **元素**  — 要包含的内容片段的元素
* **变量**  — 要使用的内容片段的哪个变体(默认为 **主控**)

* **段落**

   * **全部**  — 显示所有段落
   * **范围**

      * 指定应显示的段落范围（以分号分隔）
      * 例如，`1;3-5;7;9-*`包括1、3至5、7和9至最后段落
* **ID**  — 利用此选项，可控制HTML和数据层中组件的唯一标识符 [的唯一标识符](/help/developing/data-layer/overview.md)。
   * 如果留为空白，则会自动为您生成唯一ID，并且可以通过检查生成的页面找到该ID。
   * 如果指定了ID，则作者有责任确保该ID是唯一的。
   * 更改ID可能会影响CSS、JS和数据层跟踪。

### 段落控制选项卡{#paragraph-control-tab}

当选择&#x200B;**多个元素**&#x200B;模式时，此选项卡不可用。

![内容片段组件](/help/assets/content-fragment-edit-paragraph.png)

* **段落**  — 允许选择所有段落或范围
* **将标题处理为它们自己的段落**

## 设计对话框{#design-dialog}

设计对话框允许模板作者定义用于处理混合媒体图像和响应式网格的资源类型。

![内容片段组件的设计对话框](/help/assets/content-fragment-design.png)

* **内部响应式网格**

   * 用于内部响应式网格的Sling资源类型

## Adobe客户端数据层{#data-layer}

内容片段组件支持[Adobe客户端数据层。](/help/developing/data-layer/overview.md)
