---
title: 传送组件
description: 传送组件允许内容作者在旋转传送中显示内容。
translation-type: tm+mt
source-git-commit: c186e9ec3944d785ab0376769cf7f2307049a809
workflow-type: tm+mt
source-wordcount: '1112'
ht-degree: 1%

---


# 传送组件{#carousel-component}

核心组件传送组件允许内容作者在可导航的传送中显示内容。

## 使用 {#usage}

使用传送组件，内容作者可以在旋转的幻灯片传送中组织内容。

编辑 [对话框](#edit-dialog) ，内容作者可以创建、命名和排序多张幻灯片，并可以延迟地启用自动过渡。 使用设 [计对话框](#design-dialog)，模板作者可以定义可添加到传送的组件、启用或禁用自动过渡以及自定义样式。

## 版本和兼容性 {#version-and-compatibility}

传送组件的当前版本为v1,2018年10月随核心组件的2.2.0版引入v1，该版本在本文档中进行了说明。

下表详细列出了组件的所有受支持版本、与组件版本兼容的AEM版本以及指向先前版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM 云服务 |
|--- |--- |--- |---|
| v1 | 兼容 | 兼容 | 兼容 |

有关核心组件版本和版本的详细信息，请参阅文档 [核心组件版本](/help/versions.md)。

## 示例组件输出 {#sample-component-output}

要体验传送组件，并查看其配置选项以及HTML和JSON输出的示例，请访问组 [件库](https://adobe.com/go/aem_cmp_library_carousel)。

### 技术详细信息 {#technical-details}

有关传送组件的最新技术文 [档可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_carousel_v1)。

有关开发核心组件的更多详细信息，请参阅核 [心组件开发人员文档](/help/developing/overview.md)。

## Edit Dialog {#edit-dialog}

编辑对话框允许内容作者添加、重命名和重新排列幻灯片，以及定义自动过渡设置。

### 项目选项卡 {#items-tab}

![传送组件编辑对话框的“项目”选项卡](/help/assets/carousel-edit-items.png)

使用添 **加按钮** ，打开组件选择器以选择要添加为选项卡的组件。 添加后，将向列表添加一个条目，该条目包含以下列：

* **图标** -选项卡的组件类型图标，以便在列表中进行标识。 将鼠标悬停在上方，可将完整组件名称作为工具提示查看。
* **说明** -用作选项卡文本的说明，默认使用为选项卡选择的组件的名称。
* **删除** -点按或单击，从选项卡组件中删除选项卡。
* **重新排序** -点按或单击并拖动以对选项卡进行排序。

>[!TIP]
>
>如果缩小了页面的视区，使编辑对话框变为全屏，则“添 **加** ”按钮将被隐藏。 通过从组件浏览器拖放并放 [到页面编辑器中的传送组件，仍可将组件添加到传送组件](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#inserting-a-component-from-the-components-browser)。

### 属性选项卡 {#properties-tab}

![传送组件的编辑对话框的属性选项卡](/help/assets/carousel-edit-properties.png)

在“属 **性** ”选项卡上，内容作者可以将幻灯片设置为自动过渡。

* **自动过渡幻灯片** -活动后，组件将在指定延迟后自动前进到下一张幻灯片。
* **过渡延迟** -选中“自动过渡”幻灯片时，此值用于定义过渡之间的延迟（以毫秒为单位）。
* **停用悬停时自动暂停** -当选 **择“自动过渡** ”幻灯片时，每当光标悬停在轮盘上时，轮盘过渡将自动暂停。 选择此选项可使过渡不会暂停。
* **ID** —— 此选项允许控制HTML和数据层中组件的唯一标 [识符](/help/developing/data-layer/overview.md)。
   * 如果留空，则会自动为您生成唯一ID，并可通过检查生成的页面找到该ID。
   * 如果指定了ID，则作者有责任确保它是唯一的。
   * 更改ID可能会影响CSS、JS和数据层跟踪。

>[!NOTE]
>
>在“编辑”模式下，幻灯片高级控 **件未** 启用。 使用 [**预览&#x200B;**模式或](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#preview-mode)“视图为已发布&#x200B;**[](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)**”选项，以已发布内容的读者身份与传送进行交互。
>
>在“编辑”模式下，自动前进功能 **不启** 用。 使 **[用“视图为已发布](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)**”选项，以已发布内容的读者身份查看自动前进功能。

### “辅助功能”选项卡 {#accessibility-tab}

![传送组件编辑对话框的“辅助功能”选项卡](/help/assets/carousel-edit-accessibility.png)

在“辅 **助功能** ”选项卡上，可以为组 [件的ARIA辅助功](https://www.w3.org/WAI/standards-guidelines/aria/) 能标签设置值。

* **标签** -组件的ARIA标签属性的值

## Select Panel {#select-panel}

内容作者可以使用组 **件工具栏上的** “选择面板”选项更改为其他幻灯片进行编辑，并轻松重新排列幻灯片的顺序。

![选择面板图标](/help/assets/select-panel-icon.png)

在组件工 **具栏中** 选择“选择面板”选项后，将显示已配置的幻灯片作为下拉列表。

* 列表按幻灯片的分配排列排列，并反映在编号中。
* 首先显示幻灯片的组件类型，然后以较淡的字体显示幻灯片的说明。

![选择面板](/help/assets/select-panel-popover.png)

* 点按或单击下拉框中的条目，将编辑器中的视图切换到该幻灯片。
* 可以使用拖动手柄就地重新排列幻灯片。

## 设计对话框 {#design-dialog}

设计对话框允许模板作者定义哪些组件可以作为幻灯片添加到旋转组件，以及定义自动过渡默认值以及哪些自定义样式可供内容作者使用。

### 属性选项卡 {#properties-tab-1}

当内 **容作者将传送组件** 添加到页面时，“属性”选项卡用于定义幻灯片过渡的默认设置。

![传送组件的“设计”对话框](/help/assets/carousel-design.png)

* **自动过渡幻灯片** -定义当内容作者将旋转组件添加到页面时，默认情况下是否启用将旋转自动前进到下一张幻灯片的选项。
* **过渡延迟** -定义内容作者将传送组件添加到页面时幻灯片之间过渡延迟的默认值（以毫秒为单位）。
* **停用悬停时自动暂停** -定义在内容作者选择“自动过渡幻灯片 **”时，默认情况下是否启用禁用自动幻灯片暂停的选** 项。

### Allowed Components Tab {#allowed-components-tab}

允许 **的组件** 选项卡用于定义内容作者可以将哪些组件作为幻灯片添加到传送组件。

当在模板编辑器中定义布局容器的策略和属性时，允许的组 [件选项卡的功能与同名选项卡的功能相同。](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)

### 样式选项卡 {#styles-tab}

传送组件支持AEM样 [式系统](/help/get-started/authoring.md#component-styling)。
