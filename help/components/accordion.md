---
title: 折叠组件
description: 核心组件折叠面板组件允许创建页面折叠面板中排列的面板集合。
role: Architect, Developer, Administrator, Business Practitioner
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '1072'
ht-degree: 1%

---


# Accordion Component{#accordion-component}

核心组件折叠面板组件允许创建页面折叠面板中排列的面板集合。

## 使用 {#usage}

核心组件折叠面板组件允许创建组件集合，这些组件以面板的形式组成，并以折叠面板的形式排列在页面上，与[选项卡组件](tabs.md)类似，但允许展开和折叠面板。

* accordion的属性可以在[配置对话框](#configure-dialog)中定义。
* 可在“配置”对话框和[选择面板快显](#select-panel-popover)中定义折叠面板的顺序。
* 将Accordion组件添加到页面时的默认值可以在[设计对话框](#design-dialog)中定义。

## 深层链接到面板{#deep-linking}

Accordion和[选项卡组件](tabs.md)支持直接链接到组件中的面板。

要执行此操作：

1. 使用页面编辑器中的&#x200B;**[视图作为“已发布”](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)**&#x200B;选项将页面与组件视图。
1. Inspect页面内容并标识面板的ID。
   * 例如`id="accordion-86196c94d3-item-ca319dbb0b"`
1. 该ID将成为您可以使用哈希(`#`)附加到URL的锚点。
   * 例如`https://wknd.site/content/wknd/language-masters/en/magazine/western-australia.html#accordion-86196c94d3-item-ca319dbb0b`

导航到面板ID为锚点的URL，浏览器将直接滚动到特定组件并显示指定的面板。 如果面板配置为默认不展开，则会自动展开面板。

## 版本和兼容性{#version-and-compatibility}

Accordion组件的当前版本为v1,v1是2019年6月随核心组件版本2.5.0引入的，本文档对此进行了说明。

下表详细列出了组件的所有受支持版本、与组件版本兼容的AEM版本，以及指向先前版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | 兼容 | 兼容 | 兼容 |

有关核心组件版本和版本的详细信息，请参阅文档[核心组件版本](/help/versions.md)。

## 示例组件输出{#sample-component-output}

要体验Accordion组件，并查看其配置选项以及HTML和JSON输出的示例，请访问[组件库](https://adobe.com/go/aem_cmp_library_accordion)。

## 技术详细信息{#technical-details}

有关Accordion组件[的最新技术文档可在GitHub](https://adobe.com/go/aem_cmp_tech_accordion_v1)上找到。

有关开发核心组件的更多详细信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## 配置对话框{#configure-dialog}

通过“配置”对话框，内容作者可以定义折叠项目、其面板，以及它的行为和显示方式，以便访客页面。

### 项目选项卡{#items-tab}

![折叠组件编辑对话框的“项目”选项卡](/help/assets/accordion-edit-items.png)

使用&#x200B;**添加**&#x200B;按钮打开组件选择器以选择要添加为面板的组件。 添加后，将向列表中添加一个条目，其中包含以下列：

* **图标**  — 面板组件类型的图标，可在列表中轻松识别。将鼠标悬停在上方，可以将完整组件名称作为工具提示查看。
* **说明**  — 用作面板文本的说明，默认使用为面板选择的组件的名称。
* **删除**  — 点按或单击可从折叠组件中删除面板。
* **重新排列**  — 点按或单击并拖动以重新排列面板的顺序。

>[!TIP]
>
>如果缩小了页面的视区，使编辑对话框变为全屏，则&#x200B;**添加**&#x200B;按钮将被隐藏。 组件仍可以通过[从组件浏览器拖放到页面编辑器](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html#InsertingaComponent)中的Accordion组件上添加到Accordion组件。

### 属性选项卡{#properties-tab}

![折叠组件的编辑对话框的属性选项卡](/help/assets/accordion-edit-properties.png)

* **单个项目扩展**  — 选中此选项后，将强制一次展开单个折叠项目。展开一个项目后，所有其他项目都将折叠。
* **扩展项**  — 此选项定义加载页面时默认展开的项。
   * 选择&#x200B;**单个项目扩展**&#x200B;时，必须选择一个面板。 默认情况下，将选择第一个面板。
   * 如果未选择&#x200B;**单项扩展**，则此选项为多选选项，是可选的。
* **ID**  — 此选项允许控制HTML和数据层中组件的唯一 [标识符](/help/developing/data-layer/overview.md)。
   * 如果留空，系统会为您自动生成唯一ID，通过检查生成的页面可以找到它。
   * 如果指定了ID，则作者有责任确保它是唯一的。
   * 更改ID可能会影响CSS、JS和数据图层跟踪。

## 选择面板沿面{#select-panel-popover}

内容作者可以使用组件工具栏上的&#x200B;**选择面板**&#x200B;选项更改为其他面板进行编辑，并轻松重新排列折叠面板中面板的顺序。

![选择面板图标](/help/assets/select-panel-icon.png)

在组件工具栏中选择&#x200B;**选择面板**&#x200B;选项后，所配置的折叠面板将显示为下拉列表。

![选择面板快显](/help/assets/select-panel-popover.png)

* 列表按面板的指定排列排列，并反映在编号中。
* 首先显示面板的组件类型，然后以较浅的字体显示面板的说明。
* 点按或单击下拉菜单中的条目，将编辑器中的视图切换到该面板。
* 可使用拖动手柄就地重新排列面板。

## 设计对话框{#design-dialog}

通过设计对话框，模板作者可以定义可供使用折叠组件的内容作者使用的选项以及放置折叠组件时设置的默认值。

### 属性选项卡{#properties-tab-design}

![“设计”对话框属性选项卡](/help/assets/accordion-design-properties.png)

* **允许的标题** 元素 — 此多选下拉框定义作者允许选择的折叠项目标题HTML元素。
* **默认标题元素**  — 此下拉框定义默认的折叠项标题HTML元素。

### 允许的组件选项卡{#allowed-components-tab}

**允许的组件**&#x200B;选项卡用于定义内容作者可以将哪些组件作为项目添加到Accordion组件中的面板。

当[在模板编辑器中定义布局容器的策略和属性时，允许的组件选项卡的功能与同名选项卡的功能相同。](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html#editing-a-template-layout-template-author)

### 样式选项卡{#styles-tab}

Accordion组件支持AEM [Style System](/help/get-started/authoring.md#component-styling)。

## Adobe客户端数据层{#data-layer}

Accordion组件支持[Adobe客户端数据层。](/help/developing/data-layer/overview.md)
