---
title: 痕迹导航组件 (v1)
description: 核心组件痕迹导航组件是一个导航组件，它根据页面在内容层级中的位置构建链接的痕迹导航。
index: n
role: Architect, Developer, Admin, User
exl-id: 4845e649-033a-43a8-b5ee-892a3f2a8b98
source-git-commit: 92a3ec273a5be6751c1503835b9c2e5cbd61bb9e
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 100%

---


# 痕迹导航组件 (v1) {#breadcrumb-component-v}

核心组件痕迹导航组件是一个导航组件，它根据页面在内容层级中的位置构建链接的痕迹导航。

## 用途 {#usage}

痕迹导航组件显示当前页面在网站层级中的位置，并允许页面访客从其当前位置导航页面层级。它通常集成到页眉或页脚中。

可用选项（例如，默认导航级别和显示当前页面或隐藏页面的能力）可由模板作者在[“设计”对话框](#design-dialog)中定义。然后，内容编辑者可以在[“编辑”对话框](#edit-dialog)中选择是否显示隐藏的页面以及组件的实际导航级别。

## 版本和兼容性 {#version-and-compatibility}

本文档介绍了痕迹导航组件 (v1)，它最初随带 AEM 6.3 的核心组件 1.0.0 版引入。

下表列出了痕迹导航组件 (v1) 的兼容性。

| AEM 版本 | 痕迹导航组件 v1 |
|--- |--- |
| 6.3 | 兼容 |
| 6.4 | 兼容 |

>[!CAUTION]
>
>本文档介绍了痕迹导航组件 (v1)。
>>有关当前版本的痕迹导航组件的详细信息，请参阅[痕迹导航组件](/help/components/breadcrumb.md)文档。

## 示例组件输出 {#sample-component-output}

以下是摘自 [We.Retail](https://helpx.adobe.com/cn/experience-manager/6-4/sites/developing/using/we-retail.html) 的示例。

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
>从核心组件执行 JSON 导出需要版本 1.1.0 的核心组件。 有关更多信息，请参阅[核心组件 v1 的兼容性信息](/help/versions.md)。

## “编辑”对话框 {#edit-dialog}

利用“编辑”对话框，内容作者可以在痕迹导航中禁止显示隐藏的页面和活动的页面以及它应显示的层级中的深度。

![](/help/assets/chlimage_1-34.png)

* **导航级别中的开始位置** - 层级中的位置，痕迹导航组件从该位置开始向下导航到当前页面。例如，在 We.Retail 中：

   * 1 在 `/content/we-retail` 开始
   * 2 在 `/content/we-retail/<country>` 开始

* **显示隐藏页面** - 在痕迹导航中显示标记为隐藏的页面（默认情况，这些页面不会显示）
* **隐藏当前页面** - 在痕迹导航中禁止显示当前页面（默认情况，该页面将显示）

## “设计”对话框 {#design-dialog}

利用“设计”对话框，模板作者可以定义选项的默认值，以便在痕迹导航中禁止显示隐藏的页面和活动的页面，以及指定应显示的层级中的深度。

![](/help/assets/chlimage_1-35.png)

* **导航级别中的开始位置** - 定义层级中位置的默认值，在将痕迹导航组件添加到页面后，它会从该位置开始向下导航到当前页面。
* **显示隐藏页面** - 在向页面添加痕迹导航组件时，定义&#x200B;**显示隐藏页面**&#x200B;选项的默认值。

   * 它不会为作者启用或禁用该选项。它仅设置默认值。

* **显示当前页面** - 在向页面添加痕迹导航组件时，定义&#x200B;**隐藏当前页面**&#x200B;选项的默认值。

   * 它不会为作者启用或禁用该选项。它仅设置默认值。

## 技术详细信息 {#technical-details}

[在 GitHub 上可找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v1/breadcrumb)有关痕迹导航组件的最新技术文档。

从 GitHub 可下载整个核心组件项目。

在[核心组件开发人员文档](/help/developing/overview.md)中可找到有关开发核心组件的其他详细信息。
