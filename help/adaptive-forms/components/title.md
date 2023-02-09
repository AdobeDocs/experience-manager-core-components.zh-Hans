---
title: 自适应Forms核心组件 — 标题
description: 使用或自定义自适应Forms标题核心组件。
role: Architect, Developer, Admin, User
source-git-commit: 945e1793ae4e959f83960db46d2de4257916fe32
workflow-type: tm+mt
source-wordcount: '836'
ht-degree: 15%

---


# 标题 {#title-input-adaptive-forms-core-component}

在自适应表单中，“标题”是指在表单顶部显示的文本，通常显示在标题下方。 标题是使用标题组件指定的。 此组件可添加到表单布局中，并且可以编辑其文本以匹配表单的用途或主题。 标题用作用户表单的标签或简要说明，有助于区分表单和其他表单。

**示例**

![](/help/adaptive-forms/assets/title.png)

## 用途 {#reasons-to-use-title-in-an-adaptive-form}

在表单中使用标题是一种好做法的原因有以下几点：

* **清晰度**:标题可明确标识表单的用途，有助于用户了解他们需要提供哪些信息。

* **组织**:标题有助于按主题或用途组织表单，从而更便于用户查找所需的表单。

* **辅助功能**:标题是满足用户辅助功能需求的关键元素，因为标题会由屏幕阅读器大声朗读，从而帮助用户了解表单的上下文。

* **品牌策略**:标题还可用于显示公司或组织的名称，这有助于产生对用户的信任感和熟悉感。

* **导航**:标题也可用于在表单中导航，尤其是当表单较长或复杂时。

* **搜索引擎优化(SEO)**:在表单上设置标题也有助于实现SEO，因为搜索引擎使用标题来确定网页与搜索查询的相关性。

总的说来，表单的标题是用户体验的一个重要方面，它应该用于为表单提供简洁明了的标签，以帮助用户了解表单的上下文和目的。

## 版本和兼容性 {#version-and-compatibility}

自适应Forms标题核心组件作为核心组件2.0.4的一部分于2023年2月发布。下面是一个表格，其中显示了所有受支持的版本、AEM兼容性以及指向相应文档的链接：

|  |  |
|---|---|
| 组件版本 | AEM as a Cloud Service |
| --- | --- |
| v1 | 兼容 with<br>[版本2.0.4](/help/versions.md) 及更高版本 | 兼容 | 兼容 |

有关核心组件版本和版本的信息，请参阅 [核心组件版本](/help/versions.md) 文档。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->


## 技术详细信息 {#technical-details}

在 [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/title/v1/title). 有关开发核心组件的更多信息，请参阅 [核心组件开发人员文档](/help/developing/overview.md).

## “配置”对话框 {#configure-dialog}

您可以使用配置对话框轻松自定义访客的标题体验。 您还可以轻松定义标题选项，以提供无缝的用户体验。

![“基本”选项卡](/help/adaptive-forms/assets/title_properties.png)

内容作者可以使用“编辑”对话框定义标题文本以及选择标题级别。

* **标题**  — 通过其标题，您可以轻松地在表单中识别组件，默认情况下，标题会显示在组件顶部。 如果不添加标题，则会显示组件的名称，而不是标题文本。
* **类型/大小** - 定义标题的标题级别.
* **ID** – 利用此选项，可以控制 HTML 和数据层中组件的唯一标识符。
   * 如果留空，系统会自动为您生成一个唯一 ID，可以通过检查结果页面找到该 ID。
   * 如果指定一个 ID，作者有责任确保它是唯一的。
   * 更改此 ID 会对 CSS、JS 和数据层跟踪产生影响。

## “设计”对话框 {#design-dialog}

“设计”对话框用于定义和管理日期选取器组件的CSS样式。

### 标题

标题选项卡允许模板作者为表单作者设置默认和允许的HTML标题元素：

![“设计”对话框标题选项卡](/help/assets/accordion-design-properties.png)

* **允许的标题元素**:一个包含多个选项的列表，允许模板作者选择表单作者可以用于标题的标题元素。

* **默认标题元素**:下拉列表，用于设置标题组件的默认标题元素。


### 样式选项卡 {#styles-tab}

“设计”对话框用于定义和管理组件的CSS样式。 自适应Forms日期选取器核心组件支持AEM [样式系统](/help/get-started/authoring.md#component-styling).

**默认CSS类**:您可以为自适应Forms日期选取器核心组件提供默认CSS类。

**允许的样式**:您可以通过提供名称和表示样式的CSS类来定义样式。 例如，您可以创建名为“粗体文本”的样式，并提供CSS类“font-weight:粗体”。 您可以在自适应Forms编辑器中将这些样式用于自适应表单或将其应用于自适应表单。 要应用样式，请在自适应Forms编辑器中，选择要应用该样式的组件，导航到属性对话框，然后从 **样式** 下拉列表。 如果需要更新或修改样式，只需返回到“设计”对话框，更新“样式”选项卡中的样式，然后保存更改即可。

### “格式”选项卡 {#format-tab}

使用“格式”选项卡可指定默认和自定义日期格式。

