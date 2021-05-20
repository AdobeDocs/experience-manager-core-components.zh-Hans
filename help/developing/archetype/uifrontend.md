---
title: AEM项目原型前端构建
description: 基于AEM的应用程序的项目模板
feature: 核心组件、 AEM项目原型
role: Architect, Developer, Administrator
exl-id: 99132b49-bd06-4ac2-9348-12c0dfdfe8b2
source-git-commit: 8ff36ca143af9496f988b1ca65475497181def1d
workflow-type: tm+mt
source-wordcount: '1625'
ht-degree: 0%

---

# AEM项目原型{#uifrontend-module}的ui.frontend模块

AEM项目原型包括基于Webpack的可选专用前端构建机制。 因此， ui.frontend模块将成为项目所有前端资源（包括JavaScript和CSS文件）的中心位置。 要充分利用这一有用且灵活的功能，了解前端开发如何融入AEM项目就显得至关重要。

## AEM项目和前端开发{#aem-and-front-end-development}

在极为简化的术语中，AEM项目可被视为由两个单独但相关的部分组成：

* 可驱动AEM逻辑并生成Java库、OSGi服务等的后端开发。
* 前端开发，可推动生成网站的呈现方式和行为，并生成JavaScript和CSS库

由于这两个开发过程都集中在项目的不同部分，因此后端和前端开发可以并行进行。

![前端工作流图](/help/assets/front-end-flow.png)

但是，任何最终项目都需要利用这两种开发努力的成果，即后端和前端。

运行`npm run dev`会启动前端构建过程，该过程会收集存储在ui.frontend模块中的JavaScript和CSS文件，并生成两个名为`clientlib-site`和`clientlib-dependencies`的缩小客户端库或ClientLib，并将它们放入ui.apps模块中。 ClientLib可部署到AEM，并允许您将客户端代码存储在存储库中。

使用`mvn clean install -PautoInstallPackage`运行整个AEM项目原型时，所有项目工件（包括ClientLib）都会被推送到AEM实例。

