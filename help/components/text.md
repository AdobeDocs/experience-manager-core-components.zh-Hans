---
title: 文本组件
description: 文本组件是一个富文本编辑和合成组件，可进行就地编辑。
translation-type: tm+mt
source-git-commit: 4813748bcfa83ce7c73e81d4e4d445ecc8215d26
workflow-type: tm+mt
source-wordcount: '2200'
ht-degree: 3%

---


# 文本组件{#text-component}

核心组件文本组件是一个富文本编辑和合成组件，可进行就地编辑。

## 使用 {#usage}

文本组件优惠了强大的富文本编辑器，它允许通过简化的内嵌编辑器以及全屏格式轻松编辑文本。

“编 [辑”对话框](#edit-dialog) ，以有限的选项进行联机编辑，并且全屏编辑对话框中提供了完整功能。 使用设 [计对话框](#design-dialog)，可以为内容作者的模板配置文本格式选项，如标题、特殊字符和段落样式。

## 版本和兼容性 {#version-and-compatibility}

文本组件的当前版本为v2,2018年1月在核心组件的2.0.0版中引入了v2，本文档中对此进行了说明。

下表详细列出了组件的所有受支持版本、与组件版本兼容的AEM版本以及指向先前版本文档的链接。

| 组件版本 | AEM 6.4 | AEM 6.5 | AEM 云服务 |
|---|---|---|---|
| v2 | 兼容 | 兼容 | 兼容 |
| [v1](v1/text-v1.md) | 兼容 | 兼容 | - |

有关核心组件版本和版本的详细信息，请参阅文档 [核心组件版本](/help/versions.md)。

## 示例组件输出 {#sample-component-output}

要体验文本组件以及其配置选项以及HTML和JSON输出的示例，请访问组 [件库](https://adobe.com/go/aem_cmp_library_text)。

### 技术详细信息 {#technical-details}

有关文本组件的最新技 [术文档，请访问GitHub](https://adobe.com/go/aem_cmp_tech_text_v2)。

有关开发核心组件的更多详细信息，请参阅核 [心组件开发人员文档](/help/developing/overview.md)。

## 文本组件和富文本编辑器 {#the-text-component-and-the-rich-text-editor}

核心组件文本组件利用AEM富文本编辑器(RTE)。 RTE为内容作者提供了各种用于编辑其文本内容的功能。 RTE的配置非常灵活，并优惠了许多选项。 有关如何配置RTE的更多详细信息，请参阅 [配置富文本编辑器](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/configuring-and-extending/rich-text-editor.html)[和配置富文本编辑器插件](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/configuring-and-extending/configure-rich-text-editor-plug-ins.html)。

本文的其余部分演示了使用现成RTE配置的核心组件文本组件的标准配置。

>[!NOTE]
>
>文本组件中 [仅提供由RTE的UI](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/configuring-and-extending/configure-rich-text-editor-plug-ins.html) 配置启用的选项。

## Edit Dialog {#edit-dialog}

编辑对话框优惠用户希望合成文本的标准富文本格式工具。

![文本组件的编辑对话框](/help/assets/text-edit.png)

### 粗体

![粗体图标](/help/assets/text-bold.png)

用于对选定文本应用粗体格式或大胆设置光标后输入的文本格式。

**Ctrl+B** 可用作键盘快捷键。

### 斜体

![斜体图标](/help/assets/text-italic.png)

用于将斜体格式应用于选定文本或在光标后输入的斜体文本。

**Ctrl+I** 可用作键盘快捷键。

### 下划线

![下划线图标](/help/assets/text-underline.png)

用于将带下划线的格式应用于在光标后输入的选定文本或下划线文本。

**Ctrl+U** 可用作键盘快捷键。

### 下标

![下标图标](/help/assets/text-subscript.png)

用于将光标后输入的选定文本或文本格式化为下标。

### 上标

![上标图标](/help/assets/text-superscript.png)

用于将光标后输入的选定文本或文本格式化为上标。

### 粘贴文本

![粘贴为文本图标](/help/assets/text-paste-text.png)

将任何复制的文本粘贴为纯文本，而不使用任何格式。

选择此选项时，将打开一个窗口，在该窗口中，文本可以粘贴为纯文本，且在插入文本之前没有预览。 点按或单击复选标记以接受，点按或单击x以取消。

![粘贴为文本示例](/help/assets/text-paste-text-example.png)

### 从 Word 粘贴

![从Word粘贴图标](/help/assets/text-paste-word.png)

选择此选项时，将打开一个窗口，在将文本插入文本之前，该窗口将保持其格式预览。 点按或单击复选标记以接受，点按或单击x以取消。

![从Word中粘贴示例](/help/assets/text-paste-word-example.png)

### 超链接

![超链接图标](/help/assets/text-hyperlink.png)

使用此选项可将选定文本转换为超链接或修改已定义的链接。 仅当已选择文本并打开一个包含设置链接的其他选项的窗口时，此选项才处于活动状态。

![超链接示例](/help/assets/text-hyperlink-example.png)

* 输入路径
   * 使用“打开选择”对话框在AEM中选择路径
   * 如果链接不在AEM中，请输入绝对URL
      * 非绝对路径被解释为相对于AEM的相对路径
* 输入链接的替代描述性文本
* 选择链接行为
   * 目标
   * 相同选项卡
   * 新选项卡
   * 父框架
   * 顶层框架

   点按或单击复选标记以应用链接，或点按x以取消。

### 取消链接

![取消链接图标](/help/assets/text-unlink.png)

使用此选项可删除已应用于所选文本的链接。 仅当已选择链接时，此选项才处于活动状态。

### 查找

![查找图标](/help/assets/text-find.png)

使用此选项可搜索文本以查找指定文本字符串的匹配项。 选择此选项将打开一个窗口，用于指定搜索选项。

![查找示例](/help/assets/text-find-example.png)

输入要搜索的文本并点按，或单击“查 **找** ”开始搜索。 点按或单击x可取消。
如果要根据大小写进行精确匹配，请在开始搜索 **之前选择** “匹配大小写”选项。
如果找到匹配项，则突出显示该匹配项，并且搜索对话框灰显。 再次点按或单 **击灰显** 对话框中的“查找”按钮，以搜索下一个匹配项。

![找到示例](/help/assets/text-find-example-found.png)

如果未找到其他匹配项，则将显示一条消息，并从文本的开头开始搜索。

![查找示例，不再出现](/help/assets/text-find-example-found-end.png)

### 替换

![替换图标](/help/assets/text-replace.png)

使用此选项可搜索出现指定文本字符串的文本，并将匹配项替换为其他字符串。 选择此选项将打开一个窗口，用于指定搜索和替换选项。

![替换示例](/help/assets/text-replace-example.png)

输入要搜索的文本以及应替换的文本。

* 点按或单 **击查** 找以开始搜索。 单击或点按x可取消。
* 如果要根据大小写进行精确匹配，请在开始搜索 **之前选择** “匹配大小写”选项。
* 选 **择“全部替** 换”以一次替换所有出现的文本。

如果找到匹配项，则突出显示该匹配项，并且搜索对话框灰显。 再次单 **击灰** 显对话框中的“查找”按钮以搜索下一个匹配项，或选择“替 **换** ”按钮以替换突出显示的匹配文本。 请注意，只 **有匹配** 后，“替换”按钮才处于活动状态。

单击“查找并替换”对话框时，该对话框变得透明，单击“替换”时变得不透明。 这允许作者查看作者将替换的文本。

>[!NOTE]
>
>使用替换功能时，应与查找字符串同时输入要替换的替换字符串。 但是，在替换字符串之前，您仍可以单击“查找”以搜索该字符串。 如果在单击“查找”后输入替换字符串，则搜索将重置为文本的开头。


### 左对齐文本

![左对齐图标](/help/assets/text-left.png)

用于将文本与左边距对齐。

### 居中对齐文本

![居中文本图标](/help/assets/text-center.png)

用于将文本居中。

### 右对齐文本

![右对齐图标](/help/assets/text-right.png)

用于将文本与右边距对齐。

### Bullet

![项目符号图标](/help/assets/text-bullet.png)

用于将选定文本格式化为项目符号列表，或在光标后开始插入项目符号列表。

要结束项目符号列表，请再次点按或单 **击** “项目符号”按钮，或输入两个回车。

### 编号

![编号列表图标](/help/assets/text-numbered.png)

用于将选定文本格式化为编号列表，或在光标后开始插入编号列表。

要结束编号列表，请再次点按或单 **击** “编号”按钮，或输入两个回车。

### 突出

![输出图标](/help/assets/text-outdent.png)

用于降低在光标后输入的选定文本或文本的缩进级别。

仅当光标的选定文本或位置已缩进时才处于活动状态。

### 缩进

![缩进图标](/help/assets/text-outdent.png)

用于增加在光标后输入的选定文本或文本的缩进级别。

### 表

![表图标](/help/assets/text-table.png)

用于在文本中插入表。 选择此选项将打开一个窗口，用于指定表的详细信息。

![表示例](/help/assets/text-table-example.png)

* **列** -表的列数（必需）
* **行** -表的行数（必需）
* **宽度** -表的宽度
* **高度** -表的高度
* **单元格边距** -单元格内容周围的空格
* **单元格间距** -单元格之间的间距
* **边框** -表边框线的权重
   * 如果表的标题：
      * 应使用第一行
      * 应使用第一列
      * 应使用第一行和第一列
      * 或者不应使用标题。
* **Caption** —— 表的标题

### 拼写检查

![检查拼写图标](/help/assets/text-spellcheck.png)

用于检查文本内容的拼写。 可能的拼写错误用破红线加下划线。

有关拼写检查和自定义拼写检查字典的更多详细信息，请参 [阅文档配置富文本编辑器插件](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/configuring-and-extending/configure-rich-text-editor-plug-ins.html)。

### 特殊字符 {#special-characters}

![特殊字符图标](/help/assets/text-special-characters.png)

用于在文本中插入特殊字符。 选择此选项将打开一个窗口，其中显示可用字符。

![特殊字符示例](/help/assets/text-special-characters-example.png)

点按或单击所需字符，将其插入光标后的文本中。 可插入多个字符。 点按或单击x以关闭选择窗口。

### 编辑源文件

![源编辑图标](/help/assets/text-source.png)

用于视图和修改文本的HTML源。

点按或单击 **源编辑** 图标，以将文本的内容从格式化视图更改为视图原始HTML。 在此模式下，所有其他格式选项都被禁用。 再次点按或单 **击源编辑** 图标以返回已设置格式的视图。

>[!CAUTION]
>
>与访问原始HTML时一样，在使用“源编辑”选项时 **必须小心** !
>
>通过源编 **辑输入** 的HTML将扫描XSS风险，并删除所插入的任何脚本，且不会显示在生成的页面上。 但是，在源代码编辑中输 **入的格** 式错误的HTML可能会中断页面的模板，导致意外的格式或导致生成的页面无法使用。

>[!NOTE]
>
>由于通过源编 **辑输入的** HTML会扫描XSS风险和任何脚本并自动删除找到的脚本，因此保留的实际内容可能与在源编辑中输入的内容 **不同**。 因此，要保存使用源代码编辑所做 **的更改**，必须先退出源代码 **** 编辑，以在普通编辑器中视图文本，然后再进行保存。

### 段落格式

![段落格式图标](/help/assets/text-paragraph.png)

用于将段落格式应用于选定文本或光标后插入的文本。 选择此选项将打开一个下拉框，从中选择段落格式。

![段落格式示例](/help/assets/text-paragraph-example.png)

### 联机编辑 {#in-line-editing}

文本组件也可以联机进行编辑，但由于空间限制，并非所有格式选项都联机可用。 要查看所有选项，请切换到全屏模式。

![联机编辑示例](/help/assets/text-edit-inline-example.png)

### 设置和ID {#setting-id}

此选项允许控制HTML和数据层中组件的唯一标 [识符](/help/developing/data-layer/overview.md)。

* 如果留空，则会自动为您生成唯一ID，并可通过检查生成的页面找到该ID。
* 如果指定了ID，则作者有责任确保它是唯一的。
* 更改ID可能会影响CSS、JS和数据层跟踪。

## 设计对话框 {#design-dialog}

设计对话框允许模板作者定义内容作者可以使用的文本格式选项。

### 插件选项卡 {#plugins-tab}

插件选项卡用于启用和禁用内容作者可用的各种文本格式选项。

### 功能 {#features}

![设计对话框功能](/help/assets/text-design-features.png)

可以为组件激活或取消激活以下功能。

* 粘贴纯文本
* 过去自词
* 查找和替换
* 拼写检查器
* 插入的图像修改选项
* HTML源编辑

### 格式化 {#formatting}

![设计对话框格式](/help/assets/text-design-formatting.png)

可以为组件激活或取消激活以下格式选项。

* 表
* 列表（项目符号、数字、缩进、凸出）
* 对齐（左对齐、右对齐、居中对齐）
* 粗体、斜体、下划线
* 链接（和取消链接）
* 子／上标

### 段落样式 {#paragraph-styles}

![设计对话框段落样式](/help/assets/text-design-paragraph.png)

可以为组件激活或取消激活段落样式。 激活后，可以定义允许的格式。

* 点按或单击 **添加** 按钮以插入新样式。
* 输入样式的代码以及将在编辑对话框中显示的说明。
* 要删除样式点按或单击“删 **除** ”按钮。
* 要重新排列格式的顺序，请点按或单击并拖动手柄。

### 特殊字符 {#configuring-special-characters}

![设计对话框特殊字符](/help/assets/text-design-special-characters.png)

可以为组件激活或取消激活插入特殊字符的选项。 激活后，可以定义允许的字符。

* 点按或单击添 **加按** 钮以插入新字符。
* 输入字符的HTML代码和将在编辑对话框中显示的说明。
* 要删除字符点按或单击“删 **除** ”按钮。
* 要重新排列字符的点按顺序，请单击或拖动手柄。

## 样式选项卡 {#styles-tab}

文本组件支持AEM样 [式系统](/help/get-started/authoring.md#component-styling)。
