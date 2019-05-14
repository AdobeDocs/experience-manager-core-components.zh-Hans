---
title: 表单选项组件(v1)
seo-title: 表单选项组件(v1)
description: 'null'
seo-description: 核心组件表单选项组件允许从预定义的各种格式的预定义选项中进行选择。
uuid: a22ed77c-c9 f3-46f4-8afe-e478383 c1251
content-type: 引用
products: SG_ EXPERIENCE MANAGER/CORECOMMPANES-new
discoiquuid: e19775bfe-2bda-409a-998e-1ff4f9f23b94
disttype: dist5
gnavtheme: 浅色
groupsectionnavitems: 否
hidemerchandisingbar: 继承
hidepromocomponent: 继承
modalsize: 426 x 240
noindex: 'true'
index: n
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4e74f10e2a4119484a597178dc4577b399833dbf

---


# 表单选项组件(v1){#form-options-component-v}

核心组件表单选项组件允许从预定义的各种格式的预定义选项中进行选择。

## 使用情况 {#usage}

核心组件表单选项组件允许提交多种不同类型的选项，这些选项以不同的方式呈现，旨在与 [表单容器组件一起使用](form-container.md)。

选项、标签和单个选项的演示文稿可由 [配置对话框中的内容编辑器定义](form-options-v1.md#main-pars_title)。

## 版本和兼容性 {#version-and-compatibility}

本文档描述了表单选项组件的v1，该组件最初随AEM6.3的核心组件版本1.0.0一起引入。

下表列出了表单选项组件的v兼容性。

| 组件版本 | AEM 6.3 | AEM 6.4 |
|--- |--- |--- |
| v2 | 兼容 | 兼容 |
| v1 | 兼容 | 兼容 |

>[!CAUTION]
>
>本文档描述了表单选项组件的v1。
>
>有关表单选项组件的当前版本的详细信息，请参阅 [表单选项组件](form-options.md) 文档。

## 示例组件输出 {#sample-component-output}

以下示例取自 [We. Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)。

### 屏幕快照 {#screenshot}

![](assets/chlimage_1-89.png)

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
>核心组件中的JSON导出需要核心组件版本1.1.0。有关更多信息，请参见核心组件v [](versions.md#main-pars_title_236368006) 的兼容性信息。

## 配置对话框 {#configure-dialog}

配置对话框允许内容作者定义应显示的选项类型、标签和可用选项。

![](assets/chlimage_1-90.png)

* **类型**显示选项的方式

   * **复选框**
   * **单选按钮**
   * **下拉面板**
   * **多选下拉面板**

* **标题** -将作为选项的标签显示的标题
* **名称** -用表单数据提交的字段的名称
* **源** -定义选项的位置

   * **本地** -在组件内定义
      * 点按或单击 **添加** 按钮以添加值， **删除可** 删除值
      * **值** -提交表单时选择该选项时保存的值
      * **文本** -表单上显示的选项的标签
      * **活动** -在表单加载时，该选项被标记为选定
      * **禁用** -选项不可选择，但仍显示
      * **列表** -在AEM中定义的静态列表用于选项
         * **列表** - AEM中静态列表的路径
            * 使用“浏览”按钮查找列表资源
      * **数据源** -用于选项的数据源
         * **数据源** -数据源的资源类型
* **帮助消息** -用户可以在字段中输入的提示

## 设计对话框 {#design-dialog}

“表单选项”组件没有设计对话框。

## 技术详细信息 {#technical-details}

有关表单选项组件 [的最新技术文档可在GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/options/v1/options)上找到。

可以从GitHub下载整个核心组件项目。

有关开发核心组件的更多详细信息，请参阅 [核心组件开发人员文档](developing.md)。
