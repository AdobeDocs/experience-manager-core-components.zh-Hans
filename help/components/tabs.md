---
title: 选项卡组件
description: 选项卡组件允许创建多个选项卡来排列页面上的内容。
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

---


# 选项卡组件

核心组件选项卡组件允许将内容组织到多个选项卡上。

## 使用情况 {#usage}

选项卡组件允许内容作者在多个选项卡中组织页面内容。

在编 [辑对话框中](#edit-dialog) ，内容作者可以定义多个选项卡并设置活动选项卡。 使用设 [计对话框](#design-dialog)，模板作者可以定义可添加到选项卡的组件并自定义样式。

>[!NOTE]
>
>支持嵌套的选项卡组件（选项卡内的选项卡）。
>
>使用内容树可以定位／选择简单（非嵌套）的选 [项卡组件](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html#content-tree)，但嵌套的选项卡不能。

## 版本和兼容性 {#version-and-compatibility}

选项卡组件的当前版本为v1,v1是2018年10月随核心组件版本2.2.0引入的，本文档对此进行了说明。

下表详细列出了组件的所有受支持版本、与组件版本兼容的AEM版本，以及指向先前版本的文档的链接。

| 组件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM作为云服务 |
|--- |--- |--- |--- |---|
| v1 | 兼容 | 兼容 | 兼容 | 兼容 |

有关核心组件版本和版本的详细信息，请参阅文档核 [心组件版本](/help/versions.md)。

## 示例组件输出 {#sample-component-output}

要体验选项卡组件以及查看其配置选项的示例以及HTML和JSON输出，请访问组件 [库](https://adobe.com/go/aem_cmp_library_tabs)。

### 技术详细信息 {#technical-details}

GitHub上提供有关选项卡组件 [的最新技术文档](https://adobe.com/go/aem_cmp_tech_tabs_v1)。

有关开发核心组件的更多详细信息，请参阅核 [心组件开发人员文档](/help/developing/overview.md)。

## Edit Dialog {#edit-dialog}

编辑对话框允许内容作者创建、重命名和重新排列选项卡以及定义活动选项卡。

### 项目选项卡 {#items-tab}

![](/help/assets/screen-shot-2019-08-29-12.28.16.png)

使用添 **加按钮** ，打开组件选择器以选择要添加为选项卡的组件。 添加后，一个条目将添加到列表，其中包含以下列：

* **图标** -选项卡的组件类型图标，可在列表中轻松识别。 将鼠标悬停在上方，可将完整组件名称作为工具提示查看。
* **说明** -用作选项卡文本的说明，默认使用为选项卡选择的组件的名称。
* **删除** -点按或单击，以从选项卡组件中删除选项卡。
* **重新排列** -点按或单击并拖动以重新排列选项卡的顺序。

>[!TIP]
>
>如果缩小了页面的视区，使编辑对话框变为全屏，则“添 **加** ”按钮将隐藏。 通过从组件浏览器中拖放到页面编辑 [器中的选项卡组件，组件仍可以添加到选项卡组件](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#inserting-a-component)。

### 属性选项卡 {#properties-tab}

![](/help/assets/screen-shot-2019-08-29-12.28.32.png)

在“属 **性** ”选项卡上，内容作者可以定义加载页面时处于活动状态的选项卡。 使用“默 **认** ”选项，将选择第一个选项卡。

### 辅助功能选项卡 {#accessibility-tab}

![](/help/assets/screen-shot-2019-08-29-12.28.40.png)

在“辅 **助功能** ”选项卡上 [，可为组件的](https://www.w3.org/WAI/standards-guidelines/aria/) ARIA辅助功能标签设置值。

* **标签** -组件的ARIA标签属性的值

## Select Panel {#select-panel}

内容作者可以使用组件工具 **栏上的“选择面板** ”选项更改为其他面板进行编辑，并轻松重新排列选项卡的顺序。

![](/help/assets/screenshot_2018-10-11at165417.png)

在组件工 **具栏中选择** “选择面板”选项后，所配置的选项卡将显示为下拉列表。

* 列表按标签的分配排列排序，并反映在编号中。
* 首先显示选项卡的组件类型，然后显示字体较轻的选项卡的说明。

![](/help/assets/screenshot_2018-10-11at165154.png)

* 点按或单击下拉菜单中的条目，将编辑器中的视图切换到该选项卡。
* 使用拖动手柄可以就地重新排列选项卡。

>[!NOTE]
>
>在编辑模式下，创作者不能选择 **选项卡** 。 使用 **[“预览](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#preview-mode)**”模式或“查**[&#x200B;看为已发布内容](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)** ”选项与选项卡进行交互，就像已发布内容的读者一样。

## 设计对话框 {#design-dialog}

设计对话框允许模板作者定义哪些组件可以作为项目添加到选项卡组件，以及定义哪些自定义样式可供内容作者使用。

### 允许的组件选项卡 {#allowed-components-tab}

“允 **许的组件** ”选项卡用于定义哪些组件可以作为项目由内容作者添加到选项卡组件。

在模板编辑器中定义布局容器的策略和属性时，“允许的组件”选项卡 [的功能与同名选项卡的功能相同。](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)

### 样式选项卡 {#styles-tab}

选项卡组件支持AEM样 [式系统](/help/get-started/authoring.md#component-styling)。
