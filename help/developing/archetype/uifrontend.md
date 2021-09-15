---
title: AEM 项目原型前端构建
description: 基于 AEM 的应用程序的项目模板
feature: 核心组件，AEM 项目原型
role: Architect, Developer, Admin
exl-id: 99132b49-bd06-4ac2-9348-12c0dfdfe8b2
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: ht
source-wordcount: '1625'
ht-degree: 100%

---

# AEM 项目原型的 ui.frontend 模块 {#uifrontend-module}

AEM 项目原型包括一个可选的基于 Webpack 的专用前端构建机制。因此，ui.frontend 模块成为了项目的所有前端资源（包括 JavaScript 和 CSS 文件）的中心位置。要充分利用这项有用且灵活的功能，请务必了解前端开发如何适应 AEM 项目。

## AEM 项目和前端开发 {#aem-and-front-end-development}

简单来说，可以将 AEM 项目视为由两个独立但相关的部分组成：

* 后端开发，用于驱动 AEM 逻辑并生成 Java 库、OSGi 服务等
* 前端开发，用于驱动生成的网站的展示和行为并生成 JavaScript 和 CSS 库

由于后端开发过程和前端开发过程各自专注于项目的不同部分，因此两者可以同时进行。

![前端工作流图](/help/assets/front-end-flow.png)

但是，任何生成的项目都需要使用这两种开发工作（即后端开发和前端开发）的输出。

运行 `npm run dev` 将开始前端构建过程，在此过程中，将收集存储在 ui.frontend 模块中的 JavaScript 和 CSS 文件，并生成两个缩小的客户端库或 ClientLibs（分别称作 `clientlib-site` 和 `clientlib-dependencies`），并将它们存入 ui.apps 模块中。ClientLibs 可部署到 AEM 并允许您将客户端代码存储在存储库中。

在使用 `mvn clean install -PautoInstallPackage` 运行整个 AEM 项目原型时，所有项目构件（包括 ClientLibs）随后将被推送到 AEM 实例。

