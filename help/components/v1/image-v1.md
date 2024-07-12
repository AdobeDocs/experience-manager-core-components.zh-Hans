---
title: 图像组件 (v1)
description: 核心组件图像组件是一个自适应图像组件，具备就地编辑的功能。
index: n
role: Architect, Developer, Admin, User
exl-id: 625ce8de-5c4a-476d-b749-895493d169b1
source-git-commit: 5f25aee6ebcb7a5c6b8db0df5b8b853f15af97d0
workflow-type: tm+mt
source-wordcount: '1293'
ht-degree: 98%

---

# 图像组件 (v1) {#image-component-v}

核心组件图像组件是一个自适应图像组件，具备就地编辑的功能。

## 用途 {#usage}

利用图像组件，可以轻松放置图像资源并提供就地编辑。它具有带延迟加载的自适应图像选择功能以及面向内容作者的裁切功能。

模板作者可以在[“设计”对话框](#design-dialog)中定义允许的图像宽度以及裁切和其他设置。 内容编辑者可以在[“配置”对话框](#configure-dialog)中上传或选择资源，并在[“编辑”对话框](#edit-dialog)中裁切图像。为了增加便利性，还可以简单地就地修改图像。

## 版本和兼容性 {#version-and-compatibility}

本文档介绍了图像组件 (v1)，它最初随带 AEM 6.3 的核心组件 1.0.0 版引入。

下表列出了图像组件 (v1) 的兼容性。

| AEM 版本 | 图像组件 v1 |
|--- |--- |
| 6.3 | 兼容 |
| 6.4 | 兼容 |

>[!CAUTION]
>
>本文档介绍了图像组件 (v1)。
>
>有关当前版本的图像组件的详细信息，请参阅[图像组件](/help/components/image.md)文档。

## 示例组件输出 {#sample-component-output}

以下是摘自 [We.Retail](https://helpx.adobe.com/cn/experience-manager/6-4/sites/developing/using/we-retail.html) 的示例。

### 屏幕快照 {#screenshot}

![](/help/assets/chlimage_1-7.png)

### HTML {#html}

```
<div class="cmp cmp-image aem-GridColumn aem-GridColumn--default--12">
 
        <noscript data-cmp-image="{&#34;smartImages&#34;:[],&#34;smartSizes&#34;:[],&#34;lazyEnabled&#34;:true}">
            <img src="/content/we-retail/us/en/equipment/_jcr_content/root/responsivegrid/image.img.jpg" alt="Surfboard"/>
        </noscript>

</div>
```

### JSON {#json}

```
"image": {
              "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
              "smartSizes": [],
              "smartImages": [],
              "lazyEnabled": true,
              "src": "/content/we-retail/us/en/equipment/equipment/jcr%3acontent/root/responsivegrid/image.img.jpeg",
              ":type": "weretail/components/content/image"
            }
```

>[!NOTE]
>
>从核心组件执行 JSON 导出需要版本 1.1.0 的核心组件。 有关更多信息，请参阅[核心组件 v1 的兼容性信息](/help/versions.md)。

## “配置”对话框 {#configure-dialog}

除了标准[“编辑”对话框](#edit-dialog)和[“设计”对话框](#design-dialog)之外，图像组件还提供了一个“配置”对话框，其中定义了图像本身及其描述和基本属性。

![](/help/assets/chlimage_1-50.png)

* **图像资源**
   * 通过[资源浏览器](https://helpx.adobe.com/cn/experience-manager/6-3/sites/authoring/using/author-environment-tools.html#main-pars_title)拖放资源或点击&#x200B;**浏览**&#x200B;选项，以从本地文件系统上传。
   * 点按或单击&#x200B;**“清除”**&#x200B;以取消选择当前选定的图像。
   * 点按或单击&#x200B;**编辑**&#x200B;可在资产编辑器中[管理资产的再现](https://helpx.adobe.com/cn/experience-manager/6-3/assets/using/managing-assets-touch-ui.html#main-pars_title_19)。

* **图像是装饰性的** – 检查图像是否应被辅助技术忽略，因此不需要替换文本。这仅适用于装饰性图像。
* **替换文本** – 用于替代该图像含义或功能的文字内容，适用于视障读者。
* **链接**
   * 将图像链接到其他资源。
   * 使用“选择”对话框可链接到其他 AEM 资源。
   * 如果未链接到 AEM 资源，请输入绝对 URL。非绝对 URL 将解释为相对于 AEM。

* **题注** – 有关图像的附加信息，默认显示在图像的下方。
* **以弹出窗口显示题注** – 选中后，不会在图像下方显示题注，但在某些浏览器中，将鼠标悬停于图像上方时，会以弹出信息形式显示题注。

## “编辑”对话框 {#edit-dialog}

利用“编辑”对话框，内容作者可以裁切、修改启动地图和缩放图像。

![](/help/assets/chlimage_1-8.png)

* 开始裁切

  ![](/help/assets/chlimage_1-9.png)

  选择此选项将打开一个预定义裁切比例的下拉菜单。

   * 选择&#x200B;**手动**&#x200B;选项可定义您自己的裁切。
   * 选择&#x200B;**删除裁切**&#x200B;可显示原始资源。

  选择一个裁切选项后，可使用蓝色手柄调整图像上的裁切大小。

  ![](/help/assets/chlimage_1-10.png)

* 向右旋转

  ![](/help/assets/chlimage_1-11.png)

  使用此选项可将图像向右（顺时针）旋转 90°。

* 启动地图

  ![](/help/assets/chlimage_1-12.png)

  使用此选项可向图像应用启动地图。 选择此选项将打开一个新窗口，允许用户选择地图的形状：

   * **添加矩形地图**
   * **添加圆形地图**
   * **添加多边形地图**

      * 默认情况下，添加三角形地图。双击形状的一条线可在新的一侧添加一个新的蓝色调整大小图柄。

  选择一个地图形状后，它将叠加在图像上以便能够调整大小。拖放蓝色调整大小图柄以调整形状。

  ![](/help/assets/chlimage_1-13.png)

  调整启动地图的大小后，单击它会打开一个用于定义链接的路径的浮动工具栏。

   * **路径**
      * 使用“路径选择器”选项可在 AEM 中选择路径
      * 如果路径未在 AEM 中，请使用绝对 URL。非绝对路径将解释为相对于 AEM。

      * **替换文本**
路径目标的替代描述
      * **目标**
         * **相同选项卡**
         * **新选项卡**
         * **父框架**
         * **顶层框架**

  点按或单击蓝色复选标记可保存，点按或单击黑色 x 可取消，点按或单击红色垃圾桶可删除地图。

  ![](/help/assets/chlimage_1-14.png)

* 重置缩放

  ![](/help/assets/chlimage_1-15.png)

  如果图像已缩放，使用此选项可重置缩放级别。

* 打开缩放滑块

  ![](/help/assets/chlimage_1-16.png)

  使用此选项可显示用于控制图像的缩放级别的滑块。

  ![](/help/assets/chlimage_1-17.png)

就地编辑器也可以用于修改图像。由于有空间限制，因此仅将基本选项排成一行。对于完整的编辑选项，请使用全屏模式。

![](/help/assets/chlimage_1-18.png)

>[!NOTE]
>
>GIF 图像不支持图像编辑操作（裁切、翻转、旋转）。在编辑模式下对 GIF 所做的任何此类更改都不会保留。

## “设计”对话框 {#design-dialog}

利用“设计”对话框，模板作者可以在使用此组件时定义内容作者的裁切、上传和轮换上传。

### 主要 {#main}

在&#x200B;**主要**&#x200B;选项卡上，您可以定义允许的宽度（以像素为单位）列表，以便图像从列表中自动加载最合适的宽度。

![](/help/assets/chlimage_1-51.png)

点按或单击“添加”按钮可添加其他大小。

* 使用抓取手柄可重新排列大小。
* 使用删除图标可删除宽度。

默认情况下，图像加载会被延迟，直到图像变得可见。选择&#x200B;**禁用延迟加载**&#x200B;选项可在页面加载时加载图像。

* **启用 Web 优化图像** – 选中后， [Web 优化图像传送服务](/help/developing/web-optimized-image-delivery.md)将以 WebP 格式传送图像，使图像大小平均减少 25%。
   * 此选项仅在 AEMaaCS 中可用。
   * 当未选中或 Web 优化图像投放服务不可用时，将使用[自适应图像 Servlet](/help/developing/adaptive-image-servlet.md)。

### 功能 {#features}

在&#x200B;**功能**&#x200B;选项卡上，您可以定义在使用组件时可供内容作者使用的选项，包括上传选项、方向和裁切选项。

* **启用 Web 优化图像** – 选中此选项后，网络优化的图像投放服务将以 WebP 格式投放图像，平均将图像大小减少 25%。
   * 此选项仅在 AEMaaCS 中可用。
   * 当未选中或 Web 优化图像投放服务不可用时，将使用[自适应图像 Servlet](/help/developing/adaptive-image-servlet.md)。

* 来源

  ![](/help/assets/chlimage_1-19.png)

  选择&#x200B;**允许从文件系统上传资源**&#x200B;选项可允许内容作者从其本地计算机上传图像。要强制内容作者仅从 AEM 中选择资源，请取消选择此选项。

* 方向

  ![](/help/assets/chlimage_1-20.png)

   * **旋转** – 使用此选项可允许内容作者使用&#x200B;**向右旋转**&#x200B;选项。
   * **翻转**
使用此选项可允许内容作者使用**水平翻转**&#x200B;和&#x200B;**垂直翻转**&#x200B;选项。

  >[!CAUTION]
  >
  >默认情况下已禁用&#x200B;**翻转**&#x200B;选项。启用此选项将在图像组件的“编辑”对话框中显示&#x200B;**垂直翻转**&#x200B;和&#x200B;**水平翻转**&#x200B;按钮，但 AEM 当前不支持该功能，并且不会保留使用这些选项所做的任何更改。

* 裁切

  ![](/help/assets/chlimage_1-21.png)

  选择&#x200B;**允许裁切**&#x200B;选项可允许内容作者在“编辑”对话框中裁切组件中的图像。
   * 单击&#x200B;**“添加”**&#x200B;可添加预定义的裁切长宽比。
   * 输入一个描述性名称，该名称将显示在&#x200B;**开始裁切**&#x200B;下拉列表中。
   * 输入长宽比的数字比率。
   * 使用拖动手柄可重新排列长宽比
   * 使用垃圾桶图标可删除长宽比。

  >[!CAUTION]
  >
  >请注意，在 AEM 中，裁切比例被定义为&#x200B;**高宽比**。这与常见的宽高比的定义不同，这样做是出于对旧版兼容性的考虑。只要您提供明确的比率名称，内容作者就不会意识到任何差异，因为该名称显示在 UI 中，而不是比率本身。

## 技术详细信息 {#technical-details}

[在 GitHub 上可找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/image/v1/image)有关图像组件的最新技术文档。

从 GitHub 可下载整个核心组件项目。

在[核心组件开发人员文档](/help/developing/overview.md)中可找到有关开发核心组件的其他详细信息。
