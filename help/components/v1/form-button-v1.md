---
title: 表单按钮组件(v1)
description: 核心组件表单隐藏组件允许在表单中包含隐藏字段。
index: n
role: Architect, Developer, Administrator, Business Practitioner
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 3%

---


# 表单按钮组件(v1){#form-button-component-v}

核心组件表单按钮组件允许在表单中包含按钮字段以触发操作。

## 使用 {#usage}

核心组件表单按钮组件允许创建按钮字段，通常用于触发表单的提交，并准备与[表单容器组件](form-container-v1.md)一起使用。

按钮属性可由[配置对话框](#configure-dialog)中的内容编辑器定义。

## 版本和兼容性{#version-and-compatibility}

本文档描述了最初随AEM 6.3核心组件版本1.0.0引入的表单按钮组件的v1。

下表列表了“表单按钮”组件v1的兼容性。

| AEM 版本 | 表单按钮组件v1 |
|--- |--- |
| 6.3 | 兼容 |
| 6.4 | 兼容 |

>[!CAUTION]
>
>本文档描述了表单按钮组件的v1。
>
>有关表单按钮组件当前版本的详细信息，请参阅[表单按钮组件](/help/components/forms/form-button.md)文档。

## 示例组件输出{#sample-component-output}

以下是从[We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)取的示例。

### 屏幕快照 {#screenshot}

![](/help/assets/chlimage_1-48.png)

### HTML {#html}

```
<div class="cmp cmp-button aem-GridColumn aem-GridColumn--default--12">
    <div class="cmp cmp-button">
        <button type="BUTTON" class="btn btn-action btn-primary" name="loveToast" value="ILoveToast">
            Click here if you love toast!
        </button>
    </div>
</div>
```

### JSON {#json}

```
"container": {
              "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
              "columnCount": 12,
              "gridClassNames": "aem-Grid aem-Grid--12 aem-Grid--default--12",
              ":items": {
                "button": {
                  "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
                  ":type": "weretail/components/form/button",
                  "name": "loveToast",
                  "jcr:title": "Click here if you love toast!",
                  "type": "submit",
                  "value": "ILoveToast"
                }
              },
              ":itemsOrder": [
                "button"
              ],
              ":type": "weretail/components/form/container"
            }
```

>[!NOTE]
>
>从核心组件导出JSON需要1.1.0版的核心组件。 有关详细信息，请参阅核心组件v1](/help/versions.md)的[兼容性信息。

## 配置对话框{#configure-dialog}

配置对话框允许内容作者定义按钮的参数。

![](/help/assets/chlimage_1-49.png)

* **类型**
   * **按钮**
   * **提交**

* **标题**  — 按钮上显示的文本
   * 如果未提供，则默认为按钮类型

* **名称**  — 随表单数据提交的按钮的名称
* **值**  — 随表单数据一起提交的按钮的值

## 设计对话框{#design-dialog}

表单按钮组件没有设计对话框。

## 技术详细信息{#technical-details}

有关“表单按钮组件[”的最新技术文档，可在GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/button/v1/button)上找到。

整个核心组件项目可从GitHub下载。

有关开发核心组件的更多详细信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。
