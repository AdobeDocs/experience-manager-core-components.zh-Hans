---
title: AEM Project Archetype前端构建
seo-title: AEM Project Archetype前端构建
description: 基于AEM的应用程序的项目模板
seo-description: 基于AEM的应用程序的项目模板
contentOwner: 博纳特
content-type: 参考文件
topic-tags: 核心组件
translation-type: tm+mt
source-git-commit: 0a61f4e6d1ad8b4d5e3778018838dc70d496e1fc

---


# AEM Project Archetype前端构建 {#aem-project-archetype-front-end-build}

AEM Project Archetype包括基于Webpack的可选专用前端构建机制，该机制具有以下功能。

* 完全支持TypeScript、ES6和ES5（带有适用的Webpack包装）
* 使用TSLint规则集的TypeScript和JavaScript linting
* ES5输出，支持传统浏览器
* 通配
   * 无需在任何位置添加导入
   * 现在，所有JS和CSS文件都可添加到每个组件
      * 最佳实践是 `/clientlib/js`在、 `/clientlib/css`或 `/clientlib/scss`
   * 由于 `.content.xml` 所有内 `js.txt`容都通过Webpack运行，因此不需要或/`css.txt` 文件
   * 该全局程序将拉入该文件夹下的所有JS `/component/` 文件。
      * Webpack允许通过JS文件链接CSS/SCSS文件。
      * 他们被拉进两个入口点， `sites.js` 然后 `vendors.js`。
   * AEM使用的唯一文件是输 `site.js` 出文 `site.css` 件、 `/clientlib-site` 内以及 `dependencies.js``dependencies.css` 中 `/clientlib-dependencies`
* 区块
   * 主要（站点js/css）
   * 供应商（依赖项js/css）
* 完全支持Sass/Scss（Sass通过Webpack编译为CSS）。

## 安装 {#installation}

1. 全 [局安装NodeJS](https://nodejs.org/en/download/) (v10+)。 这也将安装npm。
1. 导航到项目中的ui.fronted并运行 `npm install`。

## 使用情况 {#usage}

以下npm脚本驱动前端工作流：

* `npm run dev` -禁用了JS优化（树摇动等）和源映射并禁用了CSS优化的完整构建。
* `npm run prod` -启用JS优化（树摇动等）、禁用源映射和启用CSS优化的完整构建。

## 输出 {#output}

### 常规 {#general}

* 站点- `site.js` 并在 `site.css` clientlib站点文件夹中创建。
* 依赖关系- `dependencies.js` 并在 `dependencies.css` clientlib-dependencies文件夹中创建。

### JavaScript {#javascript}

* 优化——对于生产构建，所有未使用或调用的JS都会被删除。

### CSS {#css}

* 自动预修复——所有CSS都通过预修复程序运行，任何需要预修的属性都将自动在CSS中添加这些属性。
* 优化——在发布时，所有CSS都通过优化程序(cssnano)运行，该优化程序根据以下默认规则将其标准化：
   * 尽可能减少CSS计算表达式，确保浏览器兼容性和压缩在等效长度、时间和角度值之间转换。 请注意，默认情况下，长度值不会转换。
   * 删除规则、选择器和声明中及周围的注释
   * 删除重复的规则、at规则和声明
      * 请注意，这仅适用于精确重复项。
   * 删除空规则、媒体查询和具有空选择器的规则，因为它们不影响输出
   * 按选择器和重叠的属性／值对合并相邻规则
   * 确保CSS文件中仅存在一个@charset，并将其移至文档顶部
   * 当结果输出较小时，将CSS初始关键字替换为实际值
   * 使用SVGO压缩内联SVG定义
* 清理——包括清除生成的CSS、JS和映射文件（按需）的明确清理任务。
* 源映射——仅限开发构建

>[!NOTE]
>前端构建选项利用共享公共配置文件的仅开发和仅生产Webpack配置文件。 这样，可以单独修改开发和生产设置。
