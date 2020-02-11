---
title: 图像组件(v1)
description: 核心组件图像组件是自适应图像组件功能的就地编辑。
index: n
translation-type: tm+mt
source-git-commit: 5439f90faef28c72367419bb7429a3a880b65229

---


# 图像组件(v1){#image-component-v}

核心组件图像组件是自适应图像组件功能的就地编辑。

## 使用情况 {#usage}

图像组件可轻松放置图像资产并提供就地编辑。 它具有自适应图像选择功能，可延迟加载以及为内容作者裁剪。

模板作者可以在设计对话框中定义允许的图像宽度以及裁剪和其他 [设置](image-v1.md#main-pars_title_1995166862)。 内容编辑器可以在“配置”对话框中上传或 [选择资产](image-v1.md#main-pars_title_55926120) ，并在“编辑”对话框中裁 [剪图像](image-v1.md#main-pars_title)。 为了更方便起见，还可以对图像进行简单的就地修改。

## 版本和兼容性 {#version-and-compatibility}

本文档描述了最初随AEM 6.3的核心组件版本1.0.0引入的图像组件版本1。

下表列出了图像组件v1的兼容性。

| AEM 版本 | 图像组件v1 |
|--- |--- |
| 6.3 | 兼容 |
| 6.4 | 兼容 |

>[!CAUTION]
>
>本文档描述了图像组件的v1。
>
>有关图像组件的当前版本的详细信息，请参阅图 [像组件文档](image.md) 。

## 示例组件输出 {#sample-component-output}

以下是从 [We.Retail获取的示例](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)。

### 屏幕快照 {#screenshot}

![](assets/chlimage_1-7.png)

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
>从核心组件导出JSON时，需要发行核心组件的1.1.0版。 有关详细信息， [请参阅核心组件v1的兼容性信息](versions.md#main-pars_title_236368006) 。

## 配置对话框 {#configure-dialog}

除了标准编辑对 [话框和设计对话框](image-v1.md#main-pars_title) ，图像组 [件还提供一个配置对话框](image-v1.md#main-pars_title_1995166862)，在该对话框中定义了图像本身及其描述和基本属性。

![](assets/chlimage_1-50.png)

* **图像资产**
   * 从资产浏览器中 [拖放资产](https://helpx.adobe.com/experience-manager/6-3/sites/authoring/using/author-environment-tools.html#main-pars_title) ，或点 **按浏览选项** ，以从本地文件系统上传。
   * 点按或单 **击清除** ，以取消选择当前选定的图像。
   * 点按或单 **击编辑** , [以在资产编辑器中管理资产的演绎版](https://helpx.adobe.com/experience-manager/6-3/assets/using/managing-assets-touch-ui.html#main-pars_title_19) 。

* **图像具有装饰性** -检查图像是否应被辅助型技术忽略，因此不需要替代文本。 这仅适用于装饰性图像。
* **替代文本** -为有视觉障碍的读者提供图像含义或功能的替代文本。
* **链接**
   * 将图像链接到其他资源。
   * 使用选择对话框链接到其他AEM资源。
   * 如果未链接到AEM资源，请输入绝对URL。 非溶质URL将解释为相对于AEM。

* **题注** -默认显示在图像下方的有关图像的其他信息。
* **将题注显示为弹出窗口** -选中此选项后，题注不会显示在图像下方，而是显示为某些浏览器在将鼠标悬停在图像上方时显示的弹出窗口。

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

* 启动映射

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

设计对话框允许模板作者定义使用此组件时内容作者的裁剪、上传和旋转上传。

### 主要 {#main}

On the **Main** tab you can define a list of allowed widths in pixels for the image to automatically load the most appropriate width from the list.

![](assets/chlimage_1-51.png)

点按或单击添加按钮以添加其他大小。

* 使用抓取手柄重新排列大小的顺序。
* 使用删除图标可删除宽度。

默认情况下，图像加载会延迟到可见为止。 选择选项“ **禁用延迟加载** ”，以在页面加载时加载图像。

### 功能 {#features}

在“功 **能** ”选项卡上，您可以定义在使用组件（包括上传选项、方向和裁剪选项）时内容作者可以使用的选项。

* 源

   ![](assets/chlimage_1-19.png)

   选择“允 **许从文件系统上传资产** ”选项，以允许内容作者从其本地计算机上传图像。 要强制内容作者仅从AEM中选择资产，请取消选择此选项。

* 方向

   ![](assets/chlimage_1-20.png)

   * **旋转** -使用此选项可允许内容作者使用“向右旋 **转** ”选项。
   * **翻转**&#x200B;使用此选项可允许内容作者使用“水平翻转” **和“垂直** 翻转”选项 **** 。
   >[!CAUTION]
   >
   >默认情 **况下** ,“翻转”选项处于禁用状态。 启用此功能后，将在图像组件的编辑对话框中显示“垂直翻转 ******** ”和“水平翻转”按钮，但AEM当前不支持该功能，并且使用这些选项所做的任何更改都不会被保留。

<!-- 
Comment Type: remark
Last Modified By: Chris Bohnert (bohnert)
Last Modified Date: 2017-11-20T05:51:34.378-0500

<p>Added caution based on CQDOC-11457. Hid the flip options in the procedure using the <strong>Draft</strong> option so that when this feature is implemented in CQ-4221539, the <strong>Draft</strong> property can simply be removed along with the caution.</p>
-->

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

## 技术详细信息 {#technical-details}

有关图像组件的最新技术文 [档可在GitHub上找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/image/v1/image)。

整个核心组件项目可从GitHub下载。

有关开发核心组件的更多详细信息，请参阅核 [心组件开发人员文档](developing.md)。
