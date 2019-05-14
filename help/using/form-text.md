---
title: 表单文本组件
seo-title: 表单文本组件
description: 'null'
seo-description: 核心组件表单文本组件允许提交表单文本。
uuid: f2418d55-3b59-4c7c-a541-d12 dda4 db4 cf
contentOwner: 用户
content-type: 引用
topic-tags: 创作
products: SG_ EXPERIENCE MANAGER/CORECOMMPANES-new
discoiquuid: a970c4b-806b-4a0a-b6 b8-b3 dca4 e9 f136
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

核心组件表单文本组件允许提交表单文本。

## 使用情况 {#usage}

表单文本组件允许提交不同类型的文本，并旨在与 [表单容器组件一起使用](form-container.md)。文本验证、标签和帮助消息类型可由 [配置对话框中的内容编辑器定义](#configure-dialog)。

## 版本和兼容性 {#version-and-compatibility}

表单文本组件的当前版本是v2，它是在2018年月核心组件的发行版2.0.0中引入的，文档中对此进行了介绍。

下表详细说明了组件的所有支持版本、组件版本的AEM版本以及以前版本的文档链接。

| 组件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v2 | 兼容 | 兼容 | 兼容 |
| [v1](form-text-v1.md) | 兼容 | 兼容 | 兼容 |

有关核心组件版本和版本的更多信息，请参阅文档 [核心组件版本](versions.md)。

## 示例组件输出 {#sample-component-output}

以下示例取自 [We. Retail](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html)。

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

### 技术详细信息 {#technical-details}

有关表单文本组件 [的最新技术文档可在GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/text/v2/text)上找到。

有关开发核心组件的更多详细信息，请参阅 [核心组件开发人员文档](developing.md)。

## 配置对话框 {#configure-dialog}

配置对话框允许内容作者定义要输入的文本类型以及默认值和标签。

### 主选项卡 {#main-tab}

![](assets/chlimage_1-23.png)

* **约束**要输入的文本类型并针对其进行验证
   * **文本**
   * **文本区域**
   * **电子邮件**
   * **电话**
   * **日期**
   * **数字**
   * **密码**
* **文本线**要在文本区域中显示的行数(仅 **当“约束”** 设置为 **文本区域时显示**)
* **标签**将为字段显示的标签
* **如果仅出于辅助功能**目的而需要标签，且不会影响与字段有关的任何其他可视化信息，则隐藏该标签。
* **元素名称**随表单数据提交的字段名称
* **在字段中预填充的值**默认值

### 关于选项卡 {#about-tab}

![](assets/chlimage_1-24.png)

* **帮助消息**提示用户在字段中输入内容的提示
* **将帮助信息显示为占位符**在表单为空且未聚焦时显示表单输入中的帮助消息

### 约束选项卡 {#constraints-tab}

![](assets/chlimage_1-25.png)

* **约束消息**
   * 如果该值对于所选的类型无效，则在提交表单时，将以工具提示形式显示消息
   * 不显示 **文本** 和 **文本区域** 限制类型
* **必需**如果选择此选项，用户必须在提交表单前填写一个值
* **使只读成为只读**的情况下，用户无法修改字段的值

## 设计对话框 {#design-dialog}

表单文本组件没有设计对话框。