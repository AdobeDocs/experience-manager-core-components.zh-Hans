---
title: 图像组件
seo-title: 图像组件
description: 核心组件图像组件是自适应图像组件，用于就地编辑。
seo-description: 核心组件图像组件是自适应图像组件，用于就地编辑。
uuid: a229d42-2428-43aa-895a-9b7c1bf02834
contentOwner: 用户
content-type: 引用
topic-tags: 创作
products: SG_ EXPERIENCE MANAGER/CORECOMMPANES-new
discoiquuid: d4684f33-2fb5-4f32-866f-7136cf1800d7
translation-type: tm+mt
source-git-commit: 1243d6cc1b0b015ee2f37ae89d0e2e42d366cc02

---


# 图像组件{#image-component}

核心组件图像组件是具有就地编辑功能的自适应图像组件。

## 使用情况 {#usage}

图像组件可轻松放置图像资源并提供就地编辑功能。它包含延迟加载以及内容作者裁剪的自适应图像选择。

设计对话框中的模板作者可以定义图像宽度以及裁剪和其他 [设置](#design-dialog)。内容编辑器可以在 [配置对话框](#configure-dialog) 中上传或选择资产，并在 [编辑对话框中裁剪图像](#edit-dialog)。为了方便起见，还提供了简单的就地修改图像。

## 版本和兼容性 {#version-and-compatibility}

图像组件的当前版本是v2，它是在2018年月版的核心组件中引入的，它在文档中进行了介绍。

下表详细说明了组件的所有支持版本、组件版本的AEM版本以及以前版本的文档链接。

| 组件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v2 | 兼容 | 兼容 | 兼容 |
| [v1](image-v1.md) | 兼容 | 兼容 | 兼容 |

有关核心组件版本和版本的更多信息，请参阅文档 [核心组件版本](versions.md)。

## SVG支持 {#svg-support}

可缩放矢量图形(SVG)由图像组件支持。

* 支持从DAM拖放SVG资源并从本地文件系统上传SVG文件。
* 自适应图像Servlet流流播放原始SVG文件(跳过转换)。
* 对于SVG图像，“智能图像”和“智能大小”设置为图像模型中的空数组。

### 安全 {#security}

由于安全原因，图像编辑器从不直接调用原始SVG。调用它 `<img src=“path-to-component”>`。因此，浏览器可防止嵌入到SVG文件中的脚本执行。

>[!CAUTION]
>
>SVG支持需要核心组件的2.1.0版本以及AEM6.4或适用于AEM6.3或更高版本的Service Pack的更高版本( [](https://helpx.adobe.com/experience-manager/6-4/release-notes/sp-release-notes.html) 用于AEM6.3或更高 [版本)](https://helpx.adobe.com/experience-manager/6-3/release-notes/sp3-release-notes.html) ，以支持 [AEM中的新图像编辑器功能](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/image-editor.html) 。

## 示例组件输出 {#sample-component-output}

以下示例取自 [We. Retail](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html)。

### 屏幕快照 {#screenshot}

![](assets/chlimage_1-7.png)

### 组件库

要体验图像组件以及查看其配置选项的示例以及HTML和JSON输出，请访问 [组件库](http://opensource.adobe.com/aem-core-wcm-components/library/image.html)。

### 技术详细信息 {#technical-details}

有关图像组件 [的最新技术文档可在GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/image/v2/image)上找到。

有关开发核心组件的更多详细信息，请参阅 [核心组件开发人员文档](developing.md)。

>[!NOTE]
>
>从核心组件版本2.1.0开始，图像组件支持 [schema.org微数据](https://schema.org)。

## 配置对话框 {#configure-dialog}

除了标准 [编辑对话框](#edit-dialog) 和 [设计对话框](#design-dialog)外，图像组件还提供了一个配置对话框，其中定义了图像本身及其描述和基本属性。

### 资产选项卡 {#asset-tab}

![](assets/screen_shot_2018-01-08at114245.png)

* **图像资产**
   * 从 [资产浏览器中拖放资产](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/author-environment-tools.html) 或点击 **浏览** 选项以从本地文件系统上传。
   * 点按或单击 **清除** 可取消选择当前选定的图像。
   * 点按或单击 **编辑** 可 [在资产编辑器](https://helpx.adobe.com/experience-manager/6-5/assets/using/managing-assets-touch-ui.html) 中合并资产的演绎版。

### 元数据选项卡 {#metadata-tab}

![](assets/screen_shot_2018-01-08at114527.png)

* **图像为装饰性**检查是否应通过辅助技术忽略图像，因此不需要替代文本。这仅适用于装饰图像。
* **为视觉障碍的读者提供的替代文本**的替代文本或功能的替代文本。
   * 从DAM中获取替代文本-选中图像的替代文本后，将填充DAM中 `dc:description` 元数据的值。

* **题注**有关图像的其他信息，默认情况下显示在图像下方。
   * **从DAM**中获取题注时，图像的题注文本将填充DAM `dc:title` 中元数据的值。
   * **显示题注作为弹出**窗口在选中时，题注不会显示在图像下方，但作为鼠标悬停在图像上方时显示的弹出窗口。

* **链接**
   * 将图像链接到其他资源。
   * 使用选择对话框链接到其他AEM资源。
   * 如果不链接到AEM资源，请输入绝对URL。非解决的URL将解释为相对于AEM的URL。

## 编辑对话框 {#edit-dialog}

编辑对话框允许内容作者裁切、修改启动图和缩放图像。

![](assets/chlimage_1-8.png)

* 开始裁剪

   ![](assets/chlimage_1-9.png)

   选择此选项将打开预定义裁剪比例的下拉列表。

   * 选择“ **Free Hand** ”选项可定义您自己的裁剪。
   * 选择 **“删除裁剪** ”选项可显示原始资产。
   选择裁剪选项后，使用蓝色手柄在图像上调整裁剪大小。

   ![](assets/chlimage_1-10.png)

* 向右旋转

   ![](assets/chlimage_1-11.png)

   使用此选项可将图像旋转90°(顺时针)。

* 水平翻转

   ![](assets/screen_shot_2018-04-16at091404.png)

   使用此选项可水平翻转图像或沿y轴将图像枢绕180°。

* 垂直翻转

   ![](assets/screen_shot_2018-04-16at091410.png)

   使用此选项可垂直翻转图像或沿x轴将图像枢绕180°。

* 启动地图

   >[!CAUTION]
   >
   >Launch Map功能需要核心组件的发行版2.1.0以及AEM6.3或用于AEM6.3或更高版本的Service Pack的更高版本( [](https://helpx.adobe.com/experience-manager/6-4/release-notes/sp-release-notes.html) 用于AEM6.3或更高 [版本)](https://helpx.adobe.com/experience-manager/6-3/release-notes/sp3-release-notes.html) ，以支持 [AEM中的新图像编辑器功能](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/image-editor.html) 。

   ![](assets/chlimage_1-12.png)

   使用此选项可将启动项映射应用于图像。选择此选项将打开一个新窗口，允许用户选择地图的形状：

   * **添加矩形图**
   * **添加圆形映射**
   * **添加多边形映射**
      * 默认情况下，添加三角形映射。双击形状线，在新一侧添加新的蓝色调整大小手柄。
   选择地图形状后，它会叠加在图像上，从而允许调整大小。拖放蓝色大小手柄可调整形状。

   ![](assets/chlimage_1-13.png)

   在调整启动地图的大小之后，单击它以打开一个浮动工具栏以定义链接的路径。

   * **路径**
      * 使用路径选取器选项在AEM中选择路径
      * 如果路径不在AEM中，请使用绝对URL。将根据AEM解释非绝对路径。
   * **替代文本**路径目标的替换说明
   * **目标**
      * **相同选项卡**
      * **新选项卡**
      * **父框架**
      * **顶层框架**
   点按或单击蓝色选中标记以保存、黑色x取消，以及红色垃圾桶可删除映射。

   ![](assets/chlimage_1-14.png)

* 重置缩放

   ![](assets/chlimage_1-15.png)

   如果图像已缩放，则使用此选项重置缩放级别。

* 打开缩放滑块

   ![](assets/chlimage_1-16.png)

   使用此选项可显示控制图像缩放级别的滑块。

   ![](assets/chlimage_1-17.png)

就地编辑器还可用于修改图像。由于空间限制，只有基本选项可用。要获得完整的编辑选项，请使用全屏模式。

![](assets/chlimage_1-18.png)

>[!NOTE]
>
>GIF图像不支持图像编辑操作(裁剪、翻转、旋转)。在编辑模式下进行的任何此类更改都不会被保留。

## 设计对话框 {#design-dialog}

设计对话框允许模板作者定义使用此组件时内容作者的裁剪、上传和旋转以及上传选项。

### 主选项卡 {#main-tab}

**在主** 选项卡上，您可以为图像定义宽度列表以自动从列表中加载最合适的宽度。

此外，您还可以定义作者将组件添加到页面时自动或禁用的常规组件选项。

![](assets/screenshot_2018-10-19at102756.png)

* **启用延迟加载**定义在将图像组件添加到页面时是否自动启用延迟加载选项。
* **图像为装饰**定义在将图像组件添加到页面时，是否自动启用装饰图像选项。
* **从DAM**定义替换文本，在将图像组件添加到页面时，是否会自动启用从DAM中检索替代文本的选项。
* **从DAM**定义题注，定义在将图像组件添加到页面时是否自动启用从DAM检索题注的选项。
* **显示题注作为弹出**式定义是否在将图像组件添加到页面时自动启用图像题注作为弹出窗口的选项。
* **禁用UUID跟踪**检查以停用图像资产的UUID跟踪。

* **宽度**为图像定义宽度列表以使图像从列表自动加载最合适的宽度。
   * 点按或单击 **添加** 按钮以添加其他大小。
      * 使用抓取手柄重新排列大小的顺序。
      * 使用 **删除** 图标删除宽度。
   * 默认情况下，加载图像时会延迟加载图像。
      * 选择“ **停用延迟加载** ”可在载入页面时加载图像。
* **JPEG质量**转换的(例如，缩放或裁剪)
JPEG图像的质量因子(以百分比和100表示)。

>[!CAUTION]
>
>“JPEG质量”选项从核心组件的2.2.0版本中可用。

>[!NOTE]
>
>从核心组件的2.2.0版本开始，图像组件将唯一的UUID属性 `data-asset-id` 添加到图像资产，以允许跟踪和分析单个资产接收的查看次数。

### 功能选项卡 {#features-tab}

在 **“功能** ”选项卡上，您可以定义内容作者在使用组件时可使用的选项，包括上传选项、方向和裁剪选项。

* 源

   ![](assets/chlimage_1-19.png)

   选择 **“允许从文件系统上传资产”以** 允许内容作者从其本地计算机上传图像。要强制内容作者只从AEM中选择资产，请取消选中此选项。

* 方向

   ![](assets/chlimage_1-20.png)

* **旋转**使用此选项允许内容作者使用 **“Roogle
Right** ”选项。
* **翻转**使用此选项可允许内容作者使用“水平 **翻转”** 和“垂直 **翻转** ”选项。

   >[!CAUTION]
   >
   >**默认** 情况下禁用“翻转”选项。启用该选项将在图像组件的编辑对话框中显示“垂直 **** 翻转”和 **** “水平翻转”按钮，但是，AEM当前不支持该功能，而使用这些选项所做的任何更改将不会被保留。

<!-- 
Comment Type: remark
Last Modified By: Chris Bohnert (bohnert)
Last Modified Date: 2017-11-20T05:51:34.378-0500

<p>Added caution based on CQDOC-11457. Hid the flip options in the procedure using the <strong>Draft</strong> option so that when this feature is implemented in CQ-4221539, the <strong>Draft</strong> property can simply be removed along with the caution.</p>
 -->

* 裁剪

   ![](assets/chlimage_1-21.png)

   选择 **“允许裁剪** ”选项，以允许内容作者在编辑对话框中的组件中裁剪图像。
   * 单击 **添加** 以添加预定义的裁剪长宽比。
   * 输入一个描述性名称，该名称将显示在 **“开始裁剪”** 下拉菜单中。
   * 输入长宽比的数值。
   * 使用拖动手柄重新排列长宽比的顺序
   * 使用垃圾桶图标可删除长宽比。
   >[!CAUTION]
   >
   >请注意，在AEM中，裁剪长宽比定义为 **高度/宽度**。这与传统的宽度/高度定义不同，并且出于传统兼容性原因而完成。只要您提供了一个清晰的比率名称，内容作者就不会注意到任何区别，因为该名称的名称是在UI中显示，而不是由比例本身显示。

### 样式选项卡 {#styles-tab-1}

图像组件支持AEM [Style System](authoring.md#component-styling)。