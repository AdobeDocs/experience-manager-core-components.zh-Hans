---
title: 客户端库和核心组件
description: 核心组件附带许多客户端库，并提供包含您自己的库的功能。
role: Architect, Developer, Admin
exl-id: 84e7c178-247b-42a2-99bf-6d1699ecee14
source-git-commit: d39fe0084522f67664203a026340b23d325c1883
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 65%

---


# 客户端库和核心组件 {#client-libraries}

核心组件附带许多客户端库，并提供包含您自己的库的功能。

## 提供的客户端库 {#provided}

核心组件提供了以下现成的客户端库。

* 此 **站点** clientlibs提供要应用于站点的组件的简单功能行为。
   * 它们可作为加快项目的起点，并鼓励扩展和实施 [自定义它们](/help/developing/customizing.md) 以获得所需的外观和功能。
* 此 **编辑者** clientlibs将应用于“创作”对话框，以确保其预期功能和外观。
* 此 **editorhook** 在编辑模式下加载时，clientlibs将应用于站点。
   * 它们包含针对编辑器触发的事件执行的JavaScript代码，有助于初始化动态功能。
* 某些组件可能具有特定的附加clientlibs，这些库设计用于特定情况，例如与一起使用时 [Dynamic Media](/help/components/image.md#dynamic-media) 例如。

## 包含客户端库 {#including}

可通过多种不同的方式来包含[客户端库](/help/developing/archetype/front-end.md#clientlibs)，具体取决于您的使用案例。以下是示例示例 [HTL代码片段](https://experienceleague.adobe.com/docs/experience-manager-htl/using/overview.html) 每一个。

### 推荐的默认使用 {#recommended-default-usage}

如果您没时间调查您所处情况下的最佳使用，则可通过将以下 HTL 行置于页面 `head` 元素中来包含客户端库：

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @
    categories='wknd.base', defer=true}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

这会将 CSS 和 JS 包含在页面 `head` 中，并且会将 `defer` 属性添加到 JS`script` includes 中，这样一来，浏览器将在执行脚本之前等待 DOM 准备就绪，从而加快页面加载速度。

### 基本用途 {#basic-usage}

用于包含客户端库类别的 JS 和 CSS 的基本语法（这将生成所有对应的 CSS `link` 元素和/或 JS `script` 元素）如下所示：

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

要一次性对多个客户端库类别执行相同操作，可以将一组字符串传递给 `categories` 参数：

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @
    categories=['wknd.base', 'cq.foundation']}">
    ${clientlibs.jsAndCssIncludes @ context="unsafe"}
</sly>
```

### 仅 CSS 或 JS {#css-js-only}

通常，需要将 CSS includes 置于 HTML `head` 元素中，并将 JS includes 置于 `body` 元素的结束位置之前。

在 `head` 中，要仅包含 CSS 而非 JS，请使用 `cssIncludes`：

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.cssIncludes @ context="unsafe"}
</sly>
```

在 `body` 结束位置之前，要仅包含 JS 而非 CSS，请使用 `jsIncludes`：

```html
<sly data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsIncludes @ context="unsafe"}
</sly>
```

### 属性 {#attributes}

要将属性应用于生成的 CSS `link` 元素和/或 JS `script` 元素，可使用大量参数：

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

可传递给 `jsAndCssIncludes` 和 `cssIncludes` 的 CSS `link` 属性：

* `media`：可传递给 `jsAndCssIncludes` 和 `jsIncludes` 的字符串 JS `script` 属性：
* `async`：布尔型
* `defer`：布尔型
* `onload`：字符串
* `crossorigin`：字符串

### 内联 {#inlining}

在某些情况下，对于优化或者对于电子邮件或 [AMP](amp.md)，可能需要将 CSS 或 JS 内联到 HTML 输出中。

要内联 CSS，可使用 `cssInline`，在此情况下，您必须编写周围的 `style` 元素：

```html
<style type="text/css"
    data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.cssInline @ context="unsafe"}
</style>
```

类似地，要内联 JS，可使用 `jsInline`，在此情况下，您必须编写周围的 `script` 元素：

```html
<script type="text/javascript"
    data-sly-use.clientlibs="${'com.adobe.cq.wcm.core.components.models.ClientLibraries' @ categories='wknd.base'}">
    ${clientlibs.jsInline @ context="unsafe"}
</script>
```

### 加载上下文感知 CSS 和 JavaScript {#context-aware-loading}

[页面组件](/help/components/page.md)还支持加载开发人员定义的上下文感知 CSS、JavaScript 或元标记。

可通过使用以下结构为 `com.adobe.cq.wcm.core.components.config.HtmlPageItemsConfig` 创建[上下文感知资源](context-aware-configs.md)来做到这一点：

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

[有关更多信息，请参阅页面组件的技术文档。](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/page/v2/page#loading-of-context-aware-cssjs)
