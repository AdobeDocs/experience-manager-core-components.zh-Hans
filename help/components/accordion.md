---
title: 折叠组件
description: 核心组件折叠面板组件允许创建以折叠面板形式排列在页面上的面板集合。
role: Architect, Developer, Administrator, Business Practitioner
exl-id: 1deb570a-3d8d-409e-805f-8460c49cf9bb
source-git-commit: 8ff36ca143af9496f988b1ca65475497181def1d
workflow-type: tm+mt
source-wordcount: '1067'
ht-degree: 1%

---

# 折叠组件{#accordion-component}

核心组件折叠面板组件允许创建以折叠面板形式排列在页面上的面板集合。

## 使用 {#usage}

核心组件折叠面板组件允许创建组件集合，这些组件以面板形式组成，并排列在页面上的折叠面板中，与[选项卡组件](tabs.md)类似，但允许展开和折叠面板。

* 可以在[配置对话框](#configure-dialog)中定义折叠项的属性。
* 可以在配置对话框以及[选择面板弹出窗口](#select-panel-popover)中定义折叠面板面板的顺序。
* 将可折叠组件添加到页面时的默认值，可在[设计对话框](#design-dialog)中定义。

## 深层链接到面板{#deep-linking}

折叠面板和[选项卡组件](tabs.md)支持直接链接到组件中的面板。

要执行此操作：

1. 使用页面编辑器中的&#x200B;**[查看已发布的页面](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/editing-content.html#view-as-published)**&#x200B;选项查看组件的页面。
1. Inspect页面内容并标识面板的ID。
   * 例如`id="accordion-86196c94d3-item-ca319dbb0b"`
1. 该ID将成为您可以使用哈希(`#`)附加到URL的锚点。
   * 例如`https://wknd.site/content/wknd/language-masters/en/magazine/western-australia.html#accordion-86196c94d3-item-ca319dbb0b`

导航到将面板ID作为锚点的URL，浏览器将直接滚动到特定组件并显示指定的面板。 如果该面板配置为默认不展开，则会自动展开该面板。

## 版本和兼容性{#version-and-compatibility}

折叠组件的当前版本为v1，该版本在2019年6月随核心组件2.5.0版引入，在本文档中进行了描述。

下表详细列出了组件的所有受支持版本、组件版本与之兼容的AEM版本，以及指向以前版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |---|---|
| v1 | 兼容 | 兼容 | 兼容 |

有关核心组件版本和版本的更多信息，请参阅文档[核心组件版本](/help/versions.md)。

## 组件输出示例{#sample-component-output}

要体验折叠组件并查看其配置选项以及HTML和JSON输出的示例，请访问[组件库](https://adobe.com/go/aem_cmp_library_accordion)。

## 技术详细信息{#technical-details}

有关可折叠组件[的最新技术文档可在GitHub](https://adobe.com/go/aem_cmp_tech_accordion_v1)上找到。

有关开发核心组件的更多详细信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## 配置对话框{#configure-dialog}

配置对话框允许内容作者定义折叠项目、其面板，以及该项目的行为方式和页面访客的显示方式。

### 项目选项卡{#items-tab}

![折叠组件编辑对话框的项目选项卡](/help/assets/accordion-edit-items.png)

使用&#x200B;**Add**&#x200B;按钮打开组件选择器以选择要添加为面板的组件。 添加后，会将一个条目添加到列表中，该列包含以下列：

* **图标**  — 面板组件类型的图标，可在列表中轻松识别。将鼠标悬停在上方可查看完整的组件名称作为工具提示。
* **描述**  — 用作面板文本的描述，默认使用为面板选择的组件的名称。
* **删除**  — 点按或单击以从折叠面板组件中删除面板。
* **重新排列**  — 点按或单击并拖动以重新排列面板的顺序。

>[!TIP]
>
>如果缩小了页面的视区，使编辑对话框变为全屏，则将隐藏&#x200B;**Add**&#x200B;按钮。 仍可以通过从组件浏览器中拖放到页面编辑器中的折叠组件](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/editing-content.html#InsertingaComponent)来将组件添加到折叠组件中。[

### 属性选项卡{#properties-tab}

![折叠组件编辑对话框的属性选项卡](/help/assets/accordion-edit-properties.png)

* **单个项目扩展**  — 选中此选项后，会强制一次展开单个折叠项目。展开一个项目后，所有其他项目都将折叠。
* **展开的项目**  — 此选项定义在加载页面时默认展开的项目。
   * 选择&#x200B;**单项扩展**&#x200B;时，必须选择一个面板。 默认情况下，将选择第一个面板。
   * 未选择&#x200B;**单项扩展**&#x200B;时，此选项是多选项，是可选的。
* **ID**  — 利用此选项，可控制HTML和数据层中组件的唯一标识符 [的唯一标识符](/help/developing/data-layer/overview.md)。
   * 如果留为空白，则会自动为您生成唯一ID，并且可以通过检查生成的页面找到该ID。
   * 如果指定了ID，则作者有责任确保该ID是唯一的。
   * 更改ID可能会影响CSS、JS和数据层跟踪。

## 选择面板弹出窗口{#select-panel-popover}

内容作者可以使用组件工具栏上的&#x200B;**选择面板**&#x200B;选项更改为其他面板进行编辑，并轻松地重新排列折叠面板中面板的顺序。

![“选择面板”图标](/help/assets/select-panel-icon.png)

在组件工具栏中选择&#x200B;**选择面板**&#x200B;选项后，配置的折叠面板将显示为下拉列表。

![选择面板弹出窗口](/help/assets/select-panel-popover.png)

* 该列表按面板的指定排列顺序排列，并反映在编号中。
* 首先显示面板的组件类型，然后以较浅字体显示面板的说明。
* 点按或单击下拉菜单中的条目，会将编辑器中的视图切换到该面板。
* 使用拖动手柄可以就地重新排列面板。

## 设计对话框{#design-dialog}

设计对话框允许模板作者定义内容作者可用的选项，这些选项使用折叠组件，并在放置折叠组件时设置默认值。

### 属性选项卡{#properties-tab-design}

![“设计”对话框属性选项卡](/help/assets/accordion-design-properties.png)

* **允许的标题元素**  — 此多选下拉列表定义了作者允许选择的折叠项目标题HTML元素。
* **默认标题元素**  — 此下拉列表定义了默认的折叠项目标题HTML元素。

### 允许的组件选项卡{#allowed-components-tab}

**允许的组件**&#x200B;选项卡用于定义哪些组件可作为内容作者可折叠面板组件中的项目添加到面板。

当[在模板编辑器中定义布局容器的策略和属性时，允许的组件选项卡的功能与同名的选项卡相同。](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/templates.html#editing-a-template-layout-template-author)

### 样式选项卡{#styles-tab}

折叠面板组件支持AEM [样式系统](/help/get-started/authoring.md#component-styling)。

## Adobe客户端数据层{#data-layer}

折叠面板组件支持[Adobe客户端数据层。](/help/developing/data-layer/overview.md)
