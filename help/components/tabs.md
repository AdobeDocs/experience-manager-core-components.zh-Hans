---
title: 选项卡组件
description: 选项卡组件允许创建多个选项卡来排列页面上的内容。
translation-type: tm+mt
source-git-commit: d3ebcea5fa1523c1a986841cd3d1a64e16e85f6d
workflow-type: tm+mt
source-wordcount: '1040'
ht-degree: 2%

---


# 选项卡组件{#tabs-component}

核心组件选项卡组件允许将内容组织到多个选项卡上。

## 使用 {#usage}

选项卡组件允许内容作者在多个选项卡中组织页面内容。

[编辑对话框](#edit-dialog)允许内容作者定义多个选项卡并设置活动选项卡。 使用[设计对话框](#design-dialog)，模板作者可以定义哪些组件可以添加到选项卡并自定义样式。

>[!TIP]
>
>支持嵌套的选项卡组件（选项卡中的选项卡）。
>
>使用[内容树](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html#content-tree)可以定位/选择简单（非嵌套）的选项卡组件，但嵌套的选项卡不能。

## 深层链接到面板{#deep-linking}

选项卡和[折叠组件](accordion.md)支持直接链接到组件中的面板。

要执行此操作：

1. 使用页面编辑器中的&#x200B;**[视图作为“已发布”](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)**&#x200B;选项将页面与组件视图。
1. Inspect页面内容并标识面板的ID。
   * 例如`id="accordion-86196c94d3-item-ca319dbb0b"`
1. 该ID将成为您可以使用哈希(`#`)附加到URL的锚点。
   * 例如`https://wknd.site/content/wknd/language-masters/en/magazine/western-australia.html#accordion-86196c94d3-item-ca319dbb0b`

导航到面板ID为锚点的URL，浏览器将直接滚动到特定组件并显示指定的面板。 如果面板配置为默认不展开，则会自动展开面板。

## 版本和兼容性{#version-and-compatibility}

当前版本的选项卡组件为v1,2018年10月随核心组件版本2.2.0引入了v1，本文档对此进行了说明。

下表详细列出了组件的所有受支持版本、与组件版本兼容的AEM版本，以及指向先前版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v1 | 兼容 | 兼容 | 兼容 |

有关核心组件版本和版本的详细信息，请参阅文档[核心组件版本](/help/versions.md)。

## 示例组件输出{#sample-component-output}

要体验选项卡组件及其配置选项以及HTML和JSON输出的示例，请访问[组件库](https://adobe.com/go/aem_cmp_library_tabs)。

### 技术详细信息{#technical-details}

有关选项卡组件[的最新技术文档可在GitHub](https://adobe.com/go/aem_cmp_tech_tabs_v1)上找到。

有关开发核心组件的更多详细信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## 编辑对话框{#edit-dialog}

在编辑对话框中，内容作者可以创建、重命名和重新排列选项卡以及定义活动选项卡。

### 项目选项卡{#items-tab}

![选项卡组件的编辑对话框项目选项卡](/help/assets/tabs-edit-items.png)

使用&#x200B;**添加**&#x200B;按钮打开组件选择器以选择要添加为选项卡的组件。 添加后，将向列表中添加一个条目，其中包含以下列：

* **图标**  — 选项卡的组件类型图标，可在列表中轻松识别。将鼠标悬停在上方，可以将完整组件名称作为工具提示查看。
* **说明**  — 用作选项卡文本的说明，默认使用为选项卡选择的组件的名称。
* **删除**  — 点按或单击可从选项卡组件中删除选项卡。
* **重新排列**  — 点按或单击并拖动以重新排列选项卡的顺序。

>[!TIP]
>
>如果缩小了页面的视区，使编辑对话框变为全屏，则&#x200B;**添加**&#x200B;按钮将被隐藏。 组件仍可以通过[从组件浏览器拖放到页面编辑器](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#inserting-a-component)中的选项卡组件来添加到选项卡组件。

### 属性选项卡{#properties-tab}

![选项卡组件的编辑对话框属性选项卡](/help/assets/tabs-edit-properties.png)

* **活动项**  — 内容作者可以定义载入页面时处于活动状态的选项卡。
   * 使用&#x200B;**Default**&#x200B;选项，将选择第一个选项卡。
* **ID**  — 此选项允许控制HTML和数据层中组件的唯一 [标识符](/help/developing/data-layer/overview.md)。
   * 如果留空，系统会为您自动生成唯一ID，通过检查生成的页面可以找到它。
   * 如果指定了ID，则作者有责任确保它是唯一的。
   * 更改ID可能会影响CSS、JS和数据图层跟踪。

### 辅助功能选项卡{#accessibility-tab}

![选项卡组件的编辑对话框辅助功能选项卡](/help/assets/tabs-edit-accessibility.png)

在&#x200B;**辅助功能**&#x200B;选项卡上，可以为组件的[ARIA辅助功能](https://www.w3.org/WAI/standards-guidelines/aria/)标签设置值。

* **Label**  — 组件的ARIA label属性值

## 选择面板{#select-panel}

内容作者可以使用组件工具栏上的&#x200B;**选择面板**&#x200B;选项更改到其他面板进行编辑，并轻松重新排列选项卡的顺序。

![选择面板图标](/help/assets/select-panel-icon.png)

在组件工具栏中选择&#x200B;**选择面板**&#x200B;选项后，将显示所配置的选项卡作为下拉列表。

* 列表按标签的指定排列排列，并反映在编号中。
* 首先显示选项卡的组件类型，然后以较浅的字体显示选项卡的说明。

![选择面板快显](/help/assets/select-panel-popover.png)

* 点按或单击下拉列表中的条目，将编辑器中的视图切换到该选项卡。
* 可以使用拖动手柄就地重新排列选项卡。

>[!NOTE]
>
>作者在&#x200B;**编辑**&#x200B;模式下无法选择制表符。 使用&#x200B;**[预览](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#preview-mode)**&#x200B;模式或&#x200B;**[视图作为已发布](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)**&#x200B;选项与选项卡进行交互，作为已发布内容的读者。

## 设计对话框{#design-dialog}

设计对话框允许模板作者定义哪些组件可以作为项目添加到选项卡组件，以及定义哪些自定义样式可供内容作者使用。

### 允许的组件选项卡{#allowed-components-tab}

**允许的组件**&#x200B;选项卡用于定义内容作者可以将哪些组件作为项目添加到选项卡组件。

当[在模板编辑器中定义布局容器的策略和属性时，允许的组件选项卡的功能与同名选项卡的功能相同。](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)

### 样式选项卡{#styles-tab}

选项卡组件支持AEM [样式系统](/help/get-started/authoring.md#component-styling)。

## Adobe客户端数据层{#data-layer}

选项卡组件支持[Adobe客户端数据层。](/help/developing/data-layer/overview.md)
