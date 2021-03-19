---
title: 包括客户端库
description: 根据您的用例，可以通过多种不同的方式包含客户端库。
role: 架构师、开发人员、管理员
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 3%

---


# 包括客户端库{#including-client-libraries}

根据您的用例，有多种不同的方法来包含[客户端库](/help/developing/archetype/uifrontend.md#clientlibs)。 本文档提供了每个代码片段的示例和示例[HTL代码片段](https://docs.adobe.com/content/help/zh-Hans/experience-manager-htl/using/overview.html)。

## 建议的默认用法{#recommended-default-usage}

如果您没有时间调查最适合您的情况，请通过在页面`head`元素中放置以下HTL行来包含您的客户端库：

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @
    categories='wknd.base', defer=true}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

这将包括页面`head`中的CSS和JS，但向JS `script`中添加`defer`属性会包括，这样浏览器会在执行脚本之前等待DOM就绪，从而优化页面加载速度。

## 基本用法{#basic-usage}

包含客户端库类别的JS和CSS的基本语法如下：`link``script`

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

要同时对多个客户端库类别执行相同操作，可以将字符串数组传递给`categories`参数：

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @
    categories=['wknd.base', 'cq.foundation']}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

## 仅CSS或JS {#css-js-only}

通常，要将CSS包含在HTML `head`元素中，而JS包含在`body`元素关闭前。

在`head`中，要仅包含CSS而不是JS，请使用`cssIncludes`:

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.cssIncludes @ context="unsafe"}
</sly>
```

在`body`关闭之前，要仅包含JS而不是CSS，请使用`jsIncludes`:

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsIncludes @ context="unsafe"}
</sly>
```

## 属性 {#attributes}

要将属性应用于生成的CSS `link`元素和/或JS `script`元素，可以使用许多参数：

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @
    categories='wknd.base',
    media='print',
    async=true,
    defer=true,
    onload='console.log(\'loaded: \' + this.src)',
    crossorigin='anonymous'}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

可传递给`jsAndCssIncludes`和`cssIncludes`的CSS `link`属性：

* `media`:可传递 `script` 给的字符串JS属 `jsAndCssIncludes` 性 `jsIncludes`:
* `async`: 布尔型
* `defer`: 布尔型
* `onload`: 字符串
* `crossorigin`: 字符串

## 内线{#inlining}

在某些情况下，要进行优化，或者为电子邮件或[AMP，](amp.md)可能需要将CSS或JS嵌入到HTML的输出中。

要内嵌CSS，可以使用`cssInline`，在这种情况下，您必须编写周围的`style`元素：

```html
<style type="text/css"
    data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.cssInline @ context="unsafe"}
</style>
```

同样，要内嵌JS，可以使用`jsInline`，在这种情况下，您必须编写周围的`script`元素：

```html
<script type="text/javascript"
    data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsInline @ context="unsafe"}
</script>
```

## 加载上下文感知CSS和JavaScript {#context-aware-loading}

[页面组件](/help/components/page.md)还支持加载开发人员定义的上下文感知CSS、JavaScript或meta标签。

为此，请使用以下结构为`com.adobe.cq.wcm.core.components.config.HtmlPageItemsConfig`创建[上下文感知资源](context-aware-configs.md):

```text
com.adobe.cq.wcm.core.components.config.HtmlPageItemsConfig
    - prefixPath="/some/path"
    + item01
        - element=["link"|"script"|"meta"]
        - location=["header"|"footer"]
        + attributes
            - attributeName01="attributeValue01"
            - attributeName02="attributeValue02"
            ...
    + item02
        ...
    ...
```

[有关详细信息，请参阅页面组件的技术文档。](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/page/v2/page#loading-of-context-aware-cssjs)
