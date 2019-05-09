---
title: 表单按钮组件(v1)
seo-title: 表单按钮组件(v1)
description: 'null'
seo-description: 核心组件表单隐藏组件允许在表单中包含隐藏字段。
uuid: 0525e70f-294f-4d35-bf96-fc0 e4 ec225 e9
content-type: 引用
products: SG_ EXPERIENCE MANAGER/CORECOMMPANES-new
discoiquuid: ea06acc0-38e2-4252-ac29-07332835b7 c4
disttype: dist5
gnavtheme: 浅色
groupsectionnavitems: 否
hidemerchandisingbar: 继承
hidepromocomponent: 继承
modalsize: 426 x 240
index: n
translation-type: tm+mt
source-git-commit: 1bbec9b1f109df88964dce051a58d111bf6cafaa

---


# 表单按钮组件(v1){#form-button-component-v}

核心组件表单按钮组件允许在表单中包含按钮字段以触发操作。

## 使用情况 {#usage}

核心组件表单按钮组件允许创建按钮字段，通常用于触发表单提交并与 [表单容器组件一起使用](form-container.md)。

按钮属性可由 [配置对话框中的内容编辑器定义](form-button-v1.md#main-pars_title)。

## 版本和兼容性 {#version-and-compatibility}

本文档描述了表单按钮组件的v1，该组件最初随AEM6.3的核心组件版本1.0.0一起引入。

下表列出了表单按钮组件的v的兼容性。

| AEM 版本 | 表单按钮组件v1 |
|--- |--- |
| 6.3 | 兼容 |
| 6.4 | 兼容 |

>[!CAUTION]
>
>本文档描述了表单按钮组件的v1。
>
>有关表单按钮组件的当前版本的详细信息，请参阅 [表单按钮组件](form-button.md) 文档。

## 示例组件输出 {#sample-component-output}

以下示例取自 [We. Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)。

### 屏幕快照 {#screenshot}

![](assets/chlimage_1-48.png)

### HTML {#html}

```
<div class="cmp cmp-button aem-GridColumn aem-GridColumn--default--12">
    <div class="cmp cmp-button">
        <button type="BUTTON" class="btn btn-action btn-primary" name="loveToast" value="ILoveToast">
            Click here if you love toast!
        </button>
    </div>
</div>
```

### JSON {#json}

```
"container": {
              "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
              "columnCount": 12,
              "gridClassNames": "aem-Grid aem-Grid--12 aem-Grid--default--12",
              ":items": {
                "button": {
                  "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
                  ":type": "weretail/components/form/button",
                  "name": "loveToast",
                  "jcr:title": "Click here if you love toast!",
                  "type": "submit",
                  "value": "ILoveToast"
                }
              },
              ":itemsOrder": [
                "button"
              ],
              ":type": "weretail/components/form/container"
            }
```

>[!NOTE]
>
>核心组件中的JSON导出需要核心组件版本1.1.0。有关更多信息，请参见核心组件v [](versions.md#main-pars_title_236368006) 的兼容性信息。

## 配置对话框 {#configure-dialog}

配置对话框允许内容作者定义按钮的参数。

![](assets/chlimage_1-49.png)

* **类型**
   * **按钮**
   * **提交**

* **标题** -按钮上显示的文本
   * 如果没有默认值，则默认为按钮类型

* **名称** -按钮的名称，该按钮使用表单数据提交
* **值** -用表单数据提交的按钮的值

## 设计对话框 {#design-dialog}

表单按钮组件没有设计对话框。

## 技术详细信息 {#technical-details}

有关表单按钮组件 [的最新技术文档，请参阅GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/form/button/v1/button)。

可以从GitHub下载整个核心组件项目。

有关开发核心组件的更多详细信息，请参阅 [核心组件开发人员文档](developing.md)。
