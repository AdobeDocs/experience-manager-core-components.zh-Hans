---
title: Accordion组件
description: 核心组件折叠面板组件允许创建在页面上折叠面板中排列的面板集合。
translation-type: tm+mt
source-git-commit: fe8a121520000ffd56ae3347469590e89121eaf0

---


# Accordion组件{#accordion-component}

核心组件折叠面板组件允许创建在页面上折叠面板中排列的面板集合。

## 使用情况 {#usage}

核心组件折叠面板组件允许创建组件集合（由面板组成），并排列在页面上的折叠面板中(与 [Tabs组件类似](tabs.md))，但允许展开和折叠面板。

* 可在配置对话框中定义accordion的 [属性](#configure-dialog)。
* 可在配置对话框和选择面板弹出窗口中定义折叠面板 [的顺序](#select-panel-popover)。
* 将Accordion组件添加到页面时的默认值可以在设计对话框中 [定义](#design-dialog)。

## 版本和兼容性 {#version-and-compatibility}

Accordion组件的当前版本为v1,v1是2019年6月随核心组件版本2.5.0引入的，本文档对此进行了说明。

下表详细列出了组件的所有受支持版本、与组件版本兼容的AEM版本，以及指向先前版本的文档的链接。

| 组件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM作为云服务 |
|--- |--- |--- |---|---|
| v1 | 兼容 | 兼容 | 兼容 | 兼容 |

有关核心组件版本和版本的详细信息，请参阅文档核 [心组件版本](/help/versions.md)。

## 示例组件输出 {#sample-component-output}

要体验Accordion组件，并查看其配置选项的示例以及HTML和JSON输出，请访问组 [件库](https://adobe.com/go/aem_cmp_library_accordion)。

## 技术详细信息 {#technical-details}

有关Accordion组件的最新技术文档 [可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_accordion_v1)。

有关开发核心组件的更多详细信息，请参阅核 [心组件开发人员文档](/help/developing/overview.md)。

## 配置对话框 {#configure-dialog}

配置对话框允许内容作者定义折叠式项目及其面板，以及该项目的行为方式和页面访客的显示方式。

### 项目选项卡 {#items-tab}

![](/help/assets/screen-shot-2019-06-21-08.26.38.png)

使用添 **加按钮** ，打开组件选择器以选择要添加为面板的组件。 添加后，一个条目将添加到列表，其中包含以下列：

* **图标** -面板组件类型的图标，可在列表中轻松识别。 将鼠标悬停在上方，可将完整组件名称作为工具提示查看。
* **说明** -用作面板文本的说明，默认使用为面板选择的组件的名称。
* **删除** -点按或单击，从折叠式组件中删除面板。
* **重新排列** -点按或单击并拖动以重新排列面板的顺序。

>[!TIP]
>
>如果缩小了页面的视区，使编辑对话框变为全屏，则“添 **加** ”按钮将隐藏。 通过从组件浏览器中拖放到页面编辑 [器中的Accordion组件，仍可以将组件添加到Accordion组件](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html#InsertingaComponent)。

### 属性选项卡 {#properties-tab}

![](/help/assets/screen-shot-2019-06-21-08.26.53.png)

* **单个项目扩展** -选择此选项后，将强制一次展开单个折叠项目。 展开一个项目后，将折叠所有其他项目。
* **扩展项目** -此选项定义加载页面时默认展开的项目。
   * 选 **择“单个项目扩展** ”后，必须选择一个面板。 默认情况下，第一个面板处于选中状态。
   * 如果未 **选择“单个项目扩展** ”，则此选项为多选选项，且是可选的。

## 选择面板弹出窗口 {#select-panel-popover}

内容作者可以使用组件工具栏上的 **“选择面板** ”选项更改为其他面板进行编辑，并轻松重新排列折叠面板中面板的顺序。

![](/help/assets/screen-shot-2019-06-21-08.49.36.png)

在组件工 **具栏中选择** “选择面板”选项后，配置的折叠面板将显示为下拉框。

![](/help/assets/screen-shot-2019-06-21-08.52.14.png)

* 列表按面板的分配排列进行排序，并反映在编号中。
* 首先显示面板的组件类型，然后显示字体较轻的面板说明。
* 点按或单击下拉菜单中的条目，将编辑器中的视图切换到该面板。
* 使用拖动手柄可以就地重新排列面板。

## 设计对话框 {#design-dialog}

设计对话框允许模板作者定义可供内容作者使用折叠组件的选项以及放置折叠组件时设置的默认值。

### 属性选项卡 {#properties-tab-design}

![](/help/assets/screen-shot-2019-06-21-08.58.11.png)

* **允许的标题元素** -此多选下拉框定义作者允许选择的折叠项目标题HTML元素。
* **默认标题元素** -此下拉框定义默认的折叠项目标题HTML元素。

### 允许的组件选项卡 {#allowed-components-tab}

“允 **许的组件** ”选项卡用于定义内容作者可以将哪些组件作为项目添加到Accordion组件中的面板。

在模板编辑器中定义布局容器的策略和属性时，“允许的组件”选项卡 [的功能与同名选项卡的功能相同。](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/siteandpage/templates.html)

### 样式选项卡 {#styles-tab}

Accordion组件支持AEM样 [式系统](/help/get-started/authoring.md#component-styling)。
