---
title: 图像组件
description: 核心组件图像组件是自适应图像组件功能就地编辑。
role: Architect, Developer, Administrator, Business Practitioner
exl-id: c5e57f4b-139f-40e7-8d79-be9a74360b63
source-git-commit: 8ff36ca143af9496f988b1ca65475497181def1d
workflow-type: tm+mt
source-wordcount: '2170'
ht-degree: 2%

---

# 图像组件{#image-component}

核心组件图像组件是具有就地编辑功能的自适应图像组件。

## 使用 {#usage}

图像组件为页面访客提供了自适应图像选择和响应行为功能，包括延迟加载，以及为内容作者轻松放置图像和裁剪图像。

模板作者可以在[设计对话框](#design-dialog)中定义图像宽度以及裁剪和其他设置。 内容编辑器可以上传或选择[配置对话框](#configure-dialog)中的资产，并在[编辑对话框](#edit-dialog)中裁剪图像。 为了更方便起见，还提供简单的图像就地修改。

## 响应功能{#responsive-features}

图像组件提供了开箱即用的强大响应功能。 在页面模板级别，可以使用[设计对话框](#design-dialog)定义图像资产的默认宽度。 然后，图像组件将自动加载正确的宽度以根据浏览器窗口的大小显示。 在调整窗口大小时，图像组件会动态加载正确的图像大小。 组件开发人员无需担心定义自定义媒体查询，因为图像组件已经过优化以加载您的内容。

此外，图像组件还支持延迟加载，以便将实际图像资产的加载推迟到在浏览器中可见为止，从而提高页面的响应性。

## Dynamic Media支持{#dynamic-media}

图像组件(从[版本2.13.0](/help/versions.md)开始)支持[Dynamic Media](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/dynamicmedia/dynamic-media.html?lang=en#dynamicmedia)资产。 [启用后，](#design-dialog) 这些功能允许您通过简单的拖放操作，或通过资产浏览器添加Dynamic Media图像资产，就像您使用任何其他图像一样。此外，还支持图像修饰符、图像预设和智能裁剪。

使用核心组件构建的Web体验不能提供功能丰富、Sensei支持、强大、高性能、跨平台的Dynamic Media图像功能。

## 版本和兼容性{#version-and-compatibility}

图像组件的当前版本为v2，该版本于2018年1月随核心组件版本2.0.0一起引入，在本文档中进行了描述。

下表详细列出了组件的所有受支持版本、组件版本与之兼容的AEM版本，以及指向以前版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v2 | 兼容 | 兼容 | 兼容 |
| [v1](v1/image-v1.md) | 兼容 | 兼容 | - |

有关核心组件版本和版本的更多信息，请参阅文档[核心组件版本](/help/versions.md)。

## SVG支持{#svg-support}

图像组件支持可缩放矢量图形(SVG)。

* 同时支持从DAM拖放SVG资产和从本地文件系统上传SVG文件。
* 自适应图像Servlet对原始SVG文件进行流式处理（跳过转换）。
* 对于SVG图像，“智能图像”和“智能大小”将在图像模型中设置为空数组。

### 安全 {#security}

出于安全考虑，图像编辑器从不直接调用原始SVG。 它通过`<img src=“path-to-component”>`调用。 这会阻止浏览器执行嵌入在SVG文件中的任何脚本。

>[!CAUTION]
>
>SVG支持要求核心组件版本2.1.0或更高版本以及适用于AEM 6.4或更高版本的[Service Pack 2](https://docs.adobe.com/content/help/zh-Hans/experience-manager-64/release-notes/sp-release-notes.html)，以支持AEM中的[图像编辑器功能](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/components-templates/image-editor.html)。

## 组件输出示例{#sample-component-output}

要体验图像组件并查看其配置选项以及HTML和JSON输出的示例，请访问[组件库](https://adobe.com/go/aem_cmp_library_image)。

### 技术详细信息{#technical-details}

有关图像组件[的最新技术文档，请参阅GitHub](https://adobe.com/go/aem_cmp_tech_image_v2)。

有关开发核心组件的更多详细信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

图像组件支持[schema.org微数据](https://schema.org)。

## 配置对话框{#configure-dialog}

除了标准的[编辑对话框](#edit-dialog)和[设计对话框](#design-dialog)之外，图像组件还提供一个配置对话框，在其中定义了图像本身及其描述和基本属性。

### 资产选项卡{#asset-tab}

![图像组件配置对话框的资产选项卡](/help/assets/image-configure-asset.png)

* **图像资产**
   * 从[资产浏览器](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html)中删除资产，或点按&#x200B;**browse**&#x200B;选项，以从本地文件系统上传。
   * 点按或单击&#x200B;**清除**&#x200B;以取消选择当前选定的图像。
   * 点按或单击&#x200B;**编辑** ，以在资产编辑器中[管理资产的演绎版。](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/assets/manage/manage-digital-assets.html)

### 元数据选项卡{#metadata-tab}

![图像组件配置对话框的元数据选项卡](/help/assets/image-configure-metadata.png)

* **预设类型**  — 此设置定义了可用的图像预设类型(图像预 **设** 器智能裁剪 **)，并且仅在启用Dynamic Media功能**&#x200B;后 [](#dynamic-meida) 才可用。
   * **图像预设**  — 选 **择** 预设类 **型** 图像 **预设后，下拉图像预设将** 可用，允许从可用的Dynamic Media预设中进行选择。仅当为选定的资产定义了预设时，此选项才可用。
   * **智能裁剪**  — 选 **择** 预设 **类型** 智 **** 能裁剪时，下拉菜单可用，允许从选定资产的可用演绎版中进行选择。仅当为选定的资产定义了演绎版时，此选项才可用。
   * **图像修饰符**  — 此处可以分隔其他Dynamic Media图像提供命令，无论选择哪种预 `&`设 **** 类型。
* **图像具有装饰性**  — 检查图像是否应被辅助型技术忽略，因此不需要替换文本。这仅适用于装饰性图像。
* **替换文本**  — 为视觉障碍读者提供图像含义或功能的替换文本。
   * **从DAM获取替换文本**  — 选中此选项后，图像的替换文本将填充DAM中元 `dc:description` 数据的值。
* **标题**  — 有关图像的其他信息，默认显示在图像下方。
   * **从DAM获取标题**  — 选中此选项后，图像的标题文本将填充DAM中元 `dc:title` 数据的值。
   * **将题注显示为弹出窗口**  — 选中此选项后，题注不会显示在图像下方，而是会在将鼠标悬停在图像上方时显示为某些浏览器显示的弹出窗口。
* **链接**  — 将图像链接到其他资源。
   * 使用选择对话框链接到其他AEM资源。
   * 如果未关联到AEM资源，请输入绝对URL。 非溶质URL将解释为相对于AEM。
* **ID**  — 利用此选项，可控制HTML和数据层中组件的唯一标识符 [的唯一标识符](/help/developing/data-layer/overview.md)。
   * 如果留为空白，则会自动为您生成唯一ID，并且可以通过检查生成的页面找到该ID。
   * 如果指定了ID，则作者有责任确保该ID是唯一的。
   * 更改ID可能会影响CSS、JS和数据层跟踪。

>[!TIP]
>
>**智能交** 叉和图 **像预** 设是互斥选项。如果作者需要将图像预设和智能裁剪呈现版本一起使用，则作者必须使用&#x200B;**图像修饰符**&#x200B;来手动添加预设。

## 编辑对话框{#edit-dialog}

编辑对话框允许内容作者裁剪、修改启动映射和缩放图像。

>[!NOTE]
>
>裁剪、旋转和缩放功能不适用于Dynamic Media资产。 如果启用了[Dynamic Media功能](#dynamic-media)，则对Dynamic Media资产执行任何此类编辑操作时都应通过[配置对话框。](#configure-dialog)

![图像组件的编辑对话框](/help/assets/image-edit.png)

* 开始裁剪

   ![开始裁剪图标](/help/assets/image-start-crop.png)

   选择此选项将打开一个下拉列表，显示预定义的裁剪比例。

   * 选择选项&#x200B;**Free Hand**&#x200B;以定义您自己的裁剪。
   * 选择选项&#x200B;**删除裁剪**&#x200B;以显示原始资产。

   选择裁剪选项后，使用蓝色手柄调整图像上裁剪的大小。

   ![裁剪选项](/help/assets/image-crop-options.png)

* 向右旋转

   ![右旋转图标](/help/assets/image-rotate-right.png)

   使用此选项将图像90°向右（顺时针）旋转。

* 水平翻转

   ![水平翻转图标](/help/assets/image-flip-horizontal.png)

   使用此选项可水平翻转图像或沿y轴旋转图像180°。

* 垂直翻转

   ![垂直翻转图标](/help/assets/image-flip-vertical.png)

   使用此选项可垂直翻转图像或沿x轴旋转图像180°。

* 重置缩放

   ![重置缩放图标](/help/assets/image-reset-zoom.png)

   如果图像已缩放，则使用此选项可重置缩放级别。

* 打开缩放滑块

   ![打开缩放滑块图标](/help/assets/image-zoom.png)

   使用此选项可显示一个滑块来控制图像的缩放级别。

   ![缩放滑块控件](/help/assets/image-zoom-slider.png)

就地编辑器也可用于修改图像。 由于空间限制，只有基本选项在线可用。 要获取完整编辑选项，请使用全屏模式。

![图像就地编辑选项](/help/assets/image-in-place-edit.png)

>[!NOTE]
>
>GIF图像不支持图像编辑操作（裁剪、翻转、旋转）。 在编辑模式下对GIF所做的任何此类更改将不会持久保留。

## 设计对话框{#design-dialog}

设计对话框允许模板作者定义内容作者在使用此组件时拥有的裁剪、上传和旋转及上传选项。

### 主选项卡{#main-tab}

在&#x200B;**主**&#x200B;选项卡上，您可以定义图像的宽度列表（以像素为单位），组件将根据浏览器大小自动加载最合适的宽度。 这是图像组件[响应功能](#responsive-features)的重要部分。

此外，您还可以定义作者将组件添加到页面时自动或禁用的常规组件选项。

![图像组件的设计对话框主选项卡](/help/assets/image-design-main.png)

* **启用DM功能**  — 选中此选项后，启用Dynamic Media [功能](#dynamic-media) 将可用。
* **启用延迟加载**  — 定义在将图像组件添加到页面时是否自动启用延迟加载选项。
* **图像具有装饰性**  — 定义在向页面添加图像组件时是否自动启用装饰性图像选项。
* **从DAM获取替代文本** — 定义在将图像组件添加到页面时，是否自动启用从DAM检索替代文本的选项。
* **从DAM获取标题**  — 定义在将图像组件添加到页面时，是否自动启用从DAM检索标题的选项。
* **将标题显示为弹出窗口**  — 定义在将图像组件添加到页面时，是否自动启用将图像标题显示为弹出窗口的选项。
* **禁用UUID跟踪**  — 选中此选项可禁用图像资产的UUID跟踪。
* **宽度**  — 为图像定义宽度列表（以像素为单位），组件会根据浏览器大小自动加载最合适的宽度。
   * 点按或单击&#x200B;**Add**&#x200B;按钮以添加其他大小。
      * 使用抓握手柄重新排列大小的顺序。
      * 使用&#x200B;**删除**&#x200B;图标删除宽度。
   * 默认情况下，图像加载会延迟到可见为止。
      * 选择选项&#x200B;**禁用延迟加载** ，以在页面加载时加载图像。
* **JPEG质量**  — 已转换（例如，缩放或裁剪）JPEG图像的质量因子（以0和100的百分比表示）。

### “功能”选项卡{#features-tab}

在&#x200B;**功能**&#x200B;选项卡上，您可以定义在使用组件（包括上传选项、方向和裁剪选项）时，内容作者可以使用的选项。

* 源

   ![图像组件的设计对话框功能选项卡](/help/assets/image-design-features-source.png)

   选择选项&#x200B;**允许从文件系统上传资产**&#x200B;以允许内容作者从其本地计算机上传图像。 要强制内容作者仅从AEM中选择资产，请取消选择此选项。

* 方向

   ![图像组件的设计对话框功能选项卡](/help/assets/image-design-features-orientation.png)

* ****
旋转使用此选项可允许内容作者使用 
**右** 旋。
* ****
反向使用此选项可允许内容作者使用 
**“水平翻** 转”和“垂直 **翻** 转”选项。

   >[!CAUTION]
   >
   >默认情况下，**Flip**&#x200B;选项处于禁用状态。 启用此选项将在图像组件的编辑对话框中显示&#x200B;**垂直翻转**&#x200B;和&#x200B;**水平翻转**&#x200B;按钮，但AEM当前不支持该功能，并且不会保留使用这些选项所做的任何更改。

* 裁剪

   ![图像组件的设计对话框功能选项卡](/help/assets/image-design-features-cropping.png)

   选择选项&#x200B;**允许裁剪** ，以允许内容作者在编辑对话框中裁剪组件中的图像。
   * 单击&#x200B;**Add**&#x200B;以添加预定义的裁剪宽高比。
   * 输入描述性名称，该名称将显示在&#x200B;**开始裁剪**&#x200B;下拉列表中。
   * 输入宽高比的数值。
   * 使用拖动手柄重新排列长宽比的顺序
   * 使用垃圾桶图标删除宽高比。

   >[!CAUTION]
   >
   >请注意，在AEM中，裁剪长宽比被定义为&#x200B;**高度/宽度**。 这与常见的宽高比的定义不同，这样做是出于对旧版兼容性的考虑。只要您提供了比率的明确名称，内容作者便不会察觉到任何差异，因为该名称会显示在UI中，而不是比率本身。

### 样式选项卡{#styles-tab-1}

图像组件支持AEM [样式系统](/help/get-started/authoring.md#component-styling)。

## 自适应图像Servlet {#adaptive-image-servlet}

图像组件使用核心组件的自适应图像Servlet。 [自适应图像](https://github.com/adobe/aem-core-wcm-components/wiki/The-Adaptive-Image-Servlet) 服务器负责图像处理和流处理，开发人员可以利用它们自 [定义核心组件](/help/developing/customizing.md)。

>[!NOTE]
>
>通过`Last-Modified`标头的条件请求受自适应图像Servlet支持，但是`Last-Modified`标头[的缓存需要在Dispatcher](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html?lang=en#caching-http-response-headers)中启用。
>
>[AEM项目原型](/help/developing/archetype/overview.md)的示例Dispatcher配置已包含此配置。

## Adobe客户端数据层{#data-layer}

图像组件支持[Adobe客户端数据层。](/help/developing/data-layer/overview.md)
