---
title: Teaser组件
description: Teaser组件可显示图像、标题、富文本，以及可选链接到其他内容。
role: Architect, Developer, Administrator, Business Practitioner
exl-id: ec75e168-6f3b-4dff-8df6-06ca7dc18688
source-git-commit: 8ff36ca143af9496f988b1ca65475497181def1d
workflow-type: tm+mt
source-wordcount: '775'
ht-degree: 2%

---

# Teaser组件{#teaser-component}

核心组件Teaser组件可以显示图像、标题、富文本，以及可选链接到其他内容。

## 使用 {#usage}

Teaser组件允许内容作者使用图像、标题或富文本轻松创建Teaser以进一步内容，并链接到进一步内容或其他操作。

模板作者可以使用[设计对话框](#design-dialog)来定义创建行动动员和添加链接的选项是否可用，以及禁用各种显示选项。 内容作者可以使用[配置对话框](#configure-dialog)来设置图像、定义CTA、设置标题和描述，以及配置指向单个Teaser的链接。 可以访问[图像组件](image.md)的[编辑对话框](image.md#edit-dialog)以修改Teaser图像。

## 版本和兼容性{#version-and-compatibility}

Teaser组件的当前版本为v1，该版本于2018年7月随核心组件2.1.0版引入，在本文档中进行了描述。

下表详细列出了组件的所有受支持版本、组件版本与之兼容的AEM版本，以及指向以前版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|---|
| v1 | 兼容 | 兼容 | 兼容 |

## 组件输出示例{#sample-component-output}

要体验Teaser组件并查看其配置选项以及HTML和JSON输出的示例，请访问[组件库](https://adobe.com/go/aem_cmp_library_teaser)。

### 技术详细信息{#technical-details}

有关Teaser组件[的最新技术文档可在GitHub](https://adobe.com/go/aem_cmp_tech_teaser_v1)上找到。

有关开发核心组件的更多详细信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## 配置对话框{#configure-dialog}

内容作者可以使用配置对话框来定义单个Teaser的属性。 此外，还有一个[编辑对话框](#edit-dialog)，用于修改选择了Teaser图像时的Teaser图像。

### 图像 {#image}

![Teaser组件的编辑对话框图像选项卡](/help/assets/teaser-edit-image.png)

* **图像资产**
   * 从[资产浏览器](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html)中删除资产，或点按&#x200B;**browse**&#x200B;选项，以从本地文件系统上传。
   * 点按或单击&#x200B;**清除**&#x200B;以取消选择当前选定的图像。
   * 点按或单击&#x200B;**编辑** ，以在资产编辑器中[管理资产的演绎版。](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/manage/manage-digital-assets.html)

>[!NOTE]
>
>[Dynamic Media](image.md#dynamic-media) 功能当前在Teaser组件中不可用。

### 文本 {#text}

![Teaser组件的编辑对话框文本选项卡](/help/assets/teaser-edit-text.png)

* **Pretitle**  — 预标题将显示在Teaser标题之前。
* **标题**  — 定义要显示为Teaser标题的标题。
   * **从链接页面获取标题**  — 选中此选项后，将使用链接页面的标题填充标题。
* **描述**  — 定义要显示为Teaser子标题的描述。
   * **从链接页面获取描述**  — 选中此选项后，描述将填充链接页面的描述。
* **ID**  — 利用此选项，可控制HTML和数据层中组件的唯一标识符 [的唯一标识符](/help/developing/data-layer/overview.md)。
   * 如果留为空白，则会自动为您生成唯一ID，并且可以通过检查生成的页面找到该ID。
   * 如果指定了ID，则作者有责任确保该ID是唯一的。
   * 更改ID可能会影响CSS、JS和数据层跟踪。

### 链接和操作{#links-actions}

![Teaser组件的编辑对话框链接选项卡](/help/assets/teaser-edit-link.png)

* **链接**  — 应用于Teaser的链接。使用路径浏览器选择链接目标。
* **启用行动动员**  — 选中此选项后，将启用行动动员的定义。列表中的第一个行动动员链接用作其他Teaser元素的链接。

## 编辑对话框{#edit-dialog}

Teaser组件将图像渲染委派给[图像组件](image.md)。 因此，内容作者可以使用[编辑对话框]（图像组件的image.md#edit-dialog）来操作Teaser图像。

## 设计对话框{#design-dialog}

设计对话框允许模板作者定义内容作者在使用此组件时拥有的Teaser选项。

### Teaser选项卡{#teaser-tab}

![Teaser组件的设计对话框](/help/assets/teaser-design.png)

* **行为召唤**
   * **禁用行动动员**  — 为内容作 **者隐藏行动** 动员选项
* **元素**
   * **隐藏前标题**  — 隐藏内容作 **** 者的前标题选项
   * **隐藏标题**  — 隐藏内容作 **** 者的标题选项
      * 选择&#x200B;**标题类型**&#x200B;后，将隐藏
   * **隐藏描述**  — 隐藏内容作 **** 者的描述选项
* **标题类型**  — 定义Teaser标题要使用的H标记。
* **链接**
   * **不链接图像**  — 选择后，Teaser图像未关联
   * **不链接标题**  — 选择后，Teaser标题将不会关联
* **图像委派**  — 信息性显示，指示Teaser委派图像处理的组件。

### 样式选项卡{#styles-tab}

Teaser组件支持AEM [Style System](/help/get-started/authoring.md#component-styling)。

## Adobe客户端数据层{#data-layer}

Teaser组件支持[Adobe客户端数据层。](/help/developing/data-layer/overview.md)
