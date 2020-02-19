---
title: 表单隐藏组件(v1)
description: 核心组件表单隐藏组件允许显示隐藏字段。
index: n
translation-type: tm+mt
source-git-commit: fe8a121520000ffd56ae3347469590e89121eaf0

---


# Form Hidden Component (v1) {#form-hidden-component-v}

核心组件表单隐藏组件允许显示隐藏字段。

## 使用情况 {#usage}

核心组件表单隐藏组件允许创建隐藏字段，以将有关当前页面的信息传回AEM，并准备与表单容器组件一起 [使用](form-container-v1.md)。

字段属性可由内容编辑器在配置对话框中 [定义](#configure-dialog)。

## 版本和兼容性 {#version-and-compatibility}

本文档描述了最初随AEM 6.3的核心组件版本1.0.0引入的表单隐藏组件的v1。

下表列出了表单隐藏组件的v1的兼容性。

| AEM 版本 | 表单隐藏组件v1 |
|--- |--- |
| 6.3 | 兼容 |
| 6.4 | 兼容 |

>[!CAUTION]
>
>本文档描述了表单隐藏组件的v1。
>
>有关表单隐藏组件的当前版本的详细信息，请参阅表 [单隐藏组件文档](/help/components/forms/form-hidden.md) 。

## 示例组件输出 {#sample-component-output}

以下是从 [We.Retail获取的示例](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)。

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
>从核心组件导出JSON时，需要发行1.1.0版的核心组件。 有关详细信息， [请参阅核心组件v1的兼容性信息](/help/versions.md#release-history-and-compatibility) 。

## 配置对话框 {#configure-dialog}

配置对话框允许内容作者定义隐藏字段的参数。

![](/help/assets/chlimage_1-26.png)

* **名称** -随表单数据一起提交的字段的名称
* **值** -随表单数据一起提交的字段的值
* **标识符** -该标识符在页面上应是唯一的，并且可用于将脚本绑定到此表单字段

## 设计对话框 {#design-dialog}

“表单隐藏”组件没有设计对话框。

## 技术详细信息 {#technical-details}

有关表单隐藏组件的最新技 [术文档可在GitHub上找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/hidden/v1/hidden)。

整个核心组件项目可从GitHub下载。

有关开发核心组件的更多详细信息，请参阅核 [心组件开发人员文档](/help/developing/overview.md)。
