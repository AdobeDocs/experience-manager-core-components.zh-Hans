---
title: 表单隐藏组件(v1)
seo-title: 表单隐藏组件(v1)
description: 核心组件表单隐藏组件允许显示隐藏字段。
seo-description: 核心组件表单隐藏组件允许显示隐藏字段。
uuid: f5005546-def5-4e1 f-8f93-e4 cfc67 a9329
content-type: 引用
products: SG_ EXPERIENCE MANAGER/CORECOMMPANES-new
discoiquuid: d35f4e71-ec7 f-4128-9123-b997 dbb5 f0 cf
index: n
translation-type: tm+mt
source-git-commit: 1bbec9b1f109df88964dce051a58d111bf6cafaa

---


# 表单隐藏组件(v1){#form-hidden-component-v}

核心组件表单隐藏组件允许显示隐藏字段。

## 使用情况 {#usage}

核心组件表单隐藏组件允许创建隐藏字段，以将有关当前页面的信息传递回AEM，并计划与 [表单容器组件一起使用](form-container.md)。

字段属性可由 [配置对话框中的内容编辑器定义](#configure-dialog)。

## 版本和兼容性 {#version-and-compatibility}

本文档描述了表单隐藏组件的v1，该组件最初随AEM6.3的核心组件版本1.0.0一起引入。

下表列出了表单隐藏组件的v兼容性。

| AEM 版本 | 表单隐藏组件v1 |
|--- |--- |
| 6.3 | 兼容 |
| 6.4 | 兼容 |

>[!CAUTION]
>
>本文档描述表单隐藏组件的v1。
>
>有关表单隐藏组件的当前版本的详细信息，请参阅 [表单隐藏组件](form-hidden.md) 文档。

## 示例组件输出 {#sample-component-output}

以下示例取自 [We. Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)。

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
>核心组件中的JSON导出需要核心组件版本1.1.0。有关更多信息，请参见核心组件v [](versions.md#release-history-and-compatibility) 的兼容性信息。

## 配置对话框 {#configure-dialog}

配置对话框允许内容作者定义隐藏字段的参数。

![](assets/chlimage_1-26.png)

* **名称** -字段的名称，该字段使用表单数据提交
* **值** -字段的值，该字段使用表单数据提交
* **标识符** -标识符在页面上应是唯一的，可用于将脚本绑定到此表单字段

## 设计对话框 {#design-dialog}

表单隐藏组件没有设计对话框。

## 技术详细信息 {#technical-details}

有关表单隐藏组件 [的最新技术文档，可在GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/hidden/v1/hidden)上找到。

可以从GitHub下载整个核心组件项目。

有关开发核心组件的更多详细信息，请参阅 [核心组件开发人员文档](developing.md)。
