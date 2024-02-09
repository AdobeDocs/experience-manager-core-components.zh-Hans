---
title: 使用 AEM 项目原型进行前端开发
description: 了解 AEM 项目原型可选的基于 Webpack 的专用前端构建机制。
feature: Core Components, AEM Project Archetype
role: Architect, Developer, Admin
exl-id: 99132b49-bd06-4ac2-9348-12c0dfdfe8b2
source-git-commit: bd92a5d1884056ca7b44ea28e5817d8bde10a4d9
workflow-type: ht
source-wordcount: '654'
ht-degree: 100%

---


# 使用 AEM 项目原型进行前端开发 {#front-end}

AEM 项目原型包括一个可选的基于 Webpack 的专用前端构建机制。因此，ui.frontend 模块成为了项目的所有前端资源（包括 JavaScript 和 CSS 文件）的中心位置。要充分利用这项有用且灵活的功能，请务必了解前端开发如何适应 AEM 项目。

本文档重点介绍前端构建模块的一般使用模式及其为您提供的功能。有关详细的构建选项和技术说明，请参阅原型的 GitHub 存储库中的文档。

>[!TIP]
>
>最新的 AEM 项目原型和相关技术文档[可以在 GitHub 上找到](https://github.com/adobe/aem-project-archetype)。

## AEM 前端和后端开发 {#front-end-back-end}

简单来说，可以将 AEM 项目视为由两个独立但相关的部分组成：

* 后端开发，用于驱动 AEM 逻辑并生成 Java 库、OSGi 服务等
* 前端开发，用于驱动生成的网站的展示和行为并生成 JavaScript 和 CSS 库

由于后端开发过程和前端开发过程各自专注于项目的不同部分，因此两者可以同时进行。

![前端工作流图](/help/assets/front-end-flow.png)

但是，任何生成的项目都需要使用这两种开发工作（即后端开发和前端开发）的输出。

## 确定标记 {#determining-markup}

无论您决定为项目实施哪种前端开发工作流，后端开发人员和前端开发人员都必须首先共同确定标记。通常，AEM 定义由核心组件提供的标记。[但如有必要，可以自定义标记。](/help/developing/customizing.md#customizing-the-markup)

## 可能的前端开发工作流 {#possible-workflows}

前端构建模块是一个有用且非常灵活的工具，但并未提供其使用方式的详细说明。以下是两个&#x200B;*可能*&#x200B;的用法示例，但您的各个项目需求可能会指示其他使用模型。

### 使用 Webpack 静态开发服务器 {#using-webpack}

利用 Webpack，您可以基于 ui.frontend 模块中的 AEM 网页的静态输出进行样式设置和开发。

1. 使用页面预览模式或在 URL 中传入 `wcmmode=disabled` 以在 AEM 中预览页面
1. 查看页面源代码并在 ui.frontend 模块中另存为静态 HTML
1. [启动 Webpack](#webpack-dev-server) 并开始样式化和生成必要的 JavaScript 和 CSS
1. 运行 `npm run dev` 可生成 Clientlib

在此流程中，AEM 开发人员可以执行前两个步骤，并将静态 HTML 传递给基于 AEM HTML 输出进行开发的前端开发人员。

>[!TIP]
>
>还可以利用[组件库](https://adobe.com/go/aem_cmp_library_cn)捕获每个组件的标记输出示例，以便在组件级别而非页面级别工作。

### 使用 Storybook {#using-storybook}

利用 [Storybook](https://storybook.js.org)，您可以执行更多原子前端开发。虽然 Storybook 未包含在 AEM 项目原型中，但您可以安装它并将您的 Storybook 构件存储在 ui.frontend 模块中。准备好在 AEM 中进行测试时，可以通过运行 `npm run dev` 将它们部署为 Clientlib。

>[!NOTE]
>
>[Storybook](https://storybook.js.org) 未包含在 AEM 项目原型中。如果您选择使用 Storybook，则必须单独安装它。

## Clientlib 概述 {#clientlibs}

可使用 [AEM Clientlib 构建前端模块。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/clientlibs.html)。在执行 NPM 构建脚本时，将构建应用程序，并且 `aem-clientlib-generator` 包会获取生成的构建输出并将其转换为此类 Clientlib。

Clientlib 将包含以下文件和目录：

* `css/`：可用 HTML 请求的 CSS 文件
* `css.txt`：告知 AEM `css/` 中的文件的顺序和名称，以便将这些文件合并
* `js/`：可用 HTML 请求的 JavaScript 文件
* `js.txt`：告知 AEM `js/` 中的文件的顺序和名称，以便将这些文件合并
* `resources/`：源映射、非入口点代码块（通过代码拆分操作产生）、静态资源（例如图标）等

>[!TIP]
>
>在 [AEM 开发文档](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/full-stack/clientlibs.html)中了解有关 AEM 如何处理 Clientlib 的更多信息，并在[核心组件文档](/help/developing/including-clientlibs.md)中了解如何包含 Clientlib 的更多信息。
