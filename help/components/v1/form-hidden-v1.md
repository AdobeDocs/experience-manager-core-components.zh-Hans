---
title: 表单隐藏组件 (v1)
description: 利用核心组件表单隐藏组件，可显示隐藏字段。
index: n
role: Architect, Developer, Admin, User
exl-id: 8e30dac0-5b4b-4fc7-af99-5791c98c90bf
source-git-commit: 92a3ec273a5be6751c1503835b9c2e5cbd61bb9e
workflow-type: ht
source-wordcount: '316'
ht-degree: 100%

---


# 表单隐藏组件 (v1) {#form-hidden-component-v}

利用核心组件表单隐藏组件，可显示隐藏字段。

## 用途 {#usage}

利用核心组件表单隐藏组件可创建隐藏字段以将有关当前页面的信息传递回 AEM，并且此组件旨在与[表单容器组件](form-container-v1.md)结合使用。

字段属性可由内容编辑者在[“配置”对话框](#configure-dialog)中定义。

## 版本和兼容性 {#version-and-compatibility}

本文档介绍了表单隐藏组件 (v1)，它最初随带 AEM 6.3 的核心组件 1.0.0 版引入。

下表列出了表单隐藏组件 (v1) 的兼容性。

| AEM 版本 | 表单隐藏组件 v1 |
|--- |--- |
| 6.3 | 兼容 |
| 6.4 | 兼容 |

>[!CAUTION]
>
>本文档介绍了表单隐藏组件 (v1)。
>
>有关当前版本的表单隐藏组件的详细信息，请参阅[表单隐藏组件](/help/components/forms/form-hidden.md)文档。

## 示例组件输出 {#sample-component-output}

以下是摘自 [We.Retail](https://helpx.adobe.com/cn/experience-manager/6-4/sites/developing/using/we-retail.html) 的示例。

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

>[!NOTE]
>
>从核心组件执行 JSON 导出需要版本 1.1.0 的核心组件。 有关更多信息，请参阅[核心组件 v1 的兼容性信息](/help/versions.md#release-history-and-compatibility)。

## “配置”对话框 {#configure-dialog}

利用“配置”对话框，内容作者可以定义隐藏字段的参数。

![](/help/assets/chlimage_1-26.png)

* **名称** - 随表单数据一起提交的字段的名称
* **值** - 随表单数据一起提交的字段的值
* **标识符** - 标识符应当在页面上是唯一的，并且可用于将脚本绑定到此表单字段

## “设计”对话框 {#design-dialog}

表单隐藏组件没有“设计”对话框。

## 技术详细信息 {#technical-details}

[在 GitHub 上可找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/hidden/v1/hidden)有关表单隐藏组件的最新技术文档。

从 GitHub 可下载整个核心组件项目。

在[核心组件开发人员文档](/help/developing/overview.md)中可找到有关开发核心组件的其他详细信息。
