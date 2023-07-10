---
title: 自适应表单核心组件 - 标题
description: 使用或自定义自适应表单标题核心组件。
role: Architect, Developer, Admin, User
exl-id: 33eac885-8d66-4a5c-9a32-0ba11e6de293
source-git-commit: 7888cfa0f1358ce8018fc1e3cc3b19eb66a82b9d
workflow-type: ht
source-wordcount: '898'
ht-degree: 100%

---

# 标题 {#title-input-adaptive-forms-core-component}

在自适应表单中，“标题”是指显示在表单顶部的文本（通常位于页眉下方）。标题是使用标题组件指定的。可以将该组件添加到表单布局中，并且可以编辑其文本以匹配表单的用途或主题。标题作为提供给用户的表单的标签或简短描述，可帮助将该表单与其他表单区分开来。

**示例**

![](/help/adaptive-forms/assets/title.png)

## 用途 {#reasons-to-use-title-in-an-adaptive-form}

有若干原因使得在表单中使用标题是一个好的做法：

* **清晰度**：标题清楚地标识了表单的用途，可帮助用户了解他们需要提供哪些信息。

* **编排**：标题可以帮助按主题或用途编排表单，使用户能够更轻松地找到他们需要的表单。

* **辅助功能**：标题是具有辅助功能需求的用户的关键元素，因为屏幕阅读器会大声读出标题，帮助用户理解表单的上下文。

* **品牌化**：标题也可用于显示公司或组织的名称，这有助于为用户建立信任感和熟悉感。

* **导航**：标题对于在表单中导航也很有用，尤其是在表单较长或较复杂时。

* **搜索引擎优化 (SEO)**：为表单创建标题在 SEO 中也很有用，因为搜索引擎可使用标题来确定网页与搜索查询的相关性。

总的来说，表单标题是用户体验的一个重要方面，它应用来为表单提供清晰简洁的标签，从而帮助用户了解表单的上下文和用途。

## 版本和兼容性 {#version-and-compatibility}

作为 Cloud Service 核心组件 2.0.4 和 AEM 6.5.16.0 Forms 或更高版本核心组件 1.1.12 的一部分，自适应表单折叠面板核心组件于 2023 年 2 月发布。下表显示所有支持的版本、AEM 兼容性以及相应文档的链接：

| 组件版本 | AEM as a Cloud Service | AEM 6.5.16.0 Forms 或更高版本 |
|---|---|---|
| v1 | 兼容<br>[版本 2.0.4](/help/adaptive-forms/version.md) 和更高版本 | 兼容<br>[版本 1.1.12](/help/adaptive-forms/version.md) 及更高但低于 2.0.0 的版本。 |

有关核心组件版本的信息，请参阅[核心组件版本](/help/adaptive-forms/version.md)文档。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->


## 技术详细信息 {#technical-details}

可在 [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/title/v1/title) 上的技术文档中获得关于自适应表单标题核心组件的最新信息。有关开发核心组件的更多信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## “配置”对话框 {#configure-dialog}

通过“配置”对话框，可轻松地自定义您为访客提供的标题体验。还可轻松地定义标题选项，从而营造一种无缝的用户体验。

![“基本”选项卡](/help/adaptive-forms/assets/title_properties.png)

内容作者可以使用“编辑”对话框定义标题文本以及选择标题级别。

* **标题** - 通过组件的标题，可轻松地标识表单中的组件，默认情况下，标题显示在该组件的顶部。如果不添加标题，则显示该组件的名称而非标题文本。
* **类型/大小** - 定义标题的标题级别。
* **ID** - 通过此选项，可控制组件在 HTML 和数据层中的唯一标识符。
   * 如果留空，则自动为您生成一个唯一 ID，通过检查所得页面即可找到该 ID。
   * 如果指定一个 ID，作者有责任确保它是唯一的。
   * 更改此 ID 会对 CSS、JS 和数据层跟踪产生影响。

## “设计”对话框 {#design-dialog}

“设计”选项卡用于定义和管理日期选取器组件的 CSS 样式。

### 标题

“标题”选项卡允许模板作者为表单作者设置默认和允许的 HTML 标题元素：

![“设计”对话框“标题”选项卡](/help/adaptive-forms/assets/title_heading.png)

* **允许的标题元素**：包含多个选项的列表，供模板作者选择允许表单作者在标题中使用哪些标题元素。

* **默认标题元素** - 下拉列表，设置标题组件的默认标题元素。

### “样式”选项卡 {#styles-tab}

该选项卡用于定义和管理组件的 CSS 样式。自适应表单日期选取器核心组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。

![“设计”对话框“标题”选项卡](/help/adaptive-forms/assets/title_styles.png)

* **默认 CSS 类**：可为自适应表单日期选取器核心组件提供默认 CSS 类。

* **允许使用的样式**：可通过提供名称和表示样式的 CSS 类而定义样式。例如，您可以创建一个名为“bold text”的样式，并提供 CSS 类“font-weight: bold”。可使用这些样式或将其应用于自适应表单编辑器中的自适应表单。要应用样式，请在自适应表单编辑器中选择要将样式应用于的组件，导航到“属性”对话框，然后从&#x200B;**样式**&#x200B;下拉列表中选择所需的样式。如果您需要更新或修改样式，只需返回“设计”对话框，在“样式”选项卡中更新样式，然后保存更改。

### “格式”选项卡 {#format-tab}

通过“格式”选项卡，可指定默认和自定义日期格式。

![“格式”选项卡](/help/adaptive-forms/assets/title_styles.png)

## 相关文章 {#related-article}

* [在 AEM Sites 页面或体验片段中创建自适应表单](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/create-or-add-an-adaptive-form-to-aem-sites-page.html)

* [创建独立的自适应表单](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html)

