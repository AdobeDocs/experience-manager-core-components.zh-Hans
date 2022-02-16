---
title: Teaser 组件
description: Teaser 组件可以显示图像、标题、富文本并可以选择链接到更多内容。
role: Architect, Developer, Admin, User
exl-id: ec75e168-6f3b-4dff-8df6-06ca7dc18688
source-git-commit: 395a1669cf3e17f649c23852addc37316b923bfd
workflow-type: tm+mt
source-wordcount: '999'
ht-degree: 69%

---

# Teaser 组件 {#teaser-component}

核心组件 Teaser 组件可以显示图像、标题、富文本并可以选择链接到更多内容。

## 用途 {#usage}

使用 Teaser 组件，内容作者可以轻松地创建 Teaser，以便让更多内容使用图像、标题或富文本，并将其链接到更多内容或其他操作。

模板作者可以使用[“设计”对话框](#design-dialog)定义创建行动号召和添加链接的选项是否可用，以及禁用各种显示选项。内容作者可以使用[“配置”对话框](#configure-dialog)来设置图像、定义 CTA、设置标题和描述，以及配置指向个别 Teaser 的链接。可以访问[图像组件](image.md)的[“编辑”对话框](image.md#edit-dialog)来修改 Teaser 图像。

## 版本和兼容性 {#version-and-compatibility}

Teaser组件的当前版本为v2，该版本于2022年2月随核心组件2.18.0版引入，在本文档中进行了描述。

下表详细说明了该组件的所有受支持版本、与该组件的版本兼容的 AEM 版本以及指向早期版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|---|
| v2 | - | 兼容 | 兼容 |
| [v1](v1/teaser.md) | 兼容 | 兼容 | 兼容 |

## 示例组件输出 {#sample-component-output}

要体验 Teaser 组件并查看其配置选项示例以及 HTML 和 JSON 输出，请访问[组件库](https://adobe.com/go/aem_cmp_library_teaser_cn)。

### 技术详细信息 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_teaser_v1_cn)有关 Teaser 组件的最新技术文档。

在[核心组件开发人员文档](/help/developing/overview.md)中可找到有关开发核心组件的其他详细信息。

## “配置”对话框 {#configure-dialog}

内容作者可以使用“配置”对话框定义个别 Teaser 的属性。在选中时，还有[“编辑”对话框](#edit-dialog)可修改 Teaser 图像。

### “链接”选项卡 {#links-tab}

![Teaser组件的编辑对话框链接选项卡](/help/assets/teaser-edit-links.png)

可从链接的页面或从第一个行动号召中链接的页面继承 Teaser 标题、描述和图像。如果未指定链接和行动号召，将从当前页面继承标题、描述和图像。

* **链接**  — 此文件链接到内容页面、外部URL或页面锚点。
* **在新选项卡中打开链接**  — 如果启用，将在新的浏览器选项卡中打开该链接。
* **行动动员**  — 此选项允许链接到多个目标。
   * 在继承Teaser标题、描述或图像时，将使用第一个行动动员中链接的页面。

### 文本选项卡 {#text-tab}

![Teaser 组件的“编辑”对话框中的“文本”选项卡](/help/assets/teaser-edit-text.png)

* **前标题** - 前标题显示在 Teaser 的标题之前。
* **标题** - 定义显示为 Teaser 大标题的标题。
   * **从链接的页面获取标题** - 在选中时，使用链接页面的标题填充标题。
* **描述** - 定义显示为 Teaser 子标题的描述。
   * **从链接的页面获取描述** - 在选中时，使用链接页面的描述填充描述。
* **ID** - 利用此选项，可以控制 HTML 和 [Data Layer](/help/developing/data-layer/overview.md) 中的组件的唯一标识符。
   * 如果留空，系统会自动为您生成一个唯一 ID，可以通过检查结果页面找到该 ID。
   * 如果指定一个 ID，作者有责任确保它是唯一的。
   * 更改此 ID 会对 CSS、JS 和 Data Layer 跟踪产生影响。

### “资源”选项卡 {#asset-tab}

![Teaser 组件的“编辑”对话框中的“图像”选项卡](/help/assets/teaser-edit-image.png)

* **从页面继承特色图像**  — 使用在链接页面或当前页面的页面属性中定义的图像（如果未找到）。
* **图像资产**  — 从 [资产浏览器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html) 或点按 **浏览** 用于从本地文件系统上传的选项。
   * 点击或单击&#x200B;**“清除”**&#x200B;以取消选择当前选定的图像。
   * 点击或单击&#x200B;**“编辑”**&#x200B;可在资源编辑器中[管理资源的再现](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html)。
* **辅助功能的替换文本**  — 利用此字段，可为视力受损的用户定义图像描述。
   * **从页面继承替换文本**  — 此选项使用 `dc:description` 元数据（如果未关联资产）或当前页面的元数据。
* **不提供替换文本**  — 当图像仅起装饰作用，或者没有向页面传达任何其他信息时，此选项会标记图像，并且这些信息会被屏幕阅读器等辅助技术忽略。

>[!NOTE]
>
>[Dynamic Media 功能](image.md#dynamic-media)当前在 Teaser 组件中不可用。

### “样式”选项卡 {#styles-tab-edit}

![Teaser列表组件编辑对话框的样式选项卡](/help/assets/teaser-edit-styles.png)

Teaser组件支持AEM [样式系统。](/help/get-started/authoring.md#component-styling).

使用下拉菜单选择要应用于组件的样式。 在编辑对话框中所做的选择与从组件工具栏中选择的选项具有相同的效果。

必须在 [设计对话框](#design-dialog) 以便下拉菜单可用。

## “编辑”对话框 {#edit-dialog}

Teaser 组件将图像渲染委派给[图像组件](image.md)。因此，内容作者可以使用[“编辑”对话框]（图像组件的 image.md#edit-dialog）来处理 Teaser 图像。

## “设计”对话框 {#design-dialog}

利用“设计”对话框，模板作者可以定义内容作者在使用此组件时具有的 Teaser 选项。

### “Teaser”选项卡 {#teaser-tab}

![Teaser 组件的“设计”对话框](/help/assets/teaser-design.png)

* **行为召唤**
   * **禁用行为召唤** - 对内容作者隐藏&#x200B;**行为召唤**&#x200B;选项
* **元素**
   * **隐藏前标题** - 对内容作者隐藏&#x200B;**前标题**&#x200B;选项
   * **隐藏标题** - 对内容作者隐藏&#x200B;**标题**&#x200B;选项
      * 在选中时，将隐藏&#x200B;**标题类型**
   * **隐藏描述** - 对内容作者隐藏&#x200B;**描述**&#x200B;选项
* **默认标题类型**  — 定义Teaser标题要使用的H标记。
* **图像委派** - 信息性显示，指示 Teaser 将图像处理委派到的组件。

### “样式”选项卡 {#styles-tab}

Teaser 组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。

## Adobe Client Data Layer {#data-layer}

Teaser 组件支持 [Adobe Client Data Layer](/help/developing/data-layer/overview.md)。
