---
title: 自适应表单核心组件 - 文件附件
description: 使用或自定义自适应表单文件附件核心组件。
role: Architect, Developer, Admin, User
exl-id: 64a54fc6-db52-481f-bf5a-60c05122004d
source-git-commit: 8a5133d8551f9e35340b40aa00876cfa0231deb5
workflow-type: tm+mt
source-wordcount: '2061'
ht-degree: 97%

---

# 文件附件组件 {#file-attachment-adaptive-forms-core-component}

<span class="preview">**提交的值的数据类型**&#x200B;功能可通过早期采用者计划获得。您可以使用官方电子邮件 ID 写信给 aem-forms-ea@adobe.com，加入早期采用者计划并申请使用该功能。</span>

通过自适应表单中的文件附件组件，用户可从其本地计算机或设备中选择并上传文件。可配置文件附件组件以允许特定文件类型、大小限制和多个附件。

**示例**

![示例](/help/adaptive-forms/assets/upload-image.png)


## 用途 {#reasons-to-use-file-attachment}

有若干原因使得在自适应表单中加入文件附件组件有益，这些原因包括：

- **收集附加信息**：通过文件附件组件，用户可在提交表单时上传文档、图像、视频或其他类型的文件。这对于收集附加信息（如简历、作品集或支持文档）很有用。

- **轻松共享大文件**：文件附件组件使用户可以轻松共享大文件，而无需依赖外部文件共享服务。

- **方便**：通过文件附件组件，用户可从其本地计算机上传文件，而无需离开表单或使用其他工具。

- **数据分析**：文件附件组件可用于从各种来源收集数据并进行分析，或将其用作进一步处理的输入。

- **用户体验**：可使用文件附件组件为用户提供一种清晰而直观的方式以上传文件，使得表单更方便用户使用。

## 版本和兼容性 {#version-and-compatibility}

自适应Forms文件附件核心组件于2023年2月发布，作为Cloud Service核心组件2.0.4以及AEM 6.5.16.0 Forms或更高版本的核心组件1.1.12的一部分。 下表显示所有支持的版本、AEM 兼容性以及相应文档的链接：

| 组件版本 | AEM as a Cloud Service | AEM 6.5.16.0 Forms或更高版本 |
|---|---|---|
| v1 | 与<br>[版本 2.0.4](/help/adaptive-forms/version.md) 和更高版本兼容 | 与<br>[版本 1.1.12](/help/adaptive-forms/version.md) 和更高版本兼容，但低于版本 2.0.0。 |

有关核心组件版本的信息，请参阅[核心组件版本](/help/adaptive-forms/version.md)文档。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion_cn). -->

## 技术详细信息 {#technical-details}

可在 [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/fileinput/v1/fileinput) 上的技术文档中获得关于自适应表单文件附件核心组件的最新信息。有关开发核心组件的更多信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## “配置”对话框 {#configure-dialog}

通过“配置”对话框，可轻松地自定义您为访客提供的文件附件体验。还可轻松地定义文件附件选项，从而营造一种无缝的用户体验。

### “基本”选项卡 {#basic-tab}

![“基本”选项卡](/help/adaptive-forms/assets/fileattachement_basictab1.png)

- **名称** - 可在表单和规则编辑器中通过唯一名称轻松地标识表单组件，但该名称不得包含空格或特殊字符。

- **标题** - 通过组件的标题，可轻松地标识表单中的组件，默认情况下，标题显示在该组件的顶部。如果不添加标题，则显示该组件的名称而非标题文本。
- **允许标题为富文本**：此功能使用户能够格式化纯文本标题，结合粗体、斜体、下划线文本、各种字体、字体大小、颜色和附加选项等功能，以增强视觉呈现和定制效果。它提供了更大的灵活性以及对创作的控制度，使标题在文档、网站或应用程序中脱颖而出。\
  选中&#x200B;**允许标题为富文本**&#x200B;复选框后，可以看到格式化选项，用于设置组件标题的样式。要访问所有可用的格式选项，您可以点击![全屏图标](/help/adaptive-forms/assets/fullscreen-icon.png)选项卡。

  ![富文本支持](/help/adaptive-forms/assets/richtext-support-title.png)

- **隐藏标题** - 选中此选项可隐藏该组件的标题。

