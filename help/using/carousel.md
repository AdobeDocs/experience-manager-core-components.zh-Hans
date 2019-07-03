---
title: 传送组件
seo-title: 传送组件
description: 'null'
seo-description: 传送组件允许内容作者在旋转轮播中演示内容。
uuid: 34934491-bd85-4f1 e-ae22-bb48 ed4 dd5 c
content-type: 引用
topic-tags: 核心组件
discoiquuid: 3510812b-9d3e-40fe-b986-0f15 d40 b42 ad
disttype: dist5
gnavtheme: 浅色
groupsectionnavitems: 否
hidemerchandisingbar: 继承
hidepromocomponent: 继承
modalsize: 426 x 240
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: eef608fb06001485aa2c2c0b574af412ed7f15a4

---


# Carousel Component{#carousel-component}

核心组件传送组件允许内容作者在可导航传送中演示内容。

## 使用情况 {#usage}

使用传送组件，内容作者可在旋转的幻灯片旋转中组织内容。

[编辑对话框](#edit-dialog) 允许内容作者创建、命名和排序多张幻灯片，并可延迟启用自动过渡。Using the [design dialog](#design-dialog), the template author can define which components can be added to the carousel, enable or disable automatic transitions, and customize the styles.

## Version and Compatibility {#version-and-compatibility}

传送组件的当前版本是v1，它是在2018年10月核心组件中推出的v1，它在本文档中进行了介绍。

下表详细说明了组件的所有支持版本、组件版本的AEM版本以及以前版本的文档链接。

| 组件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v1 | 兼容 | 兼容 | 兼容 |

For more information about Core Component versions and releases, see the document [Core Components Versions](versions.md).

## Sample Component Output {#sample-component-output}

To experience the Carousel Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library/carousel.html).

### Technical Details {#technical-details}

The latest technical documentation about the Carousel Component [can be found on GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/carousel/v1/carousel).

Further details about developing Core Components can be found in the [Core Components developer documentation](developing.md).

## Edit Dialog {#edit-dialog}

编辑对话框允许内容作者添加、重命名幻灯片和重新排列幻灯片以及定义自动过渡设置。

### Items Tab {#items-tab}

![](assets/screenshot_2018-10-12at102451.png)

Use the **Add** button to open the component selector to choose which component to add as a tab. 添加后，条目会添加到列表中，其中包含以下列：

* **图标** -选项卡的组件类型的图标，用于在列表中轻松标识。将鼠标悬停在鼠标上可查看整个组件名称作为工具提示。
* **描述** -用作选项卡文本的说明，默认为选项卡所选的组件名称。
* **删除** -点按或单击可从选项卡组件中删除选项卡。
* **重新排序** -点按或单击并拖动可对选项卡进行排序。

### Properties Tab {#properties-tab}

![](assets/screenshot_2018-11-28at141054.png)

On the **Properties** tab, the content author can set the slides to automatically transition.

* **自动过渡幻灯片** -活动时，组件会自动前进到下一张幻灯片，之后指定的延迟会出现。
* **过渡延迟** -选中自动过渡幻灯片时，此值用于定义过渡之间的延迟(以毫秒为单位)。
* **悬停时禁用自动暂停** -选中 **自动过渡幻灯片** 后，光标将在光标悬停在传送上方时自动暂停。选择此选项以使过渡暂停。

>[!NOTE]
>
>**在编辑** 模式下，幻灯片前进控件未启用。Use [**Preview** mode](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html) or the **[View as Published](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html)** option to interact with the carousel as a reader of the published content would.
>
>**在编辑** 模式下，不启用自动前进功能。Use **[View as Published](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html)** option to see the auto-advance feature as a reader of the published content would.

## Select Panel {#select-panel}

The content author can use the **Select Panel** option on the component toolbar to change to a different slide for editing as well as to easily rearrange the order of the slides.

![](assets/screenshot_2018-10-11at165417.png)

Once selecting the **Select Panel** option in the component toolbar, the configured slides are displayed as a drop-down.

* 列表由幻灯片分配的排列排序，并反映在编号中。
* 幻灯片的组件类型首先显示，后跟浅体字体的描述。

![](assets/opera_snapshot_2018-11-28141537localhost.png)

* 点击或单击下拉菜单中的条目，将编辑器中的视图切换到该幻灯片。
* 可以使用拖动手柄在就地重新排序幻灯片。

## Design Dialog {#design-dialog}

设计对话框允许模板作者定义可将哪些组件添加为传送组件，以及定义自动转换默认值以及内容作者可用的自定义样式。

### Properties Tab {#properties-tab-1}

**属性** 选项卡用于定义内容作者将传送组件添加到页面时幻灯片过渡的默认设置。

![](assets/screenshot_2018-11-28at141824.png)

* **自动转换幻灯片** -默认情况下，当内容作者将传送组件添加到页面时，将启用自动前进到下一张幻灯片的选项。
* **过渡延迟** -定义内容作者将传送组件添加到页面时幻灯片之间的过渡延迟的默认值(以毫秒为单位)。
* **停用悬停时自动暂停** -定义默认情况下，内容作者选择 **自动过渡幻灯片** 时禁用自动幻灯片暂停选项的选项。

### Allowed Components Tab {#allowed-components-tab}

**允许的组件** 选项卡用于定义内容作者可将哪些组件添加为传送组件。

The Allowed Components tab functions in the same way as the tab of the same name when [defining the policy and properties of a Layout Container in the Template Editor.](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)

### Styles Tab {#styles-tab}

The Carousel Component supports the AEM [Style System](authoring.md#component-styling).