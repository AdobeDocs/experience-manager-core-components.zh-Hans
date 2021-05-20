---
title: 包括客户端库
description: 根据您的用例，有许多不同的方法来包含客户端库。
role: Architect, Developer, Administrator
exl-id: 84e7c178-247b-42a2-99bf-6d1699ecee14
source-git-commit: 8ff36ca143af9496f988b1ca65475497181def1d
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 3%

---

# 包括客户端库{#including-client-libraries}

根据您的用例，有多种不同的方法可包含[客户端库](/help/developing/archetype/uifrontend.md#clientlibs)。 本文档提供了每个代码片段的示例和示例[HTL代码片段](https://docs.adobe.com/content/help/zh-Hans/experience-manager-htl/using/overview.html)。

## 建议的默认用法{#recommended-default-usage}

如果您没有时间调查您的最佳情况，请通过将以下HTL行放置到页面`head`元素中来包含您的客户端库：

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @
    categories='wknd.base', defer=true}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

这将在您的页面`head`中同时包含CSS和JS，但是向JS `script`中添加了`defer`属性，这样浏览器就会等待DOM准备就绪后再执行脚本，从而优化页面加载速度。

## 基本用法{#basic-usage}

要同时包含客户端库类别的JS和CSS的基本语法如下：`link``script`

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

要同时对多个客户端库类别执行相同操作，可将字符串数组传递到`categories`参数：

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @
    categories=['wknd.base', 'cq.foundation']}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

## 仅{#css-js-only} CSS或JS

通常，您会希望将CSS包含的内容放置在HTML `head`元素中，并且JS包含在`body`元素关闭之前。

在`head`中，要仅包含CSS而不包含JS，请使用`cssIncludes`:

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.cssIncludes @ context="unsafe"}
</sly>
```

在`body`结束前，要仅包含JS，而不包含CSS，请使用`jsIncludes`:

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

可传递到`jsAndCssIncludes`和`cssIncludes`的CSS `link`属性：

* `media`:字符串 `script` JS属性，可以传递 `jsAndCssIncludes` 到和 `jsIncludes`:
* `async`: 布尔型
* `defer`: 布尔型
* `onload`: 字符串
* `crossorigin`: 字符串

## 内衬 {#inlining}

在某些情况下，要进行优化，或者对于电子邮件或[AMP，可能需要将CSS或JS内联到HTML的输出中。](amp.md)

要使CSS内联，可以使用`cssInline`，在这种情况下，必须写入周围的`style`元素：

```html
<style type="text/css"
    data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.cssInline @ context="unsafe"}
</style>
```

同样，要使用JS内联，可以使用`jsInline`，在这种情况下，必须写入周围的`script`元素：

```html
<script type="text/javascript"
    data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsInline @ context="unsafe"}
</script>
```

## 加载上下文感知CSS和JavaScript {#context-aware-loading}

[页面组件](/help/components/page.md)还支持加载开发人员定义的上下文感知CSS、JavaScript或meta标记。

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

[有关更多信息，请参阅页面组件技术文档。](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/page/v2/page#loading-of-context-aware-cssjs)
