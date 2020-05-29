---
title: 图像组件
description: 核心组件图像组件是一种自适应图像组件功能，可进行就地编辑。
translation-type: tm+mt
source-git-commit: c186e9ec3944d785ab0376769cf7f2307049a809
workflow-type: tm+mt
source-wordcount: '1934'
ht-degree: 2%

---


# 图像组件{#image-component}

核心组件图像组件是一个自适应图像组件，可进行就地编辑。

## 使用 {#usage}

图像组件为页面访客提供自适应图像选择和响应式行为功能，为内容作者提供延迟加载以及简单的图像放置和裁剪。

模板作者可以在设计对话框中定义图像宽度以及裁剪和其 [他设置](#design-dialog)。 内容编辑器可以在“配置”对话框中上 [传或选择资](#configure-dialog) 产，并在“编辑”对 [话框中裁剪图像](#edit-dialog)。 为了更方便，还可以对图像进行简单的就地修改。

## 响应式功能 {#responsive-features}

图像组件附带强大的响应式功能，随时可用。 在页面模板级别，可 [以使用](#design-dialog) “设计”对话框定义图像资产的默认宽度。 然后，图像组件将自动加载正确的宽度以根据浏览器窗口的大小进行显示。 调整窗口大小时，图像组件会动态加载正确的图像大小。 由于图像组件已经过优化以加载您的内容，因此组件开发人员无需担心定义自定义媒体查询。

此外，图像组件还支持延迟加载，以延迟实际图像资产的加载，直到其在浏览器中可见为止，从而提高页面的响应性。

## 版本和兼容性 {#version-and-compatibility}

图像组件的当前版本为v2,2018年1月随核心组件的2.0.0版一起推出，本文档对此进行了说明。

下表详细列出了组件的所有受支持版本、与组件版本兼容的AEM版本以及指向先前版本文档的链接。

| 组件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM 云服务 |
|--- |--- |--- |--- |---|
| v2 | - | 兼容 | 兼容 | 兼容 |
| [v1](v1/image-v1.md) | 兼容 | 兼容 | 兼容 | - |

有关核心组件版本和版本的详细信息，请参阅文档 [核心组件版本](/help/versions.md)。

## SVG支持 {#svg-support}

图像组件支持可缩放矢量图形(SVG)。

* 支持从DAM拖放SVG资产和从本地文件系统上传SVG文件。
* 自适应图像Servlet对原始SVG文件进行流处理（跳过变换）。
* 对于SVG图像，“智能图像”和“智能大小”设置为图像模型中的空数组。

### 安全 {#security}

出于安全原因，图像编辑器从不直接调用原始SVG。 它被通过 `<img src=“path-to-component”>`。 这会阻止浏览器执行嵌入在SVG文件中的任何脚本。

>[!CAUTION]
>
>SVG支持要求核心组件版本2.1.0或更高版本以及 [AEM 6.4的Service](https://docs.adobe.com/content/help/en/experience-manager-64/release-notes/sp-release-notes.html) Pack [2或AEM 6.3的](https://helpx.adobe.com/experience-manager/6-3/release-notes/sp3-release-notes.html) Service Pack 3 [或更高版本支持AEM中](https://docs.adobe.com/content/help/en/experience-manager-64/developing/components/image-editor.html) 的新图像编辑器功能。

## 示例组件输出 {#sample-component-output}

要体验图像组件以及查看其配置选项以及HTML和JSON输出的示例，请访问组 [件库](https://adobe.com/go/aem_cmp_library_image)。

### 技术详细信息 {#technical-details}

有关图像组件的最新技术文 [档可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_image_v2)。

有关开发核心组件的更多详细信息，请参阅核 [心组件开发人员文档](/help/developing/overview.md)。

>[!NOTE]
>
>自核心组件2.1.0版起，图像组件支持 [模式.org微数据](https://schema.org)。

## 配置对话框 {#configure-dialog}

除了标准的编 [辑对话框](#edit-dialog)[和设计对话框](#design-dialog)，图像组件还优惠一个配置对话框，在该对话框中定义图像本身及其描述和基本属性。

### 资产选项卡 {#asset-tab}

![图像组件的配置对话框的资产选项卡](/help/assets/image-configure-asset.png)

* **图像资产**
   * 从资产浏览器 [中删除资产](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html) ，或点 **按浏览选** 项，以从本地文件系统上传。
   * 点按或单击 **清除** ，以取消选择当前选定的图像。
   * 点按或单 **击**[编辑，以在资产编辑器中](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/manage/manage-digital-assets.html) 管理资产的演绎版。

### 元数据选项卡 {#metadata-tab}

![图像组件的配置对话框的元数据选项卡](/help/assets/image-configure-metadata.png)

* **图像具有装饰**&#x200B;性检查是否应由辅助型技术忽略图像，因此不需要替代文本。 这仅适用于装饰图像。
* **替代文**&#x200B;本图像含义或功能的替代文本，供有视觉障碍的读者使用。
   * 从DAM获取替代文本——选中后，图像的替代文本将填充DAM中元 `dc:description` 数据的值。

* **题注**&#x200B;有关图像的其他信息，默认情况下显示在图像下方。
   * **从DAM获取**&#x200B;题注选中此项后，图像的题注文本将填充DAM中元 `dc:title` 数据的值。
   * **将题注显示为弹**&#x200B;出窗口选中此项后，题注不会显示在图像下方，而会在将鼠标悬停在图像上方时由某些浏览器显示为弹出窗口。

* **链接**
   * 将图像链接到其他资源。
   * 使用选择对话框链接到其他AEM资源。
   * 如果未链接到AEM资源，请输入绝对URL。 非溶质URL将解释为相对于AEM。

* **ID** —— 此选项允许控制HTML和数据层中组件的唯一标 [识符](/help/developing/data-layer/overview.md)。
   * 如果留空，则会自动为您生成唯一ID，并可通过检查生成的页面找到该ID。
   * 如果指定了ID，则作者有责任确保它是唯一的。
   * 更改ID可能会影响CSS、JS和数据层跟踪。

## Edit Dialog {#edit-dialog}

编辑对话框允许内容作者裁剪、修改启动映射和缩放图像。

![图像组件的编辑对话框](/help/assets/image-edit.png)

* 开始裁剪

   ![开始裁剪图标](/help/assets/image-start-crop.png)

   选择此选项将打开预定义裁剪比例的下拉框。

   * 选择“手 **自由** ”选项以定义您自己的裁剪。
   * 选择删除 **裁剪** ，以显示原始资产。
   选择裁剪选项后，使用蓝色手柄调整图像上的裁剪大小。

   ![裁剪选项](/help/assets/image-crop-options.png)

* 向右旋转

   ![向右旋转图标](/help/assets/image-rotate-right.png)

   使用此选项将图像向右（顺时针）旋转90°。

* 水平翻转

   ![水平翻转图标](/help/assets/image-flip-horizontal.png)

   使用此选项可水平翻转图像或沿y轴将图像旋转180°。

* 垂直翻转

   ![垂直翻转图标](/help/assets/image-flip-vertical.png)

   使用此选项可垂直翻转图像或沿x轴将图像旋转180°。

* 重置缩放

   ![重置缩放图标](/help/assets/image-reset-zoom.png)

   如果图像已经缩放，则使用此选项重置缩放级别。

* 打开缩放滑块

   ![打开缩放滑块图标](/help/assets/image-zoom.png)

   使用此选项可显示一个滑块来控制图像的缩放级别。

   ![缩放滑块控件](/help/assets/image-zoom-slider.png)

就地编辑器还可用于修改图像。 由于空间限制，只有基本选项可在线使用。 对于完整编辑选项，请使用全屏模式。

![图像就地编辑选项](/help/assets/image-in-place-edit.png)

>[!NOTE]
>
>GIF图像不支持图像编辑操作（裁剪、翻转、旋转）。 在编辑模式下对GIF所做的任何此类更改都不会被保留。

## 设计对话框 {#design-dialog}

设计对话框允许模板作者定义内容作者在使用此组件时具有的裁剪、上传和旋转以及上传选项。

### 主选项卡 {#main-tab}

在“主 **要** ”选项卡上，您可以为图像定义宽度列表（以像素为单位），组件将根据浏览器大小自动加载最合适的宽度。 这是图像组件响应式功 [能的重](#responsive-features) 要部分。

此外，您还可以定义在作者将组件添加到页面时自动或禁用的常规组件选项。

![图像组件的设计对话框主选项卡](/help/assets/image-design-main.png)

* **启用延迟加**&#x200B;载定义在将图像组件添加到页面时是否自动启用延迟加载选项。
* **图像具有装饰**&#x200B;性定义在将图像组件添加到页面时是否自动启用装饰性图像选项。
* **从DAM获取替代文**&#x200B;本在将图像组件添加到页面时，定义是否自动启用从DAM检索替代文本的选项。
* **从DAM获取题**&#x200B;注在将图像组件添加到页面时，定义是否自动启用从DAM检索题注的选项。
* **将题注显示为弹**&#x200B;出窗口定义在将图像组件添加到页面时，是否自动启用将图像题注显示为弹出窗口的选项。
* **禁用UUID跟**&#x200B;踪检查以禁用对图像资产UUID的跟踪。

* **宽**&#x200B;度定义图像的宽度列表（以像素为单位），组件会根据浏览器大小自动加载最合适的宽度。
   * 点按或单击添 **加按** 钮以添加其他大小。
      * 使用抓握手柄重新排列大小的顺序。
      * 使用删 **除** 图标删除宽度。
   * 默认情况下，图像加载会延迟到它们变为可见。
      * 选择“停 **用延迟加载** ”选项，在页面加载时加载图像。
* **JPEG质**&#x200B;量转换的JPEG图像的质量系数（以0和100的百分比表示）（例如，缩放或裁剪）。

>[!NOTE]
>
>“JPEG质量”选项在“核心组件”的2.2.0版中可用。

>[!NOTE]
>
>从核心组件的2.2.0版开始，图像组件将唯一的UUID属性添加 `data-asset-id` 到图像资产，以便跟踪和分析单个资产接收的视图数。

### Features Tab {#features-tab}

在“功 **能** ”选项卡上，您可以定义当使用内容作者使用的选项，包括上传选项、方向和裁剪选项。

* 源

   ![图像组件的设计对话框功能选项卡](/help/assets/image-design-features-source.png)

   选择“允 **许从文件系统上传资产** ”选项，以允许内容作者从其本地计算机上传图像。 要强制内容作者仅从AEM中选择资产，请取消选择此选项。

* 方向

   ![图像组件的设计对话框功能选项卡](/help/assets/image-design-features-orientation.png)

* **旋**&#x200B;转使用此选项可允许内容作者使用“向右 **旋转** ”选项。
* **翻转**&#x200B;使用此选项可允许内容作者使用“水平翻转” **和“垂直** 翻转”选项 **** 。

   >[!CAUTION]
   >
   >默认 **情况下** ,“翻转”选项处于禁用状态。 启用此功能将在图 **像组件的编** 辑对话框中显示 **“垂直翻转”和“水平翻转** ”按钮，但AEM当前不支持此功能，并且不会保留使用这些选项所做的任何更改。

* 裁剪

   ![图像组件的设计对话框功能选项卡](/help/assets/image-design-features-cropping.png)

   选择允许 **裁剪** ，以允许内容作者在编辑对话框中裁剪组件中的图像。
   * 单 **击** “添加”以添加预定义的裁剪长宽比。
   * 输入描述性名称，该名称将显示在“开始 **裁剪** ”下拉框中。
   * 输入长宽比的数值。
   * 使用拖动手柄重新排列长宽比的顺序
   * 使用垃圾桶图标删除长宽比。
   >[!CAUTION]
   >
   >Note that in AEM, crop aspect ratios are defined as **height/width**. 这与常见的宽高比的定义不同，这样做是出于对旧版兼容性的考虑。只要您提供比率的明确名称，内容作者就不会察觉到任何差异，因为该名称显示在UI中，而不是比率本身。

### 样式选项卡 {#styles-tab-1}

图像组件支持AEM样 [式系统](/help/get-started/authoring.md#component-styling)。

## 自适应图像Servlet {#adaptive-image-servlet}

图像组件使用核心组件的自适应图像Servlet。 [自适应图像Servlet](https://github.com/adobe/aem-core-wcm-components/wiki/The-Adaptive-Image-Servlet) 负责图像处理和流化，开发人员可以利用它们对核 [心组件的自定义](/help/developing/customizing.md)。

>[!NOTE]
>
>Adaptive Image Servlet支 `Last-Modified` 持通过头的条件请求，但需要在Dispatcher中 `Last-Modified` 启 [用头的缓存](https://docs.adobe.com/content/help/en/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html#caching-http-response-headers)。
>
>[AEM Project Archetype的示例](/help/developing/archetype/overview.md)Dispatcher配置已包含此配置。