>[!TIP]
>
>详细了解AEM在[AEM开发文档](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/clientlibs.html)中如何处理ClientLib、如何[包含这些ClientLib(a3/>)，或参见下面的[ui.frontend模块如何使用它们。](#clientlib-generation)](/help/developing/including-clientlibs.md)

## ClientLibs概述 {#clientlibs}

前端模块可使用[AEM ClientLib](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/clientlibs.html)。 执行NPM构建脚本时，将构建应用程序，并且aem-clientlib-generator包将获取生成的构建输出，并将其转换为此类ClientLib。

ClientLib将包含以下文件和目录：

* `css/`:可在HTML中请求的CSS文件
* `css.txt`:告知AEM中文件的顺序和名称， `css/` 以便合并它们
* `js/`:可在HTML中请求的JavaScript文件
* `js.txt` 告知AEM中文件的顺序和名称， `js/` 以便合并它们
* `resources/`:源映射、非入口点代码块（由代码拆分产生）、静态资产（例如图标）等。

## 可能的前端开发工作流{#possible-workflows}

前端构建模块是一个非常灵活的有用工具，但并未对其使用方式提出任何具体意见。 以下是&#x200B;*可能*&#x200B;用法的两个示例，但您的单个项目需求可能会决定其他使用模式。

### 使用Webpack静态开发服务器{#using-webpack}

使用Webpack，您可以在ui.frontend模块中根据AEM网页的静态输出进行设置和开发。

1. 在AEM中使用页面预览模式预览页面，或在URL中传入`wcmmode=disabled`
1. 在ui.frontend模块中查看页面源并另存为静态HTML
1. [启](#webpack-dev-server) 动Web包并开始设置样式并生成必要的JavaScript和CSS
1. 运行`npm run dev`以生成ClientLib

在此流程中，AEM开发人员可以执行步骤一和步骤二，并将静态HTML传递给根据AEM HTML输出进行开发的前端开发人员。

>[!TIP]
>
>您还可以利用[组件库](https://adobe.com/go/aem_cmp_library)来捕获每个组件的标记输出示例，以便在组件级别而不是页面级别工作。

### 使用故事书{#using-storybook}

使用[Storybook](https://storybook.js.org)可以执行更多原子前端开发。 尽管AEM项目原型中未包含Storybook，但您可以安装它并在ui.frontend模块中存储Storybook对象。 准备好在AEM中进行测试后，可通过运行`npm run dev`将它们部署为ClientLibs。

>[!NOTE]
>
>[](https://storybook.js.org) AEM项目原型中未包含Storybook。如果选择使用它，则必须单独安装它。

### 确定标记{#determining-markup}

无论您决定为项目实施的任何前端开发工作流程，后端开发人员和前端开发人员都必须首先就标记达成一致。 通常，AEM定义由核心组件提供的标记。 [但是，如有必要，可以自定义此设置](/help/developing/customizing.md#customizing-the-markup)。

## ui.frontend模块{#ui-frontend-module}

AEM项目原型包括基于Webpack的可选专用前端构建机制，该机制具有以下功能。

* 完全支持TypeScript、ES6和ES5（包含适用的Webpack包装器）
* 使用TSLint规则集的TypeScript和JavaScript链接
* ES5输出，用于旧版浏览器支持
* 通配
   * 无需在任意位置添加导入
   * 现在，所有JS和CSS文件都可以添加到每个组件。
      * 最佳实践在`/clientlib/js`、`/clientlib/css`或`/clientlib/scss`下
   * 由于所有内容都通过Webpack运行，因此不需要`.content.xml`或`js.txt`/`css.txt`文件。
   * 全局服务器会提取`/component/`文件夹下的所有JS文件。
      * Webpack允许通过JS文件将CSS/SCSS文件链接到中。
      * 它们通过两个入口点（`sites.js`和`vendors.js`）拉入。
   * AEM使用的唯一文件是`/clientlib-site`中的输出文件`site.js`和`site.css`，以及`/clientlib-dependencies`中的`dependencies.js`和`dependencies.css`
* 区块
   * 主（站点js/css）
   * 供应商（依赖项js/css）
* 完全Sass/Scss支持（Sass通过Webpack编译为CSS）
* 具有内置代理的静态WebPack开发服务器，可用于AEM的本地实例

>[!NOTE]
>
>有关ui.frontend模块的更多技术信息，请参阅GitHub](https://github.com/adobe/aem-project-archetype/blob/master/src/main/archetype/ui.frontend.general/README.md)上的[文档。

## 安装 {#installation}

1. 全局安装[NodeJS](https://nodejs.org/en/download/)(v10+)。 这也将安装npm。
1. 导航到项目中的ui.frontend并运行`npm install`。

>[!NOTE]
>
>您必须具有[运行带有`-DoptionIncludeFrontendModule=y`选项的原型](overview.md)来填充ui.frontend文件夹。

## 使用 {#usage}

以下npm脚本可驱动前端工作流：

* `npm run dev`  — 禁用JS优化（树摇动等）和源映射且禁用CSS优化的完整构建。
* `npm run prod`  — 在启用JS优化（树摇动等）、禁用源映射和启用CSS优化的情况下完成构建。
* `npm run start`  — 启动用于本地开发的静态WebPack开发服务器，并将对AEM的依赖性降到最低。

## 输出 {#output}

ui.frontend模块编译`ui.frontend/src`文件夹下的代码，并输出编译的CSS和JS，以及名为`ui.frontend/dist`文件夹下的任何资源。

* **Site**  — 在clientlib-site `site.js`文件夹中创 `site.css` 建与布局相关的图像和字体的 `resources/`  `dist/`文件夹和文件夹。
* **依赖项**  — 和 `dependencies.js`  `dependencies.css` 在文件夹中创 `dist/clientlib-dependencies` 建。

### JavaScript {#javascript}

* 优化 — 对于生产内部版本，所有未使用或未调用的JS都将被删除。

### CSS {#css}

* 自动预修复 — 所有CSS都通过预修复程序运行，任何需要预修复的属性都将自动在CSS中添加那些属性。
* 优化 — 在发布时，所有CSS都通过优化程序(cssnano)运行，优化程序会根据以下默认规则将其标准化：
   * 尽可能减少CSS计算表达式，确保浏览器兼容性和压缩性
在等效长度、时间和角度值之间转换。 请注意，默认情况下，长度值不会转换。
   * 删除规则、选择器和声明中及其周围的注释
   * 删除重复的规则、at规则和声明
      * 请注意，此操作仅适用于精确重复项。
   * 删除具有空选择器的空规则、媒体查询和规则，因为它们不会影响输出
   * 按选择器和重叠的属性/值对合并相邻规则
   * 确保CSS文件中只存在一@charset文件，并将其移动到文档顶部
   * 当生成的输出较小时，将CSS初始关键字替换为实际值
   * 使用SVGO压缩内联SVG定义
* 清理 — 包括明确的清理任务，用于根据需要清除生成的CSS、JS和映射文件。
* 源映射 — 仅限开发内部版本

>[!NOTE]
>
>前端构建选项利用共享通用配置文件的仅开发和仅生产WebPack配置文件。 这样，可以单独修改开发和生产设置。

### 客户端库生成{#clientlib-generation}

ui.frontend模块构建过程利用[aem-clientlib-generator](https://www.npmjs.com/package/aem-clientlib-generator)插件将编译的CSS、JS和任何资源移入ui.apps模块。 在`clientlib.config.js`中定义aem-clientlib-generator配置。 将生成以下客户端库：

* **clientlib-site**  -  `ui.apps/src/main/content/jcr_root/apps/<app>/clientlibs/clientlib-site`
* **clientlib-dependencies**  -  `ui.apps/src/main/content/jcr_root/apps/<app>/clientlibs/clientlib-dependencies`

### 在页面{#clientlib-inclusion}上包含客户端库

`clientlib-site` 和类 `clientlib-dependencies` 别将通过页面策略配置 [](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/components-templates/templates.html#template-definitions) 作为默认模板的一部分包含在页面上。要查看策略，请编辑&#x200B;**内容页面模板>页面信息>页面策略**。

站点页面上最终包含的客户端库如下所示：

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

当然，可以通过更新页面策略和/或修改相应客户端库的类别和嵌入属性来修改上述包含内容。

### 静态Webpack开发服务器{#webpack-dev-server}

ui.frontend模块是Webpack-dev-server，提供实时重装，以便在AEM之外进行快速前端开发。 该设置会利用html-webpack-plugin自动将从ui.frontend模块编译的CSS和JS注入静态HTML模板。

#### 重要文件{#important-files}

* `ui.frontend/webpack.dev.js`
   * 其中包含Webpack-dev-serve的配置，并指向要使用的html模板。
   * 它还包含运行在localhost:4502上的AEM实例的代理配置。
* `ui.frontend/src/main/webpack/static/index.html`
   * 这是服务器将针对的静态HTML。
   * 这允许开发人员进行CSS/JS更改，并看到这些更改会立即反映在标记中。
   * 假定放置在此文件中的标记准确反映由AEM组件生成的标记。
   * 此文件中的标记不会与AEM组件标记自动同步。
   * 此文件还包含对存储在AEM中的客户端库的引用，如核心组件CSS和响应式网格CSS。
   * Webpack开发服务器设置为根据`ui.frontend/webpack.dev.js`中的配置，代理本地运行的AEM实例中包含的这些CSS/JS。

#### 使用 {#using-webpack-server}

1. 从项目的根目录中运行命令`mvn -PautoInstallSinglePackage clean install` ，将整个项目安装到运行在`localhost:4502`的AEM实例中。
1. 在`ui.frontend`文件夹内导航。
1. 运行以下命令`npm run start`以启动WebPack开发服务器。 启动后，应打开浏览器（`localhost:8080`或下一个可用端口）。

您现在可以修改CSS、JS、SCSS和TS文件，并查看立即反映在WebPack开发服务器中的更改。
