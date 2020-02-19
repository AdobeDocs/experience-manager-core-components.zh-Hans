---
title: 表单文本组件
description: 核心组件表单文本组件允许输入表单文本以供提交。
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

---


# 表单文本组件{#form-text-component}

核心组件表单文本组件允许输入表单文本以供提交。

## 使用情况 {#usage}

表单文本组件允许提交不同类型的文本，并准备与表单容器组件一 [起使用](form-container.md)。 文本验证、标签和帮助消息的类型可由内容编辑器在配置对话框中 [定义](#configure-dialog)。

## 版本和兼容性 {#version-and-compatibility}

表单文本组件的当前版本为v2，该版本在2018年1月随核心组件的2.0.0版一起推出，本文档对此进行了说明。

下表详细列出了组件的所有受支持版本、与组件版本兼容的AEM版本，以及指向先前版本的文档的链接。

| 组件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM作为云服务 |
|--- |--- |--- |--- |---|
| v2 | 兼容 | 兼容 | 兼容 | 兼容 |
| [v1](/help/components/v1/form-text-v1.md) | 兼容 | 兼容 | 兼容 | - |

有关核心组件版本和版本的详细信息，请参阅文档核 [心组件版本](/help/versions.md)。

## 示例组件输出 {#sample-component-output}

以下是从 [We.Retail获取的示例](https://docs.adobe.com/content/help/en/experience-manager-65/developing/bestpractices/we-retail/we-retail.html)。

### 屏幕快照 {#screenshot}

![](/help/assets/chlimage_1-22.png)

### HTML {#html}

```
<div class="text aem-GridColumn aem-GridColumn--default--12">
   <div class="cmp-form-text">
      <label for="form-text-2146967">How many pieces of toast would you like?
      </label>
   <input class="cmp-form-text__text" type="number" id="form-text-2146967" name="pieces">
   </div>
</div>
```

### JSON {#json}

```
"text":{  
                     "columnClassNames":"aem-GridColumn aem-GridColumn--default--12",
                     "id":"form-text-2146967",
                     "title":"How many pieces of toast would you like?",
                     "name":"pieces",
                     "value":"",
                     "helpMessage":"",
                     "type":"number",
                     "readOnly":false,
                     "required":false,
                     "requiredMessage":"",
                     "constraintMessage":"",
                     "rows":2,
                     "defaultValue":"",
                     ":type":"core/wcm/components/form/text/v2/text"
                  }
```

### 技术详细信息 {#technical-details}

有关表单文本组件的最新技 [术文档可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_form_text_v2)。

有关开发核心组件的更多详细信息，请参阅核 [心组件开发人员文档](/help/developing/overview.md)。

## 配置对话框 {#configure-dialog}

配置对话框允许内容作者定义要输入的文本类型以及默认值和标签。

### 主选项卡 {#main-tab}

![](/help/assets/chlimage_1-23.png)

* **约**&#x200B;束要输入并将验证的文本类型
   * **文本**
   * **文本区域**
   * **电子邮件**
   * **电话**
   * **日期**
   * **数字**
   * **密码**
* **文本行**&#x200B;要在文本区域中显示的行数(仅当“约束”设置为“文本区 **域** ”时 **显示**)
* **标签**&#x200B;将为字段显示的标签
* **如果标签仅用于辅助功能**，并且不会传递有关该字段的任何其他可视信息，则隐藏标签，使其不显示
* **元素名**&#x200B;称随表单数据一起提交的字段的名称
* **值**&#x200B;字段中预填充的默认值

### 关于选项卡 {#about-tab}

![](/help/assets/chlimage_1-24.png)

* **帮助消**&#x200B;息提示用户可在字段中输入的内容
* **将帮助消息显示为占**&#x200B;位符在表单输入为空且未聚焦时在表单输入内显示帮助消息

### 约束选项卡 {#constraints-tab}

![](/help/assets/chlimage_1-25.png)

* **约束消息**
   * 如果该值对于所选的类型无效，则在提交表单时，将以工具提示形式显示消息
   * 不显示文本和 **文本****区域约束类型**
* **必需**：如果选择此项，则用户必须在提交表单之前填写值
* **设为只读**&#x200B;如果选中此选项，则用户无法修改字段的值

## 设计对话框 {#design-dialog}

表单文本组件没有设计对话框。
