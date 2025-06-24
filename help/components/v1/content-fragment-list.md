---
title: 内容片段列表组件(v1)
description: 利用核心组件内容片段列表组件，可显示内容片段的列表。
role: Architect, Developer, Admin, User
exl-id: 37d6632d-360d-4081-8279-8efbb369a82e
index: n
source-git-commit: 92a3ec273a5be6751c1503835b9c2e5cbd61bb9e
workflow-type: tm+mt
source-wordcount: '694'
ht-degree: 98%

---


# 内容片段列表组件(v1) {#content-fragment-list-component}

利用核心组件内容片段列表组件，可显示[内容片段](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html)的列表。

## 用途 {#usage}

利用核心组件内容片段列表组件，可包含基于内容片段模型的页面上的[内容片段](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html)的列表。这对于创建可由其他应用程序轻松使用的[无头内容](https://helpx.adobe.com/cn/experience-manager/6-5/sites/developing/user-guide.html?topic=/experience-manager/6-5/sites/developing/morehelp/headless.ug.js)特别有用。

* 可在[“配置”对话框](#configure-dialog)中选择此列表及其属性。
* 样式可应用于[“设计”对话框](#design-dialog)中的组件。

## 版本和兼容性 {#version-and-compatibility}

本文档介绍了内容片段组件 v1，此版本随 2019 年 5 月的核心组件发行版本 2.4.0 的发布引入。

>[!CAUTION]
>
>本文档介绍了内容片段列表组件 v1。
>
>有关当前版本的内容片段列表组件的详细信息，请参阅[内容片段列表组件](/help/components/content-fragment-list.md)文档。

## 示例组件输出 {#sample-component-output}

要体验内容片段列表组件并查看其配置选项示例以及 HTML 和 JSON 输出，请访问[组件库](https://adobe.com/go/aem_cmp_library_cflist_cn)。

## 技术详细信息 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_cflist_v1_cn)有关内容片段列表组件的最新技术文档。

在[核心组件开发人员文档](/help/developing/overview.md)中可找到有关开发核心组件的其他详细信息。

## “配置”对话框 {#configure-dialog}

利用“配置”对话框，内容作者可以定义哪些内容片段包括列表以及要包含的这些片段的元素。

### “属性”选项卡

**属性**&#x200B;选项卡定义列表中包含的内容片段。这主要基于选定的内容片段模型，但提供了其他过滤器选项。

![内容片段列表组件的“编辑”对话框的“属性”选项卡](/help/assets/content-fragment-list-properties.png)

* **模型** - 列表所基于的内容片段模型的路径。
   * 默认情况下，定义为&#x200B;**模型路径**&#x200B;的所有模型内容片段将包含在列表中。
* **父路径** - 应从中构建列表的父路径。
   * 将从基于选定&#x200B;**模型路径**&#x200B;的内容片段中过滤出指定&#x200B;**父路径**&#x200B;上的内容片段。
      * 单击或点击字段右侧的&#x200B;**“打开选定内容对话框”**&#x200B;按钮可指定路径。
* **标记** - 仅带指定标记的内容片段将包含在列表中。
   * 单击或点击字段右侧的&#x200B;**“打开选定内容对话框”**&#x200B;按钮可指定标记。
   * 单击或点击选定标记旁边的 X 可将其删除。
* **排序依据** - 作为列表的排序依据的内容片段模型的字段
   * 仅文本字段（包括数字、日期和时间）是可选的。
* **排序顺序** - 按&#x200B;**排序依据**&#x200B;字段对列表排序的方式
   * 升序或降序
* **最大项数** - 列表中要显示的项的最大数量
   * 无值将返回所有项。
* **ID** - 利用此选项，可以控制 HTML 和[ Data Layer ](/help/developing/data-layer/overview.md)中的组件的唯一标识符。
   * 如果留空，系统会自动为您生成一个唯一 ID，可以通过检查结果页面找到该 ID。
   * 如果指定一个 ID，作者有责任确保它是唯一的。
   * 更改此 ID 会对 CSS、JS 和 Data Layer 跟踪产生影响。

>[!NOTE]
>**排序依据**、**排序顺序**&#x200B;和&#x200B;**最大项数**&#x200B;选项已在核心组件的版本 2.7.0 中引入。

### “元素”选项卡

默认情况下，内容片段模型的所有元素将包含在列表中（除非受&#x200B;**最大项数**&#x200B;字段限制）。利用&#x200B;**元素**&#x200B;选项卡，您可以仅指定要包含的特定元素。

![内容片段列表组件的“编辑”对话框的“元素”选项卡](/help/assets/content-fragment-list-elements.png)

* **元素** - 仅指定列表中的内容片段的元素将出现。
   * 单击或点击&#x200B;**“添加”**&#x200B;按钮可添加新元素。
   * 单击或点击&#x200B;**“删除”**&#x200B;按钮可删除选定元素。
   * 拖动&#x200B;**排序**&#x200B;手柄可重新排列元素的顺序。

## “设计”对话框 {#design-dialog}

利用“设计”对话框，模板作者可以定义应用于内容片段列表组件的样式。
