---
title: 文本组件
seo-title: 文本组件
description: 文本组件是一种丰富的文本编辑和构图组件，可进行就地编辑。
seo-description: 文本组件是一种丰富的文本编辑和构图组件，可进行就地编辑。
uuid: 5f8eee8f-7317-4712-a77 f-e34 e024187
contentOwner: 用户
content-type: 引用
topic-tags: 核心组件
discoiquuid: 9a290584-565e-4392-999c-999ee4a93da1
translation-type: tm+mt
source-git-commit: eef608fb06001485aa2c2c0b574af412ed7f15a4

---


# 文本组件{#text-component}

核心组件文本组件是一种丰富的文本编辑和构图组件，可进行就地编辑。

## 使用情况 {#usage}

文本组件提供了强大的富文本编辑器，它允许以简化的线内编辑器以及全屏格式轻松编辑文本。

[编辑对话框](#edit-dialog) 具有有限的选项，可在全屏编辑对话框中提供具有完整功能的有限选项。Using the [design dialog](#design-dialog), text formatting options such as headings, special characters, and paragraph styles can be configured for the template for the content author.

## Version and Compatibility {#version-and-compatibility}

文本组件的当前版本是v2，它是在2018年月核心组件发行版中引入的，它在本文档中进行了介绍。

下表详细说明了组件的所有支持版本、组件版本的AEM版本以及以前版本的文档链接。

| 组件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|---|---|---|---|
| v2 | 兼容 | 兼容 | 兼容 |
| [v1](text-v1.md) | 兼容 | 兼容 | 兼容 |

For more information about Core Component versions and releases, see the document [Core Components Versions](versions.md).

## Sample Component Output {#sample-component-output}

To experience the Text Component as well as see examples of its configuration options as well as HTML and JSON output, visit the [Component Library](http://opensource.adobe.com/aem-core-wcm-components/library/text.html).

### Technical Details {#technical-details}

The latest technical documentation about the Text Component [can be found on GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/text/v2/text).

Further details about developing Core Components can be found in the [Core Components developer documentation](developing.md).

## The Text Component and the Rich Text Editor {#the-text-component-and-the-rich-text-editor}

核心组件文本组件利用AEM富文本编辑器(RTE)。RTE为内容作者提供了各种功能，用于编辑其文本内容。RTE在其配置中非常灵活，并提供许多选项。Further details about how the RTE can be configured can be found in the articles [Configure the Rich Text Editor](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/rich-text-editor.html) and [Configure the Rich Text Editor plug-ins](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/configure-rich-text-editor-plug-ins.html).

本文的其余部分演示了核心组件文本组件与现成RTE配置的标准配置。

>[!NOTE]
>
>Only options enabled by [UI configurations of the RTE](https://chl-author-preview.corp.adobe.com/content/help/en/experience-manager/6-5/sites/administering/using/rich-text-editor.html) are available by in the Text Component.

## Edit Dialog {#edit-dialog}

编辑对话框提供用户期望撰写文本的标准富文本格式设置工具。

![](assets/screen_shot_2018-01-11at143025.png)

### 粗体

![](assets/screen_shot_2018-01-11at125602.png)

用于将粗体格式应用于选定文本，或粗体格式(在光标之后输入)。

**Ctrl+ B** 可用作键盘快捷键。

### 斜体

![](assets/screen_shot_2018-01-11at125609.png)

用于将斜体格式应用于选定文本，或斜体文本(在光标之后输入)。

**Ctrl+ I** 可用作键盘快捷键。

### 下划线

![](assets/screen_shot_2018-01-11at125615.png)

用于对选定文本应用带下划线的格式或在光标之后输入下划线文本。

**Ctrl+ U** 可用作键盘快捷键。

### 下标

![](assets/screen_shot_2018-01-11at125703.png)

用于设置在光标之后输入的选定文本或文本的格式。

### 上标

![](assets/screen_shot_2018-01-11at125708.png)

用于将选定文本或在光标之后输入的文本设置为上标。

### 粘贴文本

![](assets/screen_shot_2018-01-11at125713.png)

将任何复制的文本粘贴为纯文本，而无需任何格式。

选择此选项时，将打开一个窗口，在该窗口中，文本可以作为纯文本粘贴，而不会作为预览插入到文本中。通过点按或单击复选标记接受，通过点按或单击x取消。

![](assets/screen_shot_2018-01-11at143234.png)

### 从 Word 粘贴

![](assets/screen_shot_2018-01-11at125717.png)

选择此选项时，将打开一个窗口，在该窗口中可以在将文本插入文本之前将其格式保留为预览。通过点按或单击复选标记接受，通过点按或单击x取消。

![](assets/screen_shot_2018-01-11at143250.png)

### 超链接

![](assets/screen_shot_2018-01-11at125839.png)

使用此选项可将选定文本转换为超链接或修改已定义的链接。此选项仅在已选择文本时处于活动状态，并且打开了一个窗口，其中包含用于设置链接的其他选项。

![](assets/screen_shot_2018-01-11at130003.png)

* 输入位置
   * 使用打开选择对话框在AEM中选择路径
   * 如果链接不在AEM内，请输入绝对URL(非绝对路径将解释为相对于AEM)
* 为链接输入替代描述性文本
* 选择链接行为
   * 目标
   * 相同选项卡
   * 新选项卡
   * 父框架
   * 顶层框架
   点按或单击复选标记以应用链接或x以取消。

### 取消链接

![](assets/screen_shot_2018-01-11at125901.png)

使用此选项可删除已应用于选定文本的链接。仅当已选择链接时，此选项才处于活动状态。

### 查找

![](assets/screen_shot_2018-01-11at125906.png)

使用此选项可搜索文本以匹配指定文本字符串。选择此选项将打开一个窗口，用于指定搜索选项。

![](assets/screen_shot_2018-01-11at130107.png)

Enter the text for which you want to search and tap or click **Find** to begin the search. 点按或单击x以取消。
If you wish to do an exact match according to the case, select the option **Match Case** before starting the search.
如果找到匹配项，则突出显示，搜索对话框将灰显。Tap or click the **Find** button again in the dimmed dialog to search for the next occurrence.

![](assets/screen_shot_2018-01-11at130145.png)

如果未找到其他实例，则会显示一条消息，并且搜索将从文本开始开始。

![](assets/screen_shot_2018-01-11at130241.png)

### 替换

![](assets/screen_shot_2018-01-11at125910.png)

使用此选项可搜索指定文本字符串的实例，并用其他字符串替换匹配项。选择此选项将打开一个窗口，用于指定搜索和替换选项。

![](assets/screen_shot_2018-01-11at130441.png)

输入要搜索的文本以及应替换的文本。

Tap or click **Find** to begin the search. 单击或点按x以取消。

If you wish to do an exact match according to the case, select the option **Match Case** before starting the search.

如果找到匹配项，则突出显示，搜索对话框将灰显。Click the **Find** button again in the dimmed dialog to search for the next occurrence or select the **Replace** button to replace the highlighted, matched text. Note that the **Replace** button is only active once a match is made.

Select **Replace all** to replace all occurrences of the text at once.

### 左对齐文本

![](assets/screen_shot_2018-01-11at142012.png)

用于将文本对齐到左边距。

### 居中对齐文本

![](assets/screen_shot_2018-01-11at142017.png)

用于居中对齐文本。

### 右对齐文本

![](assets/screen_shot_2018-01-11at142021.png)

用于将文本对齐到右边距。

### Bullet

![](assets/screen_shot_2018-01-11at142025.png)

用于将选定文本格式化为项目符号列表，或开始在光标之后插入项目符号列表。

To end a bulleted list, tap or click the **Bullet** button again or enter two carriage returns.

### 编号

![](assets/screen_shot_2018-01-11at142030.png)

用于将选定文本格式化为编号列表，或开始在光标之后插入编号列表。

To end a numbered list, tap or click the **Numbered** button again or enter two carriage returns.

### 突出

![](assets/screen_shot_2018-01-11at141917.png)

用于减小选定文本的缩进级别或光标之后输入的文本。

仅处于活动状态，如果光标的选定文本或位置已缩进。

### 缩进

![](assets/screen_shot_2018-01-11at141922.png)

用于增加选定文本的缩进级别或光标之后输入的文本。

### 表

![](assets/screen_shot_2018-01-11at141928.png)

用于在文本中插入表。选择此选项将打开一个窗口，用于指定表的详细信息。

![](assets/screen_shot_2018-01-11at142405.png)

* **列** 表的列数(必需)
* **行** 表的行数(必需)
* **宽度** 表的宽度
* **高度** 表的高度
* **单元格填充** 单元格内容周围的空间
* **单元格间距** 单元格之间的间距
* **边框** 表边框的粗细
* 如果表标题为：
   * 应使用第一行
   * 应使用第一列
   * 应使用第一行和第一列
   * 或者不应使用标题。
* **题注** 的题注

### 拼写检查

![](assets/screen_shot_2018-01-11at141935.png)

用于检查文本内容的拼写。可能的拼写错误带有断开的红色线条。

Further details about spell checking and customizing spell check dictionaries can be found in the document [Configure the Rich Text Editor Plug-Ins](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/configure-rich-text-editor-plug-ins.html).

### 特殊字符 {#special-characters}

![](assets/screen_shot_2018-01-11at142600.png)

用于在文本中插入特殊字符。选择此选项将打开显示可用字符的窗口。

![](assets/screen_shot_2018-01-11at142635.png)

点按或单击所需的字符，将其插入光标之后的文本。可以插入多个字符。点按或单击x以关闭选择窗口。

### 编辑源文件

![](assets/screen_shot_2018-01-11at142746.png)

用于查看和修改文本的HTML源。

Tap or click the **Source Edit** icon to change the content of the text from the formatted view to view the raw HTML. 在此模式中，将禁用所有其他格式选项。Tap or click the **Source Edit** icon again to return to the formatted view.

>[!CAUTION]
>
>As always the case with access to raw HTML, care must be exercised when using the **Source Edit** option!
>
>HTML entered via **Source Edit** is scanned for XSS risks and any scripts that are inserted are removed and will not appear on the resulting page. However malformed HTML entered in **Source Edit** can break the template for the page resulting in unexpected formatting or rendering the resulting page unusable.

>[!NOTE]
>
>Because HTML entered via **Source Edit** is scanned for XSS risks and any scripts and automatically removes those found, the actual content persisted may vary from what was entered in **Source Edit**. For this reason, in order to save changes made using **Source Edit**, you must first exit **Source Edit** to view the text in the normal editor before saving.

### 段落格式

![](assets/screen_shot_2018-01-11at142752.png)

用于将段落格式应用于选定文本或光标之后插入的文本。选择此选项将打开一个从中选择段落格式的下拉菜单。

![](assets/screen_shot_2018-01-11at142828.png)

文本组件也可以进行内嵌编辑，但由于空间restraints，并非所有格式选项都可用。要查看所有选项，请切换到全屏模式。

![](assets/screen_shot_2018-01-11at142921.png)

## Design Dialog {#design-dialog}

设计对话框允许模板作者定义内容作者可用的文本格式选项。

### Plugins Tab {#plugins-tab}

插件选项卡用于启用和禁用内容作者可用的各种文本格式选项。

### 功能 {#features}

![](assets/chlimage_1-28.png)

可以为组件激活或取消激活下列功能。

* 粘贴纯文本
* 过去的语言
* 查找和替换
* 拼写检查器
* 源编辑

### 格式化 {#formatting}

![](assets/chlimage_1-29.png)

可以为组件激活或取消激活以下格式选项。

* 表
* 列表
* 对齐
* 粗体、斜体、下划线
* 链接
* 子/上标

### 段落样式 {#paragraph-styles}

![](assets/chlimage_1-30.png)

可以为组件激活或取消激活段落样式。激活后，可以定义允许的格式。

* Tap or click the **Add** button to insert a new style.
* 输入样式的代码和将在编辑对话框中显示的描述。
* To remove a style tap or click the **Delete** button.
* 要重新排列格式的顺序，请点按或单击并拖动手柄。

### Configuring Special Characters {#configuring-special-characters}

![](assets/chlimage_1-31.png)

可以为组件激活或取消激活插入特殊字符的选项。激活后，可定义允许的字符。

* Tap or click the **Add** button to insert a new character.
* 输入字符的HTML代码和将在编辑对话框中显示的描述。
* To remove a character tap or click the **Delete** button.
* 要重新排列字符的顺序，请点按或单击并拖动手柄。

## Styles Tab {#styles-tab}

The Text Component supports the AEM [style system](authoring.md#component-styling).