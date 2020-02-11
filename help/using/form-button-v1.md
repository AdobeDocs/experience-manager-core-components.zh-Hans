---
title: 表单按钮组件(v1)
description: 核心组件表单隐藏组件允许在表单中包含隐藏字段。
index: n
translation-type: tm+mt
source-git-commit: 5439f90faef28c72367419bb7429a3a880b65229

---


# Form Button Component (v1){#form-button-component-v}

核心组件表单按钮组件允许在表单中包含按钮字段以触发操作。

## 使用情况 {#usage}

核心组件表单按钮组件允许创建按钮字段，通常用于触发表单的提交，并准备与表单容器组件一 [起使用](form-container.md)。

按钮属性可由内容编辑器在配置对话框中 [定义](form-button-v1.md#main-pars_title)。

## 版本和兼容性 {#version-and-compatibility}

本文档描述了最初随AEM 6.3的核心组件版本1.0.0引入的表单按钮组件的v1。

下表列出了表单按钮组件v1的兼容性。

| AEM 版本 | 表单按钮组件v1 |
|--- |--- |
| 6.3 | 兼容 |
| 6.4 | 兼容 |

>[!CAUTION]
>
>本文档描述了表单按钮组件的v1。
>
>有关表单按钮组件当前版本的详细信息，请参阅表 [单按钮组件文档](form-button.md) 。

## 示例组件输出 {#sample-component-output}

以下是从 [We.Retail获取的示例](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)。

### 屏幕快照 {#screenshot}

![](assets/chlimage_1-48.png)

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
>从核心组件导出JSON时，需要发行1.1.0版的核心组件。 有关详细信息， [请参阅核心组件v1的兼容性信息](versions.md#main-pars_title_236368006) 。

## 配置对话框 {#configure-dialog}

配置对话框允许内容作者定义按钮的参数。

![](assets/chlimage_1-49.png)

* **类型**
   * **按钮**
   * **提交**

* **标题** -按钮上显示的文本
   * 如果未提供，则默认为按钮类型

* **名称** -随表单数据一起提交的按钮的名称
* **值** -随表单数据一起提交的按钮的值

## 设计对话框 {#design-dialog}

“表单按钮”组件没有设计对话框。

## 技术详细信息 {#technical-details}

有关“表单按钮组件”的最 [新技术文档可在GitHub上找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/button/v1/button)。

整个核心组件项目可从GitHub下载。

有关开发核心组件的更多详细信息，请参阅核 [心组件开发人员文档](developing.md)。
