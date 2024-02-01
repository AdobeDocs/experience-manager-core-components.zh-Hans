---
title: 选项卡组件
description: 利用选项卡组件，可以创建多个选项卡来在页面上排列内容。
role: Architect, Developer, Admin, User
exl-id: 0031c5f3-447c-4932-898f-2f453801e492
source-git-commit: d39fe0084522f67664203a026340b23d325c1883
workflow-type: tm+mt
source-wordcount: '1034'
ht-degree: 93%

---


# 选项卡组件 {#tabs-component}

利用核心组件选项卡组件，可以在多个选项卡上整理内容。

## 用途 {#usage}

利用选项卡组件，内容作者可以在多个选项卡中整理页面内容。

内容作者可以使用[“编辑”对话框](#edit-dialog)定义多个选项卡并设置活动选项卡。利用[“设计”对话框](#design-dialog)，模板作者能够定义可向选项卡添加的组件并自定义样式。

>[!TIP]
>
>支持嵌套选项卡组件（选项卡中的选项卡）。
>
>可以使用[内容树](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html#content-tree)定位/选择简单（非嵌套）选项卡组件，但无法对嵌套选项卡执行此操作。

## 版本和兼容性 {#version-and-compatibility}

选项卡组件的当前版本是 v1，此版本随 2018 年 10 月的核心组件 2.2.0 版的发布引入，具体说明见本文。

下表详细说明了该组件的所有受支持版本、与该组件的版本兼容的 AEM 版本以及指向早期版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v1 | 兼容<br>[发行版本2.17.4](/help/versions.md) 和先前的 | 兼容 | 兼容 |

有关核心组件版本的更多信息，请参阅文档[核心组件版本](/help/versions.md)。

## 示例组件输出 {#sample-component-output}

要体验选项卡组件并查看其配置选项示例以及 HTML 和 JSON 输出，请访问[组件库](https://adobe.com/go/aem_cmp_library_tabs_cn)。

### 技术详细信息 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_tabs_v1_cn)有关选项卡组件的最新技术文档。

在[核心组件开发人员文档](/help/developing/overview.md)中可找到有关开发核心组件的其他详细信息。

## 深度链接到面板 {#deep-linking}

选项卡组件、[轮盘组件](carousel.md)和[折叠面板组件](accordion.md)支持直接链接到组件中的面板。

要执行此操作：

1. 在页面编辑器中使用&#x200B;**[以发布的形式查看](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)**&#x200B;选项查看带有组件的页面。
1. 检查页面的内容并确定面板的 ID。
   * 例如 `id="accordion-86196c94d3-item-ca319dbb0b"`
1. ID 成为您可以使用哈希 (`#`) 附加到 URL 的锚点。
   * 例如 `https://wknd.site/content/wknd/language-masters/en/magazine/western-australia.html#accordion-86196c94d3-item-ca319dbb0b`

导航到将面板 ID 作为锚点的 URL，浏览器将直接滚动到特定组件并显示指定的面板。如果面板配置为默认情况下不展开，则会自动展开。

## 选项卡和响应式设计 {#responsive-design}

所有核心组件均设计用于完全响应，确保跨设备无缝体验。

为了保持在所有条件下的响应性，某些高级组件（如选项卡组件）可能需要在实施项目的上下文中进行特定考虑。 请参阅文档 [核心组件的响应式设计](/help/responsive.md) 以了解更多信息。

## “编辑”对话框 {#edit-dialog}

内容作者可以使用“编辑”对话框创建、重命名、重新排列选项卡以及定义活动选项卡。

### “项”选项卡 {#items-tab}

![选项卡组件的“编辑”对话框中的“项”选项卡](/help/assets/tabs-edit-items.png)

使用&#x200B;**“添加”**&#x200B;按钮可打开组件选择器，选择要作为选项卡添加的组件。在添加之后，一个条目将添加到列表中，包含以下列：

* **图标** - 选项卡的组件类型的图标，用于方便在列表中识别。将鼠标悬停在上面时将显示完整的组件名称作为工具提示。
* **描述** - 用作选项卡的文本的描述，默认情况下是为选项卡选择的组件的名称。
* **删除** - 点击或单击可从选项卡组件中删除选项卡。
* **重新排列** - 点击或单击并拖动以重新排列选项卡。

>[!TIP]
>
>如果减小页面视区以便全屏显示“编辑”对话框，则将隐藏&#x200B;**“添加”**&#x200B;按钮。仍可通过将组件[从组件浏览器中拖动并放置到页面编辑器的选项卡组件上](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#inserting-a-component)来将其添加到选项卡组件中。

### “属性”选项卡 {#properties-tab}

![选项卡组件的“编辑”对话框中的“属性”选项卡](/help/assets/tabs-edit-properties.png)

* **活动项** - 内容作者可定义在加载页面时哪个选项卡活动。
   * 对于&#x200B;**默认**&#x200B;选项，将选择第一个选项卡。
* **ID** - 利用此选项，可以控制 HTML 和 [Data Layer](/help/developing/data-layer/overview.md) 中的组件的唯一标识符。
   * 如果留空，系统会自动为您生成一个唯一 ID，可以通过检查结果页面找到该 ID。
   * 如果指定一个 ID，作者有责任确保它是唯一的。
   * 更改此 ID 会对 CSS、JS 和 Data Layer 跟踪产生影响。

### “辅助功能”选项卡 {#accessibility-tab}

![选项卡组件的“编辑”对话框中的“辅助功能”选项卡](/help/assets/tabs-edit-accessibility.png)

在&#x200B;**辅助功能**&#x200B;选项卡上，可以为组件的 [ARIA 辅助功能](https://www.w3.org/WAI/standards-guidelines/aria/)标签设置值。

* **标签** - 组件的 ARIA 标签属性的值

## 选择面板 {#select-panel}

内容作者可以使用组件工具栏上的&#x200B;**“选择面板”**&#x200B;选项，更改到不同的面板进行编辑，以及轻松地重新排列选项卡。

![选择面板图标](/help/assets/select-panel-icon.png)

在组件工具栏中选择了&#x200B;**“选择面板”**&#x200B;选项之后，配置的选项卡将显示为下拉列表。

* 此列表按指定的选项卡排列方式进行排序并反映在编号中。
* 首先显示选项卡的组件类型，随后显示采用较细字体的选项卡描述。

![“选择面板”弹出框](/help/assets/select-panel-popover.png)

* 在下拉列表中点击或单击某个条目，会在编辑器中将视图切换到该选项卡。
* 可以使用拖动手柄就地重新排列选项卡。

>[!NOTE]
>
>在&#x200B;**编辑**&#x200B;模式中，作者无法选择选项卡。使用&#x200B;**[预览](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#preview-mode)**&#x200B;模式或&#x200B;**[以发布的形式查看](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)**&#x200B;选项，可以像已发布内容的读者那样与选项卡进行交互。

## “设计”对话框 {#design-dialog}

使用“设计”对话框，模板作者可以定义哪些组件可以作为项添加到选项卡组件中，并定义哪些自定义样式可供内容作者使用。

### “允许的组件”选项卡 {#allowed-components-tab}

**“允许的组件”**&#x200B;选项卡用于定义哪些组件可由内容作者作为项添加到选项卡组件。

“允许的组件”选项卡的功能与[在模板编辑器的布局容器中定义策略和属性时](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)的同名选项卡的功能相同。

### “样式”选项卡 {#styles-tab}

选项卡组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。

## Adobe Client Data Layer {#data-layer}

选项卡组件支持 [Adobe Client Data Layer](/help/developing/data-layer/overview.md)。
