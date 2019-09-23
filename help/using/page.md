---
title: 页面组件
seo-title: 页面组件
description: 页面组件是可扩展的页面组件，旨在与模板编辑器一起使用，并允许使用模板编辑器组合页眉／页脚和结构组件。
seo-description: 页面组件是可扩展的页面组件，旨在与模板编辑器一起使用，并允许使用模板编辑器组合页眉／页脚和结构组件。
uuid: 7052a5b1-e7f1-4944-a55c-faf739b6e89c
contentOwner: 用户
content-type: 引用
topic-tags: 创作
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-新
discoiquuid: cb1a745a-30c4-4ad6-a04f-fefb3666cd95
translation-type: tm+mt
source-git-commit: 1243d6cc1b0b015ee2f37ae89d0e2e42d366cc02

---


# 页面组件{#page-component}

页面组件是一个可扩展的页面组件，设计用于与模板编辑 [器一起使用](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html) ，并允许使用模板编辑器组合页眉／页脚和结构组件。

## 使用情况 {#usage}

页面组件构成了使用核心组件以及可编辑模板设计的所有页面的基础。 通过使用页面组件，页眉、页脚和页面结构可以使用其他核心组件定义为模板。

使用设 [计对话框](#design-dialog)，可以为页面定义自定义客户端库。 与具有可直接从组件访问的编辑对话框的其他组件不同，因为组件是页面本身，所以页面组件的编辑 [对话框](#edit-dialog) 是页面属性窗口。

## 版本和兼容性 {#version-and-compatibility}

页面组件的当前版本为v2，该版本在2018年1月随核心组件版本2.0.0一起引入，本文档对此进行了说明。

下表详细列出了组件的所有受支持版本、与组件版本兼容的AEM版本，以及指向先前版本的文档的链接。

| 组件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|---|---|---|---|
| [v2](page-v1.md) | 兼容 | 兼容 | 兼容 |
| v1 | 兼容 | 兼容 | 兼容 |

有关核心组件版本和版本的详细信息，请参阅文档核 [心组件版本](versions.md)。

>[!NOTE]
>
>要在页面组 `cq:Page` 件和AEM 6.3版本2的级别启用重定向， [需要Service Pack 2](https://helpx.adobe.com/experience-manager/6-3/release-notes/sp2-release-notes.html) 或更高版本。 此类重定向在以前的版本中不可用。

## 示例组件输出 {#sample-component-output}

以下是从 [We.Retail获取的示例](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html)。

### 屏幕快照 {#screenshot}

![](assets/chlimage_1.png)

### 技术详细信息 {#technical-details}

有关页面组件的最新技术文 [档可在GitHub上找到](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/page/v2/page)。

有关开发核心组件的更多详细信息，请参阅核 [心组件开发人员文档](developing.md)。

## Edit Dialog {#edit-dialog}

由于组件表示整个页面，因此通常在编辑对话框中的设置会显示在页面属 [性窗口中](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-page-properties.html) 。

## 设计对话框 {#design-dialog}

由于组件表示整个页面，因此在编辑页面模板时，可通过“页 **面信息”-&gt;“页面策略** ”访问设计对话框。

![](assets/screen_shot_2018-04-03at113410.png)

>[!NOTE]
>
>在AEM的早期版本中，页面 **策略称为** “页 **面设计”**。

### 属性选项卡 {#properties-tab}

使用“页面设计”窗口，您可以定义要加载的客户端库以及页面的Web资源库。

* **客户端库**&#x200B;这定义要加载的客户端库类别。 JavaScript添加在正文末尾，而CSS添加到页面标题。
* **客户端库JavaScript页面头**&#x200B;定义要加载到页面头中的JavaScript客户端库类别。
   * 此处定义的类别(也在“客户端库 **”字段中** )将在页面标题中加载JavaScript，而不是在正文结尾。
   * 除非“客户端库”字段中也存在类别，否则不会加 **载任何CSS** 。

* **Web资源客户端库**&#x200B;用于提供Web资源（如Favicons）的客户端库类别。

![](assets/screenshot_2018-10-19at104949.png)

可以为“客户端库”和“客 **户端库** ”JavaScript **** 页面头字段配置库，如下所示：

* 要添加新字段，请单击或点按字 **段下方** 的添加按钮。
* 要删除字段，请单击或点按要删除的字段旁边的垃圾桶图标。
* 要重新排列加载顺序，请单击或点按并拖动要移动的字段旁边的手柄。

有关使用客户端库的详细信息，请参阅 [使用客户端库](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/clientlibs.html)。

>[!CAUTION]
>
>核心组件版本2.2.0引入了为页面头单独定义客户端库的功能。

### 样式选项卡 {#styles-tab}

页面组件支持AEM样 [式系统](authoring.md#component-styling)。