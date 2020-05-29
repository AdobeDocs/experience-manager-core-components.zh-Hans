---
title: 折叠组件
description: 核心组件折叠面板组件允许创建在页面上折叠面板中排列的面板集合。
translation-type: tm+mt
source-git-commit: c186e9ec3944d785ab0376769cf7f2307049a809
workflow-type: tm+mt
source-wordcount: '1051'
ht-degree: 1%

---


# 折叠组件{#accordion-component}

核心组件折叠面板组件允许创建在页面上折叠面板中排列的面板集合。

## 使用 {#usage}

核心组件折叠面板组件允许创建组件集合，这些组件以面板的形式组成，并以折叠面板的形式排列在页面上(与选项卡组 [件类似](tabs.md))，但允许展开和折叠面板。

* 可以在“配置”对话框中定义accordion [的属性](#configure-dialog)。
* 可在配置对话框和选择面板弹出窗口中定义相应面板 [的顺序](#select-panel-popover)。
* 将折叠组件添加到页面时的默认值可以在设计对话框中 [定义](#design-dialog)。

## 到面板的深层链接 {#deep-linking}

折叠面板和 [选项卡组件](tabs.md) ，支持直接链接到组件中的面板。

要执行此操作：

1. 使用页面编辑器中的“视图 **[为已发布”选项](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/authoring/editing-content.html#view-as-published)**，将页面与组件视图。
1. 检查页面内容并标识面板的ID。
   * For example `id="accordion-86196c94d3-item-ca319dbb0b"`
1. 该ID成为可使用散列()附加到URL的锚`#`点。
   * For example `https://wknd.site/content/wknd/language-masters/en/magazine/western-australia.html#accordion-86196c94d3-item-ca319dbb0b`

导航到面板ID为锚点的URL，浏览器将直接滚动到特定组件并显示指定的面板。 如果面板配置为默认不展开，则会自动展开面板。

## 版本和兼容性 {#version-and-compatibility}

Accordion组件的当前版本为v1,2019年6月随核心组件的2.5.0版引入了v1，本文档对此进行了说明。

下表详细列出了组件的所有受支持版本、与组件版本兼容的AEM版本以及指向先前版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM 云服务 |
|--- |--- |---|---|
| v1 | 兼容 | 兼容 | 兼容 |

有关核心组件版本和版本的详细信息，请参阅文档 [核心组件版本](/help/versions.md)。

## 示例组件输出 {#sample-component-output}

要体验Accordion组件并查看其配置选项以及HTML和JSON输出的示例，请访问组 [件库](https://adobe.com/go/aem_cmp_library_accordion)。

## 技术详细信息 {#technical-details}

有关Accordion组件的最新技术文 [档可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_accordion_v1)。

有关开发核心组件的更多详细信息，请参阅核 [心组件开发人员文档](/help/developing/overview.md)。

## 配置对话框 {#configure-dialog}

配置对话框允许内容作者定义折叠项、其面板，以及它的行为和显示方式，以便访客页面。

### 项目选项卡 {#items-tab}

![折叠组件编辑对话框的“项目”选项卡](/help/assets/accordion-edit-items.png)

使用添 **加按钮** ，打开组件选择器以选择要添加为面板的组件。 添加后，将向列表添加一个条目，该条目包含以下列：

* **图标** -面板组件类型的图标，便于在列表中识别。 将鼠标悬停在上方，可将完整组件名称作为工具提示查看。
* **说明** -用作面板文本的说明，默认使用为面板选择的组件的名称。
* **删除** -点按或单击，从折叠组件中删除面板。
* **重新排列** -点按或单击并拖动以重新排列面板的顺序。

>[!TIP]
>
>如果缩小了页面的视区，使编辑对话框变为全屏，则“添 **加** ”按钮将被隐藏。 通过从组件浏览器拖放并放 [到页面编辑器中的Accordion组件，仍可将组件添加到Accordion组件](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html#InsertingaComponent)。

### 属性选项卡 {#properties-tab}

![折叠组件的编辑对话框的属性选项卡](/help/assets/accordion-edit-properties.png)

* **单个项目扩展** -选中此选项后，将强制一次扩展单个折叠项目。 展开一个项目后，所有其他项目都会折叠。
* **扩展项** -此选项定义载入页面时默认展开的项。
   * 选 **择“单个项** ”展开时，必须选择一个面板。 默认情况下，将选择第一个面板。
   * 如果未 **选择** “单个项目扩展”，则此选项为多选项，且是可选的。
* **ID** —— 此选项允许控制HTML和数据层中组件的唯一标 [识符](/help/developing/data-layer/overview.md)。
   * 如果留空，则会自动为您生成唯一ID，并可通过检查生成的页面找到该ID。
   * 如果指定了ID，则作者有责任确保它是唯一的。
   * 更改ID可能会影响CSS、JS和数据层跟踪。

## 选择面板弹出窗口 {#select-panel-popover}

内容作者可以使用组 **件工具栏上的** “选择面板”选项更改为其他面板进行编辑，还可以轻松地重新排列折叠面板中面板的顺序。

![选择面板图标](/help/assets/select-panel-icon.png)

在组件工 **具栏中** 选择“选择面板”选项后，已配置的折叠面板将显示为下拉列表。

![选择面板弹出窗口](/help/assets/select-panel-popover.png)

* 列表按面板的指定排列排列，并反映在编号中。
* 首先显示面板的组件类型，然后以较淡的字体显示面板的描述。
* 点按或单击下拉菜单中的某个条目，将编辑器中的视图切换到该面板。
* 通过使用拖动手柄，可以就地重新排列面板。

## 设计对话框 {#design-dialog}

设计对话框允许模板作者定义内容作者可以使用折叠组件的选项以及放置折叠组件时设置的默认值。

### 属性选项卡 {#properties-tab-design}

![“设计”对话框属性选项卡](/help/assets/accordion-design-properties.png)

* **允许的标题** 元素——此多选下拉框定义作者允许选择的折叠项目标题HTML元素。
* **默认标题元素** -此下拉框定义默认的折叠项目标题HTML元素。

### Allowed Components Tab {#allowed-components-tab}

允许 **的组件** 选项卡用于定义内容作者可以将哪些组件作为项目添加到折叠组件的面板。

当在模板编辑器中定义布局容器的策略和属性时，允许的组 [件选项卡的功能与同名选项卡的功能相同。](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/siteandpage/templates.html)

### 样式选项卡 {#styles-tab}

Accordion组件支持AEM样 [式系统](/help/get-started/authoring.md#component-styling)。
