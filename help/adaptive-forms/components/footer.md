---
title: 自适应Forms核心组件 — 页脚
description: 使用或自定义自适应Forms页脚核心组件。
role: Architect, Developer, Admin, User
source-git-commit: b378fbd5695f82b8fc9de3a2d53a8387099ae33b
workflow-type: tm+mt
source-wordcount: '749'
ht-degree: 19%

---


# 页脚 {#footer-adaptive-forms-core-component}

自适应表单中的页脚组件是通常显示在表单底部的区域，其中包含版权声明、相关资源的链接或联系信息等信息。 页脚可以提供其他信息，如上次更新的日期，这对具有辅助功能需求的用户会有所帮助。

**示例**

![](/help/adaptive-forms/assets/footer.png)

## 用途 {#reasons-to-use-footer}

在表单中包含页脚组件有益的原因有多种，包括：

* **法律要求**:某些表单可能需要包含免责声明、版权声明或其他法律信息。 页脚是包含此信息的方便位置。

* **导航**:页脚可以提供指向网站上其他重要页面的链接，例如隐私政策、服务条款或联系页面。

* **品牌策略**:页脚可用于包含徽标或其他品牌元素，从而有助于加强组织或网站的标识。

* **一致性**:页脚在表单的设计和布局方面保持一致，使其更加直观，便于用户导航。

* **其他上下文**:页脚可以为表单提供其他上下文，如描述表单的文本或指向相关资源的链接，从而使表单信息更丰富且用户更友好。

## 版本和兼容性 {#version-and-compatibility}

自适应Forms页脚核心组件作为核心组件2.0.4的一部分于2023年2月发布。下面是一个表格，其中显示了所有受支持的版本、AEM兼容性以及指向相应文档的链接：

|  |  |
|---|---|
| 组件版本 | AEM as a Cloud Service |
| --- | --- |
| v1 | 兼容 with<br>[版本2.0.4](/help/versions.md) 及更高版本 | 兼容 | 兼容 |

有关核心组件版本和版本的信息，请参阅 [核心组件版本](/help/versions.md) 文档。

<!-- ## Sample Component Output {#sample-component-output}

To experience the Accordion Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](https://adobe.com/go/aem_cmp_library_accordion). -->

## 技术详细信息 {#technical-details}

在以下位置的技术文档中，获取有关自适应Forms页脚核心组件的最新信息： [GitHub](https://github.com/adobe/aem-core-forms-components/tree/master/ui.af.apps/src/main/content/jcr_root/apps/core/fd/components/form/footer/v1/footer). 有关开发核心组件的更多信息，请参阅 [核心组件开发人员文档](/help/developing/overview.md).


## “配置”对话框 {#configure-dialog}

您可以使用配置对话框轻松自定义访客的页脚体验。 您还可以轻松定义页脚选项，以获得无缝的用户体验。

![“属性”选项卡](/help/adaptive-forms/assets/footer_propertiestab.png)

* **“编辑”对话框**
编辑对话框提供了标准富文本格式工具，允许用户为页脚创建文本。

* **粗体**  — 此选项将粗体格式应用于所选文本，或大胆设置光标后输入的文本格式。 `Ctrl+B` 是键盘快捷键。

* **斜体**  — 此选项将斜体格式应用于选定文本或在光标后输入的斜体文本。 `Ctrl+I` 是键盘快捷键。

![项目符号选项](/help/adaptive-forms/assets/footer_bullet.png)


* **项目符号**

   * **项目符号图标**  — 将所选文本格式设置为项目符号列表，或在光标后开始插入项目符号列表。 要结束项目符号列表，请再次点击或单击“项目符号”按钮或输入两个回车符。

   * **编号列表图标**  — 将所选文本格式化为编号列表，或在光标后开始插入编号列表。 要结束编号列表，请再次点击或单击“编号”按钮或输入两个回车符。

   * **“输出”图标**  — 它减少在光标之后输入的选定文本或文本的缩进级别。 仅当所选文本或光标位置已缩进时才处于活动状态。

   * **缩进图标**  — 增加光标后输入的选定文本或文本的缩进级别。

![超链接选项](/help/adaptive-forms/assets/footer_link.png)

* **超链接**

   * **路径**  — 输入路径
      1. 使用“打开选择”对话框可在 AEM 中选择路径.
      1. 如果链接未在 AEM 中，请输入绝对 URL.
      1. 非绝对路径将解释为相对于 AEM.
   * **替换文本**  — 为链接输入替代的描述性文本。

   * **Target**  — 选择链接行为
      * 目标
      * 相同选项卡
      * 新选项卡
      * 父框架
      * 顶层框架
   * **取消链接图标**  — 此选项会删除已应用于选定文本的链接。 仅当链接已被选中时，此选项才处于活动状态。

   * **段落格式图标**  — 利用此选项，可将段落格式应用于所选文本。 它还有助于您设置光标后插入的文本的格式。 它定义标题的标题级别。



* **ID**:利用此选项，可控制HTML和数据层中组件的唯一标识符。

   * 如果留为空白，则会自动*为您生成唯一ID，并且可以通过检查生成的页面找到该唯一ID。
   * 如果指定一个 ID，作者有责任确保它是唯一的。
   * 更改此 ID 会对 CSS、JS 和数据层跟踪产生影响。


