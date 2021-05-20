---
title: 痕迹导航组件(v1)
description: 核心组件痕迹导航组件是一个导航组件，可根据页面在内容层次结构中的位置生成链接的痕迹导航。
index: n
role: Architect, Developer, Administrator, Business Practitioner
exl-id: 4845e649-033a-43a8-b5ee-892a3f2a8b98
source-git-commit: 8ff36ca143af9496f988b1ca65475497181def1d
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 1%

---

# 痕迹导航组件(v1){#breadcrumb-component-v}

核心组件痕迹导航组件是一个导航组件，可根据页面在内容层次结构中的位置生成链接的痕迹导航。

## 使用 {#usage}

痕迹导航组件显示当前页面在网站层次结构中的位置，从而允许页面访客从其当前位置导航页面层次结构。 它通常集成到页眉或页脚中。

模板作者可在[设计对话框](#design-dialog)中定义默认导航级别以及显示当前页面或隐藏页面的功能等可用选项。 然后，内容编辑器可以选择是否应显示隐藏的页面以及组件在[编辑对话框](#edit-dialog)中的实际导航级别。

## 版本和兼容性{#version-and-compatibility}

本文档介绍了痕迹导航组件v1，该组件最初随AEM 6.3核心组件1.0.0版一起引入。

下表列出了痕迹导航组件v1的兼容性。

| AEM 版本 | 痕迹导航组件v1 |
|--- |--- |
| 6.3 | 兼容 |
| 6.4 | 兼容 |

>[!CAUTION]
>
>本文档介绍痕迹导航组件的v1。
>有关当前版本的痕迹导航组件的详细信息，请参阅[痕迹导航组件](/help/components/breadcrumb.md)文档。

## 组件输出示例{#sample-component-output}

以下是从[We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)获取的示例。

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
>从核心组件导出JSON时，需要安装核心组件版本1.1.0。 有关更多信息，请参阅核心组件v1](/help/versions.md)的[兼容性信息。

## 编辑对话框{#edit-dialog}

编辑对话框允许内容作者在痕迹导航中禁止隐藏和活动页面以及该页面应显示的层次结构深度。

![](/help/assets/chlimage_1-34.png)

* **要开始的导航级别**  — 在层次结构中，痕迹导航组件应该开始向下导航到当前页面的位置。例如，在We.Retail中：

   * 1从`/content/we-retail`开始
   * 2从`/content/we-retail/<country>`开始

* **显示隐藏**  — 显示痕迹导航中标记为隐藏的页面（默认情况下，不会显示这些页面）
* **隐藏当前** — 在痕迹导航中禁止当前页面（默认情况下将显示该页面）

## 设计对话框{#design-dialog}

设计对话框允许模板作者定义用于在痕迹导航中禁止隐藏和活动页面的选项的默认值以及应显示的层次结构深度。

![](/help/assets/chlimage_1-35.png)

* **要开始的导航级别**  — 定义在将痕迹导航组件添加到页面时，痕迹导航组件在层次结构中应开始向下导航到当前页面的位置的默认值。
* **显示隐藏**  — 定义将痕迹导航组 **件添** 加到页面时显示隐藏选项的默认值。

   * 它不会为作者启用或禁用选项。 它仅设置默认值。

* **隐藏当前**  — 定义将痕迹导航组 **件添** 加到页面时“隐藏当前”选项的默认值。

   * 它不会为作者启用或禁用选项。 它仅设置默认值。

## 技术详细信息{#technical-details}

有关痕迹导航组件[的最新技术文档，请参阅GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v1/breadcrumb)。

可以从GitHub下载整个核心组件项目。

有关开发核心组件的更多详细信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。
