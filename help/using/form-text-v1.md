---
title: 表单文本组件(v1)
seo-title: 表单文本组件(v1)
description: 'null'
seo-description: 核心组件表单文本组件允许输入表单文本以供提交。
uuid: 30123aba-57a8-4ed4-93cb-6a3d2edff9a7
content-type: 引用
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-新
discoiquuid: bd4e9930-4d81-49ae-a3d1-9a8740418dae
index: n
translation-type: tm+mt
source-git-commit: 4e74f10e2a4119484a597178dc4577b399833dbf

---


# Form Text Component (v1){#form-text-component-v}

核心组件表单文本组件允许输入表单文本以供提交。

## 使用情况 {#usage}

表单文本组件允许提交不同类型的文本，并准备与表单容器组件一 [起使用](form-container.md)。

文本验证、标签和帮助消息的类型可由内容编辑器在配置对话框中 [定义](form-text-v1.md#main-pars_title)。

## 版本和兼容性 {#version-and-compatibility}

本文档描述了最初随AEM 6.3的核心组件版本1.0.0引入的表单文本组件v1。

下表列出了表单文本组件v1的兼容性。

| AEM 版本 | 表单文本组件v1 |
|--- |--- |
| 6.3 | 兼容 |
| 6.4 | 兼容 |

>[!CAUTION]
>
>本文档描述了表单文本组件的v1。
>
>有关表单文本组件的当前版本的详细信息，请参阅表 [单文本组件文档](form-text.md) 。

## 示例组件输出 {#sample-component-output}

以下是从 [We.Retail获取的示例](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)。

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
>从核心组件导出JSON时，需要发行1.1.0版的核心组件。 有关详细信息， [请参阅核心组件v1的兼容性信息](versions.md#main-pars_title_236368006) 。

## 配置对话框 {#configure-dialog}

配置对话框允许内容作者定义要输入的文本类型以及默认值和标签。

### 主要 {#main}

![](assets/chlimage_1-23.png)

* **约束** -要输入并将验证的文本类型

   * **文本**
   * **文本区域**
   * **电子邮件**
   * **电话**
   * **日期**
   * **数字**
   * **密码**

* **文本行** -要在文本区域中显示的行数(仅当“约束”设置为“文本区 **域** ”时 **显示**)

* **标签** -将为字段显示的标签
* **隐藏标签，不显示** -如果标签仅用于辅助功能目的而且不传递有关字段的任何其他可视信息，则需要
* **元素名称** -随表单数据一起提交的字段的名称
* **值** -字段中预填充的默认值

### 关于 {#about}

![](assets/chlimage_1-24.png)

* **帮助消息** -提示用户可在字段中输入的内容
* **将帮助消息显示为占位符** -在表单输入为空且未聚焦时在表单输入内显示帮助消息

### 约束 {#constraints}

![](assets/chlimage_1-25.png)

* **约束消息**

   * 如果该值对于所选的类型无效，则在提交表单时，将以工具提示形式显示消息
   * 不显示文本和 **文本****区域约束类型**

* **必需** -如果选择此项，则用户必须在提交表单之前填写值
* **设为只读** -如果选择此项，则用户无法修改字段的值

## 设计对话框 {#design-dialog}

表单文本组件没有设计对话框。

## 技术详细信息 {#technical-details}

有关表单文本组件的最新技 [术文档可在GitHub上找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/text/v1/text)。

整个核心组件项目可从GitHub下载。

有关开发核心组件的更多详细信息，请参阅核 [心组件开发人员文档](developing.md)。
