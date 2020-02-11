---
title: 图像组件
description: 核心组件图像组件是自适应图像组件功能的就地编辑。
translation-type: tm+mt
source-git-commit: 60df01ca9efe59b67bad57610d04496a2cdded9e

---


# 图像组件{#image-component}

核心组件图像组件是一个自适应图像组件，可进行就地编辑。

## 使用情况 {#usage}

图像组件具有自适应图像选择和响应式行为，可延迟加载页面访客，以及为内容作者轻松放置图像和裁剪图像。

图像宽度以及裁剪和其他设置可由模板作者在设计对话框中定 [义](#design-dialog)。 内容编辑器可以在“配置”对话框中上传或 [选择资产](#configure-dialog) ，并在“编辑”对话框中裁 [剪图像](#edit-dialog)。 为了更方便起见，还可以对图像进行简单的就地修改。

## 响应式功能 {#responsive-features}

图像组件附带强大的响应式功能，随时可用。 在页面模板级别，可 [以使用设计](#design-dialog) 对话框来定义图像资产的默认宽度。 图像组件随后将自动加载正确的宽度以根据浏览器窗口的大小显示。 调整窗口大小时，图像组件会动态加载正确的图像大小。 由于图像组件已经过优化以加载内容，因此组件开发人员无需担心定义自定义媒体查询。

此外，图像组件还支持延迟加载，以延迟实际图像资产的加载，直到其在浏览器中可见为止，从而提高页面的响应性。

## 版本和兼容性 {#version-and-compatibility}

图像组件的当前版本是v2，该版本在2018年1月随核心组件的2.0.0版一起推出，本文档对此进行了说明。

下表详细列出了组件的所有受支持版本、与组件版本兼容的AEM版本，以及指向先前版本的文档的链接。

| 组件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM作为云服务 |
|--- |--- |--- |--- |---|
| v2 | 兼容 | 兼容 | 兼容 | 兼容 |
| [v1](image-v1.md) | 兼容 | 兼容 | 兼容 | - |

有关核心组件版本和版本的详细信息，请参阅文档核 [心组件版本](versions.md)。

## SVG支持 {#svg-support}

图像组件支持可缩放矢量图形(SVG)。

* 支持从DAM拖放SVG资源以及从本地文件系统上传SVG文件。
* 自适应图像Servlet流式传输原始SVG文件（跳过变换）。
* 对于SVG图像，“智能图像”和“智能大小”在图像模型中设置为空数组。

### 安全 {#security}

出于安全原因，图像编辑器从不直接调用原始SVG。 它被叫穿了 `<img src=“path-to-component”>`。 这会阻止浏览器执行嵌入在SVG文件中的任何脚本。

>[!CAUTION]
>
>SVG支持要求核心组件版本2.1.0或更高版本以及 [AEM 6.4的](https://docs.adobe.com/content/help/en/experience-manager-64/release-notes/sp-release-notes.html) service pack 2 [，或AEM 6.3的](https://helpx.adobe.com/experience-manager/6-3/release-notes/sp3-release-notes.html) service pack 3 [，以支持AEM中的新](https://docs.adobe.com/content/help/en/experience-manager-64/developing/components/image-editor.html) 图像编辑器功能。

## 示例组件输出 {#sample-component-output}

要体验图像组件以及查看其配置选项的示例以及HTML和JSON输出，请访问组 [件库](https://adobe.com/go/aem_cmp_library_image)。

### 技术详细信息 {#technical-details}

有关图像组件的最新技术文 [档可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_image_v2)。

有关开发核心组件的更多详细信息，请参阅核 [心组件开发人员文档](developing.md)。

>[!NOTE]
>
>自核心组件版本2.1.0起，图像组件支持 [schema.org microdata](https://schema.org)。

## 配置对话框 {#configure-dialog}

除了标准编辑对 [话框和设计对话框](#edit-dialog) ，图像组 [件还提供一个配置对话框](#design-dialog)，在该对话框中定义了图像本身及其描述和基本属性。

### 资产选项卡 {#asset-tab}

![](assets/screen_shot_2018-01-08at114245.png)

* **图像资产**
   * 从资产浏览器中 [拖放资产](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html) ，或点 **按浏览选项** ，以从本地文件系统上传。
   * 点按或单 **击清除** ，以取消选择当前选定的图像。
   * 点按或单 **击编辑** , [以在资产编辑器中管理资产的演绎版](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/manage/manage-digital-assets.html) 。

### 元数据选项卡 {#metadata-tab}

![](assets/screen_shot_2018-01-08at114527.png)

* **图像具有装饰**&#x200B;性检查辅助技术是否应忽略图像，因此不需要替代文本。 这仅适用于装饰性图像。
* **替代文**&#x200B;本供有视觉障碍的读者使用，作为图像含义或功能的替代文本。
   * 从DAM获取替代文本——选中后，图像的替代文本将填充DAM中元数据 `dc:description` 的值。

* **题注**&#x200B;有关图像的其他信息，默认情况下显示在图像下方。
   * **从DAM获取题**&#x200B;注选中此选项后，图像的题注文本将填充DAM中元数 `dc:title` 据的值。
   * **将题注显示为弹出窗口**&#x200B;选中此选项后，题注不会显示在图像下方，而是显示为某些浏览器在将鼠标悬停在图像上方时显示的弹出窗口。

* **链接**
   * 将图像链接到其他资源。
   * 使用选择对话框链接到其他AEM资源。
   * 如果未链接到AEM资源，请输入绝对URL。 非溶质URL将解释为相对于AEM。

## Edit Dialog {#edit-dialog}

编辑对话框允许内容作者裁剪、修改启动图和缩放图像。

![](assets/chlimage_1-8.png)

* 开始裁剪

   ![](assets/chlimage_1-9.png)

   选择此选项将打开预定义裁剪比例的下拉框。

   * 选择“手 **自由** ”选项以定义您自己的裁剪。
   * 选择“删除 **裁剪** ”选项以显示原始资产。
   选择裁剪选项后，使用蓝色手柄调整图像上的裁剪大小。

   ![](assets/chlimage_1-10.png)

* 向右旋转

   ![](assets/chlimage_1-11.png)

   使用此选项可将图像向右（顺时针）旋转90°。

* 水平翻转

   ![](assets/screen_shot_2018-04-16at091404.png)

   使用此选项可水平翻转图像或沿y轴将图像旋转180°。

* 垂直翻转

   ![](assets/screen_shot_2018-04-16at091410.png)

   使用此选项可垂直翻转图像或沿x轴将图像旋转180°。

* 启动映射

   >[!CAUTION]
   >
   >启动映射功能要求核心组件版本2.1.0或更高版本以及 [AEM 6.4的](https://docs.adobe.com/content/help/en/experience-manager-64/release-notes/sp-release-notes.html) service pack 2 [，或AEM 6.3的](https://helpx.adobe.com/experience-manager/6-3/release-notes/sp3-release-notes.html) service pack 3 [，以支持AEM中的新](https://docs.adobe.com/content/help/en/experience-manager-64/developing/components/image-editor.html) 图像编辑器功能。

   ![](assets/chlimage_1-12.png)

   使用此选项可将启动映射应用到图像。 选择此选项将打开一个新窗口，用户可以选择映射的形状：

   * **添加矩形映射**
   * **添加圆形图**
   * **添加多边形映射**
      * 默认情况下，添加三角形映射。 双击形状的一行以在新侧添加新的蓝色调整大小手柄。
   一旦选择了映射形状，它就会叠加在图像上以允许调整大小。 拖放蓝色的调整大小手柄以调整形状。

   ![](assets/chlimage_1-13.png)

   调整启动映射的大小后，单击它以打开一个浮动工具栏以定义链接的路径。

   * **路径**
      * 使用路径选取器选项在AEM中选择路径
      * 如果路径不在AEM中，请使用绝对URL。 非绝对路径将被解释为相对于AEM。
   * **替代文本**&#x200B;路径目标的替代说明
   * **目标**
      * **相同选项卡**
      * **“新建”选项卡**
      * **父框架**
      * **顶层框架**
   点按或单击蓝色复选标记以保存，单击黑色x以取消，单击红色垃圾桶以删除地图。

   ![](assets/chlimage_1-14.png)

* 重置缩放

   ![](assets/chlimage_1-15.png)

   如果图像已经缩放，请使用此选项重置缩放级别。

* 打开缩放滑块

   ![](assets/chlimage_1-16.png)

   使用此选项可显示一个滑块来控制图像的缩放级别。

   ![](assets/chlimage_1-17.png)

就地编辑器还可用于修改图像。 由于空间限制，只有基本选项在线可用。 对于完整编辑选项，请使用全屏模式。

![](assets/chlimage_1-18.png)

>[!NOTE]
>
>GIF图像不支持图像编辑操作（裁剪、翻转、旋转）。 在编辑模式下对GIF所做的任何此类更改都将不会被保留。

## 设计对话框 {#design-dialog}

设计对话框允许模板作者定义内容作者在使用此组件时具有的裁剪、上传和旋转以及上传选项。

### 主选项卡 {#main-tab}

在“主 **要** ”选项卡上，您可以为图像定义宽度列表（以像素为单位），组件将根据浏览器大小自动加载最合适的宽度。 这是图像组件响应式功 [能的重](#responsive-features) 要部分。

此外，您还可以定义在作者将组件添加到页面时自动或禁用的常规组件选项。

![](assets/screenshot_2018-10-19at102756.png)

* **启用延迟加**&#x200B;载定义在将图像组件添加到页面时是否自动启用延迟加载选项。
* **图像具有装饰**&#x200B;性在将图像组件添加到页面时，定义装饰性图像选项是否自动启用。
* **从DAM获取替代文本**&#x200B;在将图像组件添加到页面时，定义是否自动启用从DAM检索替代文本的选项。
* **从DAM获取题注**&#x200B;将图像组件添加到页面时，定义是否自动启用从DAM检索题注的选项。
* **将题注显示为弹出窗口**&#x200B;在将图像组件添加到页面时，定义将图像题注显示为弹出窗口的选项是否自动启用。
* **禁用UUID跟踪**&#x200B;检查以禁用对图像资产UUID的跟踪。

* **宽度**&#x200B;定义图像的宽度列表（以像素为单位），组件会根据浏览器大小自动加载最合适的宽度。
   * 点按或单击添 **加按钮** ，以添加其他大小。
      * 使用抓取手柄重新排列大小的顺序。
      * 使用“删 **除** ”图标删除宽度。
   * 默认情况下，加载图像会延迟到它们可见。
      * 选择选项“ **禁用延迟加载** ”，以在页面加载时加载图像。
* **JPEG质量**&#x200B;转换的JPEG图像的质量因子（以百分比表示，范围为0和100）（例如，缩放或裁剪）。

>[!CAUTION]
>
>“JPEG质量”选项自“核心组件”的2.2.0版起可用。

>[!NOTE]
>
>自核心组件版本2.2.0起，图像组件将唯一的UUID属性添加到图像资产，以便跟踪和分析各个资产接收的查看次数。 `data-asset-id`

### 功能选项卡 {#features-tab}

在“功 **能** ”选项卡上，您可以定义在使用组件（包括上传选项、方向和裁剪选项）时内容作者可以使用的选项。

* 源

   ![](assets/chlimage_1-19.png)

   选择“允 **许从文件系统上传资产** ”选项，以允许内容作者从其本地计算机上传图像。 要强制内容作者仅从AEM中选择资产，请取消选择此选项。

* 方向

   ![](assets/chlimage_1-20.png)

* **旋转**&#x200B;使用此选项可允许内容作者使用“向右旋 **转** ”选项。
* **翻转**&#x200B;使用此选项可允许内容作者使用“水平翻转” **和“垂直** 翻转”选项 **** 。

   >[!CAUTION]
   >
   >默认情 **况下** ,“翻转”选项处于禁用状态。 启用此功能后，将在图像组件的编辑对话框中显示“垂直翻转 ******** ”和“水平翻转”按钮，但AEM当前不支持该功能，并且使用这些选项所做的任何更改都不会被保留。

* 裁剪

   ![](assets/chlimage_1-21.png)

   选择“允 **许裁剪** ”选项，以允许内容作者在编辑对话框中裁剪组件中的图像。
   * 单击 **“添加** ”以添加预定义的裁剪长宽比。
   * 输入描述性名称，该名称将显示在“开始裁 **剪”下拉列** 表中。
   * 输入长宽比的数值。
   * 使用拖动手柄重新排列长宽比的顺序
   * 使用垃圾桶图标删除长宽比。
   >[!CAUTION]
   >
   >Note that in AEM, crop aspect ratios are defined as **height/width**. 这与传统的宽度／高度定义不同，这是出于传统兼容性的考虑。 只要您提供比率的明确名称，内容作者就不会察觉到任何差异，因为该名称显示在UI中，而不是比率本身。

### 样式选项卡 {#styles-tab-1}

图像组件支持AEM样 [式系统](authoring.md#component-styling)。

## 自适应图像Servlet {#adaptive-image-servlet}

图像组件使用核心组件的自适应图像Servlet。 [自适应图像Servlet负责图像处理和流化](https://github.com/adobe/aem-core-wcm-components/wiki/The-Adaptive-Image-Servlet) ，开发人员可以利用它们对核心组件 [的自定义设置](customizing.md)。

>[!NOTE]
>
>自适应图像Servlet `Last-Modified` 支持通过头的条件请求，但需要在调度程序中启 `Last-Modified` 用 [头的缓存](https://docs.adobe.com/content/help/en/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html#caching-http-response-headers)。
>
>[AEM Project Archetype的示例Dispatcher配置已包含此配置](overview.md)。
