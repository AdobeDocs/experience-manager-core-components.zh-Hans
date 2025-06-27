---
title: 表单选项组件 (v1)
description: 利用核心组件表单选项组件可从各种格式的预定义选项中进行选择。
index: n
role: Architect, Developer, Admin, User
exl-id: a5e8656b-eddd-48ec-876b-39bbaa70edf6
source-git-commit: 92a3ec273a5be6751c1503835b9c2e5cbd61bb9e
workflow-type: ht
source-wordcount: '459'
ht-degree: 100%

---


# 表单选项组件 (v1) {#form-options-component-v}

利用核心组件表单选项组件可从各种格式的预定义选项中进行选择。

## 用途 {#usage}

利用核心组件表单选项组件可提交不同类型的选项（这些选项通过多种不同方式提供），并且此组件旨在与[表单容器组件](form-container-v1.md)结合使用。

多个选项、标签和单个选项的呈现可由内容编辑者在[“配置”对话框](#configure-dialog)中定义。

## 版本和兼容性 {#version-and-compatibility}

本文档介绍了表单选项组件 (v1)，它最初随带 AEM 6.3 的核心组件 1.0.0 版引入。

下表列出了表单选项组件 (v1) 的兼容性。

| 组件版本 | AEM 6.3 | AEM 6.4 |
|--- |--- |--- |
| v2 | 兼容 | 兼容 |
| v1 | 兼容 | 兼容 |

>[!CAUTION]
>
>本文档介绍了表单选项组件 (v1)。
>
>有关当前版本的表单选项组件的详细信息，请参阅[表单选项组件](/help/components/forms/form-options.md)文档。

## 示例组件输出 {#sample-component-output}

以下是摘自 [We.Retail](https://helpx.adobe.com/cn/experience-manager/6-4/sites/developing/using/we-retail.html) 的示例。

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
>从核心组件执行 JSON 导出需要版本 1.1.0 的核心组件。 有关更多信息，请参阅[核心组件 v1 的兼容性信息](/help/versions.md)。

## “配置”对话框 {#configure-dialog}

利用“配置”对话框，内容作者可以定义应显示的选项类型、标签以及可用的选项。

![](/help/assets/chlimage_1-90.png)

* **类型**
如何显示选项

   * **复选框**
   * **单选按钮**
   * **下拉面板**
   * **多选下拉面板**

* **标题** - 将显示为选项标签的标题
* **名称** - 随表单数据一起提交的字段的名称
* **来源** - 在其中定义选项的位置

   * **本地** - 已在组件中定义
      * 点击或单击&#x200B;**添加**&#x200B;按钮可添加值，点击或单击&#x200B;**删除**&#x200B;可删除值
      * **值** - 提交表单期间选择该选项时保存的值
      * **文本** - 表单上显示的选项的标签
      * **活动** - 加载表单时标记为选定的选项
      * **已禁用** - 该选项不可选，但仍会显示
      * **列表** - AEM 中的其他位置定义的静态列表用于此选项
         * **列表** - AEM 中的静态列表的路径
            * 使用“浏览”按钮可找到列表资源
      * **数据源** - 数据源用于选项
         * **数据源** - 数据源的资源类型
* **帮助消息** - 关于用户可在字段中输入的内容的提示

## “设计”对话框 {#design-dialog}

表单选项组件没有“设计”对话框。

## 技术详细信息 {#technical-details}

[在 GitHub 上可找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/options/v1/options)有关表单选项组件的最新技术文档。

从 GitHub 可下载整个核心组件项目。

在[核心组件开发人员文档](/help/developing/overview.md)中可找到有关开发核心组件的其他详细信息。
