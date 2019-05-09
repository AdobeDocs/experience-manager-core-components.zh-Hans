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
source-git-commit: 1bbec9b1f109df88964dce051a58d111bf6cafaa

---


# 传送组件{#carousel-component}

核心组件传送组件允许内容作者在可导航传送中演示内容。

## 使用情况 {#usage}

使用传送组件，内容作者可在旋转的幻灯片旋转中组织内容。

[编辑对话框](#edit-dialog) 允许内容作者创建、命名和排序多张幻灯片，并可延迟启用自动过渡。使用 [设计对话框](#design-dialog)，模板作者可以定义可向传送添加哪些组件、启用或禁用自动过渡以及自定义样式。

## 版本和兼容性 {#version-and-compatibility}

传送组件的当前版本是v1，它是在2018年10月核心组件中推出的v1，它在本文档中进行了介绍。

下表详细说明了组件的所有支持版本、组件版本的AEM版本以及以前版本的文档链接。

| 组件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v1 | 兼容 | 兼容 | 兼容 |

有关核心组件版本和版本的更多信息，请参阅文档 [核心组件版本](versions.md)。

## 示例组件输出 {#sample-component-output}

以下是取自 [We. Retail](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html)的示例。

### 屏幕快照 {#screenshot}

![](assets/screenshot_2018-11-28at140433.png)

### 组件库 {#component-library}

要体验传送组件以及查看其配置选项的示例以及HTML和JSON输出，请访问 [组件库](http://opensource.adobe.com/aem-core-wcm-components/library/carousel.html)。

### 技术详细信息 {#technical-details}

有关传送组件 [的最新技术文档，请参阅GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/carousel/v1/carousel)。

有关开发核心组件的更多详细信息，请参阅 [核心组件开发人员文档](developing.md)。

## 编辑对话框 {#edit-dialog}

编辑对话框允许内容作者添加、重命名幻灯片和重新排列幻灯片以及定义自动过渡设置。

### 项目选项卡 {#items-tab}

![](assets/screenshot_2018-10-12at102451.png)

使用 **“添加** ”按钮打开组件选择器，以选择要添加为选项卡的组件。添加后，条目会添加到列表中，其中包含以下列：

* **图标** -选项卡的组件类型的图标，用于在列表中轻松标识。将鼠标悬停在鼠标上可查看整个组件名称作为工具提示。
* **描述** -用作选项卡文本的说明，默认为选项卡所选的组件名称。
* **删除** -点按或单击可从选项卡组件中删除选项卡。
* **重新排序** -点按或单击并拖动可对选项卡进行排序。

### 属性选项卡 {#properties-tab}

![](assets/screenshot_2018-11-28at141054.png)

在 **“属性** ”选项卡上，内容作者可以将幻灯片设置为自动过渡。

* **自动过渡幻灯片** -活动时，组件会自动前进到下一张幻灯片，之后指定的延迟会出现。
* **过渡延迟** -选中自动过渡幻灯片时，此值用于定义过渡之间的延迟(以毫秒为单位)。
* **悬停时禁用自动暂停** -选中 **自动过渡幻灯片** 后，光标将在光标悬停在传送上方时自动暂停。选择此选项以使过渡暂停。

>[!NOTE]
>
>**在编辑** 模式下，幻灯片前进控件未启用。使用 [**预览** 模式](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html) 或 **[“查看已发布”](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html)** 选项可与已发布内容的读者进行交互操作。
>
>**在编辑** 模式下，不启用自动前进功能。使用 **[“查看已发布](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html)** ”选项可查看已发布内容的读者将自动前进的功能。

## 选择面板 {#select-panel}

内容作者可以使用组件工具栏上的 **“选择面板** ”选项更改为其他幻灯片进行编辑，以及轻松重新排列幻灯片的顺序。

![](assets/screenshot_2018-10-11at165417.png)

在组件工具栏中选择 **“选择面板** ”选项后，配置的幻灯片将显示为下拉列表。

* 列表由幻灯片分配的排列排序，并反映在编号中。
* 幻灯片的组件类型首先显示，后跟浅体字体的描述。

![](assets/opera_snapshot_2018-11-28141537localhost.png)

* 点击或单击下拉菜单中的条目，将编辑器中的视图切换到该幻灯片。
* 可以使用拖动手柄在就地重新排序幻灯片。

## 设计对话框 {#design-dialog}

设计对话框允许模板作者定义可将哪些组件添加为传送组件，以及定义自动转换默认值以及内容作者可用的自定义样式。

### 属性选项卡 {#properties-tab-1}

**属性** 选项卡用于定义内容作者将传送组件添加到页面时幻灯片过渡的默认设置。

![](assets/screenshot_2018-11-28at141824.png)

* **自动转换幻灯片** -默认情况下，当内容作者将传送组件添加到页面时，将启用自动前进到下一张幻灯片的选项。
* **过渡延迟** -定义内容作者将传送组件添加到页面时幻灯片之间的过渡延迟的默认值(以毫秒为单位)。
* **停用悬停时自动暂停** -定义默认情况下，内容作者选择 **自动过渡幻灯片** 时禁用自动幻灯片暂停选项的选项。

### 允许的组件选项卡 {#allowed-components-tab}

**允许的组件** 选项卡用于定义内容作者可将哪些组件添加为传送组件。

在模板编辑器中 [定义布局容器的策略和属性时，允许的组件选项卡功能与同名选项卡相同。](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)

### 样式选项卡 {#styles-tab}

传送组件支持AEM [Style System](authoring.md#component-styling)。