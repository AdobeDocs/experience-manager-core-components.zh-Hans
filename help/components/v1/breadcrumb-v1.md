---
title: 痕迹导航组件(v1)
description: 核心组件痕迹导航组件是一个导航组件，它根据页面在内容层次结构中的位置构建链接的痕迹导航。
index: n
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 1%

---


# 痕迹导航组件(v1){#breadcrumb-component-v}

核心组件痕迹导航组件是一个导航组件，它根据页面在内容层次结构中的位置构建链接的痕迹导航。

## 使用 {#usage}

痕迹导航组件显示当前页面在站点层次结构中的位置，允许页面访客从其当前位置导航页面层次结构。 这通常集成到页眉或页脚中。

模板作者可以在[设计对话框](#design-dialog)中定义默认导航级别和显示当前页面或隐藏页面的功能等可用选项。 然后，内容编辑器可以在[编辑对话框](#edit-dialog)中选择是否显示隐藏页面以及组件的实际导航级别。

## 版本和兼容性{#version-and-compatibility}

本文档描述了Breadcrumb组件的v1，该组件最初随带AEM 6.3的核心组件的1.0.0版引入。

下表列表了痕迹导航组件v1的兼容性。

| AEM 版本 | 痕迹导航组件v1 |
|--- |--- |
| 6.3 | 兼容 |
| 6.4 | 兼容 |

>[!CAUTION]
>
>此文档描述痕迹导航组件的v1。
>有关Breadcrumb组件当前版本的详细信息，请参阅[Breadcrumb组件](/help/components/breadcrumb.md)文档。

## 示例组件输出{#sample-component-output}

以下是从[We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)取的示例。

### 屏幕快照 {#screenshot}

![](/help/assets/chlimage_1-33.png)

### HTML {#html}

```
<div class="cmp cmp-breadcrumb aem-GridColumn aem-GridColumn--default--12">

<ol class="breadcrumb">
    <li class="breadcrumb-item ">
        <a href="/content/we-retail/us.html">
            United States
        </a>
    </li>

    <li class="breadcrumb-item ">
        <a href="/content/we-retail/us/en.html">
            English
        </a>
    </li>

    <li class="breadcrumb-item active">
        
            Experience
        
    </li>
</ol>
 
</div>
```

### JSON {#json}

```
"breadcrumb": {
              "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
              ":type": "weretail/components/content/breadcrumb"
            }
```

>[!NOTE]
>
>从核心组件导出JSON时，需要1.1.0版的核心组件。 有关详细信息，请参阅核心组件v1](/help/versions.md)的[兼容性信息。

## 编辑对话框{#edit-dialog}

编辑对话框允许内容作者在痕迹导航中隐藏和活动的页面以及它应显示的层次结构深度。

![](/help/assets/chlimage_1-34.png)

* **导航级别到开始** -在层次结构中，痕迹导航组件应开始到当前页面的位置。例如，在We.Retail中：

   * `/content/we-retail`处的1个开始
   * `/content/we-retail/<country>`处的2个开始

* **显示隐藏** -在痕迹导航中显示标记为隐藏的页面（默认情况下，不会显示它们）
* **隐藏当前**-在痕迹导航中隐藏当前页面（默认情况下，将显示该页面）

## 设计对话框{#design-dialog}

设计对话框允许模板作者定义用于在痕迹导航中隐藏和活动页面的选项的默认值以及应显示的层次结构深度。

![](/help/assets/chlimage_1-35.png)

* **导航级别到开始** -定义在将痕迹导航组件添加到页面时，痕迹导航组件在层次结构中应开始向下走到当前页面的位置的默认值。
* **显示隐藏** -定义将痕迹导航组 **件** 添加到页面时显示隐藏选项的默认值。

   * 它不为作者启用或禁用该选项。 它只设置默认值。

* **隐藏当前** -定义将痕迹导航组 **件** 添加到页面时隐藏当前选项的默认值。

   * 它不为作者启用或禁用该选项。 它只设置默认值。

## 技术详细信息{#technical-details}

有关痕迹导航组件[的最新技术文档可在GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v1/breadcrumb)上找到。

整个核心组件项目可从GitHub下载。

有关开发核心组件的更多详细信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。
