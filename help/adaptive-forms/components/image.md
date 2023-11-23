---
title: 自适应表单核心组件 - 图像
description: 使用或自定义自适应表单图像核心组件。
role: Architect, Developer, Admin, User
exl-id: 9ee42d5d-16e3-4973-8364-5bc512ebe72e
source-git-commit: 93acf5f6f11da42a7834bbb11b15a36db1e03dc9
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# 图像 {#image-adaptive-forms-core-component}

利用自适应表单中的图像组件，可以在表单中包含图像。这些图像可用于增强表单的整体设计、提供附加信息或用作视觉辅助来帮助用户理解表单的用途。图像组件可用于在表单中添加徽标、照片或图形。

为了实现辅助功能，请务必为图像指定&#x200B;**替换文本**，以便为图像提供简短的描述性替换文本，从而向看不到图像的用户描述图像。


**示例**

![示例](/help/adaptive-forms/assets/image.png)


## 用途 {#reasons-to-use-image-in-a-form}

有若干原因使得在自适应表单中加入图像组件有益，这些原因包括：

- **品牌化**：图像可用于显示创建表单的组织的徽标或名称，从而帮助建立品牌知名度和可信度。

- **视觉辅助**：图像可以充当视觉辅助向用户提供额外一层信息，从而帮助用户理解表单的用途。

- **修饰**：图像可用于增强表单的整体设计，使其外观更具吸引力。

- **用户体验**：可使用图像为用户提供一种清晰而直观的方式以访问和填写表单字段，使得表单更方便用户使用。

## 版本和兼容性 {#version-and-compatibility}

作为 Cloud Service 核心组件 2.0.4 和 AEM 6.5.16.0 Forms 或更高版本核心组件 1.1.12 的一部分，自适应表单可折叠项面板核心组件于 2023 年 2 月发布。下表显示所有支持的版本、AEM 兼容性以及相应文档的链接：

| 组件版本 | AEM as a Cloud Service | AEM 6.5.16.0 Forms 或更高版本 |
|---|---|---|
| v1 | 兼容<br>[版本 2.0.4](/help/adaptive-forms/version.md) 和更高版本 | 兼容<br>[版本 1.1.12](/help/adaptive-forms/version.md) 及更高但低于 2.0.0 的版本。 |

有关核心组件版本的信息，请参阅[核心组件版本](/help/adaptive-forms/version.md)文档。


<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技术详细信息 {#technical-details}

可在 [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/image/v1/image) 上的技术文档中获得关于自适应表单图像核心组件的最新信息。有关开发核心组件的更多信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。


## “配置”对话框 {#configure-dialog}

通过“配置”对话框，可轻松地自定义您为访客提供的图像体验。还可轻松地定义图像选项，从而营造一种无缝的用户体验。

![“属性”选项卡](/help/adaptive-forms/assets/image_properties.png)

- **名称** - 可在表单和规则编辑器中通过唯一名称轻松地标识表单组件，但该名称不得包含空格或特殊字符。

- **标题** - 通过组件的标题，可轻松地标识表单中的组件，默认情况下，标题显示在该组件的顶部。如果不添加标题，则显示该组件的名称而非标题文本。

- **标记为未绑定表单元素**：选择选项以配置未链接到任何架构的表单字段。 此选项允许您在不更新数据源的情况下保存数据。 它还允许您以自定义方式处理数据，而不是通过标准数据库集成。

- **记录文档绑定引用** - 此选项可让您将自适应表单字段与记录文档字段相关联。当用户在自适应表单的链接字段中输入任何值时，该值也会出现在相应记录文档的链接字段中。例如，可使用记录文档绑定引用根据输入到表单中的客户 ID，在记录文档中显示客户的名称和地址。通过这种方式，AEM Forms 使您能够生成记录文档，并为收集和管理数据提供无缝的用户体验。

- **描述** - 描述是简短的文本说明，提供了有关特定图像的用途的附加信息或说明。

- **在此处放置资源或浏览找到要上传的文件** - 此选项可让使用鼠标拖放操作来放置图像等资源。您还可以使用 **浏览**&#x200B;按钮从本地文件系统上传文件。添加图像后，图像底部会出现三个按钮：
   - **编辑** - 点击或单击&#x200B;**编辑**&#x200B;可在资源中管理资源的再现。
   - **清除** - 点击或单击&#x200B;**清除**&#x200B;可取消选择当前选定的图像。
   - **选取** - 点击或单击&#x200B;**选取**&#x200B;选项可从 Assets 文件夹中选择另一个图像。

- **替换文本** - 此选项用于输入简短描述了图像的替换文本，从而为有视觉障碍的用户描述图像。

- **隐藏组件** - 选中此选项以从表单中隐藏该组件。仍可访问该组件作其他用途，如在规则编辑器中使用它进行计算。当需要存储用户无需看到或直接更改的信息时，此项很有用。

- **只读** - 选中此选项以使组件不可编辑。用户可看到但无法修改字段的值。仍可访问该组件作其他用途，如在规则编辑器中使用它进行计算。

## “设计”对话框 {#design-dialog}

“设计”对话框用于定义和管理图像组件的 CSS 样式。

### “样式”选项卡 {#styles-tab}

该选项卡用于定义和管理组件的 CSS 样式。自适应表单图像核心组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。

![“设计”对话框](/help/adaptive-forms/assets/checkbox-style.png)

- **默认 CSS 类**：可为自适应表单复选框组核心组件提供默认 CSS 类。

- **允许使用的样式**：可通过提供名称和表示样式的 CSS 类而定义样式。例如，您可以创建一个名为“bold text”的样式，并提供 CSS 类“font-weight: bold”。可使用这些样式或将其应用于自适应表单编辑器中的自适应表单。要应用样式，请在自适应表单编辑器中选择要将样式应用于的组件，导航到“属性”对话框，然后从&#x200B;**样式**&#x200B;下拉列表中选择所需的样式。如果您需要更新或修改样式，只需返回“设计”对话框，在“样式”选项卡中更新样式，然后保存更改。

### 自订属性

![自定义属性对话框](/help/adaptive-forms/assets/checkbox-customproperties.png)

通过自定义属性，可使用表单模板将自定义属性（键值对）与自适应表单核心组件关联。 自定义属性反映在组件headless演绎版的属性部分中。 它允许创建根据自定义属性值调整的动态表单行为。 例如，开发人员可以为移动、桌面或Web平台设计Headless Forms组件的各种演绎版，从而显着提升各种设备上的用户体验。

- **组名称**：您可以提供一个名称来标识自定义资产组。 您可以添加、删除或重新排列多个自定义属性组。 添加自定义属性组后，您可以看到以下选项：

   - **键值对**：通过单击 **添加** 每个自定义属性组的按钮。

   - **删除**：点击或单击以删除自定义属性名称和自定义属性值。

   - **重新排列**：点击或单击并拖动以重新排列自定义属性名称和自定义属性值的顺序。

## 相关文章 {#related-articles}

{{more-like-this}}

## 另请参阅 {#see-also}

{{see-also}}