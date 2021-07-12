---
title: 内容片段列表组件
description: 核心组件内容片段列表组件允许显示内容片段列表。
role: Architect, Developer, Admin, User
exl-id: 0f2295b1-d287-4f72-8ee4-fa98c4850e53
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '762'
ht-degree: 5%

---

# 内容片段列表组件{#content-fragment-list-component}

核心组件内容片段列表组件允许显示[内容片段](https://docs.adobe.com/content/help/zh-Hans/experience-manager-cloud-service/assets/content-fragments/content-fragments.html)的列表。

## 使用 {#usage}

核心组件内容片段列表组件允许在基于内容片段模型的页面上包含[内容片段](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/content-fragments/content-fragments.html)列表。 这对于创建[无标题内容](https://helpx.adobe.com/cn/experience-manager/6-5/sites/developing/user-guide.html?topic=/experience-manager/6-5/sites/developing/morehelp/headless.ug.js)特别有用，这些内容可以被其他应用程序轻松使用。

* 可以在[配置对话框](#configure-dialog)中选择列表及其属性。
* 样式可以应用于[设计对话框](#design-dialog)中的组件。

## 版本和兼容性 {#version-and-compatibility}

内容片段组件的当前版本为v1，该版本在2019年5月随核心组件2.4.0版引入，在本文档中进行了描述。

下表详细列出了组件的所有受支持版本、组件版本与之兼容的AEM版本，以及指向以前版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | 兼容 | 兼容 | 兼容 |

有关核心组件版本和版本的更多信息，请参阅文档[核心组件版本](/help/versions.md)。

## 组件输出示例 {#sample-component-output}

要体验内容片段列表组件并查看其配置选项以及HTML和JSON输出的示例，请访问[组件库](https://adobe.com/go/aem_cmp_library_cflist)。

## 技术详细信息 {#technical-details}

有关内容片段列表组件[的最新技术文档可在GitHub](https://adobe.com/go/aem_cmp_tech_cflist_v1)上找到。

有关开发核心组件的更多详细信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## 配置对话框 {#configure-dialog}

配置对话框允许内容作者定义构成列表的内容片段以及要包含的这些片段的元素。

### “属性”选项卡

**属性**&#x200B;选项卡定义列表中包含的内容片段。 这主要基于选定的内容片段模型，但还有其他可用的过滤器选项。

![内容片段列表组件的编辑对话框的属性选项卡](/help/assets/content-fragment-list-properties.png)

* **模型**  — 列表所基于的内容片段模型的路径。
   * 默认情况下，定义为&#x200B;**模型路径**&#x200B;的模型的所有内容片段都包含在列表中。
* **父路径**  — 应从中生成列表的父路径。
   * 基于所选&#x200B;**模型路径**&#x200B;的内容片段将被过滤为指定&#x200B;**父路径**&#x200B;上的内容片段。
      * 单击或点按字段右侧的&#x200B;**打开选择对话框**&#x200B;按钮以指定路径。
* **标记**  — 列表中将仅包含具有指定标记的内容片段。
   * 单击或点按字段右侧的&#x200B;**打开选择对话框**&#x200B;按钮以指定标记。
   * 单击或点按选定标记旁边的X可删除这些标记。
* **排序依据**  — 内容片段模型的字段，列表将按该字段进行排序
   * 只能选择文本字段（包括数字、日期和时间）。
* **排序顺序**  — 如何按顺序字段对列表 **排** 序
   * 升序或降序
* **最大项目数**  — 要在列表中显示的项目数上限
   * 没有值将返回所有项目。
* **ID**  — 利用此选项，可控制HTML和数据层中组件的唯一标识符 [的唯一标识符](/help/developing/data-layer/overview.md)。
   * 如果留为空白，则会自动为您生成唯一ID，并且可以通过检查生成的页面找到该ID。
   * 如果指定了ID，则作者有责任确保该ID是唯一的。
   * 更改ID可能会影响CSS、JS和数据层跟踪。

>[!NOTE]
>**排序依据**、**排序顺序**&#x200B;和&#x200B;**最大项目**&#x200B;选项在核心组件2.7.0版中引入。

### “元素”选项卡

默认情况下，内容片段模型的所有元素都将包含在列表中（除非受&#x200B;**最大项目**&#x200B;字段的限制）。 **元素**&#x200B;选项卡允许您仅指定要包含的特定元素。

![内容片段列表组件编辑对话框的元素选项卡](/help/assets/content-fragment-list-elements.png)

* **元素**  — 将仅显示指定列表中内容片段的元素。
   * 单击或点按&#x200B;**添加**&#x200B;按钮以添加新元素。
   * 单击或点按&#x200B;**删除**&#x200B;按钮以删除选定的元素。
   * 拖动&#x200B;**Order**&#x200B;句柄以重新排列元素的顺序。

## “设计”对话框 {#design-dialog}

设计对话框允许模板作者定义应用于内容片段列表组件的样式。
