---
title: 自适应表单核心组件 - 数字输入
description: 使用或自定义自适应表单数字输入核心组件。
role: Architect, Developer, Admin, User
exl-id: 75604ecf-1ec5-4e97-b934-d6ed49726147
source-git-commit: f0c4d6adf7266bdb6ebc7cde49656efaf3027624
workflow-type: tm+mt
source-wordcount: '2388'
ht-degree: 95%

---


# 数值框组件{#number-input-adaptive-forms-core-component}

自适应表单中的数值框组件是一类允许用户输入数值的表单字段。该组件通常由一个文本字段表示，此字段带有分别用于递增和递减数字的向上和向下箭头。

它还可以与 min、max、step、value 等属性结合使用。这些属性可用于设置字段中允许的最小值和最大值、用于递增或递减数字的步进间隔以及字段的默认值。

该组件可用于收集年龄、数量等数值数据，它也可用于执行加法和减法等数学运算。该组件还可用于验证用户输入的数值数据。

对于辅助功能，请务必指定描述数字输入字段用途的“标签”，以及预期的输入类型。

{{traditional-aem}}

**示例**

![示例](/help/adaptive-forms/assets/numeric-stepper.png)

## 用途 {#reasons-to-use-number-input-numeric-stepper}

有若干原因使得在自适应表单中加入数字输入组件有益，这些原因包括：

- **数学运算**：数值字段可用于执行数学运算，例如加法、减法、乘法和除法。

- **数据范围**：数值字段可用于通过 min、max 和 step 属性设置某个范围的有效值。

- **动态内容**：数值组件可用于显示基于表单字段的动态数据。

## 版本和兼容性 {#version-and-compatibility}

作为 Cloud Service 核心组件 2.0.4 和 AEM 6.5.16.0 Forms 或更高版本核心组件 1.1.12 的一部分，自适应表单数值框核心组件于 2023 年 2 月发布。下表显示所有支持的版本、AEM 兼容性以及相应文档的链接：

| 组件版本 | AEM as a Cloud Service | AEM 6.5.16.0 Forms 或更高版本 |
|---|---|---|
| v1 | 与<br>[版本 2.0.4](/help/adaptive-forms/version.md) 和更高版本兼容 | 与<br>[版本 1.1.12](/help/adaptive-forms/version.md) 和更高版本兼容，但低于版本 2.0.0。 |

有关核心组件版本的信息，请参阅[核心组件版本](/help/adaptive-forms/version.md)文档。