- **按钮标题** - 此选项用于设置自适应表单上显示的按钮的标签。
- **绑定引用** - 绑定引用是对存储在外部数据源中并在表单中使用的数据元素的引用。通过绑定引用，可动态地将数据绑定到表单字段，以使表单可显示来自数据源的最新数据。例如，可使用绑定引用，根据输入到表单中的客户 ID，在该表单中显示该客户的姓名和地址。还可使用绑定引用，通过输入到表单中的数据更新数据源。这样通过 AEM Forms 即可创建与外部数据源交互的表单，从而为收集和管理数据提供一种无缝的用户体验。
- **标记为未绑定表单元素**：选择此选项可配置未链接到任何架构的表单字段。利用此选项，您可以保存数据而不更新数据源。它还可让您以一种独立于标准数据库集成的自定义方式处理数据。
- **提交的值的数据类型**：选择该选项可确定如何将附加的文件提交到服务器。要以二进制数据形式发送附件，请选择 `File` 选项。要以 Base64 编码字符串形式发送附件，请选择 `String` 选项。如果选择 `String`，则将二进制格式的文件以数据 URL 形式提交到服务器。服务器自动将数据 URL 转换回二进制格式，确保与现有操作（例如发送电子邮件和生成记录文档）兼容，而无需用户进行任何更改。默认情况下，`File` 选项处于选中状态。
- **隐藏组件** - 选中此选项以从表单中隐藏该组件。仍可访问该组件作其他用途，如在规则编辑器中使用它进行计算。当需要存储用户无需看到或直接更改的信息时，此项很有用。
- **禁用组件** - 选中此选项以禁用该组件。被禁用的组件不再活跃或最终用户无法编辑它。用户可看到但无法修改字段的值。仍可访问该组件作其他用途，如在规则编辑器中使用它进行计算。
- **只读** - 选中此选项以使组件不可编辑。用户可看到但无法修改字段的值。仍可访问该组件作其他用途，如在规则编辑器中使用它进行计算。
- **允许多个附件** - 选中此选项以使用&#x200B;**文件附件**&#x200B;按钮上传多个附件。
- **拖放文本** - 这是显示在 **“附加”**&#x200B;按钮顶部的文本，用于提示用户附加或拖放文件。您可以选择自定义&#x200B;**附加**&#x200B;按钮顶部显示的文本。此外，您还可以使用富文本菜单来设置文本格式。

### “验证”选项卡 {#validation-tab}

![“验证”选项卡](/help/adaptive-forms/assets/fileattachment_validationtab.png)

- **必需** - 如果要在自适应表单中显示该组件，请选中此选项。选择此选项后，您必须先附加附件，然后再继续提交表单。选中此选项后，无法在&#x200B;**“基本”**&#x200B;选项卡中选择&#x200B;**隐藏组件**&#x200B;或&#x200B;**禁用组件**。
- **错误消息** - 通过此选项，可输入如果选中了&#x200B;**必需**&#x200B;复选框并将字段留空，所显示的消息。

- **脚本验证消息** - 通过此选项，可输入如果脚本验证失败，所显示的消息。

<!--   **Minimum files error message** - This option is used to enter an error message that is displayed if you upload files lesser than the specified minimum number of files.-->

- **最大文件大小 (MB)** - 通过此选项，可指定最大文件大小。以 MB 为单位指定文件大小。
  <!--   **Maximum files error message** - This option is used to enter an error message that is displayed if you upload files greater than the specified maximum number of files.-->

- **最大文件大小错误消息** - 此选项用于输入如果您上传的文件大小大于在&#x200B;**最大文件大小 (MB)** 选项中指定的文件大小，所显示的错误消息。

- **允许的文件类型** - 在此处添加可使用&#x200B;**文件附件**&#x200B;按钮上传的各种类型的文件。这样还可通过单击&#x200B;**添加**&#x200B;按钮而添加新的文件格式。支持的文件格式为：音频、视频、图像、文本或 PDF。还可使用以下选项删除或重新排列允许的文件类型：
   - **删除** - 点击或单击此选项以删除特定的文件类型。
   - **重新排列** - 点击或单击此选项并拖动以重新排列允许的文件类型的顺序。

- **文件类型错误消息** - 通过此选项，可输入在您上传的文件格式不是在&#x200B;**允许的文件类型**&#x200B;选项中列出的文件类型格式时所显示的错误消息。

>
>
> 通过将文件类型更改为允许的文件类型格式来提交文件，会在表单提交期间引发错误。


