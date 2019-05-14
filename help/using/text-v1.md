---
title: 文本组件(v1)
seo-title: 文本组件(v1)
description: 'null'
seo-description: 文本组件是一种丰富的文本编辑和构图组件，可进行就地编辑。
uuid: b787ebac-fa85-416a-b96 b-9d2 ee85428 ec
content-type: 引用
products: SG_ EXPERIENCE MANAGER/CORECOMMPANES-new
discoiquuid: d5e37dc7-dfd4-4a44-89b6-c15651472 c43
disttype: dist5
gnavtheme: 浅色
groupsectionnavitems: 否
hidemerchandisingbar: 继承
hidepromocomponent: 继承
modalsize: 426 x 240
noindex: 'true'
index: n
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4e74f10e2a4119484a597178dc4577b399833dbf

---


# 文本组件(v1){#text-component-v}

文本组件是一种丰富的文本编辑和构图组件，可进行就地编辑。

## 使用情况 {#usage}

文本组件提供了强大的富文本编辑器，它允许以简化的线内编辑器以及全屏格式轻松编辑文本。

[编辑对话框](text-v1.md#main-pars_title) 具有有限的选项，可在全屏编辑对话框中提供具有完整功能的有限选项。使用 [设计对话框](text-v1.md#main-pars_title_1995166862)，可以为内容作者的模板配置标题、特殊字符和段落样式等文本格式选项。

## 版本和兼容性 {#version-and-compatibility}

本文档描述了文本组件的v1，该组件最初随AEM6.3的核心组件版本1.0.0一起引入。

下表列出了文本组件的v1的兼容性。

| AEM 版本 | 文本组件v1 |
|--- |--- |
| 6.3 | 兼容 |
| 6.4 | 兼容 |

>[!CAUTION]
>
>本文档描述了文本组件的v1。
>
>有关文本组件当前版本的详细信息，请参阅 [文本组件](text.md) 文档。

## 示例组件输出 {#sample-component-output}

以下示例取自 [We. Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)。

### 屏幕快照 {#screenshot}

![](assets/chlimage_1-27.png)

### HTML {#html}

```
<div class="cmp cmp-text aem-GridColumn aem-GridColumn--default--12">
<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer porttitor ante a tortor volutpat maximus. Donec eu porta eros. Aenean sit amet eleifend arcu, eu vestibulum magna. Fusce eget nisi tincidunt, tristique felis quis, tincidunt est. Aliquam consequat aliquam quam non eleifend. Phasellus ut magna luctus, aliquam risus eget, fermentum augue. Aliquam lobortis accumsan magna, quis efficitur enim dictum eu. Pellentesque iaculis felis eget felis commodo, non euismod dolor euismod. Quisque nec arcu rutrum, mollis tortor non, sollicitudin odio. Sed dictum nulla mauris, eu pretium dui vulputate a. Maecenas lacus massa, egestas vitae tincidunt eu, interdum et magna. Lorem ipsum dolor sit amet, consectetur adipiscing elit. In eleifend ex lacus, in consectetur nunc interdum et. Donec interdum mi vitae dolor pretium mattis. In quis arcu sapien. Phasellus at metus vitae nisi tincidunt varius.<br />
</p>
</div>
```

### JSON {#json}

```
"text": {
              "columnClassNames": "aem-GridColumn aem-GridColumn--default--12",
              "text": "<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer porttitor ante a tortor volutpat maximus. Donec eu porta eros. Aenean sit amet eleifend arcu, eu vestibulum magna. Fusce eget nisi tincidunt, tristique felis quis, tincidunt est. Aliquam consequat aliquam quam non eleifend. Phasellus ut magna luctus, aliquam risus eget, fermentum augue. Aliquam lobortis accumsan magna, quis efficitur enim dictum eu. Pellentesque iaculis felis eget felis commodo, non euismod dolor euismod. Quisque nec arcu rutrum, mollis tortor non, sollicitudin odio. Sed dictum nulla mauris, eu pretium dui vulputate a. Maecenas lacus massa, egestas vitae tincidunt eu, interdum et magna. Lorem ipsum dolor sit amet, consectetur adipiscing elit. In eleifend ex lacus, in consectetur nunc interdum et. Donec interdum mi vitae dolor pretium mattis. In quis arcu sapien. Phasellus at metus vitae nisi tincidunt varius.</p>\n",
              "richText": true,
              ":type": "weretail/components/content/text"
            }
```

>[!NOTE]
>
>核心组件中的JSON导出需要核心组件版本1.1.0。有关更多信息，请参见核心组件v [](versions.md#main-pars_title_236368006) 的兼容性信息。

## 编辑对话框 {#edit-dialog}

编辑对话框提供用户期望撰写文本的标准富文本格式设置工具。

![](assets/chlimage_1-52.png)

* 粗体

   ![](assets/chlimage_1-53.png)

   用于将粗体格式应用于选定文本，或粗体格式(在光标之后输入)。

   **Ctrl+ B** 可用作键盘快捷键。

* 斜体

   ![](assets/chlimage_1-54.png)

   用于将斜体格式应用于选定文本，或斜体文本(在光标之后输入)。

   **Ctrl+ I** 可用作键盘快捷键。

* 下划线

   ![](assets/chlimage_1-55.png)

   用于对选定文本应用带下划线的格式或在光标之后输入下划线文本。

   **Ctrl+ U** 可用作键盘快捷键。

* 下标

   ![](assets/chlimage_1-56.png)

   用于设置在光标之后输入的选定文本或文本的格式。

* 上标

   ![](assets/chlimage_1-57.png)

   用于将选定文本或在光标之后输入的文本设置为上标。

* 粘贴文本

   ![](assets/chlimage_1-58.png)

   将任何复制的文本粘贴为纯文本，而无需任何格式。

   选择此选项时，将打开一个窗口，在该窗口中，文本可以作为纯文本粘贴，而不会作为预览插入到文本中。通过点按或单击复选标记接受，通过点按或单击x取消。

   ![](assets/chlimage_1-59.png)

* 从 Word 粘贴

   ![](assets/chlimage_1-60.png)

   选择此选项时，将打开一个窗口，在该窗口中可以在将文本插入文本之前将其格式保留为预览。通过点按或单击复选标记接受，通过点按或单击x取消。

   ![](assets/chlimage_1-61.png)

* 超链接

   ![](assets/chlimage_1-62.png)

   使用此选项可将选定文本转换为超链接或修改已定义的链接。此选项仅在已选择文本时处于活动状态，并且打开了一个窗口，其中包含用于设置链接的其他选项。

   ![](assets/chlimage_1-63.png)

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

* 取消链接

   ![](assets/chlimage_1-64.png)

   使用此选项可删除已应用于选定文本的链接。仅当已选择链接时，此选项才处于活动状态。

* 查找

   ![](assets/chlimage_1-65.png)

   使用此选项可搜索指定文本字符串的实例。选择此选项将打开一个窗口，用于指定搜索选项。

   ![](assets/chlimage_1-66.png)

   输入要搜索的文本，然后点按或单击 **查找** 以开始搜索。点按或单击x以取消。

   如果要根据具体情况进行精确匹配，请在开始搜索之前选择 **“匹配大小写** ”选项。

   如果找到匹配项，则突出显示，搜索对话框将灰显。在灰显对话框中再次点按或单击 **“查找”** 按钮以搜索下一个匹配项。

   ![](assets/chlimage_1-67.png)

   如果未找到其他实例，则会显示一条消息，并且搜索将从文本开始开始。

   ![](assets/chlimage_1-68.png)

* 替换

   ![](assets/chlimage_1-69.png)

   使用此选项可搜索指定文本字符串的实例，并用其他字符串替换匹配项。选择此选项将打开一个窗口，用于指定搜索和替换选项。

   ![](assets/chlimage_1-70.png)

   输入要搜索的文本以及应替换的文本。

   点按或单击 **查找** 以开始搜索。单击或点按x以取消。

   如果要根据具体情况进行精确匹配，请在开始搜索之前选择 **“匹配大小写** ”选项。

   如果找到匹配项，则突出显示，搜索对话框将灰显。再次单击灰显对话框中的 **“查找”** 按钮可搜索下一个匹配项，或选择 **替换** 按钮以替换突出显示的、匹配的文本。请注意 **，只有在完成匹配后，“替换** ”按钮才处于活动状态。

   选择 **全部替换** 以一次性替换文本的所有实例。

* 左对齐文本

   ![](assets/chlimage_1-71.png)

   用于将文本对齐到左边距。

* 居中对齐文本

   ![](assets/chlimage_1-72.png)

   用于居中对齐文本。

* 右对齐文本

   ![](assets/chlimage_1-73.png)

   用于将文本对齐到右边距。

* Bullet

   ![](assets/chlimage_1-74.png)

   用于将选定文本格式化为项目符号列表，或开始在光标之后插入项目符号列表。

   要结束项目符号列表，请再次点按或单击 **“项目符号** ”按钮，或输入两个回车符。

* 编号

   ![](assets/chlimage_1-75.png)

   用于将选定文本格式化为编号列表，或开始在光标之后插入编号列表。

   要结束编号列表，请再次点按或单击 **“已编号** ”按钮或输入两个回车符。

* 突出

   ![](assets/chlimage_1-76.png)

   用于减小选定文本的缩进级别或光标之后输入的文本。

   仅处于活动状态，如果光标的选定文本或位置已缩进。

* 缩进

   ![](assets/chlimage_1-77.png)

   用于增加选定文本的缩进级别或光标之后输入的文本。

* 表

   ![](assets/chlimage_1-78.png)

   用于在文本中插入表。选择此选项将打开一个窗口，用于指定表的详细信息。

   ![](assets/chlimage_1-79.png)

   * **列** -表的列数(必需)
   * **行** -表的行数(必需)
   * **宽度** -表的宽度
   * **高度** -表的高度
   * **单元格边距**-单元格内容周围的空间
   * **单元格间距** -单元格之间的间距
   * **边框** -表边框的粗细
   * 如果表标题为：

      * 应使用第一行
      * 应使用第一列
      * 应使用第一行和第一列
      * 或者不应使用标题。
   * **题注** -表的题注


* 拼写检查

   ![](assets/chlimage_1-80.png)

   用于检查文本内容的拼写。可能的拼写错误带有断开的红色线条。

* 特殊字符

   ![](assets/chlimage_1-81.png)

   用于在文本中插入特殊字符。选择此选项将打开显示可用字符的窗口。

   ![](assets/chlimage_1-82.png)

   点按或单击所需的字符，将其插入光标之后的文本。可以插入多个字符。点按或单击x以关闭选择窗口。

* 编辑源文件

   ![](assets/chlimage_1-83.png)

   用于查看和修改文本的HTML源。

   点按或单击 **“源编辑** ”图标以更改格式视图中的文本内容以查看原始HTML。在此模式中，将禁用所有其他格式选项。再次点按或单击 **“源编辑** ”图标以返回到带格式的视图。

   >[!CAUTION]
   >
   >与原始HTML的访问情况一样，在使用 **源编辑** 选项时，必须谨慎小心！
   >
   >
   >会扫描通过 **“源编辑** ”输入的HTML，并且会删除插入的任何脚本，而不会显示在生成页面上的任何脚本。但是 **，在“源编辑** ”中输入的格式不正确的HTML可能会破坏页面的模板，从而导致意外格式设置或呈现生成页面不可用。

* 段落格式

   ![](assets/chlimage_1-84.png)

   用于将段落格式应用于选定文本或光标之后插入的文本。选择此选项将打开一个从中选择段落格式的下拉菜单。

   ![](assets/chlimage_1-85.png)

文本组件也可以进行内嵌编辑，但由于空间restraints，并非所有格式选项都可用。要查看所有选项，请切换到全屏模式。

![](assets/chlimage_1-86.png)

## 设计对话框 {#design-dialog}

设计对话框允许模板作者定义内容作者可用的文本格式选项。

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

* 点按或单击 **“添加** ”按钮以插入新样式。
* 输入样式的代码和将在编辑对话框中显示的描述。
* 要删除样式，请点击或单击 **删除** 按钮。
* 要重新排列格式的顺序，请点按或单击并拖动手柄。

### 特殊字符 {#special-characters}

![](assets/chlimage_1-31.png)

可以为组件激活或取消激活插入特殊字符的选项。激活后，可定义允许的字符。

* 点按或单击 **添加** 按钮以插入新字符。
* 输入字符的HTML代码和将在编辑对话框中显示的描述。
* 要删除字符，请点击或单击 **删除** 按钮。
* 要重新排列字符的顺序，请点按或单击并拖动手柄。

## 技术详细信息 {#technical-details}

有关文本组件 [的最新技术文档可在GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/text/v1/text)上找到。

可以从GitHub下载整个核心组件项目。

有关开发核心组件的更多详细信息，请参阅 [核心组件开发人员文档](developing.md)。