<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技术详细信息 {#technical-details}

可在 [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/numberinput/v1/numberinput) 上的技术文档中获得关于自适应表单数字输入核心组件的最新信息。有关开发核心组件的更多信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## “配置”对话框 {#configure-dialog}

通过“配置”对话框，可轻松地自定义您为访客提供的数字输入体验。还可轻松地定义数字输入选项，从而营造一种无缝的用户体验。

### “基本”选项卡 {#basic-tab}

![“基本”选项卡](/help/adaptive-forms/assets/numberinput_basictab.png)

- **名称** - 可在表单和规则编辑器中通过唯一名称轻松地标识表单组件，但该名称不得包含空格或特殊字符。

- **标题** - 通过组件的标题，可轻松地标识表单中的组件，默认情况下，标题显示在该组件的顶部。如果不添加标题，则显示该组件的名称而非标题文本。
- **允许标题为富文本**：此功能使用户能够格式化纯文本标题，结合粗体、斜体、下划线文本、各种字体、字体大小、颜色和附加选项等功能，以增强视觉呈现和定制效果。它提供了更大的灵活性以及对创作的控制度，使标题在文档、网站或应用程序中脱颖而出。\
  选中&#x200B;**允许标题为富文本**&#x200B;复选框后，可以看到格式化选项，用于设置组件标题的样式。要访问所有可用的格式选项，您可以点击![全屏图标](/help/adaptive-forms/assets/fullscreen-icon.png)选项卡。

  ![富文本支持](/help/adaptive-forms/assets/richtext-support-title.png)

- **隐藏标题** - 选中此选项可隐藏该组件的标题。
- **占位符文本** - 表单组件中的占位符文本是指在输入字段中显示的短标签或提示，用于提示用户需要在该字段中输入什么类型的信息。当用户开始向该字段中键入时，占位符文本消失，如果将该字段留空，则占位符文本重新出现。它为用户提供视觉提示，但不充当该字段的永久标签或值。
- **绑定引用** - 绑定引用是对存储在外部数据源中并在表单中使用的数据元素的引用。通过绑定引用，可动态地将数据绑定到表单字段，以使表单可显示来自数据源的最新数据。例如，可使用绑定引用，根据输入到表单中的客户 ID，在该表单中显示该客户的姓名和地址。还可使用绑定引用，通过输入到表单中的数据更新数据源。这样通过 AEM Forms 即可创建与外部数据源交互的表单，从而为收集和管理数据提供一种无缝的用户体验。
- **标记为未绑定表单元素**：选择此选项可配置未链接到任何架构的表单字段。利用此选项，您可以保存数据而不更新数据源。它还可让您以一种独立于标准数据库集成的自定义方式处理数据。
- **隐藏组件** - 选中此选项以从表单中隐藏该组件。仍可访问该组件作其他用途，如在规则编辑器中使用它进行计算。当需要存储用户无需看到或直接更改的信息时，此项很有用。
- **禁用组件** - 选中此选项以禁用该组件。被禁用的组件不再活跃或最终用户无法编辑它。用户可看到但无法修改字段的值。仍可访问该组件作其他用途，如在规则编辑器中使用它进行计算。
- **只读** - 选中此选项以使组件不可编辑，用户可看到但无法修改字段的值。仍可访问该组件作其他用途，如在规则编辑器中使用它进行计算。
- **数值类型** - 此选项可让您选择表单字段中允许的数值的类型。您可以从下拉菜单中选择“小数”或“整数”类型。
- **默认值** - 通过此选项，可在表单字段中添加默认值。如果选中了&#x200B;**已禁用的组件**&#x200B;或&#x200B;**只读组件**，则在屏幕上显示默认值。如果用户未在表单字段中输入值，则在提交表单时提交此值。

### “验证”选项卡 {#validation-tab}

![“验证”选项卡](/help/adaptive-forms/assets/numberinput_validationtab.png)

- **必需** - 如果要在自适应表单中显示该组件，请选中此选项。选择此选项后，您必须先输入一个值，然后再继续提交表单。选中此选项后，无法在&#x200B;**“基本”**&#x200B;选项卡中选择&#x200B;**隐藏组件**&#x200B;或&#x200B;**禁用组件**。

- **错误消息** - 通过此选项，可输入如果选中了&#x200B;**必需**&#x200B;复选框并将字段留空，所显示的消息。

- **脚本验证消息** - 通过此选项，可输入如果脚本验证失败，所显示的消息。

- **最小数值/最小数字** - 使用此选项可选择允许在表单字段中输入的最小数字。如果在表单字段中输入的值小于&#x200B;**最小数值/最小数字**&#x200B;选项中指定的数字，则会出现错误消息。

- **最小值错误消息** - 此选项可让您输入在用户输入的值小于&#x200B;**最小数值/最小数字**&#x200B;选项中指定的值时显示的错误消息。

- **排除最小值** - 如果您不希望&#x200B;**最小数值/最小数字**&#x200B;选项中指定的最小值包含在要在表单字段中输入的值范围中，请选中此复选框。

- **最大数值/最大数字** - 使用此选项可选择允许在表单字段中输入的最大数字。如果在表单字段中输入的数字大于&#x200B;**最大数值/最大数字**&#x200B;选项中指定的数字，则会出现错误消息。

- **最大值错误消息** - 此选项可让您输入在用户输入的值大于&#x200B;**最大数值/最大数字**&#x200B;选项中指定的值时显示的错误消息。

- **排除最大值** - 如果您不希望&#x200B;**最大数值/最大数字**&#x200B;选项中指定的最大值包含在要在表单字段中输入的值范围中，请选中此复选框。

### “帮助内容”选项卡 {#help-content}

![“帮助内容”选项卡](/help/adaptive-forms/assets/numberinput_helptab.png)

- **简短描述** - 简短描述是一段简短的文字说明，其中提供关于特定表单字段的用途的其他信息或阐述。它帮助用户了解应将什么类型的数据输入到字段中，并可提供准则或示例以帮助确保所输入的信息有效且符合预期的标准。默认情况下，简短描述保持隐藏状态。启用&#x200B;**始终显示简短描述**&#x200B;选项以在组件下方显示它。

- **始终显示简短描述** - 启用该选项以在组件下方显示简短描述。

- **帮助文本** - 帮助文本是指提供给用户以帮助其正确填写表单字段的其他信息或指导。当用户单击组件旁的“帮助”图标 (i) 时显示它。帮助文本提供比表单字段的标签或占位符文本更详细的信息，旨在帮助用户了解该字段的要求或限制。它还可提供建议或示例，以使填写表单更轻松且更准确。

### “辅助功能”选项卡 {#accessibility}

![“辅助功能”选项卡](/help/adaptive-forms/assets/numberinput_accessibility.png)

- **屏幕阅读器文本** - 屏幕阅读器文本是指供由视障人士使用的屏幕阅读器等辅助技术读取的附加文本。此文本提供表单字段用途的音频描述，并可包括关于字段的标题、描述、名称和任何相关消息（自定义文本）的信息。屏幕阅读器文本帮助确保包括视障用户在内的所有用户均可访问表单，并使其完整地了解表单字段及其要求。
   - **自定义文本**：选中此选项以将自定义文本用于 ARIA 辅助功能标签。选中此选项将显示“自定义文本”对话框。可在“自定义文本”对话框中添加相关信息。
   - **描述**：选中此选项以将描述用于 ARIA 辅助功能标签。
   - **标题**：选中此选项以将标题用于 ARIA 辅助功能标签。
   - **名称**：选中此选项以将名称用于 ARIA 辅助功能标签。
   - **无**：如果不想为 ARIA 辅助功能标签添加任何内容，请选中此选项。

### “格式”选项卡 {#formats-configure-tab}

![“辅助功能”选项卡](/help/adaptive-forms/assets/numberinput_formattab.png)

- **显示格式** - 通过此选项，可从不同的整数类型格式中选择选项以供显示。当用户从&#x200B;**类型**&#x200B;下拉菜单中选择任意选项时，**格式**&#x200B;选项将在面板中可见。您可以选择向用户显示的数字所采用的特定格式。
- **语言**：此功能用于格式化特定字段。当用户从&#x200B;**类型**&#x200B;下拉菜单中选择任何语言选项时，**IETF BCP 47 语言标记**&#x200B;选项就会出现在面板中。将自适应表单翻译成特定语言时，您可以选择字段格式的语言。

默认情况下，语言集不可见，但用户可以通过更新模板策略输入自定义 **IETF BCP 47 语言标记** ：

1. 在模板编辑器中打开与自适应表单关联的相应模板。
2. 从下拉菜单中选择 `numberinput-default-policy` 为现有策略。

   ![日期选择器模板策略](/help/adaptive-forms/assets/numberinput-template-policy.png)

3. 单击&#x200B;**完成**。

   >[!NOTE]
   >
   > 如需了解如何将自适应表单翻译至特定语言环境的更多信息，请[点击此处](https://experienceleague.adobe.com/zh-hans/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/supporting-new-language-localization-core-components)。


## “设计”对话框 {#design-dialog}

“设计”对话框用于定义和管理数值框组件的 CSS 样式。

### “样式”选项卡 {#styles-tab}

该选项卡用于定义和管理组件的 CSS 样式。自适应表单数字输入核心组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。

![“样式”选项卡](/help/adaptive-forms/assets/datepicker_styletab.png)

- **默认 CSS 类**：可为自适应表单数值框核心组件提供默认 CSS 类。

- **允许使用的样式**：可通过提供名称和表示样式的 CSS 类而定义样式。例如，您可以创建一个名为“bold text”的样式，并提供 CSS 类“font-weight: bold”。可使用这些样式或将其应用于自适应表单编辑器中的自适应表单。要应用样式，请在自适应表单编辑器中选择要将样式应用于的组件，导航到“属性”对话框，然后从&#x200B;**样式**&#x200B;下拉列表中选择所需的样式。如果您需要更新或修改样式，只需返回“设计”对话框，在“样式”选项卡中更新样式，然后保存更改。

### 自定义属性

![“自定义属性”对话框](/help/adaptive-forms/assets/datepicker_customproperties.png)

通过自定义属性，您可使用表单模板将自定义属性（键值对）关联到自适应表单核心组件。自定义属性反映在组件 Headless 演绎版的属性部分中。它可让您创建根据自定义属性值进行调整的动态表单行为。例如，开发人员可以为移动、桌面或 Web 平台设计 Headless 表单组件的各种演绎版，从而大大提升各种设备上的用户体验。

- **组名称**：您可以提供名称来标识自定义属性组。您可以添加、删除或重新排列多个自定义属性组。添加自定义属性组后，可看到以下选项：

   - **键值对**：您可以通过单击“**添加**”按钮，为每个自定义属性组添加多个自定义属性名称和自定义属性值。

   - **删除**：点击或单击此项可删除自定义属性名称和自定义属性值。

   - **重新排列**：点击或单击并拖动可重新排列自定义属性名称和自定义属性值的顺序。

### “格式”选项卡 {#formats-tab}

格式选项卡允许您指定默认和自定义的日期格式。 此外，您还可以使用&#x200B;**添加**&#x200B;按钮添加新的自定义数字格式。

![“格式”选项卡](/help/adaptive-forms/assets/emailinput_formattab.png)

#### 在组件的模板策略中添加格式

要显示组件的可用格式，必须将其添加到组件的模板策略中。

>[!VIDEO](https://video.tv.adobe.com/v/3477976?quality=12&learn=on)

要将格式添加到模板策略，请执行以下操作：

1. 在模板编辑器中打开与一个或多个自适应表单关联的相应模板。
2. 在&#x200B;**允许的组件**&#x200B;部分中，选择&#x200B;**[!UICONTROL Number Input]**组件。
   ![日期选取器范本原则](/help/adaptive-forms/assets/number-input-policy.png)
3. 单击&#x200B;**[!UICONTROL 添加]**&#x200B;图标以为Number Input组件创建新策略。
4. 输入策略的名称，然后在&#x200B;**格式**选项卡下选择所有必需的格式。
   ![创建策略](/help/adaptive-forms/assets/date-picker-format-policy.png)
5. 单击&#x200B;**[!UICONTROL 完成]**。

<!--

## Related article {#related-article}

* [Create a standalone Adaptive Form](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html)

-->

## 相关文章 {#related-articles}

{{more-like-this}}

## 另请参阅 {#see-also}

{{see-also}}
