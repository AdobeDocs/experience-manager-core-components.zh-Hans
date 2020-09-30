---
title: AEM Project Archetype前端构建
description: 基于AEM的应用程序的项目模板
translation-type: tm+mt
source-git-commit: 2926c51c2ab97b50b9ec4942cd5415c15a1411b6
workflow-type: tm+mt
source-wordcount: '1622'
ht-degree: 0%

---


# aem Project Archetype的ui.frontend模块 {#uifrontend-module}

AEM Project Archetype包括一个可选的、基于Webpack的专用前端构建机制。 因此，ui.frontend模块成为项目所有前端资源（包括JavaScript和CSS文件）的中心位置。 要充分利用这一有用、灵活的功能，必须了解前端开发如何适合AEM项目。

## AEM项目和前端开发 {#aem-and-front-end-development}

用极为简化的术语来说，AEM项目可以认为是由两个单独但相关的部分组成的：

* 后端开发，它驱动AEM的逻辑并生成Java库、OSGi服务等。
* 前端开发，它驱动生成网站的演示和行为并生成JavaScript和CSS库

由于这两个开发过程都集中在项目的不同部分，因此后端和前端开发可以并行进行。

![前端工作流程图](/help/assets/front-end-flow.png)

但是，任何最终的项目都需要同时使用这些开发工作的产出，即后端和前端。

运 `npm run dev` 行开始前端构建过程，该过程收集存储在ui.frontend模块中的JavaScript和CSS文件，并生成调用并存放在ui.apps模块中的两个精简客户端库 `clientlib-site``clientlib-dependencies` 或ClientLib。 ClientLib可部署到AEM并允许您将客户端代码存储在存储库中。

当整个AEM项目原型使用所有项目 `mvn clean install -PautoInstallPackage` 对象（包括ClientLib）运行时，会将其推送到AEM实例。

