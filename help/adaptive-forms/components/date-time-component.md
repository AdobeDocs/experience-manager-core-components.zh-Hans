---
title: 自适应表单核心组件 - 日期和时间
description: 使用或自定义自适应表单日期和时间核心组件。
role: Architect, Developer, Admin, User
source-git-commit: daeabccaff39e255c111c6af2540ca4d5be0c709
workflow-type: ht
source-wordcount: '1898'
ht-degree: 100%

---


# 日期和时间组件

自适应表单中的日期和时间组件是一个用户界面元素，允许用户使用日程表和时钟界面选择&#x200B;**日期和时间**，或者手动输入特定格式的值。它可确保在日期和时间都非常重要的用例中进行准确的标准化输入。

**示例**

![示例](/help/adaptive-forms/assets/date-time-picker.png)

## 用途 {#reasons-to-use-date-time-picker}

在自适应表单中加入日期和时间选取器很有好处，这可能有若干原因，包括：

- **便利**：允许用户轻松选择日期和时间，无需手动输入数值。
- **一致性**：在整个表单中强制日期和时间的标准格式输入。
- **改进用户体验**：通过日程表和时间选择器提供直观的用户界面。
- **事件计划**：在预约、面谈或会议计划表格中十分有用。
- **旅行和预订**：使用户能够选择入住/退房日期和时间。
- **数据准确性**：与自由文本输入相比，减少输入错误。

## 版本和兼容性 {#version-and-compatibility}

自适应表单日期和时间核心组件于 **2025 年 8 月**&#x200B;作为 Cloud Service 的&#x200B;**核心组件 2.24.6** 及更高版本的一部分发布。

| 组件版本 | AEM as a Cloud Service | AEM 6.5.16.0 Forms 或更高版本 |
|---|---|---|
| v1 | 兼容<br>[版本 2.24.6](/help/adaptive-forms/version.md) 和更高版本 | |

有关各版本的详细信息，请参阅[核心组件版本](/help/adaptive-forms/version.md)。

## 技术详细信息 {#technical-details}

