---
title: 导航组件
description: 导航组件允许用户轻松导航全球化的站点结构。
translation-type: tm+mt
source-git-commit: d3ebcea5fa1523c1a986841cd3d1a64e16e85f6d
workflow-type: tm+mt
source-wordcount: '1382'
ht-degree: 1%

---


# 导航组件{#navigation-component}

导航组件允许用户轻松导航全球化的站点结构。

## 使用 {#usage}

导航组件列表列表一个页面树，以便站点的用户可以轻松导航站点结构。

导航组件可以自动检测站点的全球化站点结构，并且[可自动适应本地化页面。](#localized-site-structure) 此外，它还可以通过使用阴影重定向页面来 [表示除](#shadow-structure) 主内容结构之外的其他结构来支持任何任意站点结构。

[编辑对话框](#edit-dialog)允许内容作者定义导航根页面以及导航深度。 [设计对话框](#design-dialog)允许模板作者为导航根和深度定义默认值。

## 本地化站点结构支持{#localized-site-structure}

网站通常针对不同区域提供多种语言版本。 通常，每个本地化页面都将包含作为页面模板的一部分包含的导航元素。 导航组件允许您将其放置在站点所有页面的模板上一次，然后它会根据您的全球化站点结构自动适应各个本地化页面。

* 有关导航组件的本地化功能的工作方式的示例，请参阅[下面的部分](#example-localization)。
* 有关核心组件的本地化功能如何协同工作的示例，请参阅“核心组件”页面[的本地化功能页面](/help/get-started/localization.md)。

### 示例 {#example-localization}

假设您的内容如下所示：

```
/content
+-- wknd
   +-- language-masters
      +-- de
         \-- experience
            \-- arctic-surfing-in-lofoten
      +-- en
         \-- experience
            \-- arctic-surfing-in-lofoten
      +-- es
      +-- fr
      \-- it
   +-- us
      +-- en
         \-- experience
            \-- arctic-surfing-in-lofoten
      \-- es
   \-- ch
      +-- de
         \-- experience
            \-- arctic-surfing-in-lofoten
      +-- fr
      \-- it
+-- wknd-events
\-- wknd-shop
```

对于站点WKND，您可能希望将导航组件作为标题的一部分放置在页面模板上。 模板的一部分后，您可以将组件的&#x200B;**导航根**&#x200B;设置为`/content/wknd/language-masters/en`，因为这是该站点的主控内容开始的位置。 您可能还希望将&#x200B;**导航结构深度**&#x200B;设置为`2`，因为您可能不希望组件显示整个内容树，而是希望前两个级别显示，因此它用作概述。

使用&#x200B;**导航根**&#x200B;值，导航组件知道在`/content/wknd/language-masters/en`开始导航后，可以通过向下递归站点的结构两级（由&#x200B;**导航结构深度**&#x200B;值定义）来生成导航选项。

无论用户正在查看什么本地化页面，导航组件都可以通过了解当前页面的位置找到相应的本地化页面，然后向后工作到根页面，然后转发到相应的页面。

因此，如果访客正在查看`/content/ch/de/experience/arctic-surfing-in-lofoten`，则组件知道基于`/content/wknd/language-masters/de`生成导航结构。 同样，如果访客正在查看`/content/us/en/experience/arctic-surfing-in-lofoten`，则组件知道根据`/content/wknd/language-masters/en`生成导航结构。

## 卷影站点结构支持{#shadow-structure}

有时，需要为访客创建一个与实际站点结构不同的导航菜单。 或许促销活动应通过重新排列内容列表来突出显示菜单中的特定内容。 使用阴影页面（它只能重定向到其他内容页面），导航组件可以生成任何必要的任意导航结构。

为此，您需要：

1. 将阴影页面创建为表示所需网站结构的空页面。 这通常称为阴影站点结构。
1. 在这些页面的页面属性中设置&#x200B;**Redirect**&#x200B;值以指向实际的内容页面。
1. 在阴影页面的页面属性中设置&#x200B;**在导航中隐藏**&#x200B;选项。
1. 将导航组件的&#x200B;**导航根**&#x200B;值设置为指向新阴影站点结构的根。

导航组件随后将根据阴影站点结构呈现菜单。 组件呈现的链接指向阴影页面重定向到的实际内容页面，而不是指向阴影页面本身。 此外，即使导航基于阴影页面，该组件也会显示实际页面的名称并正确突出显示活动页面。 导航组件有效地使阴影页面对访客完全透明。

>[!NOTE]
>阴影页使您的导航选项更加灵活，但请记住，此结构的维护是完全手动完成的。 如果您重新排列实际的站点内容或添加/删除内容，则需要根据需要手动更新阴影结构。

>[!NOTE]
>渲染阴影站点结构时，导航逻辑只递归阴影页面。 该逻辑不递归重定向目标的结构。

## 版本和兼容性{#version-and-compatibility}

导航组件的当前版本为v1,2018年1月随核心组件版本2.0.0引入了v1，本文档对此进行了说明。

下表详细列出了组件的所有受支持版本、与组件版本兼容的AEM版本，以及指向先前版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v1 | 兼容 | 兼容 | 兼容 |

有关核心组件版本和版本的详细信息，请参阅文档[核心组件版本](/help/versions.md)。

## 示例组件输出{#sample-component-output}

要体验导航组件以及查看其配置选项以及HTML和JSON输出的示例，请访问[组件库](https://adobe.com/go/aem_cmp_library_navigation)。

## 技术详细信息{#technical-details}

有关导航组件[的最新技术文档可在GitHub](https://adobe.com/go/aem_cmp_tech_navigation_v1)上找到。

有关开发核心组件的更多详细信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

>[!NOTE]
>
>从2.1.0版核心组件开始，导航组件支持[模式.org microdata](https://schema.org)。

## 编辑对话框{#edit-dialog}

在“编辑”对话框中，内容作者可以定义用于导航的根页面和导航结构的深度。

### 属性选项卡{#properties-tab}

![导航组件的编辑对话框属性选项卡](/help/assets/navigation-edit-properties.png)

* **导航根**  — 将用于生成导航树的根页面。
* **排除根级别**  — 通常，导航中不应包含根。此选项允许您指定要从根中向上排除多少级。 例如：
   * 0 =显示根级别
   * 1 =排除根级别
   * 2 =排除根，再向上1级
   * 以此类推。
* **收集所有子页面**  — 收集所有作为导航根的后代的页面。
* **导航结构深度**  — 定义组件在导航树中相对于导航根显示的级别数(仅当未选择“收集所 **有子页** 面”时可用)。
* **禁用遮蔽**  — 如果层次结构中的页面是重定向，则将显示重定向页面的名称而不是目标。有关详细信息，请参阅[阴影站点结构支持](#shadow-structure)。
* **ID**  — 此选项允许控制HTML和数据层中组件的唯一 [标识符](/help/developing/data-layer/overview.md)。
   * 如果留空，系统会为您自动生成唯一ID，通过检查生成的页面可以找到它。
   * 如果指定了ID，则作者有责任确保它是唯一的。
   * 更改ID可能会影响CSS、JS和数据图层跟踪。

### 辅助功能选项卡{#accessibility-tab}

![导航组件的编辑对话框辅助功能选项卡](/help/assets/navigation-edit-accessibility.png)

在&#x200B;**辅助功能**&#x200B;选项卡上，可以为组件的[ARIA辅助功能](https://www.w3.org/WAI/standards-guidelines/aria/)标签设置值。

* **Label**  — 组件的ARIA label属性值

## 设计对话框{#design-dialog}

设计对话框允许模板作者设置向内容作者显示的导航根页面和导航深度的默认值。

### 属性选项卡{#properties-tab-design}

![导航组件的设计对话框](/help/assets/navigation-design.png)

* **导航根**  — 导航结构的根页面的默认值，该值将用于生成导航树并在内容作者将组件添加到页面时默认。
* **排除根级别**  — 通常，导航中不应包含根。此选项允许您指定要从根目录向上排除多少级的默认值。 例如：
   * 0 =显示根级别
   * 1 =排除根级别
   * 2 =排除根，再向上1级
   * 以此类推。
* **收集所有子页面**  — 用于收集所有作为导航根的子页面的选项的默认值。
* **导航结构深度**  — 导航结构深度的默认值。
* **禁用遮蔽**  — 添加导航组件时是否应禁用遮蔽的默认值

### 样式选项卡{#styles-tab}

导航组件支持AEM [样式系统](/help/get-started/authoring.md#component-styling)。

## Adobe客户端数据层{#data-layer}

导航组件支持[Adobe客户端数据层。](/help/developing/data-layer/overview.md)
