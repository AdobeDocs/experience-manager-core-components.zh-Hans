---
title: 痕迹导航组件(v1)
description: 核心组件痕迹导航组件是一个导航组件，用于根据页面在内容层次结构中的位置构建链接的痕迹导航。
index: n
role: 架构师、开发人员、管理员、业务从业者
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '551'
ht-degree: 1%

---


# 痕迹导航组件(v1){#breadcrumb-component-v}

核心组件痕迹导航组件是一个导航组件，用于根据页面在内容层次结构中的位置构建链接的痕迹导航。

## 使用 {#usage}

痕迹导航组件显示当前页面在站点层次结构中的位置，允许页面访客从其当前位置导航页面层次结构。 这通常集成到页眉或页脚中。

模板作者在[设计对话框](#design-dialog)中可以定义默认导航级别和显示当前页面或隐藏页面的功能等可用选项。 然后，内容编辑器可以选择是否显示隐藏页面以及组件在[编辑对话框](#edit-dialog)中的实际导航级别。

## 版本和兼容性{#version-and-compatibility}

本文档描述了Breadcrumb组件的v1，它最初随AEM 6.3的核心组件版本1.0.0引入。

下表列表了痕迹导航组件v1的兼容性。

| AEM 版本 | 痕迹导航组件v1 |
|--- |--- |
| 6.3 | 兼容 |
| 6.4 | 兼容 |

>[!CAUTION]
>
>此文档描述了痕迹导航组件的v1。
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
>从核心组件导出JSON需要1.1.0版的核心组件。 有关详细信息，请参阅核心组件v1](/help/versions.md)的[兼容性信息。

## 编辑对话框{#edit-dialog}

通过编辑对话框，内容作者可以隐藏痕迹导航中的隐藏和活动页面以及应显示的层次结构中的深度。

![](/help/assets/chlimage_1-34.png)

* **导航级别到开始**  — 在层次结构中，痕迹导航组件应开始向下浏览到当前页面的位置。例如，在We.Retail中：

   * `/content/we-retail`处的1个开始
   * `/content/we-retail/<country>`处的2个开始

* **显示隐藏**  — 显示在痕迹导航中标记为隐藏的页面（默认情况下，不会显示它们）
* **隐藏当前** — 在痕迹导航中隐藏当前页面（默认情况下将显示该页面）

## 设计对话框{#design-dialog}

设计对话框允许模板作者定义用于隐藏痕迹导航中隐藏和活动页面的选项的默认值以及应显示的层次结构中的深度。

![](/help/assets/chlimage_1-35.png)

* **导航级别到开始**  — 定义在将痕迹导航组件添加到页面时，痕迹导航组件应开始在层次结构中向下浏览到当前页面的位置的默认值。
* **显示隐藏**  — 定义将痕迹导航组 **件添** 加到页面时显示隐藏选项的默认值。

   * 它不为作者启用或禁用此选项。 它只设置默认值。

* **隐藏当前**  — 定义将痕迹导航组 **件添** 加到页面时隐藏当前选项的默认值。

   * 它不为作者启用或禁用此选项。 它只设置默认值。

## 技术详细信息{#technical-details}

有关Breadcrumb组件[的最新技术文档可在GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v1/breadcrumb)上找到。

整个核心组件项目可从GitHub下载。

有关开发核心组件的更多详细信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。
