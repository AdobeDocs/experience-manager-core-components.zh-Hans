---
title: 表单文本组件(v1)
description: 核心组件表单文本组件允许输入表单文本以供提交。
index: n
role: Architect, Developer, Administrator, Business Practitioner
exl-id: d6fbc596-cb42-4478-8a3c-aa5aead3be0a
source-git-commit: 8ff36ca143af9496f988b1ca65475497181def1d
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 8%

---

# 表单文本组件(v1){#form-text-component-v}

核心组件表单文本组件允许输入表单文本以供提交。

## 使用 {#usage}

表单文本组件允许提交不同类型的文本，并准备与[表单容器组件](form-container-v1.md)一起使用。

文本验证、标签和帮助消息的类型可由[配置对话框](#configure-dialog)中的内容编辑器定义。

## 版本和兼容性{#version-and-compatibility}

本文档介绍了表单文本组件v1，最初是在AEM 6.3的核心组件1.0.0版中引入的。

下表列出了表单文本组件v1的兼容性。

| AEM 版本 | 表单文本组件v1 |
|--- |--- |
| 6.3 | 兼容 |
| 6.4 | 兼容 |

>[!CAUTION]
>
>本文档介绍表单文本组件的v1。
>
>有关表单文本组件当前版本的详细信息，请参阅[表单文本组件](/help/components/forms/form-text.md)文档。

## 组件输出示例{#sample-component-output}

以下是从[We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)获取的示例。

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
>从核心组件导出JSON时，需要安装核心组件版本1.1.0。 有关更多信息，请参阅核心组件v1](/help/versions.md)的[兼容性信息。

## 配置对话框{#configure-dialog}

配置对话框允许内容作者定义要输入的文本类型以及默认值和标签。

### 主要 {#main}

![](/help/assets/chlimage_1-23.png)

* **约束**  — 要输入并将针对其进行验证的文本类型

   * **文本**
   * **文本区域**
   * **电子邮件**
   * **电话**
   * **日期**
   * **数字**
   * **密码**

* **文本行**  — 要在文本区域中显示的行数(仅当“约束”设置为“文 **** 本区域” **时显示**)

* **标签**  — 将为字段显示的标签
* **隐藏标签以防显示**  — 如果仅出于辅助功能目的而需要标签，并且不会传递有关该字段的任何其他可视化信息，则需要此标签
* **元素名称**  — 随表单数据一起提交的字段的名称
* **值**  — 在字段中预填充的默认值

### 关于 {#about}

![](/help/assets/chlimage_1-24.png)

* **帮助消息**  — 向用户提示可在字段中输入的内容
* **将帮助消息显示为占位符**  — 在表单输入中显示帮助消息，当该消息为空且未集中

### 约束 {#constraints}

![](/help/assets/chlimage_1-25.png)

* **约束消息**

   * 如果该值对于所选的类型无效，则在提交表单时，将以工具提示形式显示消息
   * 未显示&#x200B;**Text**&#x200B;和&#x200B;**Text Area**&#x200B;约束类型

* **必需**  — 如果选中此项，则用户必须在提交表单之前填写值
* **设为只读**  — 如果选中，则用户无法修改字段的值

## 设计对话框{#design-dialog}

表单文本组件没有设计对话框。

## 技术详细信息{#technical-details}

有关表单文本组件[的最新技术文档，请参阅GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/text/v1/text)。

可以从GitHub下载整个核心组件项目。

有关开发核心组件的更多详细信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。
