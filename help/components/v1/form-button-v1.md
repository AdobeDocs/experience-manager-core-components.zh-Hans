---
title: 表单按钮组件 (v1)
description: 利用核心组件表单隐藏组件，可在表单中包含隐藏字段。
index: n
role: Architect, Developer, Admin, User
exl-id: 2c06a942-7ac5-4847-9d11-7bbcd0ea51bd
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 100%

---

# 表单按钮组件 (v1) {#form-button-component-v}

利用核心组件表单按钮组件，可在表单中包含按钮字段来触发操作。

## 用途 {#usage}

利用核心组件表单按钮组件可以创建按钮字段（这通常会触发表单提交），并且此组件旨在与[表单容器组件](form-container-v1.md)结合使用。

按钮属性可由内容编辑者在[“配置”对话框](#configure-dialog)中定义。

## 版本和兼容性 {#version-and-compatibility}

本文档介绍了表单按钮组件 (v1)，它最初随带 AEM 6.3 的核心组件 1.0.0 版引入。

下表列出了表单按钮组件 (v1) 的兼容性。

| AEM 版本 | 表单按钮组件 v1 |
|--- |--- |
| 6.3 | 兼容 |
| 6.4 | 兼容 |

>[!CAUTION]
>
>本文档介绍了表单按钮组件 (v1)。
>
>有关当前版本的表单按钮组件的详细信息，请参阅[表单按钮组件](/help/components/forms/form-button.md)文档。

## 示例组件输出 {#sample-component-output}

以下是摘自 [We.Retail](https://helpx.adobe.com/cn/experience-manager/6-4/sites/developing/using/we-retail.html) 的示例。

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
>从核心组件执行 JSON 导出需要版本 1.1.0 的核心组件。 有关更多信息，请参阅[核心组件 v1 的兼容性信息](/help/versions.md)。

## “配置”对话框 {#configure-dialog}

利用“配置”对话框，内容作者可以定义按钮的参数。

![](/help/assets/chlimage_1-49.png)

* **类型**
   * **按钮**
   * **提交**

* **标题** - 按钮上显示的文本
   * 如果未提供，则默认为按钮类型

* **名称** - 随表单数据一起提交的按钮的名称
* **值** - 随表单数据一起提交的按钮的值

## “设计”对话框 {#design-dialog}

表单按钮组件没有“设计”对话框。

## 技术详细信息 {#technical-details}

[在 GitHub 上可找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/button/v1/button)有关表单按钮组件的最新技术文档。

从 GitHub 可下载整个核心组件项目。

在[核心组件开发人员文档](/help/developing/overview.md)中可找到有关开发核心组件的其他详细信息。
