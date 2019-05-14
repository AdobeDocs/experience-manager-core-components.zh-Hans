---
title: 表单隐藏组件
seo-title: 表单隐藏组件
description: 'null'
seo-description: 核心组件表单隐藏组件允许显示隐藏字段。
uuid: 63a1b381-f45 c-4241-b743-dea8 abd45 e11
contentOwner: 用户
content-type: 引用
topic-tags: 核心组件
discoiquuid: 36e49035-7641-4bad-8a61-7223060032903
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


# 表单隐藏组件{#form-hidden-component}

核心组件表单隐藏组件允许显示隐藏字段。

## 使用情况 {#usage}

核心组件表单隐藏组件允许创建隐藏字段，以将有关当前页面的信息传递回AEM，并计划与 [表单容器组件一起使用](form-container.md)。

字段属性可由 [配置对话框中的内容编辑器定义](form-hidden.md)。

## 版本和兼容性 {#version-and-compatibility}

Form Hidden Component的当前版本是v2，它是在2018年月版中随核心组件发行引入的，文档中对此进行了介绍。

下表详细说明了组件的所有支持版本、组件版本的AEM版本以及以前版本的文档链接。

| 组件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v2 | 兼容 | 兼容 | 兼容 |
| [v1](form-hidden-v1.md) | 兼容 | 兼容 | 兼容 |

有关核心组件版本和版本的更多信息，请参阅文档 [核心组件版本](versions.md)。

## 示例组件输出 {#sample-component-output}

以下示例取自 [We. Retail](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html)。

### HTML {#html}

```
<div class="cmp cmp-form aem-GridColumn aem-GridColumn--default--12">
 <form method="POST" action="/content/we-retail/us/en/experience.html" id="new_form" name="new_form" enctype="multipart/form-data" class="aem-Grid aem-Grid--12 aem-Grid--default--12 ">
  <input type="hidden" name=":formstart" value="/content/we-retail/us/en/experience/jcr:content/root/responsivegrid/container">
   <div class="visible aem-GridColumn aem-GridColumn--default--12">
    <input type="hidden" id="ghostToast" name="Invisible Toast" value="ghostToast">
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
                "hidden": {
                  "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
                  ":type": "weretail/components/form/hidden",
                  "name": "Invisible Toast",
                  "id": "ghostToast",
                  "value": "ghostToast"
                }
              },
              ":itemsOrder": [
                "hidden"
              ],
              ":type": "weretail/components/form/container"
            }
```

### 技术详细信息 {#technical-details}

有关表单隐藏组件 [的最新技术文档，可在GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/form/hidden/v2/hidden)上找到。

有关开发核心组件的更多详细信息，请参阅 [核心组件开发人员文档](developing.md)。

## 配置对话框 {#configure-dialog}

配置对话框允许内容作者定义隐藏字段的参数。

![](assets/chlimage_1-26.png)

* **名称**使用表单数据提交的字段名称
* **值**字段使用表单数据提交的值
* **标识符标识符**在页面上应是唯一的，可用于将脚本绑定到此表单字段

因为“表单隐藏”组件通常没有可见属性，因此，在编辑器中，组件的占位符会显示 **“名称** ”和 **“值”** 字段值，以帮助作者识别相应的“表单隐藏”组件。

![](assets/screenshot_2018-10-19at094927.png)

## 设计对话框 {#design-dialog}

表单隐藏组件没有设计对话框。