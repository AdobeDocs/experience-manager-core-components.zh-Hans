---
title: 自适应表单核心组件 - 页脚
description: 使用或自定义自适应表单页脚核心组件。
role: Architect, Developer, Admin, User
exl-id: c8e7d3fe-4b82-4a80-8da2-19f6cff1e3e9
source-git-commit: 7888cfa0f1358ce8018fc1e3cc3b19eb66a82b9d
workflow-type: tm+mt
source-wordcount: '806'
ht-degree: 96%

---

# 页脚 {#footer-adaptive-forms-core-component}

自适应表单中的页脚组件是一般出现在表单底部的区域，其中包含版权声明、相关资源的链接或联系信息等信息。页脚可提供上次更新的日期等附加信息，这对于有辅助功能需求的用户可能有益。

**示例**

![](/help/adaptive-forms/assets/footer.png)

## 用途 {#reasons-to-use-footer}

有若干原因使得在自适应表单中加入页脚组件有益，这些原因包括：

* **法律要求**：某些表单可能必须加入免责声明、版权声明或其他法律信息。可在页脚中方便地加入此信息。

* **导航**：页脚可以提供指向网站上的其他重要页面的链接，例如隐私政策、服务条款或联系页面。

* **品牌化**：可使用页脚加入徽标或其他品牌化元素，帮助加强受众对组织或网站的认同感。

* **一致性**：页脚使表单的设计和布局保持一致，令其变得更加直观，并且用户可轻松地导航。

* **附加上下文**：页脚可以为表单提供附加上下文，例如描述表单的文本或指向相关资源的链接，从而使表单包含更多信息并对用户更加友好。

## 版本和兼容性 {#version-and-compatibility}

作为 Cloud Service 核心组件 2.0.4 和 AEM 6.5.16.0 Forms 或更高版本核心组件 1.1.12 的一部分，自适应表单折叠面板核心组件于 2023 年 2 月发布。下表显示所有支持的版本、AEM 兼容性以及相应文档的链接：

| 组件版本 | AEM as a Cloud Service | AEM 6.5.16.0 Forms 或更高版本 |
|---|---|---|
| v1 | 兼容<br>[版本 2.0.4](/help/adaptive-forms/version.md) 和更高版本 | 兼容<br>[版本 1.1.12](/help/adaptive-forms/version.md) 及更高但低于 2.0.0 的版本。 |

有关核心组件版本的信息，请参阅[核心组件版本](/help/adaptive-forms/version.md)文档。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技术详细信息 {#technical-details}

可在 [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/footer/v1/footer) 上的技术文档中获得关于自适应表单页脚核心组件的最新信息。有关开发核心组件的更多信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。


## “配置”对话框 {#configure-dialog}

通过“配置”对话框，可轻松地自定义您为访客提供的页脚体验。还可轻松地定义页脚选项，从而营造一种无缝的用户体验。

![“属性”选项卡](/help/adaptive-forms/assets/footer_propertiestab.png)

* **“编辑”对话框**
“编辑”对话框提供多种标准的富文本格式化工具，通过这些工具，用户可为页脚创建文本。

* **粗体** - 此选项可将粗体格式应用于所选的文本或为在光标后输入的文本设置粗体格式。`Ctrl+B` 为键盘快捷键。

* **斜体** - 此选项将斜体格式应用于所选的文本或为在光标后输入的文本设置斜体格式。`Ctrl+I` 为键盘快捷键。

![项目符号选项](/help/adaptive-forms/assets/footer_bullet.png)


* **项目符号**

   * **“项目符号”图标** - 它将所选的文本设置为带项目符号的列表格式或在光标后开始插入带项目符号的列表。要结束带项目符号的列表，请再次点击或单击“项目符号”按钮或输入两个回车符。

   * **“带编号的列表”图标** - 它将所选的文本设置为带编号的列表格式或在光标后开始插入带编号的列表。要结束带编号的列表，请再次点击或单击“编号”按钮或输入两个回车符。

   * **“减少缩进”图标** - 它降低所选的文本或在光标后输入的文本的缩进级别。只有已缩进了所选的文本或光标的位置，才激活此图标。

   * **“缩进”图标** - 它提高所选的文本或在光标后输入的文本的缩进级别。

![超链接选项](/help/adaptive-forms/assets/footer_link.png)

* **超链接**

   * **路径** - 输入路径
      1. 使用“打开所选内容”对话框在 AEM 中选择某个路径。
      1. 如果链接不在 AEM 中，请输入绝对 URL。
      1. 非绝对路径被解释为相对于 AEM 的路径。

   * **替换文本** - 输入链接的替换描述文本。

   * **目标** - 选择链接行为
      * 目标
      * 相同选项卡
      * 新选项卡
      * 父框架
      * 顶层框架

   * **“取消链接”图标** - 此选项删除已应用于所选文本的链接。只有已选择了链接，才激活此选项。

   * **“段落格式”图标** - 通过此选项，可将段落格式应用于所选的文本。它还帮助您为在光标后插入的文本设置格式。它定义标题的标题级别。

* **ID**：通过此选项，可控制组件在 HTML 和数据层中的唯一标识符。

   * 如果留空，则自动为您生成一个唯一 ID，通过检查所得页面即可找到该 ID。
   * 如果指定一个 ID，作者有责任确保它是唯一的。
   * 更改此 ID 会对 CSS、JS 和数据层跟踪产生影响。

## 相关文章 {#related-article}

* [在AEM Sites页面或体验片段中创建自适应表单](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html)

* [创建独立的自适应表单](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html)
