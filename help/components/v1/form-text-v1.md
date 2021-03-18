---
title: 表单文本组件(v1)
description: 核心组件表单文本组件允许输入要提交的表单文本。
index: n
role: 架构师、开发人员、管理员、业务从业者
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 8%

---


# 表单文本组件(v1){#form-text-component-v}

核心组件表单文本组件允许输入要提交的表单文本。

## 使用 {#usage}

表单文本组件允许提交不同类型的文本，并准备与[表单容器组件](form-container-v1.md)一起使用。

文本验证、标签和帮助消息的类型可由[配置对话框](#configure-dialog)中的内容编辑器定义。

## 版本和兼容性{#version-and-compatibility}

本文档描述了表单文本组件的v1，该组件最初随AEM 6.3核心组件的1.0.0版引入。

下表列表了表单文本组件v1的兼容性。

| AEM 版本 | 表单文本组件v1 |
|--- |--- |
| 6.3 | 兼容 |
| 6.4 | 兼容 |

>[!CAUTION]
>
>本文档介绍了表单文本组件的v1。
>
>有关表单文本组件当前版本的详细信息，请参阅[表单文本组件](/help/components/forms/form-text.md)文档。

## 示例组件输出{#sample-component-output}

以下是从[We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)取的示例。

### 屏幕快照 {#screenshot}

![](/help/assets/chlimage_1-22.png)

### HTML {#html}

```
<div class="cmp cmp-form aem-GridColumn aem-GridColumn--default--12">
 <form method="POST" action="/content/we-retail/us/en/experience.html" id="new_form" name="new_form" enctype="multipart/form-data" class="aem-Grid aem-Grid--12 aem-Grid--default--12 ">
     <input type="hidden" name=":formstart" value="/content/we-retail/us/en/experience/jcr:content/root/responsivegrid/container">
     <div class="cmp cmp-form-field aem-GridColumn aem-GridColumn--default--12">
   <div class="form-group">
       <label for="form-text-978484744">How many pieces of toast would you like?</label>
          <input type="number" id="form-text-978484744" name="pieces">
   </div>
  </div>
 </form>
</div>
```

### JSON {#json}

```
"container": {
              "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
              "columnCount": 12,
              "gridClassNames": "aem-Grid aem-Grid--12 aem-Grid--default--12",
              ":items": {
                "text": {
                  "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
                  ":type": "weretail/components/form/text",
                  "name": "piecesOfToast",
                  "jcr:title": "How many pieces of toast would you like?",
                  "type": "number",
                  "rows": "2"
                }
              },
              ":itemsOrder": [
                "text"
              ],
              ":type": "weretail/components/form/container"
            }
```

>[!NOTE]
>
>从核心组件导出JSON需要1.1.0版的核心组件。 有关详细信息，请参阅核心组件v1](/help/versions.md)的[兼容性信息。

## 配置对话框{#configure-dialog}

配置对话框允许内容作者定义要输入的文本类型以及默认值和标签。

### 主要 {#main}

![](/help/assets/chlimage_1-23.png)

* **约束**  — 要输入并将验证的文本类型

   * **文本**
   * **文本区域**
   * **电子邮件**
   * **电话**
   * **日期**
   * **数字**
   * **密码**

* **文本行**  — 要在文本区域中显示的行数(仅当“约束”设置为“文 **** 本区域”时 **显示**)

* **标签**  — 将为字段显示的标签
* **隐藏标签以免显示**  — 如果标签仅用于辅助功能目的而且不传递有关字段的任何其他可视信息，则需要
* **元素名称**  — 随表单数据提交的字段的名称
* **Value**  — 字段中预填充的默认值

### 关于 {#about}

![](/help/assets/chlimage_1-24.png)

* **帮助消息**  — 向用户提示可在字段中输入的内容
* **将帮助消息显示为占位符**  — 在表单输入为空且未聚焦时在表单输入内显示帮助消息

### 约束 {#constraints}

![](/help/assets/chlimage_1-25.png)

* **约束消息**

   * 如果该值对于所选的类型无效，则在提交表单时，将以工具提示形式显示消息
   * 未针对&#x200B;**Text**&#x200B;和&#x200B;**Text Area**&#x200B;约束类型显示

* **必需**  — 如果选中，则用户必须在提交表单之前填写值
* **设为只读**  — 如果选中，则用户无法修改字段的值

## 设计对话框{#design-dialog}

表单文本组件没有设计对话框。

## 技术详细信息{#technical-details}

有关表单文本组件[的最新技术文档可在GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/text/v1/text)上找到。

整个核心组件项目可从GitHub下载。

有关开发核心组件的更多详细信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。