>[!TIP]
>
>进一步了解AEM在AEM开发文档中如 [何处理ClientLib](https://docs.adobe.com/content/help/en/experience-manager-65/developing/introduction/clientlibs.html)，如 [何包含它们](/help/developing/including-clientlibs.md)，或查看 [下面ui.frontend模块如何使用它们。](#clientlib-generation)

## ClientLibs概述 {#clientlibs}

前端模块可使用AEM [ClientLib](https://docs.adobe.com/content/help/en/experience-manager-65/developing/introduction/clientlibs.html)。 执行NPM构建脚本时，将构建应用程序，aem-clientlib-generator包将获得的构建输出并将其转换为此类ClientLib。

ClientLib将包含以下文件和目录：

* `css/`:可在HTML中请求的CSS文件
* `css.txt`:告诉AEM文件的顺序和名称， `css/` 以便合并它们
* `js/`:可在HTML中请求的JavaScript文件
* `js.txt` 告诉AEM文件的顺序和名称， `js/` 以便合并它们
* `resources/`:源映射、非入口点代码块（由代码拆分产生）、静态资产（例如图标）等。

## 可能的前端开发工作流 {#possible-workflows}

前端构建模块是一个实用且非常灵活的工具，但并未对它的使用方式提出任何具体意见。 以下是两个可能的使 *用示例* ，但您的个别项目需求可能决定其他使用模式。

### 使用Webpack Static Development Server {#using-webpack}

使用Webpack，您可以根据ui.frontend模块中AEM网页的静态输出进行样式设计和开发。

1. 预览AEM中使用页面预览模式或在URL `wcmmode=disabled` 中传递页面
1. 视图页面源并在ui.frontend模块中另存为静态HTML
1. [开始Web](#webpack-dev-server) Pack并开始设计样式并生成必要的JavaScript和CSS
1. 运 `npm run dev` 行以生成ClientLib

在此流程中，AEM开发人员可以执行步骤一和步骤二，并将静态HTML传递给基于AEM HTML输出进行开发的前端开发人员。

>[!TIP]
>
>您还可以利用组 [件库](https://adobe.com/go/aem_cmp_library) ，捕获每个组件标记输出的样本，以便在组件级别而不是页面级别工作。

### 使用故事书 {#using-storybook}

使 [用Storybook](https://storybook.js.org) ，您可以执行更多原子前端开发。 尽管AEM Project Archetype中不包含Storybook，但您可以安装它，并在ui.frontend模块中存储Storybook对象。 准备好在AEM中进行测试后，可以通过运行将它们部署为ClientLib `npm run dev`。

>[!NOTE]
>
>[AEM](https://storybook.js.org) Project Archetype中不包含Storybook。 如果选择使用它，则必须单独安装它。

### 确定标记 {#determining-markup}

无论您决定为您的项目实施哪个前端开发工作流程，后端开发人员和前端开发人员都必须首先同意该标记。 通常，AEM定义由核心组件提供的标记。 [但是，如有必要，可以自定义此项](/help/developing/customizing.md#customizing-the-markup)。

## ui.frontend模块 {#ui-frontend-module}

AEM Project Archetype包括基于Webpack的可选专用前端构建机制，该机制具有以下功能。

* 完全TypeScript、ES6和ES5支持（带有适用的Webpack包装）
* 使用TSLint规则集的TypeScript和JavaScript linting
* ES5输出，支持传统浏览器
* 通配
   * 无需在任何位置添加导入
   * 现在，所有JS和CSS文件都可添加到每个组件。
      * 最佳实践在 `/clientlib/js`以下 `/clientlib/css`、或 `/clientlib/scss`
   * 由于 `.content.xml` 所有内 `js.txt`容都通过Webpack运行`css.txt` ，因此无需任何或／文件。
   * 该全局程序将拉入该文件夹下的所有JS `/component/` 文件。
      * Webpack允许通过JS文件链接CSS/SCSS文件。
      * 他们被拉进两个入口点， `sites.js` 然后 `vendors.js`。
   * AEM使用的唯一文件是输 `site.js` 出 `site.css` 文件 `/clientlib-site` 以及 `dependencies.js` 输 `dependencies.css` 入 `/clientlib-dependencies`
* 区块
   * 主要（站点js/css）
   * 供应商（依赖项js/css）
* 完全Sass/Scss支持（Sass通过Webpack编译为CSS）
* 具有AEM本地实例的内置代理的静态webpack开发服务器

>[!NOTE]
>
>有关ui.frontend模块的更多技术信息，请参阅GitHub [上的文档](https://github.com/adobe/aem-project-archetype/blob/master/src/main/archetype/ui.frontend.general/README.md)。

## 安装 {#installation}

1. 全 [局安装](https://nodejs.org/en/download/) NodeJS(v10+)。 这也将安装npm。
1. 在项目中导航到ui.frontend并运行 `npm install`。

>[!NOTE]
>
>您必须运 [行带有](overview.md) “填充ui. `-DoptionIncludeFrontendModule=y` frontend”文件夹”选项的原型。

## 使用 {#usage}

以下npm脚本驱动前端工作流：

* `npm run dev` -禁用JS优化（树摇动等）和源映射并禁用CSS优化的完整构建。
* `npm run prod` -在启用JS优化（树摇动等）、禁用源映射和启用CSS优化的情况下实现完整构建。
* `npm run start` -开始静态webpack开发服务器进行本地开发，并且只依赖AEM。

## 输出 {#output}

ui.frontend模块编译文件夹下的代码 `ui.frontend/src` ，并输出已编译的CSS和JS以及名为的文件夹下的任何资源 `ui.frontend/dist`。

* **站点** - `site.js`以及布局相关 `site.css` 图像和字体的文件夹都在clientlib-site文 `resources/``dist/`件夹中创建。
* **依赖项** - `dependencies.js` 并 `dependencies.css` 在文件夹中创 `dist/clientlib-dependencies` 建。

### JavaScript {#javascript}

* 优化——对于生产构建，所有未使用或未调用的JS都会被删除。

### CSS {#css}

* 自动预修——所有CSS都通过预修器运行，任何需要预修的属性都将自动在CSS中添加这些属性。
* 优化——在发布时，所有CSS都通过优化程序(cssnano)运行，优化程序根据以下默认规则将其标准化：
   * 尽可能减少CSS计算表达式，确保浏览器兼容性和压缩在等效长度、时间和角度值之间进行转换。 请注意，默认情况下，长度值不会转换。
   * 删除规则、选择器和声明中及周围的注释
   * 删除重复的规则、at规则和声明
      * 请注意，这仅适用于精确重复。
   * 删除空规则、媒体查询和具有空选择器的规则，因为它们不影响输出
   * 按选择器和重叠的属性／值对合并相邻规则
   * 确保CSS文件中仅存在一个@charset并将其移至文档顶部
   * 当结果输出较小时，将CSS初始关键字替换为实际值
   * 使用SVGO压缩内联SVG定义
* 清理——包括明确的清理任务，用于按需清除生成的CSS、JS和映射文件。
* 源映射——仅限开发构建

>[!NOTE]
>
>前端构建选项利用共享公共配置文件的仅开发和仅生产Webpack配置文件。 这样，可以单独修改开发和生产设置。

### 客户端库生成 {#clientlib-generation}

ui.frontend模块构建过程利用 [aem-clientlib-generator](https://www.npmjs.com/package/aem-clientlib-generator) plugin将编译的CSS、JS和任何资源移入ui.apps模块。 aem-clientlib-generator配置在中定义 `clientlib.config.js`。 将生成以下客户端库：

* **clientlib-site** - `ui.apps/src/main/content/jcr_root/apps/<app>/clientlibs/clientlib-site`
* **clientlib-dependencies** - `ui.apps/src/main/content/jcr_root/apps/<app>/clientlibs/clientlib-dependencies`

### 在页面上包括客户端库 {#clientlib-inclusion}

`clientlib-site` 和 `clientlib-dependencies` 类别通过页面策略配 [置作为默认模板的一](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/components-templates/templates.html#template-definitions) 部分，包括在页面上。 要视图策略，请编辑“内 **容页面模板”>“页面信息”>“页面策略**”。

站点页面中最终包含的客户端库如下：

```
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

当然，可以通过更新页面策略和／或修改各个客户端库的类别和嵌入属性来修改上述包含内容。

### 静态Webpack Development Server {#webpack-dev-server}

ui.frontend模块包含一个webpack-dev-server，它提供实时重装，以便在AEM之外进行快速前端开发。 安装程序利用html-webpack-plugin自动将从ui.frontend模块编译的CSS和JS注入静态HTML模板。

#### 重要文件 {#important-files}

* `ui.frontend/webpack.dev.js`
   * 它包含webpack-dev-serve的配置并指向要使用的html模板。
   * 它还包含运行在localhost:4502上的AEM实例的代理配置。
* `ui.frontend/src/main/webpack/static/index.html`
   * 这是服务器将运行的静态HTML。
   * 这允许开发人员进行CSS/JS更改，并立即在标记中反映这些更改。
   * 假定放入此文件中的标记准确反映了AEM组件生成的标记。
   * 此文件中的标记不会自动与AEM组件标记同步。
   * 此文件还包含对存储在AEM中的客户端库（如核心组件CSS和响应式网格CSS）的引用。
   * Webpack开发服务器设置为代理这些CSS/JS包括基于中的配置运行的本地AEM实例 `ui.frontend/webpack.dev.js`。

#### 使用 {#using-webpack-server}

1. 从项目的根目录中运行命令 `mvn -PautoInstallSinglePackage clean install` ，将整个项目安装到运行于的AEM实例 `localhost:4502`。
1. 在文件夹内 `ui.frontend` 导航。
1. 运行以下命令 `npm run start` 以开始webpack dev server。 启动后，它应打开浏览器(`localhost:8080` 或下一个可用端口)。

您现在可以修改CSS、JS、SCSS和TS文件，并立即查看Webpack开发服务器中反映的更改。
