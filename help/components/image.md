---
title: 图像组件
description: 核心组件图像组件是自适应图像组件。
role: Architect, Developer, Admin, User
exl-id: c5e57f4b-139f-40e7-8d79-be9a74360b63
source-git-commit: 5d2d79c96dc934efd7cccefb1a6a343813376483
workflow-type: tm+mt
source-wordcount: '1957'
ht-degree: 100%

---


# 图像组件 {#image-component}

核心组件图像组件是自适应图像组件。

## 用途 {#usage}

图像组件具有自适应图像选择和响应式行为，页面访客可以延迟加载，内容作者可以轻松放置图像。

内容作者可使用[“编辑”对话框](#edit-dialog)编辑图像资源，如应用裁切或旋转图像。

模板作者可以在[“设计”对话框](#design-dialog)中定义图像宽度以及其他设置。内容编辑者可以在[“配置”对话框](#configure-dialog)中上传或选择资源。

## 版本和兼容性 {#version-and-compatibility}

图像组件的当前版本是 v3，此版本随 2022 年 2 月的核心组件发行版 2.18.0 的发布引入，具体说明见本文。

下表详述所有支持的组件版本、组件版本与其兼容的 AEM 版本以及旧版文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|--- |--- |--- |---|
| v3 | - | 兼容 | 兼容 |
| [v2](v2/image.md) | 兼容 | 兼容 | 兼容 |
| [v1](v1/image-v1.md) | 兼容 | 兼容 | 兼容 |

有关核心组件版本的更多信息，请参阅文档[核心组件版本](/help/versions.md)。

## 响应式功能 {#responsive-features}

图像组件提供了可靠的响应式功能，可以直接使用。在页面模板级别，可以使用[“设计”对话框](#design-dialog)来定义图像资源的默认宽度。图像组件根据浏览器窗口的大小，自动加载适合显示的宽度。在窗口调整大小时，图像组件即时动态加载正确的图像大小。组件开发人员无需担心自定义媒体查询的定义方式，因为图像组件已经针对加载内容进行了优化。

此外，图像组件支持延迟加载，可以将实际图像资源的加载推迟到在浏览器中可见时，从而提升了页面的响应能力。

>[!TIP]
>
>默认情况下，图像组件由自适应图像 Servlet 提供支持。 有关其工作原理的详细信息，请参阅[自适应图像 Servlet](/help/developing/adaptive-image-servlet.md)。

## Dynamic Media 支持 {#dynamic-media}

图像组件（截止 [发行版本 2.13.0](/help/versions.md)）支持 [Dynamic Media](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/assets/dynamicmedia/dynamic-media.html) 资源。[在启用时](#design-dialog)，这些功能提供了一种能力，即通过简单的拖放功能或者通过资源浏览器，就可以像对任何其他图像一样加载 Dynamic Media 图像资源。此外还支持图像修饰符、图像预设和智能裁切。

使用核心组件构建的 Web 体验现在具备丰富、支持 Sensei、可靠、高性能、跨平台的 Dynamic Media 图像功能。

## 远程资产支持 {#remote-assets}

图像组件（截止 [发行版本 2.23.2](/help/versions.md)）支持远程资产。[配置后，](/help/developing/remote-assets.md) 您可以从远程服务中为您的图像组件选择资产。

## SVG 支持 {#svg-support}

图像组件支持可缩放矢量图 (SVG)。

* 支持从 DAM 拖放 SVG 资源以及从本地文件系统上传 SVG 文件。
* 对原始 SVG 文件进行流式处理（跳过转换）。
* 对于 SVG 图像，“智能图像”和“智能大小”均设置为图像模型中的空数组。

### 安全性 {#security}

为安全起见，图像编辑器从不直接调用原始 SVG。通过 `<img src="path-to-component">` 调用它。这可以防止浏览器执行在 SVG 文件中嵌入的任何脚本。

## 示例组件输出 {#sample-component-output}

要体验图像组件并查看其配置选项以及 HTML 和 JSON 输出的示例，请访问[组件库](https://adobe.com/go/aem_cmp_library_image_cn)。

### 技术详细信息 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_image_v3_cn)有关图像组件的最新技术文档。

在[核心组件开发人员文档](/help/developing/overview.md)中可找到有关开发核心组件的其他详细信息。

图像组件支持 [schema.org 微数据](https://schema.org)。

## “编辑”对话框 {#edit-dialog}

利用“编辑”对话框，内容作者可以裁切和缩放图像。

根据是否启用了 [Dynamic Media](#dynamic-media) 或 [远程资产支持](#remote-assets) 功能，对于编辑图像可用的选项有所不同。

### 编辑标准资源 {#standard-assets}

如果编辑标准 AEM 资源，可在图像组件的上下文菜单中单击&#x200B;**编辑**&#x200B;图标。

![图像组件的“编辑”对话框](/help/assets/image-edit.png)

* 开始裁切

  ![开始裁切图标](/help/assets/image-start-crop.png)

  选择此选项将打开一个预定义裁切比例的下拉菜单。

   * 选择&#x200B;**删除裁切**&#x200B;可显示原始资源。

  选择一个裁切选项后，可使用蓝色手柄调整图像上的裁切大小。

  ![裁切选项](/help/assets/image-crop-options.png)

* 向右旋转

  ![向右旋转图标](/help/assets/image-rotate-right.png)

  使用此选项可将图像向右（顺时针）旋转 90°。

* 重置缩放

  ![重置缩放图标](/help/assets/image-reset-zoom.png)

  如果图像已缩放，使用此选项可重置缩放级别。

* 打开缩放滑块

  ![打开缩放滑块图标](/help/assets/image-zoom.png)

  使用此选项可显示用于控制图像的缩放级别的滑块。

  ![缩放滑块控件](/help/assets/image-zoom-slider.png)

就地编辑器也可以用于修改图像。由于有空间限制，因此仅将基本选项排成一行。对于完整的编辑选项，请使用全屏模式。

![图像就地编辑选项](/help/assets/image-in-place-edit.png)

>[!NOTE]
>
>GIF 图像不支持编辑图像的操作。在编辑模式下对 GIF 作出的任何此类更改并不持续存在。

### 编辑 Dynamic Media 资源 {#dynamic-media-assets}

如果启用了 [Dynamic Media 功能](#dynamic-media)，则必须在资源控制台中执行对图像本身的编辑。

## “配置”对话框 {#configure-dialog}

图像组件提供了一个“配置”对话框，其中定义了图像本身及其描述和基本属性。

### “资源”选项卡 {#asset-tab}

![图像组件“配置”对话框的“资源”选项卡](/help/assets/image-configure-asset.png)

* **从页面继承精选图像** – 此选项使用[链接页面的精选图像](page.md)或当前页面的精选图像（如果未链接图像）。

* **图像资源** - 如果选中了&#x200B;**从页面继承特色图像**，则自动填充此项。取消选中可通过设置以下选项而手动定义图像。

   * 将资源放置在[资源浏览器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/environment-tools.html)中或点按&#x200B;**浏览**&#x200B;选项，以使您可从本地文件系统上传。
   * 点按或单击&#x200B;**清除**&#x200B;以取消选择当前选择的图像。
   * 点按或单击&#x200B;**选取**&#x200B;以打开[资源浏览器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/environment-tools.html)，以使您可选择图像。
      * 如果启用了 [远程资产支持](#remote-assets)，您有选择资产的多种选项：
         * **本地**&#x200B;从本地 AEM 资源库选择。
         * **远程**&#x200B;从您的 AEM 实例之外的 Dynamic Media 库选择。
   * 点按或单击&#x200B;**“编辑”**&#x200B;可在“资产编辑器中”[管理资产的再现](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/assets/manage/manage-digital-assets.html)。

* **用于辅助功能的替换文本** – 此字段允许您为视障用户定义图像的描述。

   * **从页面继承替换文本** – 此选项使用 DAM 中 `dc:description` 元数据的链接资源值的替代描述或当前页面的替代描述（如果未链接资源）。

* **不提供替换文本** - 标出图像，以使其在图像纯粹起装饰作用或以其他方式不向页面传达额外信息的情况下被屏幕阅读器等辅助技术忽略。

### “元数据”选项卡 {#metadata-tab}

![图像组件“配置”对话框的“元数据”选项卡](/help/assets/image-configure-metadata.png)

* **预设类型** – 这定义了可用图像预设的类型，可以是&#x200B;**图像预设**&#x200B;或&#x200B;**智能裁切**，并且仅在启用了 [Dynamic Media 功能](#dynamic-meida)的情况下可用。
   * **图像预设** - 选中了&#x200B;**图像预设**&#x200B;的&#x200B;**预设类型**&#x200B;时，下拉菜单&#x200B;**图像预设**&#x200B;可用，并允许从可用的 Dynamic Media 预设中选择。 此项只有在为所选资源定义了预设时才可用。
   * **智能裁剪** - 选中&#x200B;**智能裁剪**&#x200B;的&#x200B;**预设类型**&#x200B;时，将有&#x200B;**演绎版**&#x200B;下拉菜单可用，可从中选择所选资源的可用演绎版。只有为所选资源定义了演绎版，才有此项可用。
   * **图像修饰符** – 在这里可以定义其他 Dynamic Media 图像服务命令，不论选择了什么&#x200B;**预设类型**，都使用 `&` 分隔。
* **题注** – 有关图像的附加信息，默认显示在图像的下方。
   * **从 DAM 获取题注** - 选中此项时，为图像的题注文本填入 DAM 中 `dc:title` 元数据的值。
   * **以弹出窗口显示题注** - 选中此项后，将光标悬停在图像上方时，并不在图像下方显示题注，而是被某些浏览器显示为弹出窗口。
* **链接** – 将图像链接到其他资源。
   * 使用“选择”对话框可链接到其他 AEM 资源。
   * 如果未链接到 AEM 资源，请输入绝对 URL。无法解析的 URL 被解释为相对于 AEM。
   * **在新标签页中打开链接** - 此选项在新浏览器窗口中打开链接。
* **ID** - 通过此选项，可控制组件在 HTML 和[数据层](/help/developing/data-layer/overview.md)中的唯一标识符。
   * 如果留空，则自动为您生成一个唯一 ID，通过检查所得页面即可找到该 ID。
   * 如果指定一个 ID，作者有责任确保它是唯一的。
   * 更改 ID 可能会影响 CSS、JS 和数据层跟踪。

>[!TIP]
>
>**智能裁剪**&#x200B;和&#x200B;**图像预设**&#x200B;为互斥选项。如果作者必须使用图像预设配合智能裁剪演绎版，则该作者必须使用&#x200B;**图像修饰符**&#x200B;手动添加预设。

### “样式”选项卡 {#styles-tab-edit}

![图像组件“编辑”对话框的“样式”选项卡](/help/assets/image-configure-styles.png)

图像组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。

使用下拉菜单选择要应用于该组件的样式。在“编辑”对话框中所做的选择与从组件工具栏中选择的操作效果相同。

必须在[“设计”对话框](#design-dialog)中为此组件配置样式，以便有下拉菜单可用。

## “设计”对话框 {#design-dialog}

### 主选项卡 {#main-tab}

![图像组件“设计”对话框的主选项卡](/help/assets/image-design-main.png)

* **启用 DM 功能** – 在选中时，[Dynamic Media 功能](#dynamic-media)可用。
   * 仅当环境中启用了 Dynamic Media 时，才会出现此选项。
* **启用 Web 优化图像** - 选中此项后，[Web 优化图像投放服务](/help/developing/web-optimized-image-delivery.md)以 WebP 格式投放图像，使图像大小平均减小 25%。
   * 仅在 AEMaaCS 中有此选项可用。
   * 当未选中此项或 Web 优化图像投放服务不可用时，将使用[自适应图像 Servlet](/help/developing/adaptive-image-servlet.md)。
* **禁用延迟加载** - 选中此项后，组件预先加载所有图像而不延迟加载。
* **图像是装饰性的** – 定义在将图像组件添加到页面时，是否自动启用装饰性图像选项。
* **从 DAM 获取替换文本** – 定义在将图像组件添加到页面时，是否自动启用从 DAM 检索替换文本的选项。
* **从 DAM 获取题注** – 定义在将图像组件添加到页面时，是否自动启用从 DAM 检索题注的选项。
* **以弹出窗口显示题注** – 定义在将图像组件添加到页面时，是否自动启用以弹出窗口显示图像题注的选项。
* **调整宽度** – 此值用于调整作为 DAM 资源的基本图像的宽度。
   * 保留图像的纵横比。
   * 如果此值大于图像的实际宽度，则此值无效。
   * 此值不影响 SVG 图像。

可为图像定义以像素为单位的宽度的列表，而组件根据浏览器大小自动加载最合适的宽度。这是图像组件的[响应式功能](#responsive-features)的重要组成部分。

* **宽度** – 定义图像的宽度（以像素为单位），组件将根据浏览器的大小自动加载最合适的宽度。
   * 点按或单击&#x200B;**“添加”**&#x200B;按钮可添加其他大小。
      * 使用抓取手柄重新排列大小顺序。
      * 使用&#x200B;**“删除”**&#x200B;图标可删除宽度。
   * 默认情况下，图像加载会被延迟，直到图像变得可见。
      * 选择&#x200B;**禁用延迟加载**&#x200B;选项，以使您可在加载页面时加载图像。
* **JPEG 质量** - 转换（例如，缩放或裁剪）的 JPEG 图像的质量系数（以从 0 到 100 的百分比表示）。

>[!TIP]
>
>查看文档[自适应图像 Servlet](/help/developing/adaptive-image-servlet.md) 以了解通过仔细定义宽度来优化演绎版选择的提示。

### 样式选项卡 {#styles-tab}

图像组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。

## Adobe 客户端数据层 {#data-layer}

图像组件支持 [Adobe 客户端数据层](/help/developing/data-layer/overview.md)。
