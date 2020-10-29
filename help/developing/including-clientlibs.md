---
title: 包括客户端库
description: 根据您的用例，可以通过多种不同的方式包含客户端库。
translation-type: tm+mt
source-git-commit: afce571ada011c38c83830628f09a9e268658965
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 3%

---


# 包括客户端库 {#including-client-libraries}

根据您的用例，可以通过多种 [不同的方式](/help/developing/archetype/uifrontend.md#clientlibs) 来包含客户端库。 此文档提供每个代码 [片段的示例](https://docs.adobe.com/content/help/zh-Hans/experience-manager-htl/using/overview.html) 和示例HTL代码片段。

## 建议的默认使用 {#recommended-default-usage}

如果您没有时间调查最适合您的情况，请通过在页面元素中放置以下HTL行来包含客户端 `head` 库：

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @
    categories='wknd.base', defer=true}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

这将包括页面中的CSS和 `head`JS，但向JS中添加 `defer` 属性会包 `script` 括，这样浏览器就会等待DOM准备好，然后执行脚本，从而优化页面加载速度。

## 基本使用 {#basic-usage}

包含客户端库类别的JS和CSS的基本语法(将生成所有相应的CSS元 `link` 素和／或JS元 `script` 素)如下：

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

要同时对多个客户端库类别执行相同操作，可以将字符串数组传递给该 `categories` 参数：

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @
    categories=['wknd.base', 'cq.foundation']}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

## 仅限CSS或JS {#css-js-only}

通常，要将CSS包含的内容放在HTML元 `head` 素中，而JS包含在元素关闭之前 `body` 。

在中 `head`，要仅包含CSS而不是JS，请使用 `cssIncludes`:

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.cssIncludes @ context="unsafe"}
</sly>
```

在关 `body` 闭之前，要仅包含JS而不包含CSS，请使用 `jsIncludes`:

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsIncludes @ context="unsafe"}
</sly>
```

## 属性 {#attributes}

要将属性应用于生 `link` 成的CSS元素和/ `script` 或JS元素，可以使用许多参数：

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

可 `link` 以传递到的CSS属 `jsAndCssIncludes` 性和 `cssIncludes`:

* `media`:字符 `script` 串JS属性，可传递给 `jsAndCssIncludes` 和 `jsIncludes`:
* `async`: 布尔型
* `defer`: 布尔型
* `onload`: 字符串
* `crossorigin`: 字符串

## 内衬 {#inlining}

在某些情况下，要进行优化， [或者](amp.md) 为电子邮件或AMP，可能需要将CSS或JS嵌入到HTML的输出中。

要嵌入CSS, `cssInline` 可以使用，在这种情况下，您必须编写周围的元 `style` 素：

```html
<style type="text/css"
    data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.cssInline @ context="unsafe"}
</style>
```

同样，要内嵌JS，可 `jsInline` 以使用它，在这种情况下，您必须编写周围的元 `script` 素：

```html
<script type="text/javascript"
    data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsInline @ context="unsafe"}
</script>
```

## 加载上下文感知CSS和JavaScript {#context-aware-loading}

页 [面组件](/help/components/page.md) 还支持加载开发人员定义的上下文感知CSS、JavaScript或meta标签。

这是通过使用以 [下结构创建上下文感](context-aware-configs.md)`com.adobe.cq.wcm.core.components.config.HtmlPageItemsConfig` 知资源来完成的：

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
