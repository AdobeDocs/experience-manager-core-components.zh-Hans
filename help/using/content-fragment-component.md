---
title: 内容片段组件
seo-title: 内容片段组件
description: 'null'
seo-description: 核心组件内容片段组件允许显示内容片段。
uuid: ec807de9-f76 c-4850-9e-c3 e439 a1 d626
contentOwner: 用户
content-type: 引用
topic-tags: 创作
products: SG_ EXPERIENCE MANAGER/CORECOMMPANES-new
discoiquuid: f093f58e-9755-4a4f-803a-ab93 a50 e6870
translation-type: tm+mt
source-git-commit: 1bbec9b1f109df88964dce051a58d111bf6cafaa

---


# 内容片段组件{#content-fragment-component}

核心组件内容片段组件允许显示 [内容片段](https://helpx.adobe.com/experience-manager/6-5/assets/using/content-fragments.html)。

>[!NOTE]
>
>在核心组件版本2.4.0之前，内容片段组件可作为核心组件的扩展提供，必须单独下载并明确启用。

## 使用情况 {#usage}

核心组件内容片段组件允许在页面上包含 [内容片段](https://helpx.adobe.com/experience-manager/6-5/assets/using/content-fragments.html) 。

* 可以在 [配置对话框](#configure-dialog)中选择片段及其属性。
* 可以在 [设计对话框](#design-dialog)中定义处理特定图像和网格的资源类型。
* 编辑选项将在 [内容片段编辑器中打开选定片段](https://helpx.adobe.com/content/help/en/experience-manager/6-5/assets/using/content-fragments.html)。

## 版本和兼容性 {#version-and-compatibility}

内容片段组件的当前版本是v1，它是在2017年10月核心组件中引入的版本1.1.0，本文档中有介绍。

下表详细说明了组件的所有支持版本、组件版本的AEM版本以及以前版本的文档链接。

| 组件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |---|
| v1 | 兼容 | 兼容 | 兼容 |

有关核心组件版本和版本的更多信息，请参阅文档 [核心组件版本](versions.md)。

## 示例组件输出 {#sample-component-output}

要体验内容片段组件以及查看其配置选项的示例以及HTML和JSON输出，请访问 [组件库](http://opensource.adobe.com/aem-core-wcm-components/library/content-fragment.html)。

## 技术详细信息 {#technical-details}

有关内容片段组件 [的最新技术文档可在GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/extension/contentfragment/content/src/content/jcr_root/apps/core/wcm/extension/components/contentfragment/v1/contentfragment)上找到。

有关开发核心组件的更多详细信息，请参阅 [核心组件开发人员文档](developing.md)。

## 配置对话框 {#configure-dialog}

配置对话框允许内容作者定义要包含的片段和要包含的片段元素。

![](assets/chlimage_1-87.png)

* **内容片段**

   * 所需内容片段的路径
   * 可使用 **选择对话框** 来查找片段

* **元素** -要包含的内容片段的元素
* **变体** -要使用的内容片段的变体(默认为 **主变量**)

* **段落**

   * **全部** -显示所有段落
   * **范围**

      * 指定应以分号分隔的段落范围
      * 例如 `1;3-5;7;9-*` ，要包括第一个、第三个到第5个、第七个和第九个至最后一个段落

* **将标题作为其自己的段落**

## 设计对话框 {#design-dialog}

设计对话框允许模板作者定义用于处理混合媒体图像和响应式网格的资源类型。

![](assets/chlimage_1-88.png)

* **混合媒体图像类型**

   * 用于呈现混合媒体图像的 Sling 资源类型

* **内部响应式网格**

   * 用于内部响应网格的Sling资源类型