在 [GitHub](https://github.com/adobe/aem-core-forms-components) 上获取有关自适应表单日期和时间核心组件的最新技术详细信息。有关核心组件开发的更多信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## “配置”对话框 {#configure-dialog}

配置对话框允许自定义日期和时间。

### “基本”选项卡 {#basic-tab}

![“基本”选项卡](/help/adaptive-forms/assets/datetime_basictab.png)

- **名称** - 名称在规则编辑器中唯一标识组件。名称字符串中不允许使用特殊字符和空格。

- **标题** - 标题是一个字符串，它显示在自适应表单中某个组件的顶部。标题在自适应表单的树结构中唯一地标识该组件。如果不添加标题，则显示该组件的名称而非标题文本。
- **允许标题为富文本**：此功能使用户能够格式化纯文本标题，结合粗体、斜体、下划线文本、各种字体、字体大小、颜色和附加选项等功能，以增强视觉呈现和定制效果。它提供了更大的灵活性以及对创作的控制度，使标题在文档、网站或应用程序中脱颖而出。\
  选中&#x200B;**允许标题为富文本**&#x200B;复选框后，可以看到格式化选项，用于设置组件标题的样式。要访问所有可用的格式选项，您可以点击![全屏图标](/help/adaptive-forms/assets/fullscreen-icon.png)选项卡。

  ![富文本支持](/help/adaptive-forms/assets/richtext-support-title.png)

- **隐藏标题** - 选中此选项以在自适应表单中隐藏该组件类型的标题。

- **占位符文本** - 表单组件中的占位符文本是指在输入字段中显示的短标签或提示，用于提示用户需要在该字段中输入什么类型的信息。当用户开始向该字段中键入时，占位符文本消失，如果将该字段留空，则占位符文本重新出现。它为用户提供视觉提示，但不充当该字段的永久标签或值。
- **绑定引用** - 绑定引用是对存储在外部数据源中并在表单中使用的数据元素的引用。通过绑定引用，可动态地将数据绑定到表单字段，以使表单可显示来自数据源的最新数据。例如，可使用绑定引用，根据输入到表单中的客户 ID，在该表单中显示该客户的姓名和地址。还可使用绑定引用，通过输入到表单中的数据更新数据源。这样通过 AEM Forms 即可创建与外部数据源交互的表单，从而为收集和管理数据提供一种无缝的用户体验。

- **标记为未绑定表单元素**：选择此选项可配置未链接到任何架构的表单字段。利用此选项，您可以保存数据而不更新数据源。它还可让您以一种独立于标准数据库集成的自定义方式处理数据。

- **隐藏组件** - 选中此选项以从表单中隐藏该组件。仍可访问该组件作其他用途，如在规则编辑器中使用它进行计算。当需要存储用户无需看到或直接更改的信息时，此项很有用。
- **禁用组件** - 选中此选项以禁用该组件。被禁用的组件不再活跃或最终用户无法编辑它。用户可看到但无法修改字段的值。仍可访问该组件作其他用途，如在规则编辑器中使用它进行计算。
- **只读** - 选中此选项以使组件不可编辑。用户可看到但无法修改字段的值。仍可访问该组件作其他用途，如在规则编辑器中使用它进行计算。
- **默认日期和时间** - 通过此选项可在表单字段中添加日期和时间。输入的日期默认显示在组件的位置。如果用户没有输入日期和时间，这个值就采用表单提交的时间。如果选择了&#x200B;**被禁用的组件**&#x200B;或&#x200B;**只读组件**，屏幕上就会显示默认日期和时间，并在提交表单时提交默认值。

### “验证”选项卡 {#validation-tab}

![“验证”选项卡](/help/adaptive-forms/assets/datetime_validation.png)

- **必需** - 如果要在自适应表单中显示该组件，请选中此选项。选择此选项后，您必须先做出选择，之后才能继续提交表单。选中此选项后，无法在&#x200B;**“基本”**&#x200B;选项卡中选择&#x200B;**隐藏组件**&#x200B;或&#x200B;**禁用组件**。

- **错误消息** - 通过此选项，可输入如果选中了&#x200B;**必需**&#x200B;复选框并将表单字段留空，所显示的消息。

- **脚本验证消息** - 通过此选项，可输入如果脚本验证失败，所显示的消息。

- **最早日期** - 通过此选项，可输入要求的最早日期。如果输入的日期早于“最早日期和时间”中指定的值，屏幕上就会显示一条错误消息。通过&#x200B;**最早日期错误消息**&#x200B;对话框，可添加自定义错误消息。

- **最早日期错误消息** - 您可以在&#x200B;**最早日期错误消息**&#x200B;对话框中添加在输入的日期早于&#x200B;**最早日期**&#x200B;选项中指定日期和时间的情况下应显示的自定义错误消息。

- **最晚日期** - 您可以通过此选项输入要求的最晚日期和时间。如果输入的日期或时间晚于“最晚日期”中指定的日期或时间，屏幕上就会显示一条错误消息。通过&#x200B;**最晚日期错误消息**&#x200B;对话框，可添加自定义错误消息。

- **最晚日期错误消息** - 您可以在&#x200B;**最晚日期错误消息**&#x200B;对话框中添加在输入的日期或时间晚于&#x200B;**最晚日期**&#x200B;选项中指定的日期或时间的情况下应显示的自定义错误消息。

### “帮助内容”选项卡 {#help-content-tab}

![“帮助内容”选项卡](/help/adaptive-forms/assets/datetime_helptab.png)

- **简短描述** - 简短描述是一段简短的文字说明，其中提供关于特定表单字段的用途的其他信息或阐述。它帮助用户了解应将什么类型的数据输入到字段中，并可提供准则或示例以帮助确保所输入的信息有效且符合预期的标准。默认情况下，简短描述保持隐藏状态。启用&#x200B;**始终显示简短描述**&#x200B;选项以在组件下方显示它。

- **始终显示简短描述** - 启用该选项以在组件下方显示简短描述。

- **帮助文本** - 帮助文本是指提供给用户以帮助其正确填写表单字段的其他信息或指导。当用户单击组件旁的“帮助”图标 (i) 时显示它。帮助文本提供比表单字段的标签或占位符文本更详细的信息，旨在帮助用户了解该字段的要求或限制。它还可提供建议或示例，以使填写表单更轻松且更准确。


### “辅助功能”选项卡 {#accessibility-tab}

![“辅助功能”选项卡](/help/adaptive-forms/assets/datetime_accessibilitytab.png)

- **屏幕阅读器文本** - 屏幕阅读器文本是指专供由视障人士使用的屏幕阅读器等辅助技术读取的附加文本。此文本提供表单字段用途的音频描述，并可包括关于字段的标题、描述、名称和任何相关消息（自定义文本）的信息。屏幕阅读器文本帮助确保包括视障用户在内的所有用户均可访问表单，并使其完整地了解表单字段及其要求。
   - **自定义文本**：选中此选项以将自定义文本用于 ARIA 辅助功能标签。选中此选项将显示“自定义文本”对话框。可在“自定义文本”对话框中添加相关信息。
   - **描述**：选中此选项以将描述用于 ARIA 辅助功能标签。
   - **标题**：选中此选项以将标题用于 ARIA 辅助功能标签。
   - **名称**：选中此选项以将名称用于 ARIA 辅助功能标签。
   - **无**：如果不想为 ARIA 辅助功能标签添加任何内容，请选中此选项。

<!--
### Formats Tab {#format-tab}

![Formats tab](/help/adaptive-forms/assets/datepicker_formattab.png)

-   **Display Format** - It represents the date format that is displayed to the user. The **Type** option allows the user to select the date format. You can also customize the date format using the **Custom** option in the **Type** dropdown menu.

-   **Edit Format** - It represents a date format in which the user can edit the date. The **Type** option allows the user to select the date format. You can also customize the date format using the **Custom** option in the **Type** dropdown menu.
-  **Format error message** - This option allows you to enter the message displayed on the screen when the entered date is not in the correct format.
- **Language** - This feature is used for formatting the specific field. When a user selects any language option from the **Type** drop-down menu, the **IETF BCP 47 language tag** option appears in the panel. You can choose the language for field formatting when translating an Adaptive Form into a specific language.
  
The set of languages is not visible by default, but users can input a custom **IETF BCP 47 language tag** by updating the template policy:

  1. Open the corresponding template associated with an Adaptive Form in the template editor.
  2. Select the existing policy as `datepicker-default-policy` from the drop-down menu.
   
        ![Date Picker template Policy](/help/adaptive-forms/assets/date-picker-template-policy.png)

  3. Click **Done**.

        >[!NOTE]
        >
        > For further information on how to translate an Adaptive Form to a specific locale, [click here](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/supporting-new-language-localization-core-components).
-->

## “设计”对话框 {#design-dialog}

“设计”对话框用于定义和管理日期和时间组件的 CSS 样式。

### “样式”选项卡 {#styles-tab}

该选项卡用于定义和管理组件的 CSS 样式。自适应表单日期和时间核心组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。

![“样式”选项卡](/help/adaptive-forms/assets/datepicker_styletab.png)

- **默认 CSS 类**：您可以为自适应表单日期和时间核心组件提供一个默认 CSS 类。

- **允许使用的样式**：可通过提供名称和表示样式的 CSS 类而定义样式。例如，您可以创建一个名为“bold text”的样式，并提供 CSS 类“font-weight: bold”。可使用这些样式或将其应用于自适应表单编辑器中的自适应表单。要应用样式，请在自适应表单编辑器中选择要将样式应用于的组件，导航到“属性”对话框，然后从&#x200B;**样式**&#x200B;下拉列表中选择所需的样式。如果您需要更新或修改样式，只需返回“设计”对话框，在“样式”选项卡中更新样式，然后保存更改。

### 自定义属性

![“自定义属性”对话框](/help/adaptive-forms/assets/datepicker_customproperties.png)

通过自定义属性，您可使用表单模板将自定义属性（键值对）关联到自适应表单核心组件。自定义属性反映在组件 Headless 演绎版的属性部分中。它可让您创建根据自定义属性值进行调整的动态表单行为。例如，开发人员可以为移动、桌面或 Web 平台设计 Headless 表单组件的各种演绎版，从而大大提升各种设备上的用户体验。

- **组名称**：您可以提供名称来标识自定义属性组。您可以添加、删除或重新排列多个自定义属性组。添加自定义属性组后，可看到以下选项：

   - **键值对**：您可以通过单击“**添加**”按钮，为每个自定义属性组添加多个自定义属性名称和自定义属性值。

   - **删除**：点击或单击此项可删除自定义属性名称和自定义属性值。

   - **重新排列**：点击或单击并拖动可重新排列自定义属性名称和自定义属性值的顺序。

<!--
### Formats Tab {#formats-tab}

The formats tab allows you to specify default and custom date formats.

![Formattab](/help/adaptive-forms/assets/datepicker_formatpolicy.png)



## Related article {#related-article}

* [Create a standalone Adaptive Form](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html)

-->

## 相关文章 {#related-articles}

{{more-like-this}}

## 另请参阅 {#see-also}

{{see-also}}


