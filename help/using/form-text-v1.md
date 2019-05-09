---
title: 表单文本组件(v1)
seo-title: 表单文本组件(v1)
description: 'null'
seo-description: 核心组件表单文本组件允许提交表单文本。
uuid: 30123aa-57a8-4ed4-93cb-6a3d3d edff9a7
content-type: 引用
products: SG_ EXPERIENCE MANAGER/CORECOMMPANES-new
discoiquuid: bd4e9930-4d81-49ae-a3 d1-9a8740418 DAE
index: n
translation-type: tm+mt
source-git-commit: 1bbec9b1f109df88964dce051a58d111bf6cafaa

---


# 表单文本组件(v1){#form-text-component-v}

核心组件表单文本组件允许提交表单文本。

## 使用情况 {#usage}

表单文本组件允许提交不同类型的文本，并旨在与 [表单容器组件一起使用](form-container.md)。

文本验证、标签和帮助消息类型可由 [配置对话框中的内容编辑器定义](form-text-v1.md#main-pars_title)。

## 版本和兼容性 {#version-and-compatibility}

本文档描述了表单文本组件的v1，该组件最初随AEM6.3的核心组件版本1.0.0一起引入。

下表列出了表单文本组件的v1的兼容性。

| AEM 版本 | 表单文本组件v1 |
|--- |--- |
| 6.3 | 兼容 |
| 6.4 | 兼容 |

>[!CAUTION]
>
>本文档描述表单文本组件的v1。
>
>有关表单文本组件的当前版本的详细信息，请参阅 [表单文本组件](form-text.md) 文档。

## 示例组件输出 {#sample-component-output}

以下示例取自 [We. Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)。

### 屏幕快照 {#screenshot}

![](assets/chlimage_1-22.png)

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
>核心组件中的JSON导出需要核心组件版本1.1.0。有关更多信息，请参见核心组件v [](versions.md#main-pars_title_236368006) 的兼容性信息。

## 配置对话框 {#configure-dialog}

配置对话框允许内容作者定义要输入的文本类型以及默认值和标签。

### 主要 {#main}

![](assets/chlimage_1-23.png)

* **约束** -要输入的文本类型，将针对

   * **文本**
   * **文本区域**
   * **电子邮件**
   * **电话**
   * **日期**
   * **数字**
   * **密码**

* **文本行** -要在文本区域中显示的行数(仅 **当“约束”** 设置为 **文本区域时显示**)

* **标签** -将为字段显示的标签
* **隐藏显示的标签** -如果标签仅用于辅助功能，且不构成有关字段的任何其他可视化信息，则需要此标签
* **元素名称** -用表单数据提交的字段名称
* **值** -在字段中预填充的默认值

### 关于 {#about}

![](assets/chlimage_1-24.png)

* **帮助消息** -向用户提示字段中输入内容的提示
* **将帮助信息显示为占位符** -在表单为空且未聚焦时，在表单输入中显示帮助消息

### 约束 {#constraints}

![](assets/chlimage_1-25.png)

* **约束消息**

   * 如果该值对于所选的类型无效，则在提交表单时，将以工具提示形式显示消息
   * 不显示 **文本** 和 **文本区域** 限制类型

* **必需** -如果选择此选项，用户必须在提交表单前填写一个值
* **仅设为只读** -如果选择此选项，用户将无法修改字段的值

## 设计对话框 {#design-dialog}

表单文本组件没有设计对话框。

## 技术详细信息 {#technical-details}

有关表单文本组件 [的最新技术文档可在GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/text/v1/text)上找到。

可以从GitHub下载整个核心组件项目。

有关开发核心组件的更多详细信息，请参阅 [核心组件开发人员文档](developing.md)。
