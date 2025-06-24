---
title: 轮盘组件
description: 使用轮盘组件，内容作者可在旋转轮盘中展示内容。
role: Architect, Developer, Admin, User
exl-id: 3331214c-a05c-47e1-b54c-fbfd1045bd60
source-git-commit: dd30def59a8f037864da875ef4c831b11f766e57
workflow-type: tm+mt
source-wordcount: '1317'
ht-degree: 100%

---


# 轮盘组件{#carousel-component}

使用核心组件轮盘组件，内容作者可在可导航的轮盘中展示内容。

{{traditional-aem}}

## 用途 {#usage}

使用轮盘组件，内容作者可以将内容排列在旋转的幻灯片轮盘中。

内容作者可以使用[“编辑”对话框](#edit-dialog)创建、命名和排序多个幻灯片，以及启用带有延迟的自动过渡。使用[“设计”对话框](#design-dialog)，模板作者可以定义哪些组件可以添加到轮盘中，启用或禁用自动过渡，以及自定义样式。

## 版本和兼容性 {#version-and-compatibility}

轮盘组件的当前版本是 V1，此版本随 2018 年 10 月的核心组件发行版本 2.2.0 的发布引入，具体说明见本文。

下表详细说明了该组件的所有受支持版本、与该组件的版本兼容的 AEM 版本以及指向早期版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|--- |--- |--- |---|---|
| v1 | 与<br>[版本 2.17.4](/help/versions.md) 和更低版本兼容 | 兼容 | 兼容 | 兼容 |

有关核心组件版本的更多信息，请参阅文档[核心组件版本](/help/versions.md)。

## 示例组件输出 {#sample-component-output}

要体验轮盘组件并查看其配置选项示例以及 HTML 和 JSON 输出，请访问[组件库](https://adobe.com/go/aem_cmp_library_carousel_cn)。

### 技术详细信息 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_carousel_v1_cn)有关轮盘组件的最新技术文档。

在[核心组件开发人员文档](/help/developing/overview.md)中可找到有关开发核心组件的其他详细信息。

## 深度链接到面板 {#deep-linking}

轮盘组件、[选项卡组件](tabs.md)和[折叠面板组件](accordion.md)支持直接链接到组件中的面板。

要执行此操作：

1. 在页面编辑器中使用&#x200B;**[以发布的形式查看](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)**&#x200B;选项查看带有组件的页面。
1. 检查页面的内容并确定面板的 ID。
   * 例如 `id="carousel-bfe4fa6647-item-47f1a7ca67-tabpanel"`
1. ID 成为您可以使用哈希 (`#`) 附加到 URL 的锚点。
   * 例如 `https://wknd.site/content/wknd/language-masters/en/magazine/western-australia.html#carousel-bfe4fa6647-item-47f1a7ca67-tabpanel`

导航到将面板 ID 作为锚点的 URL，浏览器将直接滚动到特定组件并显示指定的面板。如果将面板配置为默认不显示，则将自动滚动它。

## 轮播和响应式设计 {#responsive-design}

所有核心组件均设计为完全响应式，确保跨设备的无缝体验。

一些高级组件（例如轮播组件）可能需要在实施项目的背景下进行具体考虑，以便在所有条件下都保持响应能力。请参阅文档[核心组件的响应式设计](/help/responsive.md)，了解更多信息。

## “编辑”对话框 {#edit-dialog}

内容作者可以使用“编辑”对话框添加、重命名和重新排列幻灯片，以及定义自动过渡设置。

### “项”选项卡 {#items-tab}

![轮盘组件“编辑”对话框的“项”选项卡](/help/assets/carousel-edit-items.png)

使用&#x200B;**“添加”**&#x200B;按钮可打开组件选择器，选择要作为选项卡添加的组件。在添加之后，一个条目将添加到列表中，包含以下列：

* **图标** - 选项卡的组件类型的图标，用于方便在列表中识别。将鼠标悬停在上面时将显示完整的组件名称作为工具提示。
* **描述** - 用作选项卡的文本的描述，默认情况下是为选项卡选择的组件的名称。
* **删除** - 点击或单击可从选项卡组件中删除选项卡。
* **重新排序** - 点击或单击并拖动以重新排序选项卡。

>[!TIP]
>
>如果减小页面视区以便全屏显示“编辑”对话框，则将隐藏&#x200B;**“添加”**&#x200B;按钮。组件仍可以通过[从组件浏览器拖动并放置在页面编辑器的轮盘组件上](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#inserting-a-component-from-the-components-browser)来添加到轮盘组件中。

### “属性”选项卡 {#properties-tab}

![轮盘组件“编辑”对话框的“属性”选项卡](/help/assets/carousel-edit-properties.png)

在&#x200B;**属性**&#x200B;选项卡上，内容作者可以设置幻灯片自动过渡。

* **活动项** - 内容作者可定义在加载页面时哪个选项卡活动。
* **自动过渡幻灯片** - 在激活时，组件将在指定的延迟之后进入下一张幻灯片。
* **过渡延迟** - 选择了自动过渡幻灯片时，此值用于定义过渡之间的延迟（以毫秒为单位）。
* **禁止在光标悬停时自动暂停** - 选择了&#x200B;**自动过渡幻灯片**&#x200B;时，只要光标悬停在轮盘上时，轮盘过渡将自动暂停。选择此选项可不暂停过渡。
* **ID** - 利用此选项，可以控制 HTML 和[ Data Layer ](/help/developing/data-layer/overview.md)中的组件的唯一标识符。
   * 如果留空，系统会自动为您生成一个唯一 ID，可以通过检查结果页面找到该 ID。
   * 如果指定一个 ID，作者有责任确保它是唯一的。
   * 更改此 ID 会对 CSS、JS 和 Data Layer 跟踪产生影响。

>[!NOTE]
>
>在&#x200B;**“编辑”**&#x200B;模式下不会启用幻灯片前进控件。使用&#x200B;[**预览**&#x200B;模式](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#preview-mode)或&#x200B;**[以发布的形式查看](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)**&#x200B;选项，可以像已发布内容的读者那样与轮盘交互。
>
>在&#x200B;**“编辑”**&#x200B;模式下不会启用自动前进功能。使用&#x200B;**[以发布的形式查看](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)**&#x200B;选项，可以像已发布内容的读者那样查看自动前进功能。

### “辅助功能”选项卡 {#accessibility-tab}

![轮盘组件“编辑”对话框的“辅助功能”选项卡](/help/assets/carousel-edit-accessibility.png)

在&#x200B;**辅助功能**&#x200B;选项卡上，可以为组件的 [ARIA 辅助功能](https://www.w3.org/WAI/standards-guidelines/aria/)标签设置值。

* **标签** - 轮盘的 aria-label 属性的值，它描述轮盘的内容
* **上一个** - 轮盘导航的上一个按钮标签的 aria-label 属性的值
* **下一个** - 轮盘导航的下一个按钮标签的 aria-label 属性的值
* **播放** - 轮盘导航的播放按钮标签的 aria-label 属性的值
* **暂停** - 轮盘导航的暂停按钮标签的 aria-label 属性的值
* **选项卡列表** - 轮盘导航的项目列表标签的 aria-label 属性的值
* **将项目的 aria 标签设置为其标题** - 如果选中此选项，则自动将轮盘项目标题设置为其 aria-label 描述。

## 选择面板 {#select-panel}

内容作者可以使用组件工具栏上的&#x200B;**“选择面板”**&#x200B;选项，更改到不同的幻灯片进行编辑，以及轻松地重新排列幻灯片的顺序。

![选择面板图标](/help/assets/select-panel-icon.png)

在组件工具栏中选择了&#x200B;**“选择面板”**&#x200B;选项之后，配置的幻灯片将显示为下拉列表。

* 下拉列表按照向幻灯片分配的顺序排列，并体现在编号中。
* 首先显示幻灯片的组件类型，然后是较细字体的幻灯片描述。

![选择面板](/help/assets/select-panel-popover.png)

* 在下拉列表中点击或单击某个条目，会在编辑器中将视图切换到该幻灯片。
* 可以使用拖动手柄就地对幻灯片排序。

## “设计”对话框 {#design-dialog}

使用“设计”对话框，模板作者可以定义哪些组件可以作为幻灯片添加到轮盘组件中，以及定义自动过渡默认值和可供内容作者使用的自定义样式。

### “属性”选项卡 {#properties-tab-1}

在内容作者添加轮盘组件到页面时，可以使用&#x200B;**属性**&#x200B;选项卡定义幻灯片过渡的默认设置。

![轮盘组件“设计”对话框](/help/assets/carousel-design.png)

* **自动过渡幻灯片** - 定义默认情况下，当内容作者添加轮盘组件到页面时，默认选项是否自动将轮盘前进到下一张幻灯片。
* **前置控制元素** - 选中后，控制元素将被放在轮盘项目的前面以提高可访问性。

### “允许的组件”选项卡 {#allowed-components-tab}

**“允许的组件”**&#x200B;选项卡用于定义哪些组件可以由内容作者作为幻灯片添加到轮盘组件。

“允许的组件”选项卡的功能，与[在模板编辑器的布局容器中定义策略和属性时](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html)的同名选项卡的功能相同。

### “样式”选项卡 {#styles-tab}

轮盘组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。

## Adobe Client Data Layer {#data-layer}

轮盘组件支持 [Adobe Client Data Layer](/help/developing/data-layer/overview.md)。
