---
title: 选项卡组件
seo-title: 选项卡组件
description: 选项卡组件允许创建多个选项卡，以排列页面上的内容。
seo-description: 选项卡组件允许创建多个选项卡，以排列页面上的内容。
uuid: 46f71233-8b12-4887-a0 c6-ad24 dc469 cb1
content-type: 引用
topic-tags: 核心组件
discoiquuid: 966d47fb-d35 d-4103-b29 d-4ef0 aa739 f24
translation-type: tm+mt
source-git-commit: eef608fb06001485aa2c2c0b574af412ed7f15a4

---


# 选项卡组件

核心组件选项卡组件允许将内容组织到多个选项卡上。

## 使用情况 {#usage}

选项卡组件允许内容作者在多个选项卡中组织页面内容。

[编辑对话框](#edit-dialog) 允许内容作者定义多个选项卡以及设置活动选项卡。Using the [design dialog](#design-dialog), the template author can define which components can be added to tabs and customize the styles.

>[!NOTE]
>
>支持嵌套选项卡组件(选项卡中的选项卡)。
>
>Simple (non-nested) tab components can be located/selected using the [content tree](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/author-environment-tools.html), however nested tabs can not be.

## Version and Compatibility {#version-and-compatibility}

选项卡组件的当前版本是v1，它是在2018年10月版核心组件中引入的，它在本文档中进行了介绍。

下表详细说明了组件的所有支持版本、组件版本的AEM版本以及以前版本的文档链接。

| 组件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v1 | 兼容 | 兼容 | 兼容 |

For more information about Core Component versions and releases, see the document [Core Components Versions](versions.md).

## Sample Component Output {#sample-component-output}

To experience the Tabs Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library/tabs.html).

### Technical Details {#technical-details}

The latest technical documentation about the Tabs Component [can be found on GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/tabs/v1/tabs).

Further details about developing Core Components can be found in the [Core Components developer documentation](developing.md).

## Edit Dialog {#edit-dialog}

编辑对话框允许内容作者创建、重命名和重新排列选项卡以及定义活动选项卡。

### Items Tab {#items-tab}

![](assets/screenshot_2018-10-11at153557.png)

Use the **Add** button to open the component selector to choose which component to add as a tab. 添加后，条目会添加到列表中，其中包含以下列：

* **图标** -选项卡的组件类型的图标，用于在列表中轻松标识。将鼠标悬停在鼠标上可查看整个组件名称作为工具提示。
* **描述** -用作选项卡文本的说明，默认为选项卡所选的组件名称。
* **删除** -点按或单击可从选项卡组件中删除选项卡。
* **重新排列** -点按或单击并拖动可重新排列选项卡的顺序。

### Properties Tab {#properties-tab}

![](assets/screenshot_2018-10-19at140646.png)

On the **Properties** tab, the content author can define which tab is active when the page is loaded. With the **Default** option, the first tab will be selected.

## Select Panel {#select-panel}

The content author can use the **Select Panel** option on the component toolbar to change to a different panel for editing as well as to easily rearrange the order of the tabs.

![](assets/screenshot_2018-10-11at165417.png)

Once selecting the **Select Panel** option in the component toolbar, the configured tabs are displayed as a drop-down.

* 列表由选项卡分配的排列排序，并反映在编号中。
* 将首先显示选项卡的组件类型，后跟较亮字体中的选项卡描述。

![](assets/screenshot_2018-10-11at165154.png)

* 点击或单击下拉菜单中的条目，将编辑器中的视图切换到该选项卡。
* 使用拖动手柄可以就地重新排列选项卡。

>[!NOTE]
>
>Tabs are not selectable by the author when in **Edit** mode. Use [**Preview** mode](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html) or the **[View as Published](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html)** option to interact with the tabs as a reader of the published content would.

## Design Dialog {#design-dialog}

设计对话框允许模板作者定义可将哪些组件添加为选项卡组件的项目，以及定义内容作者可用的自定义样式。

### Allowed Components Tab {#allowed-components-tab}

**允许的组件** 选项卡用于定义内容作者可以将哪些组件添加为选项卡组件的项目。

The Allowed Components tab functions in the same way as the tab of the same name when [defining the policy and properties of a Layout Container in the Template Editor.](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)

### Styles Tab {#styles-tab}

The Tabs Component supports the AEM [Style System](authoring.md#component-styling).