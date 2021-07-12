---
title: 轮播组件
description: 轮播组件允许内容作者以旋转轮播显示内容。
role: Architect, Developer, Admin, User
exl-id: 3331214c-a05c-47e1-b54c-fbfd1045bd60
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '1125'
ht-degree: 1%

---

# 轮播组件{#carousel-component}

核心组件轮播组件允许内容作者在可导航的轮播中显示内容。

## 使用 {#usage}

内容作者使用轮播组件以旋转的幻灯片轮播方式组织内容。

[编辑对话框](#edit-dialog)允许内容作者创建、命名和排序多张幻灯片，并允许延迟自动过渡。 使用[设计对话框](#design-dialog)，模板作者可以定义可以添加到轮播的组件、启用或禁用自动过渡以及自定义样式。

## 版本和兼容性 {#version-and-compatibility}

传送组件的当前版本为v1，该版本于2018年10月随核心组件2.2.0版引入，在本文档中进行了描述。

下表详细列出了组件的所有受支持版本、组件版本与之兼容的AEM版本，以及指向以前版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v1 | 兼容 | 兼容 | 兼容 |

有关核心组件版本和版本的更多信息，请参阅文档[核心组件版本](/help/versions.md)。

## 组件输出示例 {#sample-component-output}

要体验轮播组件并查看其配置选项以及HTML和JSON输出的示例，请访问[组件库](https://adobe.com/go/aem_cmp_library_carousel)。

### 技术详细信息 {#technical-details}

有关轮播组件[的最新技术文档，请参阅GitHub](https://adobe.com/go/aem_cmp_tech_carousel_v1)。

有关开发核心组件的更多详细信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## 编辑对话框 {#edit-dialog}

编辑对话框允许内容作者添加、重命名和重新排列幻灯片，以及定义自动过渡设置。

### “项目”选项卡 {#items-tab}

![轮播组件编辑对话框的项目选项卡](/help/assets/carousel-edit-items.png)

使用&#x200B;**Add**&#x200B;按钮打开组件选择器以选择要添加为选项卡的组件。 添加后，会将一个条目添加到列表中，该列包含以下列：

* **图标**  — 选项卡的组件类型图标，以便在列表中轻松识别。将鼠标悬停在上方可查看完整的组件名称作为工具提示。
* **描述**  — 用作选项卡文本的描述，默认使用为选项卡选择的组件的名称。
* **删除**  — 点按或单击以从选项卡组件中删除选项卡。
* **重新排序**  — 点按或单击并拖动以对选项卡进行排序。

>[!TIP]
>
>如果缩小了页面的视区，使编辑对话框变为全屏，则将隐藏&#x200B;**Add**&#x200B;按钮。 组件仍可以通过从组件浏览器中拖放到页面编辑器](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#inserting-a-component-from-the-components-browser)中的轮播组件中的[，添加到轮播组件中。

### “属性”选项卡 {#properties-tab}

![轮播组件编辑对话框的属性选项卡](/help/assets/carousel-edit-properties.png)

在&#x200B;**属性**&#x200B;选项卡上，内容作者可以将幻灯片设置为自动过渡。

* **自动过渡幻灯片**  — 激活后，组件将在指定的延迟后自动前进到下一张幻灯片。
* **过渡延迟**  — 如果选择“自动”过渡幻灯片，则此值用于定义过渡之间的延迟（以毫秒为单位）。
* **禁用悬停时的自动暂停**  — 选中“自 **动过渡** ”幻灯片后，每当光标悬停在轮播上时，轮播过渡将自动暂停。选择此选项，以便过渡不会暂停。
* **ID**  — 利用此选项，可控制HTML和数据层中组件的唯一标识符 [的唯一标识符](/help/developing/data-layer/overview.md)。
   * 如果留为空白，则会自动为您生成唯一ID，并且可以通过检查生成的页面找到该ID。
   * 如果指定了ID，则作者有责任确保该ID是唯一的。
   * 更改ID可能会影响CSS、JS和数据层跟踪。

>[!NOTE]
>
>在&#x200B;**编辑**&#x200B;模式下，未启用幻灯片预览控件。 使用&#x200B;[**预览**&#x200B;模式](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#preview-mode)或&#x200B;**[查看已发布内容](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)**&#x200B;选项，以已发布内容的读者身份与轮播进行交互。
>
>在&#x200B;**编辑**&#x200B;模式下，未启用自动前进功能。 使用&#x200B;**[查看已发布内容](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)**&#x200B;选项，以已发布内容的读者身份查看自动推进功能。

### “辅助功能”选项卡 {#accessibility-tab}

![轮播组件编辑对话框的辅助功能选项卡](/help/assets/carousel-edit-accessibility.png)

在&#x200B;**辅助功能**&#x200B;选项卡上，可以为组件的[ARIA辅助功能](https://www.w3.org/WAI/standards-guidelines/aria/)标签设置值。

* **标签**  — 组件的ARIA标签属性的值

## 选择面板 {#select-panel}

内容作者可以使用组件工具栏上的&#x200B;**选择面板**&#x200B;选项更改为其他幻灯片以进行编辑，并轻松地重新排列幻灯片的顺序。

![“选择面板”图标](/help/assets/select-panel-icon.png)

在组件工具栏中选择&#x200B;**选择面板**&#x200B;选项后，配置的幻灯片将显示为下拉列表。

* 列表按幻灯片的分配排列排列，并反映在编号中。
* 首先显示幻灯片的组件类型，然后以较浅字体显示幻灯片的描述。

![选择面板](/help/assets/select-panel-popover.png)

* 点按或单击下拉菜单中的条目，将编辑器中的视图切换到该幻灯片。
* 可使用拖动手柄就地重新排序幻灯片。

## “设计”对话框 {#design-dialog}

设计对话框允许模板作者定义哪些组件可以作为幻灯片添加到轮播组件，以及定义自动过渡默认值以及哪些自定义样式可供内容作者使用。

### “属性”选项卡 {#properties-tab-1}

当内容作者将轮播组件添加到页面时， **属性**&#x200B;选项卡用于定义幻灯片过渡的默认设置。

![轮播组件的“设计”对话框](/help/assets/carousel-design.png)

* **自动过渡幻灯片**  — 定义在内容作者将轮播组件添加到页面时，默认情况下是否启用自动将轮播前进到下一张幻灯片的选项。
* **过渡延迟**  — 定义内容作者将轮播组件添加到页面时，幻灯片之间过渡延迟的默认值（以毫秒为单位）。
* **禁用悬停时的自动暂停**  — 定义在内容作者选择自动过渡幻灯片时，默认情况下是否启用 **禁用** 自动幻灯片暂停的选项。

### 允许的组件选项卡 {#allowed-components-tab}

**允许的组件**&#x200B;选项卡用于定义哪些组件可作为内容作者向轮播组件添加的幻灯片。

当[在模板编辑器中定义布局容器的策略和属性时，允许的组件选项卡的功能与同名的选项卡相同。](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html)

### “样式”选项卡 {#styles-tab}

传送组件支持AEM [样式系统](/help/get-started/authoring.md#component-styling)。

## Adobe客户端数据层 {#data-layer}

传送组件支持[Adobe客户端数据层。](/help/developing/data-layer/overview.md)
