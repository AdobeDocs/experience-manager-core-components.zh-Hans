---
title: 文本组件 (v1)
description: 文本组件是一种富文本编辑和撰写组件，具有就地编辑功能。
index: n
role: Architect, Developer, Admin, User
exl-id: c9fe3052-a33d-412e-9456-52c9a0cea292
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: ht
source-wordcount: '1657'
ht-degree: 100%

---

# 文本组件 (v1) {#text-component-v}

文本组件是一种富文本编辑和撰写组件，具有就地编辑功能。

## 用途 {#usage}

文本组件提供了一个强大的富文本编辑器，允许在简化的内联编辑器中以全屏格式轻松编辑文本。

[“编辑”对话框](#edit-dialog)具有带有限选项的内联编辑功能，可在全屏编辑对话框中实现完整功能。利用[“设计”对话框](#design-dialog)，可以为内容作者配置模板的文本格式选项，例如标题、特殊字符和段落样式。

## 版本和兼容性 {#version-and-compatibility}

本文档介绍了文本组件 v1，它最初随带 AEM 6.3 的核心组件发行版本 1.0.0 引入。

下表列出了文本组件 v1 的兼容性。

| AEM 版本 | 文本组件 v1 |
|--- |--- |
| 6.3 | 兼容 |
| 6.4 | 兼容 |

>[!CAUTION]
>
>本文档介绍了文本组件 v1。
>
>有关当前版本的文本组件的详细信息，请参阅[文本组件](/help/components/text.md)文档。

## 示例组件输出 {#sample-component-output}

以下是摘自 [We.Retail](https://helpx.adobe.com/cn/experience-manager/6-4/sites/developing/using/we-retail.html) 的示例。

### 屏幕快照 {#screenshot}

![](/help/assets/chlimage_1-27.png)

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
>从核心组件执行 JSON 导出需要版本 1.1.0 的核心组件。有关更多信息，请参阅[核心组件 v1 的兼容性信息](/help/versions.md)。

## “编辑”对话框 {#edit-dialog}

“编辑”对话框提供了用户将用于撰写文本的标准富文本格式工具。

![](/help/assets/chlimage_1-52.png)

* 粗体

   ![](/help/assets/chlimage_1-53.png)

   用于对所选文本应用粗体格式或对在光标后输入的文本应用粗体格式。

   **Ctrl+B** 可用作快捷键。

* 斜体

   ![](/help/assets/chlimage_1-54.png)

   用于对所选文本应用斜体格式或对在光标后输入的文本应用斜体格式。

   **Ctrl+I** 可用作快捷键。

* 下划线

   ![](/help/assets/chlimage_1-55.png)

   用于对所选文本应用下划线格式或对在光标后输入的文本应用下划线格式。

   **Ctrl+U** 可用作快捷键。

* 下标

   ![](/help/assets/chlimage_1-56.png)

   用于将所选文本或在光标后输入的文本设置为下标格式。

* 上标

   ![](/help/assets/chlimage_1-57.png)

   用于将所选文本或在光标后输入的文本设置为上标格式。

* 粘贴为文本

   ![](/help/assets/chlimage_1-58.png)

   将任何复制的文本粘贴为纯文本，而不设置任何格式。

   当选择此选项时，将打开一个窗口，其中的文本可以粘贴为无格式的纯文本，作为插入文本中之前的预览。通过点击或单击复选标记可接受，通过点击或单击 x 可取消。

   ![](/help/assets/chlimage_1-59.png)

* 从 Word 粘贴

   ![](/help/assets/chlimage_1-60.png)

   当选择此选项时，将打开一个窗口，其中的文本可粘贴并保留其格式，作为插入文本中之前的预览。通过点击或单击复选标记可接受，通过点击或单击 x 可取消。

   ![](/help/assets/chlimage_1-61.png)

* 超链接

   ![](/help/assets/chlimage_1-62.png)

   使用此选项可将所选文本转换为超链接或修改已定义的链接。此选项仅在已选择文本并打开一个窗口（其中包含用于设置链接的附加选项）时处于活动状态。

   ![](/help/assets/chlimage_1-63.png)

   * 输入位置

      * 使用“打开选择”对话框可在 AEM 中选择路径
      * 如果链接不在 AEM 中，请输入绝对 URL（非绝对路径将解释为相对于 AEM）
   * 输入链接的替换描述文本
   * 选择链接行为

      * 目标
      * 相同选项卡
      * 新选项卡
      * 父框架
      * 顶层框架

   点击或单击复选标记可应用链接，点击或单击 x 可取消。

* 取消链接

   ![](/help/assets/chlimage_1-64.png)

   使用此选项可删除已应用于所选文本的链接。此选项仅在已选择链接时处于活动状态。

* 查找

   ![](/help/assets/chlimage_1-65.png)

   使用此选项可搜索文本以确定指定文本字符串的匹配项。选择此选项将打开一个用于指定搜索选项的窗口。

   ![](/help/assets/chlimage_1-66.png)

   输入要搜索的文本并点击或单击&#x200B;**查找**&#x200B;以开始搜索。点击或单击 x 可取消。

   如果您希望根据大小写进行精确匹配，请选择选项&#x200B;**匹配大小写**，然后再开始搜索。

   如果找到一个匹配项，则将突出显示该匹配项，并且搜索对话框将灰显。在灰显的对话框中再次点击或单击&#x200B;**查找**&#x200B;按钮可搜索下一个匹配项。

   ![](/help/assets/chlimage_1-67.png)

   如果未找到其他匹配项，则将显示一条消息，并且将从文本的开头重新开始搜索。

   ![](/help/assets/chlimage_1-68.png)

* 替换

   ![](/help/assets/chlimage_1-69.png)

   使用此选项可搜索文本以确定指定文本字符串的匹配项，并将匹配项替换为其他字符串。选择此选项将打开一个用于指定搜索和替换选项的窗口。

   ![](/help/assets/chlimage_1-70.png)

   输入要搜索的文本以及应替换为的文本。

   点击或单击&#x200B;**查找**&#x200B;可开始搜索。单击或点击 x 可取消。

   如果您希望根据大小写进行精确匹配，请选择选项&#x200B;**匹配大小写**，然后再开始搜索。

   如果找到一个匹配项，则将突出显示该匹配项，并且搜索对话框将灰显。在灰显对话框中再次单击&#x200B;**查找**&#x200B;按钮可搜索下一个匹配项，选择&#x200B;**替换**&#x200B;按钮可替换突出显示的匹配文本。请注意，**替换**&#x200B;按钮仅在进行匹配后处于活动状态。

   选择&#x200B;**全部替换**&#x200B;可一次性替换文本的所有匹配项。

* 左对齐文本

   ![](/help/assets/chlimage_1-71.png)

   用于将文本与左边距对齐。

* 居中对齐文本

   ![](/help/assets/chlimage_1-72.png)

   用于将文本居中对齐。

* 右对齐文本

   ![](/help/assets/chlimage_1-73.png)

   用于将文本与右边距对齐。

* 项目符号

   ![](/help/assets/chlimage_1-74.png)

   用于将所选文本设置为项目符号列表格式或在光标后开始插入项目符号列表。

   要结束项目符号列表，请再次点击或单击&#x200B;**项目符号**&#x200B;按钮或输入两个回车符。

* 编号

   ![](/help/assets/chlimage_1-75.png)

   用于将所选文本设置为编号列表格式或在光标后开始插入编号列表。

   要结束编号列表，请再次点击或单击&#x200B;**编号**&#x200B;按钮或输入两个回车符。

* 减少缩进

   ![](/help/assets/chlimage_1-76.png)

   用于降低所选文本或光标后输入的文本的缩进级别。

   仅当所选文本或光标位置已缩进时才处于活动状态。

* 缩进

   ![](/help/assets/chlimage_1-77.png)

   用于增加所选文本或光标后输入的文本的缩进级别。

* 表

   ![](/help/assets/chlimage_1-78.png)

   用于将表插入文本中。选择此选项将打开一个用于指定表的详细信息的窗口。

   ![](/help/assets/chlimage_1-79.png)

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


* 检查拼写

   ![](/help/assets/chlimage_1-80.png)

   用于检查文本内容的拼写。为可能的拼写错误加下划线（红色虚线）。

* 特殊字符

   ![](/help/assets/chlimage_1-81.png)

   用于将特殊字符插入文本中。选择此选项将打开一个用于显示可用字符的窗口。

   ![](/help/assets/chlimage_1-82.png)

   点击或单击所需字符以将其插入光标后的文本中。可插入多个字符。点击或单击 x 可关闭选择窗口。

* 编辑源文件

   ![](/help/assets/chlimage_1-83.png)

   用于查看和修改文本的 HTML 源。

   点击或单击&#x200B;**编辑源文件**&#x200B;图标可从格式化视图更改文本内容以查看原始 HTML。在此模式中，将禁用所有其他格式选项。再次点击或单击&#x200B;**编辑源文件**&#x200B;图标可返回格式化视图。

   >[!CAUTION]
   >
   >与访问原始 HTML 的情况一样，使用&#x200B;**编辑源文件**&#x200B;选项时必须小心！
   >
   >
   >将扫描通过&#x200B;**编辑源文件**&#x200B;输入的 HTML 以确定是否存在 XSS 风险，插入的任何脚本将被删除且不会显示在结果页上。不过，在&#x200B;**编辑源文件**&#x200B;中输入的格式错误的 HTML 可能会破坏页面的模板，从而导致意外的格式设置或表明生成的页面不可用。

* 段落格式

   ![](/help/assets/chlimage_1-84.png)

   用于对所选文本或在光标后插入的文本应用段落格式。选择此选项将打开一个下拉菜单，可从中选择段落格式。

   ![](/help/assets/chlimage_1-85.png)

也可以对文本组件进行内联编辑，但由于空间限制，无法对所有格式选项进行内联编辑。要查看所有选项，请切换到全屏模式。

![](/help/assets/chlimage_1-86.png)

## “设计”对话框 {#design-dialog}

利用“设计”对话框，模板作者可以定义哪些文本格式选项可供内容作者使用。

### 功能 {#features}

![](/help/assets/chlimage_1-28.png)

可以为组件激活或停用以下功能。

* 粘贴纯文本
* 从 Word 粘贴
* 查找并替换
* 拼写检查器
* 源编辑

### 格式 {#formatting}

![](/help/assets/chlimage_1-29.png)

可以为组件激活或停用以下格式选项。

* 表
* 列表
* 对齐方式
* 粗体、斜体、下划线
* 链接
* 下标/上标

### 段落样式 {#paragraph-styles}

![](/help/assets/chlimage_1-30.png)

可以为组件激活或停用段落样式。在激活时，可以定义允许的格式。

* 点击或单击&#x200B;**添加**&#x200B;按钮可插入新样式。
* 输入将在“编辑”对话框中显示的样式代码和描述。
* 要删除样式，请点击或单击&#x200B;**删除**&#x200B;按钮。
* 要重新设置格式的顺序，请点击或单击并拖动手柄。

### 特殊字符 {#special-characters}

![](/help/assets/chlimage_1-31.png)

可以为组件激活或停用用于插入特殊字符的选项。在激活时，可以定义允许的字符。

* 点击或单击&#x200B;**添加**&#x200B;按钮可插入新字符。
* 输入将在“编辑”对话框中显示的字符的 HTML 代码和描述。
* 要删除字符，请点击或单击&#x200B;**删除**&#x200B;按钮。
* 要重新设置字符的顺序，请点击或单击并拖动手柄。

## 技术详细信息 {#technical-details}

[在 GitHub 上可找到](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/text/v1/text)有关文本组件的最新技术文档。

从 GitHub 可下载整个核心组件项目。

在[核心组件开发人员文档](/help/developing/overview.md)中可找到有关开发核心组件的其他详细信息。
