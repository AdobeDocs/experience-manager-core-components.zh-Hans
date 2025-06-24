---
title: 文本组件
description: 文本组件是一种富文本编辑和撰写组件，具有就地编辑功能。
role: Architect, Developer, Admin, User
exl-id: bcea202a-9ecb-4dcd-99b6-0848cbb9d500
source-git-commit: dd30def59a8f037864da875ef4c831b11f766e57
workflow-type: tm+mt
source-wordcount: '2185'
ht-degree: 100%

---


# 文本组件{#text-component}

核心组件文本组件是一种富文本编辑和撰写组件，具有就地编辑功能。

{{traditional-aem}}

## 用途 {#usage}

文本组件提供了一个强大的富文本编辑器，允许在简化的内联编辑器中以全屏格式轻松编辑文本。

[“编辑”对话框](#edit-dialog)具有带有限选项的内联编辑功能，可在全屏编辑对话框中实现完整功能。利用[“设计”对话框](#design-dialog)，可以为内容作者配置模板的文本格式选项，例如标题、特殊字符和段落样式。

## 版本和兼容性 {#version-and-compatibility}

文本组件的当前版本是 v2，此版本随 2018 年 1 月的核心组件发行版本 2.0.0 的发布引入，具体说明见本文。

下表详细说明了该组件的所有受支持版本、与该组件的版本兼容的 AEM 版本以及指向早期版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM 6.5 LTS | AEM as a Cloud Service |
|---|---|---|---|---|
| v2 | 与<br>[版本 2.17.4](/help/versions.md) 和更低版本兼容 | 兼容 | 兼容 | 兼容 |
| [v1](v1/text-v1.md) | 兼容 | 兼容 | - | 兼容 |

有关核心组件版本的更多信息，请参阅文档[核心组件版本](/help/versions.md)。

## 示例组件输出 {#sample-component-output}

要体验文本组件并查看其配置选项示例以及 HTML 和 JSON 输出，请访问[组件库](https://adobe.com/go/aem_cmp_library_text_cn)。

### 技术详细信息 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_text_v2_cn)有关文本组件的最新技术文档。

在[核心组件开发人员文档](/help/developing/overview.md)中可找到有关开发核心组件的其他详细信息。

## 文本组件和富文本编辑器 {#the-text-component-and-the-rich-text-editor}

核心组件文本组件利用 AEM 富文本编辑器 (RTE)。RTE 为内容作者提供了一系列广泛的功能来编辑其文本内容。RTE 的配置非常灵活，并切提供了许多选项。有关如何配置 RTE 的其他详细信息，请参阅文章[配置富文本编辑器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/configuring-and-extending/rich-text-editor.html)和[配置富文本编辑器插件](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/configuring-and-extending/configure-rich-text-editor-plug-ins.html)。

本文章的其余部分演示了带现成的 RTE 配置的核心组件文本组件的标准配置。

>[!NOTE]
>
>仅由 [RTE 的 UI 配置](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/configuring-and-extending/configure-rich-text-editor-plug-ins.html)启用的选项在文本组件中可用。

## “编辑”对话框 {#edit-dialog}

“编辑”对话框提供了用户将用于撰写文本的标准富文本格式工具。

![文本组件的“编辑”对话框](/help/assets/text-edit.png)

### 粗体

![“粗体”图标](/help/assets/text-bold.png)

用于对所选文本应用粗体格式或对在光标后输入的文本应用粗体格式。

**Ctrl+B** 可用作快捷键。

### 斜体

![“斜体”图标](/help/assets/text-italic.png)

用于对所选文本应用斜体格式或对在光标后输入的文本应用斜体格式。

**Ctrl+I** 可用作快捷键。

### 下划线

![“下划线”图标](/help/assets/text-underline.png)

用于对所选文本应用下划线格式或对在光标后输入的文本应用下划线格式。

**Ctrl+U** 可用作快捷键。

### 下标

![“下标”图标](/help/assets/text-subscript.png)

用于将所选文本或在光标后输入的文本设置为下标格式。

### 上标

![“上标”图标](/help/assets/text-superscript.png)

用于将所选文本或在光标后输入的文本设置为上标格式。

### 粘贴为文本

![“粘贴为文本”图标](/help/assets/text-paste-text.png)

将任何复制的文本粘贴为纯文本，而不设置任何格式。

当选择此选项时，将打开一个窗口，其中的文本可以粘贴为无格式的纯文本，作为插入文本中之前的预览。通过点击或单击复选标记可接受，通过点击或单击 x 可取消。

![粘贴为文本示例](/help/assets/text-paste-text-example.png)

### 从 Word 粘贴

![“从 Word 粘贴”图标](/help/assets/text-paste-word.png)

当选择此选项时，将打开一个窗口，其中的文本可粘贴并保留其格式，作为插入文本中之前的预览。通过点击或单击复选标记可接受，通过点击或单击 x 可取消。

![从 Word 粘贴示例](/help/assets/text-paste-word-example.png)

### 超链接

![“超链接”图标](/help/assets/text-hyperlink.png)

使用此选项可将所选文本转换为超链接或修改已定义的链接。此选项仅在已选择文本并打开一个窗口（其中包含用于设置链接的附加选项）时处于活动状态。

![超链接示例](/help/assets/text-hyperlink-example.png)

* 输入路径
   * 使用“打开选择”对话框可在 AEM 中选择路径
   * 如果链接未在 AEM 中，请输入绝对 URL
      * 非绝对路径将解释为相对于 AEM
* 输入链接的替换描述文本
* 选择链接行为
   * 目标
   * 相同选项卡
   * 新选项卡
   * 父框架
   * 顶层框架

  点击或单击复选标记可应用链接，点击或单击 x 可取消。

### 取消链接

![“取消链接”图标](/help/assets/text-unlink.png)

使用此选项可删除已应用于所选文本的链接。此选项仅在已选择链接时处于活动状态。

### 查找

![“查找”图标](/help/assets/text-find.png)

使用此选项可搜索文本以确定指定文本字符串的匹配项。选择此选项将打开一个用于指定搜索选项的窗口。

![查找示例](/help/assets/text-find-example.png)

输入要搜索的文本并点击或单击&#x200B;**“查找”**以开始搜索。点击或单击 x 可取消。
如果您希望根据大小写进行精确匹配，请选择选项**匹配大小写**，然后再开始搜索。
如果找到一个匹配项，则将突出显示该匹配项，并且搜索对话框将灰显。在灰显的对话框中再次点击或单击**查找**&#x200B;按钮可搜索下一个匹配项。

![查找示例 - 已找到](/help/assets/text-find-example-found.png)

如果未找到其他匹配项，则将显示一条消息，并且将从文本的开头重新开始搜索。

![查找示例 - 无其他匹配项](/help/assets/text-find-example-found-end.png)

### 替换

![“替换”图标](/help/assets/text-replace.png)

使用此选项可搜索文本以确定指定文本字符串的匹配项，并将匹配项替换为其他字符串。选择此选项将打开一个用于指定搜索和替换选项的窗口。

![替换示例](/help/assets/text-replace-example.png)

输入要搜索的文本以及应替换为的文本。

* 点击或单击&#x200B;**查找**&#x200B;可开始搜索。单击或点击 x 可取消。
* 如果您希望根据大小写进行精确匹配，请选择选项&#x200B;**匹配大小写**，然后再开始搜索。
* 选择&#x200B;**全部替换**&#x200B;可一次性替换文本的所有匹配项。

如果找到一个匹配项，则将突出显示该匹配项，并且搜索对话框将灰显。在灰显对话框中再次单击&#x200B;**查找**&#x200B;按钮可搜索下一个匹配项，选择&#x200B;**替换**&#x200B;按钮可替换突出显示的匹配文本。请注意，**替换**&#x200B;按钮仅在进行匹配后处于活动状态。

在单击“查找”时，“查找和替换”对话框变为透明；在单击“替换”时，此对话框变为不透明。这允许作者审查自己将替换的文本。

>[!NOTE]
>
>在使用替换功能时，要替换的替换字符串应与查找字符串同时输入。不过，您仍可以在替换字符串之前单击“查找”来搜索它。如果在单击“查找”后输入替换字符串，则搜索将重置到文本的开头。


### 左对齐文本

![“左对齐”图标](/help/assets/text-left.png)

用于将文本与左边距对齐。

### 居中对齐文本

![“居中对齐文本”图标](/help/assets/text-center.png)

用于将文本居中对齐。

### 右对齐文本

![“右对齐”图标](/help/assets/text-right.png)

用于将文本与右边距对齐。

### 项目符号

![“项目符号”图标](/help/assets/text-bullet.png)

用于将所选文本设置为项目符号列表格式或在光标后开始插入项目符号列表。

要结束项目符号列表，请再次点击或单击&#x200B;**“项目符号”**&#x200B;按钮或输入两个回车符。

### 编号

![“编号列表”图标](/help/assets/text-numbered.png)

用于将所选文本设置为编号列表格式或在光标后开始插入编号列表。

要结束编号列表，请再次点击或单击&#x200B;**“编号”**&#x200B;按钮或输入两个回车符。

### 减少缩进

![“减少缩进”图标](/help/assets/text-outdent.png)

用于降低所选文本或光标后输入的文本的缩进级别。

仅当所选文本或光标位置已缩进时才处于活动状态。

### 缩进

![“缩进”图标](/help/assets/text-indent.png)

用于增加所选文本或光标后输入的文本的缩进级别。

### 表

![“表”图标](/help/assets/text-table.png)

用于将表插入文本中。选择此选项将打开一个用于指定表的详细信息的窗口。

![表示例](/help/assets/text-table-example.png)

* **列数** - 表的列数（必需）
* **行数** - 表的行数（必需）
* **宽度** - 表的宽度
* **高度** - 表的高度
* **单元格内边距** - 单元格内容周围的空间
* **单元格间距** - 单元格之间的空间
* **边框** - 表的边框线的粗细
   * 对于表的标题：
      * 应使用第一行
      * 应使用第一列
      * 应使用第一行和第一列
      * 或者不应使用标题。
* **题注** - 表的题注

### 检查拼写

![“检查拼写”图标](/help/assets/text-spellcheck.png)

用于检查文本内容的拼写。为可能的拼写错误加下划线（红色虚线）。

有关拼写检查和自定义拼写检查词典的更多详细信息，请参阅[配置富文本编辑器插件](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/configuring-and-extending/configure-rich-text-editor-plug-ins.html)文档。

### 特殊字符 {#special-characters}

![“特殊字符”图标](/help/assets/text-special-characters.png)

用于将特殊字符插入文本中。选择此选项将打开一个用于显示可用字符的窗口。

![特殊字符示例](/help/assets/text-special-characters-example.png)

点击或单击所需字符以将其插入光标后的文本中。可插入多个字符。点击或单击 x 可关闭选择窗口。

### 编辑源文件

![“编辑源文件”图标](/help/assets/text-source.png)

用于查看和修改文本的 HTML 源。

点击或单击&#x200B;**“编辑源文件”**&#x200B;图标可从格式化视图更改文本内容以查看原始 HTML。在此模式中，将禁用所有其他格式选项。再次点击或单击&#x200B;**“编辑源文件”**&#x200B;图标可返回格式化视图。

>[!CAUTION]
>
>与访问原始 HTML 的情况一样，使用&#x200B;**编辑源文件**&#x200B;选项时必须小心！
>
>将扫描通过&#x200B;**编辑源文件**&#x200B;输入的 HTML 以确定是否存在 XSS 风险，插入的任何脚本将被删除且不会显示在结果页上。不过，在&#x200B;**编辑源文件**&#x200B;中输入的格式错误的 HTML 可能会破坏页面的模板，从而导致意外的格式设置或表明生成的页面不可用。

>[!NOTE]
>
>由于将扫描通过&#x200B;**编辑源文件**&#x200B;输入的 HTML 以确定是否存在 XSS 风险和任何脚本，并且会自动删除找到的脚本，因此保留的实际内容可能会因在&#x200B;**编辑源文件**&#x200B;中输入的内容而异。因此，要保存使用&#x200B;**编辑源文件夹**&#x200B;所做的更改，您必须先退出&#x200B;**编辑源文件**&#x200B;以在保存之前在常用编辑器中查看文本。

### 段落格式

![“段落格式”图标](/help/assets/text-paragraph.png)

用于对所选文本或在光标后插入的文本应用段落格式。选择此选项将打开一个下拉菜单，可从中选择段落格式。

![段落格式示例](/help/assets/text-paragraph-example.png)

### 内联编辑 {#in-line-editing}

也可以对文本组件进行内联编辑，但由于空间限制，无法对所有格式选项进行内联编辑。要查看所有选项，请切换到全屏模式。

![内联编辑示例](/help/assets/text-edit-inline-example.png)

### 设置 ID {#setting-id}

此选项允许你控制 HTML 和 [数据层中组件的唯一标识符。](/help/developing/data-layer/overview.md)

* 如果留空，则自动为您生成一个唯一 ID，通过检查所得页面即可找到该 ID。
* 如果指定一个 ID，作者有责任确保它是唯一的。
* 更改此 ID 会对 CSS、JS 和数据层跟踪产生影响。

## “设计”对话框 {#design-dialog}

利用“设计”对话框，模板作者可以定义哪些文本格式选项可供内容作者使用。

### “插件”选项卡 {#plugins-tab}

“插件”选项卡用于启用和禁用对内容作者可用的各种文本格式选项。

### 功能 {#features}

![“设计”对话框 - 功能](/help/assets/text-design-features.png)

可以为组件激活或停用以下功能。

* 粘贴纯文本
* 从 Word 粘贴
* 查找并替换
* 拼写检查器
* 插入的图像修改选项
* HTML 源编辑

### 格式 {#formatting}

![“设计”对话框 - 格式](/help/assets/text-design-formatting.png)

可以为组件激活或停用以下格式选项。

* 表
* 列表（项目符号、编号、缩进、减少缩进）
* 对齐方式（左对齐、右对齐、居中对齐）
* 粗体、斜体、下划线
* 链接（和取消链接）
* 下标/上标

### 段落样式 {#paragraph-styles}

![“设计”对话框 - 段落样式](/help/assets/text-design-paragraph.png)

可以为组件激活或停用段落样式。在激活时，可以定义允许的格式。

* 点击或单击&#x200B;**“添加”**&#x200B;按钮可插入新样式。
* 输入将在“编辑”对话框中显示的样式代码和描述。
* 要删除样式，请点击或单击&#x200B;**“删除”**&#x200B;按钮。
* 要重新设置格式的顺序，请点击或单击并拖动手柄。

### 特殊字符 {#configuring-special-characters}

![“设计”对话框 - 特殊字符](/help/assets/text-design-special-characters.png)

可以为组件激活或停用用于插入特殊字符的选项。在激活时，可以定义允许的字符。

* 点击或单击&#x200B;**“添加”**&#x200B;按钮可插入新字符。
* 输入将在“编辑”对话框中显示的字符的 HTML 代码和描述。
* 要删除字符，请点击或单击&#x200B;**“删除”**&#x200B;按钮。
* 要重新设置字符的顺序，请点击或单击并拖动手柄。

## “样式”选项卡 {#styles-tab}

文本组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。

## Adobe Client Data Layer {#data-layer}

文本组件支持 [Adobe Client Data Layer](/help/developing/data-layer/overview.md)。
