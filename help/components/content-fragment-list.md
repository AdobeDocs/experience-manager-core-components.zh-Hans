---
title: 内容片段列表组件
description: 核心组件内容片段列表组件允许显示内容片段列表。
translation-type: tm+mt
source-git-commit: c186e9ec3944d785ab0376769cf7f2307049a809
workflow-type: tm+mt
source-wordcount: '762'
ht-degree: 3%

---


# 内容片段列表组件{#content-fragment-list-component}

核心组件内容片段列表组件允许显示内容片段 [列表](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/content-fragments/content-fragments.html)。

## 使用 {#usage}

核心组件内容片段列表组件允许在基于内容片 [段模型](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/content-fragments/content-fragments.html) 的页面上包含内容片段的列表。 这对于创建其他应用程 [序可轻松](https://helpx.adobe.com/cn/experience-manager/6-5/sites/developing/user-guide.html?topic=/experience-manager/6-5/sites/developing/morehelp/headless.ug.js) 使用的无头内容尤为有用。

* 列表及其属性可在配置对话框中 [进行选择](#configure-dialog)。
* 样式可在设计对话框中应用 [于组件](#design-dialog)。

## 版本和兼容性 {#version-and-compatibility}

内容片段组件的当前版本为v1,2019年5月随核心组件版本2.4.0一起推出，本文档对此进行了说明。

下表详细列出了组件的所有受支持版本、与组件版本兼容的AEM版本以及指向先前版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM 云服务 |
|--- |--- |---|---|
| v1 | 兼容 | 兼容 | 兼容 |

有关核心组件版本和版本的详细信息，请参阅文档 [核心组件版本](/help/versions.md)。

## 示例组件输出 {#sample-component-output}

要体验内容片段列表组件以及查看其配置选项以及HTML和JSON输出的示例，请访问组件 [库](https://adobe.com/go/aem_cmp_library_cflist)。

## 技术详细信息 {#technical-details}

有关内容片段列表组件的最 [新技术文档可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_cflist_v1)。

有关开发核心组件的更多详细信息，请参阅核 [心组件开发人员文档](/help/developing/overview.md)。

## 配置对话框 {#configure-dialog}

配置对话框允许内容作者定义要包括的列表和这些片段的元素的内容片段。

### 属性选项卡

属性 **选项卡** 定义列表中包含的内容片段。 这主要基于所选的内容片段模型，但还有其他可用的筛选选项。

![内容片段列表组件编辑对话框的属性选项卡](/help/assets/content-fragment-list-properties.png)

* **模型** -列表所基于的内容片段模型的路径。
   * 默认情况下，定义为“模型路径”的模型的所 **有内容片段** ，都包括在列表中。
* **父路径** -应从中构建列表的父路径。
   * 将根据所选模型路径 **筛选内容片段** ，并将其筛选为指定父路径 **上的内容片段**。
      * 单击或点按 **字段右侧** 的“打开选择对话框”按钮以指定路径。
* **标记** -只有具有指定标记的内容片段才会包含在列表中。
   * 单击或点按 **字段右侧** 的“打开选择对话框”按钮以指定标记。
   * 单击或点按选定标记旁边的X可删除它们。
* **排序依据** -内容片段模型的字段，列表将按该字段进行排序
   * 只有文本字段（包括数字、日期和时间）是可选的。
* **排序顺序** -列表如何按“排序依据” **字段排序** 。
   * 升序或降序
* **最大项目** -列表中要显示的最大项目数
   * 没有值将返回所有项目。
* **ID** —— 此选项允许控制HTML和数据层中组件的唯一标 [识符](/help/developing/data-layer/overview.md)。
   * 如果留空，则会自动为您生成唯一ID，并可通过检查生成的页面找到该ID。
   * 如果指定了ID，则作者有责任确保它是唯一的。
   * 更改ID可能会影响CSS、JS和数据层跟踪。

>[!NOTE]
>Order By ****、Sort Order **和Max Items****** 选项已在核心组件版本2.7.0中引入。

### “元素”选项卡

默认情况下，内容片段模型的所有元素将包含在列表中(除非受“最大项目” **字段的限** 制)。 “元 **素** ”选项卡允许您仅指定要包含的特定元素。

![内容片段列表组件编辑对话框的元素选项卡](/help/assets/content-fragment-list-elements.png)

* **元素** -将仅显示指定列表中内容片段的元素。
   * 单击或点按 **添加** 按钮以添加新元素。
   * 单击或点按删 **除按** 钮以删除选定元素。
   * 拖动 **Order** 句柄以重新排列元素的顺序。

## 设计对话框 {#design-dialog}

设计对话框允许模板作者定义应用于内容片段列表组件的样式。
