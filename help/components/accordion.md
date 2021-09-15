---
title: 折叠组件
description: 使用核心组件折叠组件，可在页面上创建一系列以折叠形式排列的面板。
role: Architect, Developer, Admin, User
exl-id: 1deb570a-3d8d-409e-805f-8460c49cf9bb
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: ht
source-wordcount: '1067'
ht-degree: 100%

---

# 折叠组件{#accordion-component}

使用核心组件折叠组件，可在页面上创建一系列以折叠形式排列的面板。

## 用途 {#usage}

使用核心组件折叠组件，可以创建一系列由面板组成的组件，并在页面上以折叠形式排列，类似于[选项卡组件](tabs.md)，但允许展开和折叠面板。

* 折叠的属性可在[“配置”对话框](#configure-dialog)中定义。
* 折叠面板的顺序可以在“配置”对话框以及[“选择面板”弹出框](#select-panel-popover)中定义。
* 将折叠组件添加到页面时的默认值可以在[“设计”对话框](#design-dialog)中定义。

## 深度链接到面板 {#deep-linking}

折叠组件和[选项卡组件](tabs.md)支持直接链接到组件中的面板。

要执行此操作：

1. 在页面编辑器中使用&#x200B;**[以发布的形式查看](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)**&#x200B;选项查看带有组件的页面。
1. 检查页面的内容并确定面板的 ID。
   * 例如 `id="accordion-86196c94d3-item-ca319dbb0b"`
1. ID 成为您可以使用哈希 (`#`) 附加到 URL 的锚点。
   * 例如 `https://wknd.site/content/wknd/language-masters/en/magazine/western-australia.html#accordion-86196c94d3-item-ca319dbb0b`

导航到将面板 ID 作为锚点的 URL，浏览器将直接滚动到特定组件并显示指定的面板。如果面板配置为默认情况下不展开，则会自动展开。

## 版本和兼容性 {#version-and-compatibility}

折叠组件的当前版本是 V1，此版本随 2019 年 6 月的核心组件发行版本 2.5.0 的发布引入，具体说明见本文。

下表详细说明了该组件的所有受支持版本、与该组件的版本兼容的 AEM 版本以及指向早期版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | 兼容 | 兼容 | 兼容 |

有关核心组件版本的更多信息，请参阅文档[核心组件版本](/help/versions.md)。

## 示例组件输出 {#sample-component-output}

要体验折叠组件并查看其配置选项示例以及 HTML 和 JSON 输出，请访问[组件库](https://adobe.com/go/aem_cmp_library_accordion_cn)。

## 技术详细信息 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_accordion_v1_cn)有关折叠组件的最新技术文档。

在[核心组件开发人员文档](/help/developing/overview.md)中可找到有关开发核心组件的其他详细信息。

## “配置”对话框 {#configure-dialog}

利用“配置”对话框，内容作者可以定义折叠项，以及对于页面的访客它会如何表现和显示。

### “项”选项卡 {#items-tab}

![折叠组件“编辑”对话框的“项”选项卡](/help/assets/accordion-edit-items.png)

使用&#x200B;**添加**&#x200B;按钮可打开组件选择器，来选择要作为面板添加的组件。在添加之后，一个条目将添加到列表中，包含以下列：

* **图标** - 面板的组件类型的图标，用于方便在列表中识别。将鼠标悬停在上面时将显示完整的组件名称作为工具提示。
* **描述** - 用作面板的文本的描述，默认情况下是为面板选择的组件的名称。
* **删除** - 点击或单击可从折叠组件中删除面板。
* **重新排列** - 点击或单击并拖动以重新排列面板。

>[!TIP]
>
>如果减小页面视区以便全屏显示“编辑”对话框，则将隐藏&#x200B;**添加**&#x200B;按钮。组件仍可以通过[从组件浏览器拖动并放置在页面编辑器的折叠组件上](https://helpx.adobe.com/cn/experience-manager/6-5/sites/authoring/using/editing-content.html#InsertingaComponent)来添加到折叠组件中。

### “属性”选项卡 {#properties-tab}

![折叠组件“编辑”对话框的“属性”选项卡](/help/assets/accordion-edit-properties.png)

* **单项展开** - 在选中时，此选项强制一次展开单个折叠项。展开一项将折叠所有其他项。
* **展开项** - 此选项定义加载页面时默认展开的项。
   * 在选中了&#x200B;**单项展开**&#x200B;时，必须选择一个面板。不过默认情况下选择第一个面板。
   * 未选中&#x200B;**单项展开**&#x200B;时，此选项为多选并且是可选的。
* **ID** - 利用此选项，可以控制 HTML 和[ Data Layer ](/help/developing/data-layer/overview.md)中的组件的唯一标识符。
   * 如果留空，系统会自动为您生成一个唯一 ID，可以通过检查结果页面找到该 ID。
   * 如果指定一个 ID，作者有责任确保它是唯一的。
   * 更改此 ID 会对 CSS、JS 和 Data Layer 跟踪产生影响。

## “选择面板”弹出框 {#select-panel-popover}

内容作者可以使用组件工具栏上的&#x200B;**选择面板**&#x200B;选项，更改到不同的面板进行编辑，以及轻松地重新排列折叠中的面板。

![选择面板图标](/help/assets/select-panel-icon.png)

在组件工具栏中选择了&#x200B;**选择面板**&#x200B;选项之后，配置的折叠面板将显示为下拉列表。

![“选择面板”弹出框](/help/assets/select-panel-popover.png)

* 下拉列表按照向面板分配的顺序排列，并体现在编号中。
* 首先显示面板的组件类型，然后是较细字体的面板描述。
* 在下拉列表中点击或单击某个条目，会在编辑器中将视图切换到该面板。
* 可以使用拖动手柄就地重新排列面板。

## “设计”对话框 {#design-dialog}

使用“设计”对话框，模板作者可以定义哪些选项可供使用折叠组件的内容作者使用，以及在放置折叠组件时的默认设置。

### “属性”选项卡 {#properties-tab-design}

![“设计”对话框“属性”选项卡](/help/assets/accordion-design-properties.png)

* **允许的标题元素** - 此多选下拉菜单定义允许作者选择的折叠项标题 HTML 元素。
* **默认标题元素** - 此下拉菜单定义默认折叠项标题 HTML 元素。

### “允许的组件”选项卡 {#allowed-components-tab}

**允许的组件**&#x200B;选项卡用于定义哪些项可以由内容作者作为面板添加到折叠组件。

“允许的组件”选项卡的功能，与[在模板编辑器的布局容器中定义策略和属性时](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html#editing-a-template-layout-template-author)的同名选项卡的功能相同。

### “样式”选项卡 {#styles-tab}

折叠组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。

## Adobe Client Data Layer {#data-layer}

折叠组件支持 [Adobe Client Data Layer](/help/developing/data-layer/overview.md)。
