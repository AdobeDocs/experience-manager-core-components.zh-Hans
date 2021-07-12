---
title: 表单隐藏组件(v1)
description: 核心组件表单隐藏组件允许显示隐藏字段。
index: n
role: Architect, Developer, Admin, User
exl-id: 8e30dac0-5b4b-4fc7-af99-5791c98c90bf
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 2%

---

# 表单隐藏组件(v1) {#form-hidden-component-v}

核心组件表单隐藏组件允许显示隐藏字段。

## 使用 {#usage}

核心组件表单隐藏组件允许创建隐藏字段，以将有关当前页面的信息传递回AEM，并且该组件将与[表单容器组件](form-container-v1.md)一起使用。

字段属性可由[配置对话框](#configure-dialog)中的内容编辑器定义。

## 版本和兼容性 {#version-and-compatibility}

本文档介绍了表单隐藏组件v1，该组件最初随AEM 6.3核心组件1.0.0版引入。

下表列出了“表单隐藏组件”v1的兼容性。

| AEM 版本 | 表单隐藏组件v1 |
|--- |--- |
| 6.3 | 兼容 |
| 6.4 | 兼容 |

>[!CAUTION]
>
>本文档介绍“表单隐藏组件”的v1。
>
>有关当前版本的表单隐藏组件的详细信息，请参阅[表单隐藏组件](/help/components/forms/form-hidden.md)文档。

## 组件输出示例 {#sample-component-output}

以下是从[We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)获取的示例。

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
>从核心组件导出JSON时，需要安装核心组件版本1.1.0。 有关更多信息，请参阅核心组件v1](/help/versions.md#release-history-and-compatibility)的[兼容性信息。

## 配置对话框 {#configure-dialog}

配置对话框允许内容作者定义隐藏字段的参数。

![](/help/assets/chlimage_1-26.png)

* **名称**  — 随表单数据一起提交的字段名称
* **Value**  — 随表单数据提交的字段值
* **标识符**  — 标识符在页面上应是唯一的，可用于将脚本绑定到此表单字段

## “设计”对话框 {#design-dialog}

“表单隐藏”组件没有设计对话框。

## 技术详细信息 {#technical-details}

有关表单隐藏组件[的最新技术文档可在GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/hidden/v1/hidden)上找到。

可以从GitHub下载整个核心组件项目。

有关开发核心组件的更多详细信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。
