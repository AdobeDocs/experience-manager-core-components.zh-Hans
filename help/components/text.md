---
title: 文本组件
description: 文本组件是一种富文本编辑和合成组件，可进行就地编辑。
role: Architect, Developer, Admin, User
exl-id: bcea202a-9ecb-4dcd-99b6-0848cbb9d500
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '2213'
ht-degree: 4%

---

# 文本组件{#text-component}

核心组件文本组件是一种富文本编辑和合成组件，可进行就地编辑。

## 使用 {#usage}

文本组件提供了强大的富文本编辑器，通过该编辑器，可以在简化的内嵌编辑器中轻松编辑文本以及全屏格式。

[编辑对话框](#edit-dialog)具有在全屏编辑对话框中提供的具有完整功能的有限选项的内嵌编辑功能。 使用[设计对话框](#design-dialog)，可以为内容作者的模板配置文本格式选项，例如标题、特殊字符和段落样式。

## 版本和兼容性 {#version-and-compatibility}

文本组件的当前版本为v2，该版本于2018年1月随核心组件2.0.0版引入，在本文档中进行了描述。

下表详细列出了组件的所有受支持版本、组件版本与之兼容的AEM版本，以及指向以前版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|---|
| v2 | 兼容 | 兼容 | 兼容 |
| [v1](v1/text-v1.md) | 兼容 | 兼容 | - |

有关核心组件版本和版本的更多信息，请参阅文档[核心组件版本](/help/versions.md)。

## 组件输出示例 {#sample-component-output}

要体验文本组件并查看其配置选项以及HTML和JSON输出的示例，请访问[组件库](https://adobe.com/go/aem_cmp_library_text)。

### 技术详细信息 {#technical-details}

有关文本组件[的最新技术文档可在GitHub](https://adobe.com/go/aem_cmp_tech_text_v2)上找到。

有关开发核心组件的更多详细信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。

## 文本组件和富文本编辑器 {#the-text-component-and-the-rich-text-editor}

核心组件文本组件可利用AEM富文本编辑器(RTE)。 RTE为内容作者提供了多种用于编辑其文本内容的功能。 RTE的配置非常灵活，提供了多个选项。 有关如何配置RTE的更多详细信息，请参阅以下文章： [配置富文本编辑器](https://docs.adobe.com/content/help/zh-Hans/experience-manager-cloud-service/implementing/configuring-and-extending/rich-text-editor.html)和[配置富文本编辑器插件](https://docs.adobe.com/content/help/zh-Hans/experience-manager-cloud-service/implementing/configuring-and-extending/configure-rich-text-editor-plug-ins.html)。

本文的其余部分演示了使用现成RTE配置的核心组件文本组件的标准配置。

>[!NOTE]
>
>文本组件中仅提供由RTE](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/configuring-and-extending/configure-rich-text-editor-plug-ins.html)的UI配置启用的选项。[

## 编辑对话框 {#edit-dialog}

编辑对话框提供了用户期望撰写文本的标准富文本格式工具。

![文本组件的编辑对话框](/help/assets/text-edit.png)

### 粗体

![粗体图标](/help/assets/text-bold.png)

用于对所选文本应用粗体格式或在光标后大胆设置输入文本的格式。

**Ctrl+** B可用作键盘快捷键。

### 斜体

![斜体图标](/help/assets/text-italic.png)

用于将斜体格式应用于选定文本或在光标后输入的斜体文本。

**Ctrl+** Ican用作键盘快捷键。

### 下划线

![下划线图标](/help/assets/text-underline.png)

用于对光标后输入的选定文本或下划线文本应用下划线格式。

**Ctrl+** Ucan用作键盘快捷键。

### 下标

![下标图标](/help/assets/text-subscript.png)

用于将光标后输入的选定文本或文本格式化为下标。

### 上标

![上标图标](/help/assets/text-superscript.png)

用于将光标后输入的选定文本或文本格式化为上标。

### 粘贴文本

![“粘贴为文本”图标](/help/assets/text-paste-text.png)

将任何复制的文本粘贴为纯文本，而不使用任何格式。

选择此选项时，将打开一个窗口，在将文本插入文本之前，该窗口可以将文本作为纯文本进行粘贴，而不作为预览进行格式设置。 通过点按或单击复选标记接受，通过点按或单击x取消。

![粘贴为文本示例](/help/assets/text-paste-text-example.png)

### 从 Word 粘贴

![“从Word粘贴”图标](/help/assets/text-paste-word.png)

选择此选项时，将打开一个窗口，可在其中粘贴文本，并在将文本插入文本之前，将其格式保留为预览。 通过点按或单击复选标记接受，通过点按或单击x取消。

![从Word中粘贴示例](/help/assets/text-paste-word-example.png)

### 超链接

![超链接图标](/help/assets/text-hyperlink.png)

使用此选项可将所选文本转换为超链接或修改已定义的链接。 只有在已选择文本并打开一个窗口（其中包含用于设置链接的其他选项）时，此选项才处于活动状态。

![超链接示例](/help/assets/text-hyperlink-example.png)

* 输入路径
   * 使用打开选择对话框在AEM中选择路径
   * 如果链接不在AEM中，请输入绝对URL
      * 非绝对路径被解释为相对于AEM
* 为链接输入替代的描述性文本
* 选择链接行为
   * Target
   * 相同选项卡
   * 新选项卡
   * 父框架
   * 顶层框架

   点按或单击复选标记以应用链接，或点按x以取消。

### 取消链接

![取消链接图标](/help/assets/text-unlink.png)

使用此选项可删除已应用于所选文本的链接。 仅当已选择链接时，此选项才处于活动状态。

### 查找

![“查找”图标](/help/assets/text-find.png)

使用此选项可搜索文本，以查找指定文本字符串的出现情况。 选择此选项将打开一个用于指定搜索选项的窗口。

![查找示例](/help/assets/text-find-example.png)

输入要搜索的文本，然后点按或单击&#x200B;**查找**以开始搜索。 点按或单击x以取消。
如果您希望根据大小写进行精确匹配，请在开始搜索之前选择选项**Match Case**。
如果找到匹配项，则会突出显示该匹配项，并且搜索对话框变暗。 再次点按或单击灰显对话框中的**查找**&#x200B;按钮，以搜索下一个实例。

![查找找到的示例](/help/assets/text-find-example-found.png)

如果未找到其他发生次数，则将显示一条消息，并将从文本的开头重新开始搜索。

![查找示例，不再发生](/help/assets/text-find-example-found-end.png)

### 替换

![“替换”图标](/help/assets/text-replace.png)

使用此选项可搜索文本以查找指定文本字符串的出现次数，并将匹配项替换为其他字符串。 选择此选项将打开一个用于指定搜索和替换选项的窗口。

![替换示例](/help/assets/text-replace-example.png)

输入要搜索的文本以及应替换的文本。

* 点按或单击&#x200B;**查找**&#x200B;以开始搜索。 单击或点按x可取消。
* 如果您希望根据大小写进行精确匹配，请在开始搜索之前选择选项&#x200B;**Match Case**。
* 选择&#x200B;**全部替换**&#x200B;以一次替换所有出现的文本。

如果找到匹配项，则会突出显示该匹配项，并且搜索对话框变暗。 再次单击灰显对话框中的&#x200B;**查找**&#x200B;按钮以搜索下一个出现项，或选择&#x200B;**替换**&#x200B;按钮以替换高亮显示的匹配文本。 请注意，只有在进行匹配后，**Replace**&#x200B;按钮才处于活动状态。

单击“查找”(Find)后，“查找和替换”(Find and Replace)对话框将变得透明，单击“替换”(Replace)后，对话框将变得不透明。 这允许作者查看作者将替换的文本。

>[!NOTE]
>
>使用替换功能时，应当与查找字符串同时输入要替换的替换字符串。 但是，在替换字符串之前，您仍可以单击“查找”以搜索该字符串。 如果在单击“查找”后输入替换字符串，则搜索将重置为文本的开头。


### 左对齐文本

![左对齐图标](/help/assets/text-left.png)

用于将文本与左边距对齐。

### 居中对齐文本

![居中对齐文本图标](/help/assets/text-center.png)

用于将文本居中。

### 右对齐文本

![右对齐图标](/help/assets/text-right.png)

用于将文本与右边距对齐。

### Bullet

![项目符号图标](/help/assets/text-bullet.png)

用于将所选文本格式设置为项目符号列表或开始在光标后插入项目符号列表。

要结束项目符号列表，请再次点按或单击&#x200B;**项目符号**&#x200B;按钮，或输入两个回车符。

### 编号

![编号列表图标](/help/assets/text-numbered.png)

用于将所选文本格式化为编号列表，或在光标后开始插入编号列表。

要结束编号列表，请再次点按或单击&#x200B;**编号**&#x200B;按钮，或输入两个回车符。

### 突出

![“输出”图标](/help/assets/text-outdent.png)

用于降低在光标之后输入的选定文本或文本的缩进级别。

仅当光标的选定文本或位置已缩进时，才处于活动状态。

### 缩进

![缩进图标](/help/assets/text-outdent.png)

用于增加在光标之后输入的选定文本或文本的缩进级别。

### 表

![“表”图标](/help/assets/text-table.png)

用于在文本中插入表。 选择此选项将打开一个窗口，用于指定表的详细信息。

![表示例](/help/assets/text-table-example.png)

* **列**  — 表的列数（必需）
* **行**  — 表的行数（必需）
* **宽度**  — 表的宽度
* **高度**  — 表的高度
* **单元格内边距**  — 单元格内容周围的空格
* **单元格间距**  — 单元格之间的间距
* **边框**  — 表格边框线的粗细
   * 如果表标题为：
      * 应使用第一行
      * 应使用第一列
      * 应使用第一行和第一列
      * 或者不应使用标头。
* **题注**  — 表的题注

### 检查拼写

![检查拼写图标](/help/assets/text-spellcheck.png)

用于检查文本内容的拼写。 可能的拼写错误带有破折的红线下划线。

有关拼写检查和自定义拼写检查字典的更多详细信息，请参阅文档[配置富文本编辑器插件](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/configuring-and-extending/configure-rich-text-editor-plug-ins.html)。

### 特殊字符 {#special-characters}

![特殊字符图标](/help/assets/text-special-characters.png)

用于在文本中插入特殊字符。 选择此选项将打开一个显示可用字符的窗口。

![特殊字符示例](/help/assets/text-special-characters-example.png)

点按或单击所需的字符，以将其插入到光标后的文本中。 可插入多个字符。 点按或单击x以关闭选择窗口。

### 编辑源文件

![“源编辑”图标](/help/assets/text-source.png)

用于查看和修改文本的HTML源。

点按或单击&#x200B;**源编辑**&#x200B;图标，以更改格式化视图中的文本内容，以查看原始HTML。 在此模式下，所有其他格式选项都会被禁用。 再次点按或单击&#x200B;**源编辑**&#x200B;图标，以返回到带格式的视图。

>[!CAUTION]
>
>与访问原始HTML的情况一样，在使用&#x200B;**源编辑**&#x200B;选项时必须小心！
>
>通过&#x200B;**Source Edit**&#x200B;输入的HTML会扫描是否存在XSS风险，并且所有插入的脚本都会被删除，并且不会显示在生成的页面上。 但是，在&#x200B;**Source Edit**&#x200B;中输入的格式错误的HTML可能会破坏页面的模板，从而导致意外格式设置或导致生成的页面无法使用。

>[!NOTE]
>
>由于通过&#x200B;**Source Edit**&#x200B;输入的HTML会扫描XSS风险和任何脚本并自动删除发现的脚本，因此保留的实际内容可能与在&#x200B;**Source Edit**&#x200B;中输入的内容有所不同。 因此，要保存使用&#x200B;**源编辑**&#x200B;所做的更改，必须先退出&#x200B;**源编辑**，才能在普通编辑器中查看文本，然后再保存。

### 段落格式

![段落格式图标](/help/assets/text-paragraph.png)

用于将段落格式应用于所选文本或光标后插入的文本。 选择此选项将打开一个下拉列表，其中选择了段落格式。

![段落格式示例](/help/assets/text-paragraph-example.png)

### 内联编辑 {#in-line-editing}

文本组件也可以内嵌编辑，但由于空间限制，并非所有格式选项都可内嵌使用。 要查看所有选项，请切换到全屏模式。

![内嵌编辑示例](/help/assets/text-edit-inline-example.png)

### 设置和ID {#setting-id}

此选项允许控制HTML和[数据层](/help/developing/data-layer/overview.md)中组件的唯一标识符。

* 如果留为空白，则会自动为您生成唯一ID，并且可以通过检查生成的页面找到该ID。
* 如果指定了ID，则作者有责任确保该ID是唯一的。
* 更改ID可能会影响CSS、JS和数据层跟踪。

## “设计”对话框 {#design-dialog}

设计对话框允许模板作者定义内容作者可以使用的文本格式选项。

### “插件”选项卡 {#plugins-tab}

插件选项卡用于启用和禁用内容作者可用的各种文本格式选项。

### 功能 {#features}

![设计对话框功能](/help/assets/text-design-features.png)

可以为组件激活或停用以下功能。

* 粘贴纯文本
* 过去
* 查找和替换
* 拼写检查程序
* 插入的图像修改选项
* HTML源编辑

### 格式 {#formatting}

![设计对话框格式](/help/assets/text-design-formatting.png)

可以为组件激活或停用以下格式选项。

* 表
* 列表（项目符号、数字、缩进、缩进）
* 对齐方式（左对齐、右对齐、居中对齐）
* 粗体、斜体、下划线
* 链接（和取消链接）
* 子/上标

### 段落样式 {#paragraph-styles}

![设计对话框段落样式](/help/assets/text-design-paragraph.png)

可以为组件激活或停用段落样式。 激活后，可定义允许的格式。

* 点按或单击&#x200B;**Add**&#x200B;按钮以插入新样式。
* 输入样式的代码以及将在编辑对话框中显示的描述。
* 要删除样式，请点按或单击&#x200B;**删除**&#x200B;按钮。
* 要重新排列格式的顺序，请点按或单击并拖动控制滑块。

### 特殊字符 {#configuring-special-characters}

![设计对话框特殊字符](/help/assets/text-design-special-characters.png)

可以为组件激活或停用用于插入特殊字符的选项。 激活后，可以定义允许使用的字符。

* 点按或单击&#x200B;**添加**&#x200B;按钮以插入新字符。
* 输入字符的HTML代码以及将在编辑对话框中显示的描述。
* 要删除字符，请点按或单击&#x200B;**删除**&#x200B;按钮。
* 要重新排列字符的顺序，请点按或单击并拖动手柄。

## “样式”选项卡 {#styles-tab}

文本组件支持AEM [样式系统](/help/get-started/authoring.md#component-styling)。

## Adobe客户端数据层 {#data-layer}

文本组件支持[Adobe客户端数据层。](/help/developing/data-layer/overview.md)
