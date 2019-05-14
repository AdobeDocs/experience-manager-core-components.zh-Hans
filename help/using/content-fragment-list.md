---
title: 内容片段列表组件
seo-title: 内容片段列表组件
description: 'null'
seo-description: 核心组件内容片段列表组件允许显示内容片段列表。
contentOwner: Bohnert
content-type: 引用
topic-tags: 创作
products: SG_ EXPERIENCE MANAGER/CORECOMMPANES-new
translation-type: tm+mt
source-git-commit: d683f8110b514860bba11e08e6923be49e92652f

---


# 内容片段列表组件{#content-fragment-list-component}

核心组件内容片段列表组件允许显示 [内容片段列表](https://helpx.adobe.com/experience-manager/6-5/assets/using/content-fragments.html)。

## 使用情况 {#usage}

核心组件内容片段列表组件允许在基于内容片段模型的页面上包含 [内容片段](https://helpx.adobe.com/experience-manager/6-5/assets/using/content-fragments.html) 列表。这对于创建 [可轻松由其他应用程序占用的无外设内容](https://helpx.adobe.com/experience-manager/6-5/sites/developing/user-guide.html?topic=/experience-manager/6-5/sites/developing/morehelp/headless.ug.js) 尤为有用。

* 可以在 [配置对话框](#configure-dialog)中选择列表及其属性。
* 样式可应用于 [设计对话框](#design-dialog)中的组件。

## 版本和兼容性 {#version-and-compatibility}

内容片段组件的当前版本是v1，它是在2019年月版的核心组件中引入的，该版本在本文档中进行了介绍。

下表详细说明了组件的所有支持版本、组件版本的AEM版本以及以前版本的文档链接。

| 组件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |---|
| v1 | 兼容 | 兼容 | 兼容 |

有关核心组件版本和版本的更多信息，请参阅文档 [核心组件版本](versions.md)。

## 示例组件输出 {#sample-component-output}

要体验内容片段列表组件以及其配置选项的示例以及HTML和JSON输出，请访问 [组件库](http://opensource.adobe.com/aem-core-wcm-components/library/content-fragment-list.html)。

## 技术详细信息 {#technical-details}

有关内容片段列表组件的 [最新技术文档可在GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/contentfragmentlist/v1/contentfragmentlist)上找到。

有关开发核心组件的更多详细信息，请参阅 [核心组件开发人员文档](developing.md)。

## 配置对话框 {#configure-dialog}

配置对话框允许内容作者定义包含列表和要包含的片段元素的内容片段。

### 属性选项卡

**属性** 选项卡定义了包含在列表中的内容片段。这主要基于选定的内容片段模型，但还有其他筛选器选项可用。

![](assets/screen-shot-2019-05-08-10.47.19.png)

* **模型** -列表所基于的内容片段模型的路径。
   * 默认情况下，定义为 **“模型路径”的模型的所有内容片段** 都包含在列表中。
* **父路径** -应从中构建列表的父路径。
   * 基于选定 **的模型路径** 的内容片段将被过滤为指定 **的父路径**上的内容片段。
   * 单击或点按字段右侧的 **打开选择对话框** 按钮可指定路径。
* **标记** -只有具有指定标记的内容片段才会包含在列表中。
   * 单击或点按字段右侧的 **打开选择对话框** 按钮可指定标记。
   * 单击或点按选定标记旁边的X以删除它们。


### Elements选项卡

默认情况下，内容片段模型的所有元素都将包含在列表中。**Elements** 允许您只指定要包含的特定元素。

![](assets/screen-shot-2019-05-08-10.47.34.png)

* **元素** -只会显示指定列表中内容片段的元素。
   * 单击或点按 **添加** 按钮以添加新元素
   * 单击或点按 **删除** 按钮可删除选定的元素
   * 拖动 **顺序** 手柄以重新排列元素的顺序。

## 设计对话框 {#design-dialog}

设计对话框允许模板作者定义应用于内容片段列表组件的样式。