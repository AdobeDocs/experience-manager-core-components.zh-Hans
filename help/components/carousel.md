---
title: 传送组件
description: 传送组件允许内容作者在旋转传送中显示内容。
translation-type: tm+mt
source-git-commit: d3ebcea5fa1523c1a986841cd3d1a64e16e85f6d
workflow-type: tm+mt
source-wordcount: '1125'
ht-degree: 1%

---


# 传送组件{#carousel-component}

核心组件传送组件允许内容作者在可导航的传送中显示内容。

## 使用 {#usage}

使用传送组件，内容作者可以在旋转的幻灯片轮盘中组织内容。

[编辑对话框](#edit-dialog)允许内容作者创建、命名和排序多张幻灯片，并允许延迟自动过渡。 使用[设计对话框](#design-dialog)，模板作者可以定义可添加到传送的组件、启用或禁用自动过渡以及自定义样式。

## 版本和兼容性{#version-and-compatibility}

传送组件的当前版本为v1,2018年10月随核心组件版本2.2.0引入了v1，本文档对此进行了说明。

下表详细列出了组件的所有受支持版本、与组件版本兼容的AEM版本，以及指向先前版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v1 | 兼容 | 兼容 | 兼容 |

有关核心组件版本和版本的详细信息，请参阅文档[核心组件版本](/help/versions.md)。

## 示例组件输出{#sample-component-output}

要体验传送组件，并查看其配置选项以及HTML和JSON输出的示例，请访问[组件库](https://adobe.com/go/aem_cmp_library_carousel)。

### 技术详细信息{#technical-details}

有关传送组件[的最新技术文档可在GitHub](https://adobe.com/go/aem_cmp_tech_carousel_v1)上找到。

有关开发核心组件的更多详细信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## 编辑对话框{#edit-dialog}

编辑对话框允许内容作者添加、重命名和重新排列幻灯片，并定义自动过渡设置。

### 项目选项卡{#items-tab}

![传送组件编辑对话框的“项目”选项卡](/help/assets/carousel-edit-items.png)

使用&#x200B;**添加**&#x200B;按钮打开组件选择器以选择要添加为选项卡的组件。 添加后，将向列表中添加一个条目，其中包含以下列：

* **图标**  — 选项卡的组件类型图标，可在列表中轻松识别。将鼠标悬停在上方，可以将完整组件名称作为工具提示查看。
* **说明**  — 用作选项卡文本的说明，默认使用为选项卡选择的组件的名称。
* **删除**  — 点按或单击，从选项卡组件中删除选项卡。
* **重新排序**  — 点按或单击并拖动以对选项卡进行排序。

>[!TIP]
>
>如果缩小了页面的视区，使编辑对话框变为全屏，则&#x200B;**添加**&#x200B;按钮将被隐藏。 组件仍可通过从组件浏览器中拖动并放到页面编辑器](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#inserting-a-component-from-the-components-browser)中的传送组件上来添加到传送组件。[

### 属性选项卡{#properties-tab}

![传送组件的编辑对话框的属性选项卡](/help/assets/carousel-edit-properties.png)

在&#x200B;**属性**&#x200B;选项卡上，内容作者可以将幻灯片设置为自动过渡。

* **自动过渡幻灯片**  — 活动后，组件将在指定延迟后自动前进到下一张幻灯片。
* **过渡延迟**  — 当选择“自动过渡”幻灯片时，此值用于定义过渡之间的延迟（以毫秒为单位）。
* **停用悬停时自动暂停**  — 选中“ **自动过渡** ”幻灯片后，每当光标悬停在轮盘上时，轮盘过渡将自动暂停。选择此选项可使过渡不会暂停。
* **ID**  — 此选项允许控制HTML和数据层中组件的唯一 [标识符](/help/developing/data-layer/overview.md)。
   * 如果留空，系统会为您自动生成唯一ID，通过检查生成的页面可以找到它。
   * 如果指定了ID，则作者有责任确保它是唯一的。
   * 更改ID可能会影响CSS、JS和数据图层跟踪。

>[!NOTE]
>
>在&#x200B;**编辑**&#x200B;模式下，幻灯片前进控件未启用。 使用&#x200B;[**预览** mode](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#preview-mode)或&#x200B;**[视图作为已发布内容的读者与传送交互。](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)**
>
>在&#x200B;**编辑**&#x200B;模式下，不启用自动前进功能。 使用&#x200B;**[视图作为已发布内容的读者查看自动前进功能。](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)**

### 辅助功能选项卡{#accessibility-tab}

![传送组件编辑对话框的“辅助功能”选项卡](/help/assets/carousel-edit-accessibility.png)

在&#x200B;**辅助功能**&#x200B;选项卡上，可以为组件的[ARIA辅助功能](https://www.w3.org/WAI/standards-guidelines/aria/)标签设置值。

* **Label**  — 组件的ARIA label属性值

## 选择面板{#select-panel}

内容作者可以使用组件工具栏上的&#x200B;**选择面板**&#x200B;选项更改为其他幻灯片进行编辑，并轻松重新排列幻灯片的顺序。

![选择面板图标](/help/assets/select-panel-icon.png)

在组件工具栏中选择&#x200B;**选择面板**&#x200B;选项后，将显示已配置的幻灯片作为下拉框。

* 列表按幻灯片的分配排列排列，并反映在编号中。
* 首先显示幻灯片的组件类型，然后以较浅的字体显示幻灯片的说明。

![选择面板](/help/assets/select-panel-popover.png)

* 点按或单击下拉菜单中的条目，将编辑器中的视图切换到该幻灯片。
* 可以使用拖动手柄就地重新排列幻灯片。

## 设计对话框{#design-dialog}

设计对话框允许模板作者定义哪些组件可以作为幻灯片添加到传送组件，以及定义自动过渡默认值以及哪些自定义样式可供内容作者使用。

### 属性选项卡{#properties-tab-1}

**属性**&#x200B;选项卡用于定义内容作者将传送组件添加到页面时幻灯片过渡的默认设置。

![传送组件的“设计”对话框](/help/assets/carousel-design.png)

* **自动过渡幻灯片**  — 定义当内容作者将传送组件添加到页面时，默认情况下是否启用将传送自动前进到下一张幻灯片的选项。
* **过渡延迟**  — 定义内容作者将传送组件添加到页面时幻灯片之间过渡延迟的默认值（以毫秒为单位）。
* **停用悬停时自动暂停**  — 定义在内容作者选择“自动过渡幻灯片”时，默认情况下是否启 **用禁** 用自动幻灯片暂停选项。

### 允许的组件选项卡{#allowed-components-tab}

**允许的组件**&#x200B;选项卡用于定义内容作者可以将哪些组件作为幻灯片添加到传送组件。

当[在模板编辑器中定义布局容器的策略和属性时，允许的组件选项卡的功能与同名选项卡的功能相同。](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)

### 样式选项卡{#styles-tab}

传送组件支持AEM [样式系统](/help/get-started/authoring.md#component-styling)。

## Adobe客户端数据层{#data-layer}

传送组件支持[Adobe客户端数据层。](/help/developing/data-layer/overview.md)