### “帮助内容”选项卡 {#help-content-tab}

![“帮助内容”选项卡](/help/adaptive-forms/assets/fileattachement_helpcontenttab.png)

- **简短描述** - 简短描述是一段简短的文字说明，其中提供关于特定表单字段的用途的其他信息或阐述。它帮助用户了解应将什么类型的数据输入到字段中，并可提供准则或示例以帮助确保所输入的信息有效且符合预期的标准。默认情况下，简短描述保持隐藏状态。启用&#x200B;**始终显示简短描述**&#x200B;选项以在组件下方显示它。

- **始终显示简短描述** - 启用该选项以在组件下方显示简短描述。

- **帮助文本** - 帮助文本是指提供给用户以帮助其正确填写表单字段的其他信息或指导。当用户单击组件旁的“帮助”图标 (i) 时显示它。帮助文本提供比表单字段的标签或占位符文本更详细的信息，旨在帮助用户了解该字段的要求或限制。它还可提供建议或示例，以使填写表单更轻松且更准确。

### “辅助功能”选项卡 {#accessibility-tab}


![“辅助功能”选项卡](/help/adaptive-forms/assets/fileattachement_accessibilitytab.png)

- **屏幕阅读器文本** - 屏幕阅读器文本是指专供由视障人士使用的屏幕阅读器等辅助技术读取的附加文本。此文本提供表单字段用途的音频描述，并可包括关于字段的标题、描述、名称和任何相关消息（自定义文本）的信息。屏幕阅读器文本帮助确保包括视障用户在内的所有用户均可访问表单，并使其完整地了解表单字段及其要求。

   - **自定义文本**：选中此选项以将自定义文本用于 ARIA 辅助功能标签。选中此选项将显示“自定义文本”对话框。可在“自定义文本”对话框中添加相关信息。
   - **描述**：选中此选项以将描述用于 ARIA 辅助功能标签。
   - **标题**：选中此选项以将标题用于 ARIA 辅助功能标签。
   - **名称**：选中此选项以将名称用于 ARIA 辅助功能标签。
   - **无**：如果不想为 ARIA 辅助功能标签添加任何内容，请选中此选项。

## “设计”对话框 {#design-dialog}

“设计”对话框用于定义和管理文件附件组件的 CSS 样式。

### “样式”选项卡 {#styles-tab}

自适应表单文件附件核心组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。

![“设计”对话框](/help/adaptive-forms/assets/checkbox-style.png)

- **默认 CSS 类**：可为自适应表单文件附件核心组件提供默认 CSS 类。

- **允许使用的样式**：可通过提供名称和表示样式的 CSS 类而定义样式。例如，您可以创建一个名为“bold text”的样式，并提供 CSS 类“font-weight: bold”。可使用这些样式或将其应用于自适应表单编辑器中的自适应表单。要应用样式，请在自适应表单编辑器中选择要将样式应用于的组件，导航到“属性”对话框，然后从&#x200B;**样式**&#x200B;下拉列表中选择所需的样式。如果您需要更新或修改样式，只需返回“设计”对话框，在“样式”选项卡中更新样式，然后保存更改。

### 自定义属性

![“自定义属性”对话框](/help/adaptive-forms/assets/checkbox-customproperties.png)

通过自定义属性，您可使用表单模板将自定义属性（键值对）关联到自适应表单核心组件。自定义属性反映在组件 Headless 演绎版的属性部分中。它可让您创建根据自定义属性值进行调整的动态表单行为。例如，开发人员可以为移动、桌面或 Web 平台设计 Headless 表单组件的各种演绎版，从而大大提升各种设备上的用户体验。

- **组名称**：您可以提供名称来标识自定义属性组。您可以添加、删除或重新排列多个自定义属性组。添加自定义属性组后，可看到以下选项：

   - **键值对**：您可以通过单击“**添加**”按钮，为每个自定义属性组添加多个自定义属性名称和自定义属性值。

   - **删除**：点按或单击此项可删除自定义属性名称和自定义属性值。

   - **重新排列**：点按或单击并拖动可重新排列自定义属性名称和自定义属性值的顺序。
<!--

## Related article {#related-article}

* [Create a standalone Adaptive Form](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html?lang=zh-Hans)

-->

## 相关文章 {#related-articles}

{{more-like-this}}

## 另请参阅 {#see-also}

{{see-also}}
