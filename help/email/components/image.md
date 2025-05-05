---
title: 电子邮件图像组件
description: 电子邮件图像组件是一个自适应图像组件，具备就地编辑的功能。
role: Architect, Developer, Admin, User
exl-id: f5d40047-3082-4edd-a5f6-6ab3e33997f9
source-git-commit: 91969e4956bef1a511b8d588d5290a7999bf86ec
workflow-type: tm+mt
source-wordcount: '1624'
ht-degree: 100%

---


# 电子邮件图像组件 {#email-image-component}

电子邮件图像组件是一个自适应图像组件，具备就地编辑的功能。

## 用途 {#usage}

电子邮件图像组件具有自适应图像选择和响应行为，为页面访问者提供延迟加载，以及为内容作者提供简单的拖放图像投放和配置。

* 模板作者可以在[“设计”对话框](#design-dialog)中定义图像宽度以及其他设置。
* 内容编辑者可以在[“配置”对话框](#configure-dialog)中上传或选择资源。

## 版本和兼容性 {#version-and-compatibility}

电子邮件图像组件的当前版本是 v1，此版本随 2022 年 10 月的电子邮件核心组件发行版本 X 的发布引入，具体说明见本文档。

下表详细说明了该组件的所有受支持版本、与该组件的版本兼容的 AEM 版本以及指向早期版本文档的链接。

| 组件版本 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|---|---|---|---|
| v1 | 兼容 | - | - |

有关核心组件版本的更多信息，请参阅文档[电子邮件核心组件版本](/help/email/versions.md)。

## 响应式功能 {#responsive-features}

电子邮件图像组件提供了可靠的响应式功能，可以直接使用。 在页面模板级别，可以使用[“设计”对话框](#design-dialog)来定义图像资源的默认宽度。然后，电子邮件图像组件将自动加载正确的宽度，可根据浏览器窗口的大小进行显示。 在窗口调整大小时，电子邮件图像组件即时动态加载正确的图像大小。 组件开发人员无需担心自定义媒体查询的定义方式，因为电子邮件图像组件已经针对加载内容进行了优化。

此外，电子邮件图像组件支持延迟加载，可以将实际图像资源的加载推迟到在浏览器中可见时，从而提升了内容的响应能力。

>[!TIP]
>
>默认情况下，电子邮件图像组件由自适应图像 Servlet 提供支持。 有关其工作原理的详细信息，请参阅[自适应图像 Servlet](#adaptive-image-servlet)。

## Dynamic Media 支持 {#dynamic-media}

电子邮件图像组件支持 [Dynamic Media](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/dynamicmedia/dynamic-media.html?lang=zh-Hans#dynamicmedia) 资源。 [在启用时](#design-dialog)，这些功能提供了一种能力，即通过简单的拖放功能或者通过资源浏览器，就可以像对任何其他图像一样加载 Dynamic Media 图像资源。此外还支持图像修饰符、图像预设和智能裁切。

使用电子邮件核心组件构建的电子邮件体验现在具备丰富、支持 Sensei、可靠、高性能、跨平台的 Dynamic Media 图像功能。

## SVG 支持 {#svg-support}

电子邮件图像组件支持可缩放矢量图 (SVG)。

* 从 DAM 拖放上传 SVG 资源以及从本地文件系统上传 SVG 文件均受支持。
* 对原始 SVG 文件进行流式处理（跳过转换）。
* 对于 SVG 图像，“智能图像”和“智能大小”均设置为图像模型中的空数组。

### 安全性 {#security}

为安全起见，图像编辑器从不直接调用原始 SVG。通过 `<img src=“path-to-component”>` 调用它。这可以防止浏览器执行在 SVG 文件中嵌入的任何脚本。

### 技术详细信息 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_email_image_v1_cn)有关电子邮件图像组件的最新技术文档。

在[核心组件开发人员文档](/help/developing/overview.md)中可找到有关开发核心组件的其他详细信息。

图像组件支持 [schema.org 微数据。](https://schema.org)

## “配置”对话框 {#configure-dialog}

电子邮件图像组件提供了一个“配置”对话框，其中定义了图像本身及其描述和基本属性。

### “资源”选项卡 {#asset-tab}

![电子邮件图像组件“配置”对话框的“资源”选项卡](/help/email/assets/email-image-configure-asset.png)

* **从页面继承精选图像** – 此选项使用[链接页面的精选图像](page.md)或当前页面的精选图像（如果未链接图像）。

* **用于辅助功能的替换文本** – 此字段允许您为视障用户定义图像的描述。

   * **从页面继承替换文本** – 此选项使用 DAM 中 `dc:description` 元数据的链接资源值的替代描述或当前页面的替代描述（如果未链接资源）。

* **图像资源**
   * 通过[资源浏览器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/environment-tools.html?lang=zh-Hans)拖放资源或点击&#x200B;**浏览**&#x200B;选项，以从本地文件系统上传。
   * 点按或单击&#x200B;**“清除”**&#x200B;以取消选择当前选定的图像。
   * 点按或单击&#x200B;**“编辑”**&#x200B;可在“资产编辑器中”[管理资产的再现](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/manage-digital-assets.html?lang=zh-Hans)。

* **不提供替换文本** – 此选项将图像标记为被屏幕阅读器等辅助技术忽略，以用于图像纯粹起装饰作用或不向页面传达额外信息的情况。

* **禁用延迟加载** – 此选项预加载所有图像组件，而不根据需要加载。

### “元数据”选项卡 {#metadata-tab}

![图像组件“配置”对话框的“元数据”选项卡](/help/email/assets/email-image-configure-metadata.png)

* **预设类型** – 这定义了可用图像预设的类型，可以是&#x200B;**图像预设**&#x200B;或&#x200B;**智能裁切**，并且仅在启用了 [Dynamic Media 功能](#dynamic-meida)的情况下可用。
   * **图像预设** - 选中了&#x200B;**图像预设**&#x200B;的&#x200B;**预设类型**&#x200B;时，下拉菜单&#x200B;**图像预设**&#x200B;可用，并允许从可用的 Dynamic Media 预设中选择。 此项只有在为所选资源定义了预设时才可用。
   * **智能裁切** - 选中了&#x200B;**智能裁切**&#x200B;的&#x200B;**预设类型**&#x200B;时，下拉菜单&#x200B;**再现**&#x200B;可用，并允许从所选资源的可用再现中选择。 此项只有在为所选资源定义了再现时才可用。
   * **图像修饰符** - 在这里可以定义其他 Dynamic Media 图像服务命令，不论选择了什么&#x200B;**预设类型**，都使用 `&` 分隔。
* **题注** – 有关图像的附加信息，默认显示在图像的下方。
   * **从 DAM 获取题注** – 选中时，将使用 DAM 中 `dc:title` 元数据的值填充图像的题注文本。仅在从 DAM 中选择资产时可用。
   * **以弹出窗口显示题注** – 选中后，不会在图像下方显示题注，但在某些浏览器中，将鼠标悬停于图像上方时，会以弹出信息形式显示题注。
* **链接** – 将图像链接到其他资源。
   * 使用“选择”对话框可链接到其他 AEM 资源。
   * 如果未链接到 AEM 资源，请输入绝对 URL。非绝对 URL 将解释为相对于 AEM。
   * **在新标签页中打开链接** – 此选项在一个新的浏览器窗口中打开链接。
* **ID** - 此选项允许控制 HTML 中组件的唯一标识符。
   * 如果留空，则自动为您生成一个唯一 ID，通过检查所得页面即可找到该 ID。
   * 如果指定一个 ID，作者有责任确保它是唯一的。
   * 更改 ID 会对 CSS 产生影响。
* **固定为** – 此选项定义图像的宽度（以像素为单位）。
* **将图像缩放到可用宽度** – 此选项将 `"width":"100%"` 应用到图像样式属性。

>[!TIP]
>
>**智能裁切**&#x200B;和&#x200B;**图像预设**&#x200B;为互斥选项。如果作者需要使用图像预设配合智能裁切演绎版，则作者必须使用&#x200B;**图像修饰符**&#x200B;手动添加预设。

### “样式”选项卡 {#styles-tab-edit}

![电子邮件图像组件“编辑”对话框的“样式”选项卡](/help/assets/image-configure-styles.png)

电子邮件图像组件支持 AEM [样式系统。](/help/get-started/authoring.md#component-styling)

使用下拉菜单选择要应用于该组件的样式。在“编辑”对话框中所做的选择与从组件工具栏中选择的操作效果相同。

必须在[“设计”对话框](#design-dialog)中为此组件配置样式，以便选项卡可用。

## “设计”对话框 {#design-dialog}

### 主选项卡 {#main-tab}

![图像组件“设计”对话框的主选项卡](/help/email/assets/email-image-design-main.png)

* **启用 DM 功能** – 在选中时，[Dynamic Media 功能](#dynamic-media)可用。
   * 仅当环境中启用了 Dynamic Media 时，才会出现此选项。
* **启用 Web 优化图像** – 选中后，[Web 优化图像传送服务](/help/developing/web-optimized-image-delivery.md)将以 WebP 格式传送图像，使图像大小平均减少 25%。
   * 此选项仅在 AEMaaCS 中可用。
   * 当未选中或 Web 优化图像投放服务不可用时，将使用[自适应图像 Servlet](/help/developing/adaptive-image-servlet.md)。
* **图像是装饰性的** – 定义在将图像组件添加到页面时，是否自动启用装饰性图像选项。
* **从 DAM 获取替换文本** – 定义在将图像组件添加到页面时，是否自动启用从 DAM 检索替换文本的选项。
* **从 DAM 获取题注** – 定义在将图像组件添加到页面时，是否自动启用从 DAM 检索题注的选项。
* **以弹出窗口显示题注** – 定义在将图像组件添加到页面时，是否自动启用以弹出窗口显示图像题注的选项。
* **调整宽度** – 此值用于调整作为 DAM 资源的基本图像的宽度。
   * 图像的长宽比将被保留。
   * 如果该值大于图像的实际宽度，则该值无效。
   * 该值对 SVG 图像没有影响。

您可以定义图像的宽度（以像素为单位），组件将根据浏览器的大小自动加载最合适的宽度。这是电子邮件图像组件的[响应式功能](#responsive-features)的重要组成部分。

* **宽度** – 定义图像的宽度（以像素为单位），组件将根据浏览器的大小自动加载最合适的宽度。
   * 点按或单击&#x200B;**“添加”**&#x200B;按钮可添加其他大小。
      * 使用抓取手柄可重新排列大小。
      * 使用&#x200B;**“删除”**&#x200B;图标可删除宽度。
   * 默认情况下，图像加载会被延迟，直到图像变得可见。
      * 选择&#x200B;**禁用延迟加载**&#x200B;选项可在页面加载时加载图像。
* **JPEG 质量** – 用于转换（例如，缩放或裁切）的 JPEG 图像的质量系数（以从 0 到 100 的百分比表示）。
* **默认宽度** - 将在设计对话框中使用的默认图像宽度（以像素为单位）

>[!TIP]
>
>查看文档[自适应图像 Servlet](/help/developing/adaptive-image-servlet.md) 以了解通过仔细定义宽度来优化演绎版选择的提示。

### 样式选项卡 {#styles-tab}

电子邮件图像组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。
