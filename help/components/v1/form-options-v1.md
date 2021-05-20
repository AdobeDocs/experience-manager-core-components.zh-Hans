---
title: 表单选项组件(v1)
description: 核心组件表单选项组件允许从各种格式的预定义选项中进行选择。
index: n
role: Architect, Developer, Administrator, Business Practitioner
exl-id: a5e8656b-eddd-48ec-876b-39bbaa70edf6
source-git-commit: 8ff36ca143af9496f988b1ca65475497181def1d
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 3%

---

# 表单选项组件(v1){#form-options-component-v}

核心组件表单选项组件允许从各种格式的预定义选项中进行选择。

## 使用 {#usage}

核心组件表单选项组件允许以多种不同方式提交不同类型的选项，这些选项将与[表单容器组件](form-container-v1.md)一起使用。

选项、标签和单个选项的表示方式可由[配置对话框](#configure-dialog)中的内容编辑器定义。

## 版本和兼容性{#version-and-compatibility}

本文档介绍表单选项组件v1，最初是在AEM 6.3的核心组件1.0.0版中引入的。

下表列出了表单选项组件v1的兼容性。

| 组件版本 | AEM 6.3 | AEM 6.4 |
|--- |--- |--- |
| v2 | 兼容 | 兼容 |
| v1 | 兼容 | 兼容 |

>[!CAUTION]
>
>本文档介绍表单选项组件的v1。
>
>有关表单选项组件当前版本的详细信息，请参阅[表单选项组件](/help/components/forms/form-options.md)文档。

## 组件输出示例{#sample-component-output}

以下是从[We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)获取的示例。

### 屏幕快照 {#screenshot}

![](/help/assets/chlimage_1-89.png)

### HTML {#html}

```
<div class="cmp cmp-form aem-GridColumn aem-GridColumn--default--12">
<form method="POST" action="/content/we-retail/us/en/experience.html" id="new_form" name="new_form" enctype="multipart/form-data" class="aem-Grid aem-Grid--12 aem-Grid--default--12 ">
    <input type="hidden" name=":formstart" value="/content/we-retail/us/en/experience/jcr:content/root/responsivegrid/container">
    
    <div class="cmp cmp-options aem-GridColumn aem-GridColumn--default--12">

    <fieldset class="form-group checkbox">
        <legend>What is your favorite type of toast?</legend>
        
        <div class="checkbox-item">
            <label>
              <input type="checkbox" name="toasttypes" value="dry">
              Plain dry toast
            </label>
        </div>
<div class="checkbox-item">
            <label>
              <input type="checkbox" name="toasttypes" value="french">
              French toast
            </label>
        </div>
<div class="checkbox-item">
            <label>
              <input type="checkbox" name="toasttypes" value="texas">
              Texas toast
            </label>
        </div>

    </fieldset>
    
</div>
    
</form></div>
```

### JSON {#json}

```
"container": {
              "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
              "columnCount": 12,
              "gridClassNames": "aem-Grid aem-Grid--12 aem-Grid--default--12",
              ":items": {
                "options": {
                  "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
                  ":type": "weretail/components/form/options",
                  "name": "toastTypes",
                  "jcr:title": "What is your favorite type of toast?",
                  "source": "local",
                  "type": "checkbox"
                }
              },
              ":itemsOrder": [
                "options"
              ],
              ":type": "weretail/components/form/container"
            }
```

>[!NOTE]
>
>从核心组件导出JSON时，需要安装核心组件版本1.1.0。 有关更多信息，请参阅核心组件v1](/help/versions.md)的[兼容性信息。

## 配置对话框{#configure-dialog}

配置对话框允许内容作者定义应显示的选项类型、标签以及可用的选项。

![](/help/assets/chlimage_1-90.png)

* ****
类型如何显示选项

   * **复选框**
   * **单选按钮**
   * **下拉面板**
   * **多选下拉面板**

* **标题**  — 将作为选项标签显示的标题
* **名称**  — 使用表单数据提交的字段的名称
* **来源**  — 定义选项的位置

   * **本地**  — 在组件中定义
      * 点按或单击&#x200B;**Add**&#x200B;按钮以添加值， **Delete**&#x200B;可删除值
      * **值**  — 提交表单时选择该选项时保存的值
      * **文本**  — 表单上显示的选项的标签
      * **活动**  — 在表单加载时，选项被标记为已选中
      * **禁用**  — 选项不可选，但仍显示
      * **列表**  — 在AEM其他位置定义的静态列表将用于选项
         * **列表**  - AEM中静态列表的路径
            * 使用Browse按钮查找列表资源
      * **数据源**  — 使用数据源进行选项
         * **数据源**  — 数据源的资源类型
* **帮助消息**  — 向用户提供可在字段中输入内容的提示

## 设计对话框{#design-dialog}

表单选项组件没有设计对话框。

## 技术详细信息{#technical-details}

有关表单选项组件[的最新技术文档可在GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/options/v1/options)上找到。

可以从GitHub下载整个核心组件项目。

有关开发核心组件的更多详细信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。