>[!TIP]
>
>详细了解 AEM 如何处理 ClientLibs（参阅 [AEM 开发文档](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/clientlibs.html)），如何[包含它们](/help/developing/including-clientlibs.md)，或参阅下面的 [ui.frontend 模块如何使用它们](#clientlib-generation)。

## ClientLibs 概述 {#clientlibs}

可使用 [AEM ClientLib](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/clientlibs.html) 构建前端模块。在执行 NPM 构建脚本时，将构建应用程序，并且 aem-clientlib-generator 包会获取生成的构建输出并将其转换为此类 ClientLib。

ClientLib 将包含以下文件和目录：

* `css/`：可用 HTML 请求的 CSS 文件
* `css.txt`：告知 AEM `css/` 中的文件的顺序和名称，以便将这些文件合并
* `js/`：可用 HTML 请求的 JavaScript 文件
* `js.txt`：告知 AEM `js/` 中的文件的顺序和名称，以便将这些文件合并
* `resources/`：源映射、非入口点代码块（通过代码拆分操作产生）、静态资源（例如图标）等

## 可能的前端开发工作流 {#possible-workflows}

前端构建模块是一个有用且非常灵活的工具，但并未提供其使用方式的详细说明。以下是两个&#x200B;*可能*&#x200B;的用法示例，但您的各个项目需求可能会指示其他使用模型。

### 使用 Webpack 静态开发服务器 {#using-webpack}

利用 Webpack，您可以基于 ui.frontend 模块中的 AEM 网页的静态输出进行样式设置和开发。

1. 使用页面预览模式或在 URL 中传入 `wcmmode=disabled` 以在 AEM 中预览页面
1. 查看页面源代码并在 ui.frontend 模块中另存为静态 HTML
1. [启动 Webpack](#webpack-dev-server) 并开始样式化和生成必要的 JavaScript 和 CSS
1. 运行 `npm run dev` 可生成 ClientLibs

在此流程中，AEM 开发人员可以执行前两个步骤，并将静态 HTML 传递给基于 AEM HTML 输出进行开发的前端开发人员。

>[!TIP]
>
>还可以利用[组件库](https://adobe.com/go/aem_cmp_library_cn)捕获每个组件的标记输出示例，以便在组件级别而非页面级别工作。

### 使用 Storybook {#using-storybook}

利用 [Storybook](https://storybook.js.org)，您可以执行更多原子前端开发。虽然 Storybook 未包含在 AEM 项目原型中，但您可以安装它并将您的 Storybook 构件存储在 ui.frontend 模块中。准备好在 AEM 中进行测试时，可以通过运行 `npm run dev` 将它们部署为 ClientLibs。

>[!NOTE]
>
>[Storybook](https://storybook.js.org) 未包含在 AEM 项目原型中。如果您选择使用 Storybook，则必须单独安装它。

### 确定标记 {#determining-markup}

无论您决定为项目实施哪种前端开发工作流，后端开发人员和前端开发人员都必须首先共同确定标记。通常，AEM 定义由核心组件提供的标记。[但如有必要，可以自定义标记](/help/developing/customizing.md#customizing-the-markup)。

## ui.frontend 模块 {#ui-frontend-module}

AEM 项目原型包括一个可选的基于 Webpack 的专用前端构建机制，并具有以下功能。

* 完全的 TypeScript、ES6 和 ES5 支持（带适用的 Webpack 包装程序）
* 使用 TSLint 规则集的 TypeScript 和 JavaScript Linting
* ES5 输出，用于支持旧式浏览器
* 通配
   * 无需在任何位置添加导入
   * 现在可以将所有 JS 和 CSS 文件添加到每个组件中。
      * 最佳实践位于 `/clientlib/js`、`/clientlib/css` 或 `/clientlib/scss` 下
   * 由于一切都是通过 Webpack 运行的，因此无需 `.content.xml` 或 `js.txt`/`css.txt` 文件。
   * globber 将所有 JS 文件拉入 `/component/` 文件夹下方。
      * Webpack 允许通过 JS 文件链接 CSS/SCSS 文件。
      * 通过 `sites.js` 和 `vendors.js` 这两个入口点将它们拉入。
   * AEM 使用的唯一文件是 `/clientlib-site` 中的输出文件 `site.js` 和 `site.css` 以及 `/clientlib-dependencies` 中的输出文件 `dependencies.js` 和 `dependencies.css`
* 块
   * 主要（站点 js/css）
   * 供应商（依赖项 js/css）
* 完全 Sass/Scss 支持（Sass 通过 Webpack 编译为 CSS）
* 带有 AEM 本地实例的内置代理的静态 Webpack 开发服务器

>[!NOTE]
>
>有关 ui.frontend 模块的更多技术信息，请参阅 [GitHub 上的文档](https://github.com/adobe/aem-project-archetype/blob/master/src/main/archetype/ui.frontend.general/README.md)。

## 安装 {#installation}

1. 全局安装 [NodeJS](https://nodejs.org/en/download/) (v10+)。这还将安装 npm。
1. 导航到项目中的 ui.frontend 并运行 `npm install`。

>[!NOTE]
>
>您必须使用选项 `-DoptionIncludeFrontendModule=y` [运行原型](overview.md)才能填充 ui.frontend 文件夹。

## 用途 {#usage}

以下 npm 脚本驱动前端工作流：

* `npm run dev` - 完整构建，禁用了 JS 优化（tree shaking 等）、启用了源映射并禁用了 CSS 优化。
* `npm run prod` - 完整构建，启用了 JS 优化（tree shaking 等）、禁用了源映射并启用了 CSS 优化。
* `npm run start` - 启动静态 Webpack 开发服务器以进行本地开发，并且对 AEM 的依赖最少。

## 输出 {#output}

ui.frontend 模块编译 `ui.frontend/src` 文件夹下的代码，并输出编译后的 CSS 和 JS 以及名为 `ui.frontend/dist` 的文件夹下的任何资源。

* **站点** - 在 `dist/`clientlib-site 文件夹中创建与布局相关的图像和字体的 `site.js`、`site.css` 和 `resources/` 文件夹。
* **依赖项** - 在 `dist/clientlib-dependencies` 文件夹中创建 `dependencies.js` 和 `dependencies.css`。

### JavaScript {#javascript}

* 优化 - 对于生产构建，将删除所有未使用或未调用的 JS。

### CSS {#css}

* 自动前缀 - 所有 CSS 都通过前缀器运行，并且任何需要前缀的属性都将自动添加到 CSS 中。
* 优化 - 在发布时，所有 CSS 都通过优化器 (cssnano) 运行，该优化器根据以下默认规则对其进行标准化：
   * 尽可能减少 CSS 计算表达式，确保浏览器兼容性和压缩
在等效长度、时间和角度值之间转换。请注意，默认情况下，不会转换长度值。
   * 删除规则、选择器和声明中及其附近的注释
   * 删除重复的规则、at-rule 和声明
      * 请注意，这仅适用于完全重复项。
   * 删除空规则、媒体查询和带空选择器的规则，因为它们不影响输出
   * 按选择器和重叠的属性/值对合并相邻规则
   * 确保 CSS 文件中只有一个 @charset 并将它移动到文档顶部
   * 当生成的输出较小时，将 CSS 初始关键词替换为实际值
   * 使用 SVGO 压缩内联 SVG 定义
* 清理 - 包括显式清理任务，用于按需清除生成的 CSS、JS 和 Map 文件。
* 源映射 - 仅开发构建

>[!NOTE]
>
>前端构建选项使用共享公共配置文件的 dev-only 和 prod-only Webpack 配置文件。通过这种方式，可以单独修改开发和生产设置。

### 客户端库生成 {#clientlib-generation}

ui.frontend 模块构建过程利用 [aem-clientlib-generator](https://www.npmjs.com/package/aem-clientlib-generator) 插件将编译后的 CSS、JS 和任何资源移入 ui.apps 模块。在 `clientlib.config.js` 中定义 aem-clientlib-generator 配置。生成以下客户端库：

* **clientlib-site** - `ui.apps/src/main/content/jcr_root/apps/<app>/clientlibs/clientlib-site`
* **clientlib-dependencies** - `ui.apps/src/main/content/jcr_root/apps/<app>/clientlibs/clientlib-dependencies`

### 在页面上包含客户端库 {#clientlib-inclusion}

通过[页面策略配置](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/components-templates/templates.html#template-definitions)在页面上将 `clientlib-site` 和 `clientlib-dependencies` 类别作为默认模板的一部分包含。要查看策略，请编辑&#x200B;**内容页面模板 > 页面信息 > 页面策略**。

站点页面上最终的客户端库包含如下：

```html
<HTML>
    <head>
        <link rel="stylesheet" href="clientlib-base.css" type="text/css">
        <script type="text/javascript" src="clientlib-dependencies.js"></script>
        <link rel="stylesheet" href="clientlib-dependencies.css" type="text/css">
        <link rel="stylesheet" href="clientlib-site.css" type="text/css">
    </head>
    <body>
        ....
        <script type="text/javascript" src="clientlib-site.js"></script>
        <script type="text/javascript" src="clientlib-base.js"></script>
    </body>
</HTML>
```

当然，可以通过更新页面策略和/或修改相应客户端库的类别和嵌入属性来修改上述包含。

### 静态 Webpack 开发服务器 {#webpack-dev-server}

ui.frontend 模块中包含一个 webpack-dev-server，它为 AEM 外部的快速前端开发提供了实时重新加载。该设置利用 html-webpack-plugin 自动将从 ui.frontend 模块编译的 CSS 和 JS 注入静态 HTML 模板中。

#### 重要文件 {#important-files}

* `ui.frontend/webpack.dev.js`
   * 这包含 webpack-dev-serve 的配置并指向要使用的 html 模板。
   * 它还包含在 localhost:4502 上运行的 AEM 实例的代理配置。
* `ui.frontend/src/main/webpack/static/index.html`
   * 这是服务器将针对其运行的静态 HTML。
   * 这使开发人员能够进行 CSS/JS 更改，并且所做的更改会立即在标记中反映出来。
   * 假定置于此文件中的标记准确地反映了由 AEM 组件生成的标记。
   * 此文件中的标记不会自动与 AEM 组件标记同步。
   * 此文件还包含对存储在 AEM 中的客户端库的引用，例如核心组件 CSS 和响应式网格 CSS。
   * Webpack 开发服务器将设置为根据 `ui.frontend/webpack.dev.js` 中的配置从本地运行的 AEM 实例代理这些 CSS/JS includes。

#### 使用 {#using-webpack-server}

1. 从项目的根目录中，运行命令 `mvn -PautoInstallSinglePackage clean install` 以将整个项目安装到 `localhost:4502` 上运行的 AEM 实例。
1. 在 `ui.frontend` 文件夹中导航。
1. 运行以下命令 `npm run start` 以启动 webpack 开发服务器。此服务器在启动后将打开浏览器（`localhost:8080` 或下一个可用端口）。

您现在可以修改 CSS、JS、SCSS 和 TS 文件，并且您所做的更改会立即在 webpack 开发服务器中反映出来。
