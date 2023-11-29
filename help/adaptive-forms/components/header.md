---
title: 自适应表单核心组件 - 页眉
description: 使用或自定义自适应表单页眉核心组件。
role: Architect, Developer, Admin, User
exl-id: aa18def9-0bec-4475-8dde-213860621ef5
source-git-commit: 93acf5f6f11da42a7834bbb11b15a36db1e03dc9
workflow-type: ht
source-wordcount: '679'
ht-degree: 100%

---

# 页眉 {#header-adaptive-forms-core-component}

自适应表单中的页眉组件是表单顶部的一个部分，通常包括表单的标题、徽标或名称。页眉还可以包含其他信息，例如表单用途的简短描述、创建表单的组织的名称或表单帮助的联系信息。页眉用于向用户提供表单概述，并为他们将填写的信息提供上下文。它用于帮助用户了解表单的用途以及如何正确填写表单。

**示例**

![](/help/adaptive-forms/assets/header.png)

## 用途 {#reasons-to-use-header}

- **品牌化**：页眉可用于显示创建表单的组织的徽标或名称，从而帮助建立品牌知名度和可信度。

- **上下文**：页眉可以提供表单用途的简短描述，帮助用户了解表单的使用上下文。

- **导航**：页眉可以包含允许用户导航到网站或应用程序的其他部分的链接或按钮。

- **信息**：页眉可以包含联系信息或指向帮助资源的链接，使用户能够在需要时更轻松地获得帮助。

- **用户体验**：可使用页眉为用户提供一种清晰而直观的方式以访问和填写表单字段，使得表单更方便用户使用。

## 版本和兼容性 {#version-and-compatibility}

作为 Cloud Service 核心组件 2.0.4 和 AEM 6.5.16.0 Forms 或更高版本核心组件 1.1.12 的一部分，自适应表单可折叠项面板核心组件于 2023 年 2 月发布。下表显示所有支持的版本、AEM 兼容性以及相应文档的链接：

| 组件版本 | AEM as a Cloud Service | AEM 6.5.16.0 Forms 或更高版本 |
|---|---|---|
| v1 | 兼容<br>[版本 2.0.4](/help/adaptive-forms/version.md) 和更高版本 | 兼容<br>[版本 1.1.12](/help/adaptive-forms/version.md) 及更高但低于 2.0.0 的版本。 |

有关核心组件版本的信息，请参阅[核心组件版本](/help/adaptive-forms/version.md)文档。


<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->


## 技术详细信息 {#technical-details}

可在 [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/pageheader/v1/pageheader) 上的技术文档中获得关于自适应表单页眉核心组件的最新信息。有关开发核心组件的更多信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## “配置”对话框 {#configure-dialog}

通过“配置”对话框，可轻松地自定义您为访客提供的页眉体验。还可轻松地定义页眉选项，从而营造一种无缝的用户体验。

### “图像”选项卡 {#image-tab}

页眉的这个部分包含页眉标题和图像。

![“图像”选项卡](/help/adaptive-forms/assets/header_image.png)

- **图像资源** - 此选项可使用鼠标拖放操作来放置图像等资源。您还可以使用 **浏览**&#x200B;按钮从本地文件系统上传文件。添加图像后，图像底部会出现三个按钮。添加图像后，图像底部会出现三个按钮：
   - **编辑** - 点击或单击&#x200B;**编辑**&#x200B;可在资源中管理资源的再现。
   - **清除** - 点击或单击&#x200B;**清除**&#x200B;可取消选择当前选定的图像。
   - **选取** - 点击或单击&#x200B;**选取**&#x200B;选项可从 Assets 文件夹中选择另一个图像。

- **标题** - 此选项用于将标题添加到页眉。对话框中包括预定义的文本，并且用户可修改这些文本。
- **链接到** - 您可以使用&#x200B;**浏览**&#x200B;图标将标题链接到文件夹。
- **描述** - 描述是简短的文本说明，提供了有关特定图像的用途的附加信息或说明。
- **大小 (px)** - 此选项可通过增加或减少像素来帮助调整图像的长度和宽度。

![“辅助功能”选项卡](/help/adaptive-forms/assets/header_accessibility.png)

- **替换文本** - 此选项用于输入简短描述了图像的替换文本，从而为有视觉障碍的用户描述图像。

- **图像是装饰性的** – 检查图像是否应被辅助技术忽略，因此不需要替换文本。这仅适用于装饰性图像。

### “文本”选项卡 {#text-tab}

此部分允许输入要包含在页眉中的文本。

<!--

## Related article {#related-article}

* [Create a standalone Adaptive Form](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html)

-->

## 相关文章 {#related-articles}

{{more-like-this}}

## 另请参阅 {#see-also}

{{see-also}}
