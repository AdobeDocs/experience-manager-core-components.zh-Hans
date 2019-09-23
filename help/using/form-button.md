---
title: 表单按钮组件
seo-title: 表单按钮组件
description: 'null'
seo-description: 核心组件表单隐藏组件允许在表单中包含隐藏字段。
uuid: 22c53cd0-d0bc-4e5d-89f3-5ac4f61a9100
contentOwner: 用户
content-type: 引用
topic-tags: 创作
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-新
discoiquuid: a6e2974a-243f-40ab-903c-c7d3e8615bcc
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


# 表单按钮组件{#form-button-component}

核心组件表单按钮组件允许包含按钮以触发页面上的操作。

## 使用情况 {#usage}

核心组件表单按钮组件允许创建按钮字段，通常用于触发表单的提交，并准备与表单容器组件一 [起使用](form-container.md)。

按钮属性可由内容编辑器在配置对话框中 [定义](form-button.md)。

## 版本和兼容性 {#version-and-compatibility}

表单按钮组件的当前版本为v2,v2是2018年1月随核心组件版本2.0.0一起引入的，本文档对此进行了说明。

下表详细列出了组件的所有受支持版本、与组件版本兼容的AEM版本，以及指向先前版本的文档的链接。

| 组件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v2 | 兼容 | 兼容 | 兼容 |
| [v1](form-button-v1.md) | 兼容 | 兼容 | 兼容 |

有关核心组件版本和版本的详细信息，请参阅文档核 [心组件版本](versions.md)。

## 示例组件输出 {#sample-component-output}

以下是从 [We.Retail获取的示例](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html)。

### 屏幕快照 {#screenshot}

![](assets/screen_shot_2018-01-12at120021.png)

### HTML {#html}

```
<div class="container responsivegrid aem-GridColumn aem-GridColumn--default--12">
<form method="POST" action="/content/we-retail/us/en/experience.html" id="new_form" name="new_form" enctype="multipart/form-data" class="cmp-form aem-Grid aem-Grid--12 aem-Grid--default--12">
    <input type="hidden" name=":formstart" value="/content/we-retail/us/en/experience/jcr:content/root/responsivegrid/container">
    
    <div class="button aem-GridColumn aem-GridColumn--default--12">
<button type="BUTTON" class="cmp-form-button" name="loveToast" value="ILoveToast">Click here if you love toast!</button>
</div>

</form>
</div>
```

### JSON {#json}

```
"button":{  
                           "columnClassNames":"aem-GridColumn aem-GridColumn--default--12",
                           ":type":"core/wcm/sandbox/components/form/button/v2/button",
                           "name":"loveToast",
                           "jcr:title":"Click here if you love toast!",
                           "type":"button",
                           "value":"ILoveToast"
                        }
```

### 技术详细信息 {#technical-details}

有关“表单按钮组件”的最 [新技术文档可在GitHub上找到](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/form/button/v2/button)。

有关开发核心组件的更多详细信息，请参阅核 [心组件开发人员文档](developing.md)。

## 配置对话框 {#configure-dialog}

配置对话框允许内容作者定义按钮的参数。

### 属性选项卡 {#properties-tab}

![](assets/screen_shot_2018-01-12at120433.png)

* **类型**

   * **按钮**
   * **提交**

* **标题** -按钮上显示的文本

   * 如果未提供，则默认为按钮类型

* **名称** -随表单数据一起提交的按钮的名称
* **值** -随表单数据一起提交的按钮的值

## 设计对话框 {#design-dialog}

### 样式选项卡 {#styles-tab}

表单按钮组件支持AEM样 [式系统](authoring.md#component-styling)。