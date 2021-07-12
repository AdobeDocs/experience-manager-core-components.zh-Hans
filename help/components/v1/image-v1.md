---
title: 图像组件(v1)
description: 核心组件图像组件是自适应图像组件功能就地编辑。
index: n
role: Architect, Developer, Admin, User
exl-id: 625ce8de-5c4a-476d-b749-895493d169b1
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '1229'
ht-degree: 3%

---

# 图像组件(v1) {#image-component-v}

核心组件图像组件是自适应图像组件功能就地编辑。

## 使用 {#usage}

图像组件允许轻松放置图像资产并提供就地编辑功能。 它具有具有延迟加载的自适应图像选择以及为内容作者裁剪的功能。

模板作者可以在[设计对话框](#design-dialog)中定义允许的图像宽度以及裁剪和其他设置。 内容编辑器可以上传或选择[配置对话框](#configure-dialog)中的资产，并在[编辑对话框](#edit-dialog)中裁剪图像。 为了更方便起见，还提供简单的图像就地修改。

## 版本和兼容性 {#version-and-compatibility}

本文档介绍了图像组件v1，该组件最初随AEM 6.3核心组件1.0.0版一起引入。

下表列出了图像组件v1的兼容性。

| AEM 版本 | 图像组件v1 |
|--- |--- |
| 6.3 | 兼容 |
| 6.4 | 兼容 |

>[!CAUTION]
>
>本文档介绍图像组件的v1。
>
>有关当前版本的图像组件的详细信息，请参阅[图像组件](/help/components/image.md)文档。

## 组件输出示例 {#sample-component-output}

以下是从[We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)获取的示例。

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
>从核心组件导出JSON时，需要安装核心组件版本1.1.0。 有关更多信息，请参阅核心组件v1](/help/versions.md)的[兼容性信息。

## 配置对话框 {#configure-dialog}

除了标准的[编辑对话框](#edit-dialog)和[设计对话框](#design-dialog)之外，图像组件还提供一个配置对话框，在其中定义了图像本身及其描述和基本属性。

![](/help/assets/chlimage_1-50.png)

* **图像资产**
   * 从[资产浏览器](https://helpx.adobe.com/experience-manager/6-3/sites/authoring/using/author-environment-tools.html#main-pars_title)中删除资产，或点按&#x200B;**browse**&#x200B;选项，以从本地文件系统上传。
   * 点按或单击&#x200B;**清除**&#x200B;以取消选择当前选定的图像。
   * 点按或单击&#x200B;**编辑** ，以在资产编辑器中[管理资产的演绎版。](https://helpx.adobe.com/experience-manager/6-3/assets/using/managing-assets-touch-ui.html#main-pars_title_19)

* **图像具有装饰性**  — 检查图像是否应被辅助型技术忽略，因此不需要替换文本。这仅适用于装饰性图像。
* **替换文本**  — 为视觉障碍读者提供图像含义或功能的替换文本。
* **链接**
   * 将图像链接到其他资源。
   * 使用选择对话框链接到其他AEM资源。
   * 如果未关联到AEM资源，请输入绝对URL。 非溶质URL将解释为相对于AEM。

* **标题**  — 默认显示在图像下方的有关图像的其他信息。
* **将题注显示为弹出窗口**  — 选中此选项后，题注不会显示在图像下方，而是会在将鼠标悬停在图像上方时显示为某些浏览器显示的弹出窗口。

## 编辑对话框 {#edit-dialog}

编辑对话框允许内容作者裁剪、修改启动映射和缩放图像。

![](/help/assets/chlimage_1-8.png)

* 开始裁剪

   ![](/help/assets/chlimage_1-9.png)

   选择此选项将打开一个下拉列表，显示预定义的裁剪比例。

   * 选择选项&#x200B;**Free Hand**&#x200B;以定义您自己的裁剪。
   * 选择选项&#x200B;**删除裁剪**&#x200B;以显示原始资产。

   选择裁剪选项后，使用蓝色手柄调整图像上裁剪的大小。

   ![](/help/assets/chlimage_1-10.png)

* 向右旋转

   ![](/help/assets/chlimage_1-11.png)

   使用此选项将图像90°向右（顺时针）旋转。

* 启动映射

   ![](/help/assets/chlimage_1-12.png)

   使用此选项可将启动映射应用到图像。 选择此选项将打开一个新窗口，允许用户选择映射的形状：

   * **添加矩形映射**
   * **添加循环图**
   * **添加多边形映射**

      * 默认情况下，会添加三角形映射。 双击形状的一行，在新侧面添加新的蓝色大小调整手柄。

   一旦选择了映射形状，该形状就会叠加在图像上以允许调整大小。 拖放蓝色的调整大小手柄以调整形状。

   ![](/help/assets/chlimage_1-13.png)

   调整启动映射的大小后，单击该映射以打开一个浮动工具栏以定义链接的路径。

   * **路径**
      * 使用路径选取器选项在AEM中选择路径
      * 如果路径不在AEM中，则使用绝对URL。 非绝对路径将被解释为相对于AEM。

      * **替**
换文本路径目标的替换描述
      * **Target**
         * **“相同”选项卡**
         * **新建选项卡**
         * **父框架**
         * **顶层框架**

   点按或单击要保存的蓝色复选标记，黑色x要取消，红色垃圾桶可以删除地图。

   ![](/help/assets/chlimage_1-14.png)

* 重置缩放

   ![](/help/assets/chlimage_1-15.png)

   如果图像已缩放，则使用此选项可重置缩放级别。

* 打开缩放滑块

   ![](/help/assets/chlimage_1-16.png)

   使用此选项可显示一个滑块来控制图像的缩放级别。

   ![](/help/assets/chlimage_1-17.png)

就地编辑器也可用于修改图像。 由于空间限制，只有基本选项在线可用。 要获取完整编辑选项，请使用全屏模式。

![](/help/assets/chlimage_1-18.png)

>[!NOTE]
>
>GIF图像不支持图像编辑操作（裁剪、翻转、旋转）。 在编辑模式下对GIF所做的任何此类更改将不会持久保留。

## “设计”对话框 {#design-dialog}

设计对话框允许模板作者定义使用此组件时内容作者进行的裁剪、上传和旋转上传。

### 主要 {#main}

在&#x200B;**主**&#x200B;选项卡上，您可以定义允许的宽度列表（以像素为单位），以便图像自动从列表中加载最合适的宽度。

![](/help/assets/chlimage_1-51.png)

点按或单击添加按钮以添加其他大小。

* 使用抓握手柄重新排列大小的顺序。
* 使用删除图标可删除宽度。

默认情况下，图像加载会延迟到可见为止。 选择选项&#x200B;**禁用延迟加载** ，以在页面加载时加载图像。

### 功能 {#features}

在&#x200B;**功能**&#x200B;选项卡上，您可以定义在使用组件（包括上传选项、方向和裁剪选项）时，内容作者可以使用的选项。

* 源

   ![](/help/assets/chlimage_1-19.png)

   选择选项&#x200B;**允许从文件系统上传资产**&#x200B;以允许内容作者从其本地计算机上传图像。 要强制内容作者仅从AEM中选择资产，请取消选择此选项。

* 方向

   ![](/help/assets/chlimage_1-20.png)

   * **旋转**  — 使用此选项可允许内容作者使用旋转 **右** 键。
   * ****
反向使用此选项可允许内容作者使用 
**“水平翻** 转”和“垂直 **翻** 转”选项。
   >[!CAUTION]
   >
   >默认情况下，**Flip**&#x200B;选项处于禁用状态。 启用此选项将在图像组件的编辑对话框中显示&#x200B;**垂直翻转**&#x200B;和&#x200B;**水平翻转**&#x200B;按钮，但AEM当前不支持该功能，并且不会保留使用这些选项所做的任何更改。

* 裁剪

   ![](/help/assets/chlimage_1-21.png)

   选择选项&#x200B;**允许裁剪** ，以允许内容作者在编辑对话框中裁剪组件中的图像。
   * 单击&#x200B;**Add**&#x200B;以添加预定义的裁剪宽高比。
   * 输入描述性名称，该名称将显示在&#x200B;**开始裁剪**&#x200B;下拉列表中。
   * 输入宽高比的数值。
   * 使用拖动手柄重新排列长宽比的顺序
   * 使用垃圾桶图标删除宽高比。

   >[!CAUTION]
   >
   >请注意，在AEM中，裁剪长宽比被定义为&#x200B;**高度/宽度**。 这与常见的宽高比的定义不同，这样做是出于对旧版兼容性的考虑。只要您提供了比率的明确名称，内容作者便不会察觉到任何差异，因为该名称会显示在UI中，而不是比率本身。

## 技术详细信息 {#technical-details}

有关图像组件[的最新技术文档，请参阅GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/image/v1/image)。

可以从GitHub下载整个核心组件项目。

有关开发核心组件的更多详细信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。
