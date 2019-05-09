---
title: 页面组件
seo-title: 页面组件
description: 页面组件是可扩展的页面组件，设计用于与模板编辑器配合使用，并允许使用模板编辑器组合页面标题/页脚和结构组件。
seo-description: 页面组件是可扩展的页面组件，设计用于与模板编辑器配合使用，并允许使用模板编辑器组合页面标题/页脚和结构组件。
uuid: 7052a5b1-e7 f1-4944-a55 c-faf739 b6 e89 c
contentOwner: 用户
content-type: 引用
topic-tags: 创作
products: SG_ EXPERIENCE MANAGER/CORECOMMPANES-new
discoiquuid: cb1a745a-30c4-4ad6-a04 f-feffb3666 cd95
translation-type: tm+mt
source-git-commit: 1bbec9b1f109df88964dce051a58d111bf6cafaa

---


# 页面组件{#page-component}

页面组件是可扩展的页面组件，用于与 [模板编辑器](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html) 配合使用，并允许页面标题/页脚和结构组件使用模板编辑器进行组合。

## 使用情况 {#usage}

页面组件构成了使用核心组件以及可编辑模板设计的所有页面的基础。使用页面组件、页眉、页脚和页面结构可以定义为使用其他核心组件的模板。

使用 [设计对话框](#design-dialog)，可以为页面定义自定义客户端库。与其他具有可直接从组件访问的编辑对话框的组件不同，因为组件本身是页面本身，因此页面组件的 [编辑对话框](#edit-dialog) 是页面属性窗口。

## 版本和兼容性 {#version-and-compatibility}

页面组件的当前版本是v2，该版本是在2018年月版的核心组件中引入的，它在文档中进行了介绍。

下表详细说明了组件的所有支持版本、组件版本的AEM版本以及以前版本的文档链接。

| 组件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|---|---|---|---|
| [v2](page-v1.md) | 兼容 | 兼容 | 兼容 |
| v1 | 兼容 | 兼容 | 兼容 |

有关核心组件版本和版本的更多信息，请参阅文档 [核心组件版本](versions.md)。

>[!NOTE]
>
>要对页面组件 `cq:Page` 和AEM6.3的版本进行重定向， [需要Service Pack](https://helpx.adobe.com/experience-manager/6-3/release-notes/sp2-release-notes.html) 或更高版本。此类重定向在以前的版本中不可用。

## 示例组件输出 {#sample-component-output}

以下示例取自 [We. Retail](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html)。

### 屏幕快照 {#screenshot}

![](assets/chlimage_1.png)

### 技术详细信息 {#technical-details}

有关页面组件 [的最新技术文档可在GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/page/v2/page)上找到。

有关开发核心组件的更多详细信息，请参阅 [核心组件开发人员文档](developing.md)。

## 编辑对话框 {#edit-dialog}

由于组件代表整个页面，因此通常在编辑对话框中显示的设置位于 [页面属性](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-page-properties.html) 窗口中。

## 设计对话框 {#design-dialog}

由于组件代表整个页面，因此编辑页面模板时，将通过 **页面信息-&gt;页面策略** 访问设计对话框。

![](assets/screen_shot_2018-04-03at113410.png)

>[!NOTE]
>
>在AEM的早期版本中 **，页面策略** 称为 **页面设计**。

### 属性选项卡 {#properties-tab}

使用页面设计窗口，您可以定义要加载的客户端库以及页面的Web资源库。

* **客户端库**此定义要加载的客户端库类别。JavaScript添加到正文末尾，CSS添加到页面头部。
* **客户端库JavaScript页面标题**此操作定义要在页面头部加载的JavaScript客户端库类别。
   * 在此定义的类别在 **客户端库** 字段中也将加载JavaScript，而不是在正文结尾加载JavaScript。
   * 除非 **在Client Libraries** 字段中也存在该类别，否则不加载CSS。

* **Web资源客户端库**用于提供Web资源(如优点)的客户端库类别。

![](assets/screenshot_2018-10-19at104949.png)

可以为 **客户端库** 和 **客户端库JavaScript页面头** 字段配置库，如下所示：

* 要添加新字段，请单击或点按字段下方的 **添加** 按钮。
* 要删除字段，请单击或点按要删除的字段旁边的垃圾桶图标。
* 要重新排列加载顺序，请单击或点按并拖动要移动的字段旁边的手柄。

有关使用客户端库的详细信息，请参阅 [使用客户端库](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/clientlibs.html)。

>[!CAUTION]
>
>在核心组件版本2.2.0中引入了单独定义页面头部的客户端库的功能。

### 样式选项卡 {#styles-tab}

页面组件支持AEM [Style System](authoring.md#component-styling)。