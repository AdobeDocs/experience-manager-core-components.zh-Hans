---
title: 表单选项组件
description: 核心组件表单选项组件允许从各种格式的预定义选项中进行选择。
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a

---


# 表单选项组件 {#form-options-component}

核心组件表单选项组件允许从各种格式的预定义选项中进行选择。

## 使用情况 {#usage}

核心组件表单选项组件允许以多种不同方式显示不同类型的选项的提交，并且该组件旨在与表单容器组件一 [起使用](form-container.md)。

选项、标签和单个选项的演示可由内容编辑器在配置对话框中定 [义](#configure-dialog)。

## 版本和兼容性 {#version-and-compatibility}

表单选项组件的当前版本为v2，该版本在2018年1月随核心组件的2.0.0版一起推出，本文档对此进行了说明。

下表详细列出了组件的所有受支持版本、与组件版本兼容的AEM版本，以及指向先前版本的文档的链接。

| 组件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 | AEM作为云服务 |
|--- |--- |--- |--- |---|
| v2 | 兼容 | 兼容 | 兼容 | 兼容 |
| [v1](/help/components/v1/form-options-v1.md) | 兼容 | 兼容 | 兼容 | - |

有关核心组件版本和版本的详细信息，请参阅文档核 [心组件版本](/help/versions.md)。

## 示例组件输出 {#sample-component-output}

以下是从 [We.Retail获取的示例](https://docs.adobe.com/content/help/en/experience-manager-65/developing/bestpractices/we-retail/we-retail.html)。

### 屏幕快照 {#screenshot}

![](/help/assets/screen_shot_2018-01-12at113648.png)

### HTML {#html}

```
<form method="POST" action="/content/we-retail/us/en/experience.html" id="new_form" name="new_form" enctype="multipart/form-data" class="cmp-form aem-Grid aem-Grid--12 aem-Grid--default--12">
    <input type="hidden" name=":formstart" value="/content/we-retail/us/en/experience/jcr:content/root/responsivegrid/container">
    
    <div class="hidden aem-GridColumn aem-GridColumn--default--12">
<input type="hidden" id="form-hidden-66464844" name="hidden">

</div>
<div class="hidden aem-GridColumn aem-GridColumn--default--12">
<input type="hidden" id="form-hidden-858231075" name="hidden">

</div>
<div class="hidden aem-GridColumn aem-GridColumn--default--12">
<input type="hidden" id="form-hidden-862566768" name="hidden">

</div>
<div class="container responsivegrid aem-GridColumn aem-GridColumn--default--12">

    <input type="hidden" name=":formstart" value="/content/we-retail/us/en/experience/jcr:content/root/responsivegrid/container/container">
    
    <div class="options aem-GridColumn aem-GridColumn--default--12">

    <fieldset class="cmp-form-options">
        
            <legend class="cmp-form-options__legend">What is your favorite type of toast?</legend>
            <label class="cmp-form-options__field-label">
                <input class="cmp-form-options__field cmp-form-options__field--radio" type="radio" name="favToast" value="dryToast">
                Plain dry toast
            </label>
<label class="cmp-form-options__field-label">
                <input class="cmp-form-options__field cmp-form-options__field--radio" type="radio" name="favToast" value="frenchToast">
                French Toast
            </label>
<label class="cmp-form-options__field-label">
                <input class="cmp-form-options__field cmp-form-options__field--radio" type="radio" name="favToast" value="texasToast">
                Texas Toast
            </label>

    </fieldset>

</div>

</div></form>
```

### JSON {#json}

```
"container":{  
                           "columnClassNames":"aem-GridColumn aem-GridColumn--default--12",
                           "columnCount":12,
                           "gridClassNames":"aem-Grid aem-Grid--12 aem-Grid--default--12",
                           ":items":{  
                              "options_816658469":{  
                                 "columnClassNames":"aem-GridColumn aem-GridColumn--default--12",
                                 "id":"form-options-269951232",
                                 "title":"What is your favorite type of toast?",
                                 "name":"favToast",
                                 "type":"RADIO",
                                 "items":[  
                                    {  
                                       "value":"dryToast",
                                       "text":"Plain dry toast",
                                       "selected":false,
                                       "disabled":false
                                    },
                                    {  
                                       "value":"frenchToast",
                                       "text":"French Toast",
                                       "selected":false,
                                       "disabled":false
                                    },
                                    {  
                                       "value":"texasToast",
                                       "text":"Texas Toast",
                                       "selected":false,
                                       "disabled":false
                                    }
                                 ],
                                 ":type":"core/wcm/sandbox/components/form/options/v2/options"
                              }
                           },
                           ":itemsOrder":[  
                              "options_816658469"
                           ],
                           ":type":"core/wcm/sandbox/components/form/container/v2/container"
                        }
```

### 技术详细信息 {#technical-details}

有关“表单选项”组件的最 [新技术文档可在GitHub上找到](https://adobe.com/go/aem_cmp_tech_form_options_v2)。

有关开发核心组件的更多详细信息，请参阅核 [心组件开发人员文档](/help/developing/overview.md)。

## 配置对话框 {#configure-dialog}

配置对话框允许内容作者定义应显示的选项类型、标签以及可用的选项。

![](/help/assets/screen_shot_2018-01-12at113153.png)

* **类型** -选项的显示方式
   * **复选框**
   * **单选按钮**
   * **下拉面板**
   * **多选下拉面板**
* **标**&#x200B;题将显示为选项标签的标题
* **名称**&#x200B;随表单数据提交的字段的名称
* **源**&#x200B;定义选项的位置
   * **本地**&#x200B;在组件中定义
      * 点按或单击 **添加** 按钮以添加值， **删除** 以删除值
      * **值**&#x200B;提交表单时选择该选项时保存的值
      * **文本**&#x200B;表单上显示的选项的标签
      * **活动**&#x200B;加载表单时，该选项被标记为已选中
      * **禁用**&#x200B;此选项不可选，但仍显示
      * **列表** AEM中其他位置定义的静态列表用于选项
         * **列表** AEM中静态列表的路径
            * 使用“浏览”按钮查找列表资源
      * **数据源**&#x200B;数据源用于选项
         * **数据源**&#x200B;数据源的资源类型
* **帮助消**&#x200B;息提示用户可在字段中输入的内容

## 设计对话框 {#design-dialog}

### 样式选项卡 {#styles-tab}

表单选项组件支持AEM样 [式系统](/help/get-started/authoring.md#component-styling)。
