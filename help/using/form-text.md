---
title: 表单文本组件
seo-title: 表单文本组件
description: 'null'
seo-description: 核心组件表单文本组件允许输入表单文本以供提交。
uuid: f2418d55-0b59-4c7c-a541-d12dda4db4cf
contentOwner: 用户
content-type: 引用
topic-tags: 创作
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-new
discoiquuid: 3a970c4b-806b-4a0a-b6b8-b3dca4e9f136
disttype: dist5
gnavtheme: 浅色
groupsectionnavitems: 否
hidemerchandisingbar: 继承
hidepromocomponent: 继承
modalsize: 426 x 240
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1243d6cc1b0b015ee2f37ae89d0e2e42d366cc02

---


# 表单文本组件{#form-text-component}

核心组件表单文本组件允许输入表单文本以供提交。

## 使用情况 {#usage}

表单文本组件允许提交不同类型的文本，并准备与表单容器组件一 [起使用](form-container.md)。 文本验证、标签和帮助消息的类型可由内容编辑器在配置对话框中 [定义](#configure-dialog)。

## 版本和兼容性 {#version-and-compatibility}

表单文本组件的当前版本为v2，该版本在2018年1月随核心组件的2.0.0版一起推出，本文档对此进行了说明。

下表详细列出了组件的所有受支持版本、与组件版本兼容的AEM版本，以及指向先前版本的文档的链接。

| 组件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v2 | 兼容 | 兼容 | 兼容 |
| [v1](form-text-v1.md) | 兼容 | 兼容 | 兼容 |

For more information about Core Component versions and releases, see the document [Core Components Versions](versions.md).

## 示例组件输出 {#sample-component-output}

以下是从 [We.Retail获取的示例](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html)。

### 屏幕快照 {#screenshot}

![](assets/chlimage_1-22.png)

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

### Technical Details {#technical-details}

有关表单文本组件的最新技 [术文档可在GitHub上找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/text/v2/text)。

Further details about developing Core Components can be found in the Core Components developer documentation.[](developing.md)

## Configure Dialog {#configure-dialog}

The configure dialog allows the content author to define the type of text to be input as well as default values and labels.

### Main Tab {#main-tab}

![](assets/chlimage_1-23.png)

* **Constraint
The type of text to be input and will be validated against**
   * **文本**
   * **文本区域**
   * **电子邮件**
   * **电话**
   * **日期**
   * **数字**
   * **密码**
* **Text lines
Number of lines to be displayed in the text area (only displayed when Constraint is set to Text Area)**********
* **标签**&#x200B;将为字段显示的标签
* **如果标签仅用于辅助功能**，并且不会传递有关该字段的任何其他可视信息，则隐藏标签，使其不显示
* **元素名**&#x200B;称随表单数据一起提交的字段的名称
* **值**&#x200B;字段中预填充的默认值

### About Tab {#about-tab}

![](assets/chlimage_1-24.png)

* **帮助消**&#x200B;息提示用户可在字段中输入的内容
* **Display help message as placeholder**
To display the help message inside the form input when it is empty and not focused

### 约束选项卡 {#constraints-tab}

![](assets/chlimage_1-25.png)

* **约束消息**
   * 如果该值对于所选的类型无效，则在提交表单时，将以工具提示形式显示消息
   * 不显示文本和 **文本****区域约束类型**
* **Required**
If selected the user must fill in a value before submitting the form
* **设为只读**&#x200B;如果选中此选项，则用户无法修改字段的值

## 设计对话框 {#design-dialog}

表单文本组件没有设计对话框。