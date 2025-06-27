---
title: 内容片段列表组件
description: 利用核心组件内容片段列表组件，可显示内容片段的列表。
role: Architect, Developer, Admin, User
exl-id: 0f2295b1-d287-4f72-8ee4-fa98c4850e53
source-git-commit: dd30def59a8f037864da875ef4c831b11f766e57
workflow-type: ht
source-wordcount: '806'
ht-degree: 100%

---


# 内容片段列表组件{#content-fragment-list-component}

利用核心组件内容片段列表组件，可显示[内容片段](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html)的列表。

{{traditional-aem}}

## 用途 {#usage}

利用核心组件内容片段列表组件，可包含基于内容片段模型的页面上的[内容片段](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/content-fragments/content-fragments.html)的列表。这对于创建可由其他应用程序轻松使用的[无头内容](https://helpx.adobe.com/cn/experience-manager/6-5/sites/developing/user-guide.html?topic=/experience-manager/6-5/sites/developing/morehelp/headless.ug.js)特别有用。

* 可在[“配置”对话框](#configure-dialog)中选择此列表及其属性。
* 样式可应用于[“设计”对话框](#design-dialog)中的组件。

## 版本和兼容性 {#version-and-compatibility}

内容片段组件的当前版本是 v2，此版本随 2022 年 2 月的核心组件发行版 2.18.0 的发布引入，具体说明见本文。

下表详细说明了该组件的所有受支持版本、与该组件的版本兼容的 AEM 版本以及指向早期版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|---|----|---|---|---|
| v2 | - | 兼容 | 兼容 | 兼容 |
| [v1](v1/content-fragment-list.md) | 兼容 | 兼容 | - | 兼容 |

有关核心组件版本的更多信息，请参阅文档[核心组件版本](/help/versions.md)。

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

### “样式”选项卡 {#styles-tab-edit}

![内容片段列表组件的“编辑”对话框的“样式”选项卡](/help/assets/content-fragment-list-styles.png)

内容片段列表组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。

使用下拉菜单选择要应用于该组件的样式。在“编辑”对话框中所做的选择与从组件工具栏中选择的操作效果相同。

必须在[“设计”对话框](#design-dialog)中为此组件配置样式，以便下拉菜单可用。

## “设计”对话框 {#design-dialog}

### “样式”选项卡 {#styles-tab}

内容片段列表组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。
