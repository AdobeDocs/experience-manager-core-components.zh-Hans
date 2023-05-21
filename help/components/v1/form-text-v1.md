---
title: 表单文本组件 (v1)
description: 利用核心组件表单文本组件，可以输入表单文本供提交。
index: n
role: Architect, Developer, Admin, User
exl-id: d6fbc596-cb42-4478-8a3c-aa5aead3be0a
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 100%

---

# 表单文本组件 (v1) {#form-text-component-v}

利用核心组件表单文本组件，可以输入表单文本供提交。

## 用途 {#usage}

利用表单文本组件可提交不同类型的文本，此组件旨在与[表单容器组件](form-container-v1.md)结合使用。

文本验证的类型、标签和帮助消息可由内容编辑者在[“配置”对话框](#configure-dialog)中定义。

## 版本和兼容性 {#version-and-compatibility}

本文档介绍了表单文本组件 (v1)，它最初随带 AEM 6.3 的核心组件 1.0.0 版引入。

下表列出了表单文本组件 (v1) 的兼容性。

| AEM 版本 | 表单文本组件 v1 |
|--- |--- |
| 6.3 | 兼容 |
| 6.4 | 兼容 |

>[!CAUTION]
>
>本文档介绍了表单文本组件 (v1)。
>
>有关当前版本的表单文本组件的详细信息，请参阅[表单文本组件](/help/components/forms/form-text.md)文档。

## 示例组件输出 {#sample-component-output}

以下是摘自 [We.Retail](https://helpx.adobe.com/cn/experience-manager/6-4/sites/developing/using/we-retail.html) 的示例。

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
>从核心组件执行 JSON 导出需要版本 1.1.0 的核心组件。 有关更多信息，请参阅[核心组件 v1 的兼容性信息](/help/versions.md)。

## “配置”对话框 {#configure-dialog}

利用“配置”对话框，内容作者可以定义要作为默认值和标签输入的文本的类型。

### 主要 {#main}

![](/help/assets/chlimage_1-23.png)

* **约束** - 要输入并进行验证的文本的类型。

   * **文本**
   * **文本区域**
   * **电子邮件**
   * **电话**
   * **日期**
   * **数字**
   * **密码**

* **文本行** - 在文本区域中显示的行数（仅在&#x200B;**约束**&#x200B;设置为&#x200B;**文本区域**&#x200B;时显示）

* **标签** - 将为字段显示的标签
* **隐藏标签以不被显示** - 在标签仅用于辅助功能且不影响有关字段的任何其他可视信息时需要
* **元素名称** - 随表单数据一起提交的字段的名称
* **值** - 在字段中预填充的默认值

### 关于 {#about}

![](/help/assets/chlimage_1-24.png)

* **帮助消息** - 关于用户可在字段中输入的内容的提示
* **将帮助消息显示为占位符** - 当表单输入为空且焦点不在其上时，在表单输入中显示帮助消息

### 约束 {#constraints}

![](/help/assets/chlimage_1-25.png)

* **约束消息**

   * 如果该值对于所选的类型无效，则在提交表单时，将以工具提示形式显示消息
   * 对于&#x200B;**文本**&#x200B;和&#x200B;**文本区域**&#x200B;约束类型不显示

* **必填** - 如果选择，用户必须在提交表单之前填充值
* **使只读** - 如果选中，用户无法修改字段的值

## “设计”对话框 {#design-dialog}

表单文本组件没有“设计”对话框。

## 技术详细信息 {#technical-details}

[在 GitHub 上可找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/text/v1/text)有关表单文本组件的最新技术文档。

从 GitHub 可下载整个核心组件项目。

在[核心组件开发人员文档](/help/developing/overview.md)中可找到有关开发核心组件的其他详细信息。
