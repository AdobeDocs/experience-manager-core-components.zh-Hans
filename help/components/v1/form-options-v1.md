---
title: 表单选项组件(v1)
description: 核心组件表单选项组件允许从各种格式的预定义选项中进行选择。
index: n
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

---


# Form Options Component (v1) {#form-options-component-v}

核心组件表单选项组件允许从各种格式的预定义选项中进行选择。

## 使用情况 {#usage}

核心组件表单选项组件允许以多种不同方式显示不同类型的选项的提交，并且该组件旨在与表单容器组件一 [起使用](form-container-v1.md)。

选项、标签和单个选项的演示可由内容编辑器在配置对话框中定 [义](#configure-dialog)。

## 版本和兼容性 {#version-and-compatibility}

本文档描述了最初随AEM 6.3的核心组件版本1.0.0引入的表单选项组件的v1。

下表列出了表单选项组件v1的兼容性。

| 组件版本 | AEM 6.3 | AEM 6.4 |
|--- |--- |--- |
| v2 | 兼容 | 兼容 |
| v1 | 兼容 | 兼容 |

>[!CAUTION]
>
>本文档描述了表单选项组件的v1。
>
>有关表单选项组件当前版本的详细信息，请参阅表 [单选项组件文档](/help/components/forms/form-options.md) 。

## 示例组件输出 {#sample-component-output}

以下是从 [We.Retail获取的示例](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)。

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
>从核心组件导出JSON时，需要发行核心组件的1.1.0版。 有关详细信息， [请参阅核心组件v1的兼容性信息](/help/versions.md) 。

## 配置对话框 {#configure-dialog}

配置对话框允许内容作者定义应显示的选项类型、标签以及可用的选项。

![](/help/assets/chlimage_1-90.png)

* **类**&#x200B;型选项的显示方式

   * **复选框**
   * **单选按钮**
   * **下拉面板**
   * **多选下拉面板**

* **标题** -将显示为选项标签的标题
* **名称** -随表单数据提交的字段的名称
* **源** -定义选项的位置

   * **本地** -在组件中定义
      * 点按或单击 **添加** 按钮以添加值， **删除** 以删除值
      * **值** -提交表单时选择该选项时保存的值
      * **文本** -表单上显示的选项的标签
      * **活动** -加载表单时，该选项被标记为已选中
      * **禁用** -此选项不可选，但仍显示
      * **列表** - AEM中其他位置定义的静态列表用于此选项
         * **列表** - AEM中静态列表的路径
            * 使用“浏览”按钮查找列表资源
      * **数据源** -数据源用于选项
         * **数据源** -数据源的资源类型
* **帮助消息** -提示用户可在字段中输入的内容

## 设计对话框 {#design-dialog}

“表单选项”组件没有设计对话框。

## 技术详细信息 {#technical-details}

有关“表单选项”组件的最 [新技术文档可在GitHub上找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/options/v1/options)。

整个核心组件项目可从GitHub下载。

有关开发核心组件的更多详细信息，请参阅核 [心组件开发人员文档](/help/developing/overview.md)。
