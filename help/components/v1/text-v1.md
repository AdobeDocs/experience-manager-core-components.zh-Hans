---
title: 文本组件(v1)
description: 文本组件是一个富文本编辑和合成组件，可进行就地编辑。
index: n
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a
workflow-type: tm+mt
source-wordcount: '1657'
ht-degree: 3%

---


# 文本组件(v1){#text-component-v}

文本组件是一个富文本编辑和合成组件，可进行就地编辑。

## 使用 {#usage}

文本组件优惠了强大的富文本编辑器，它允许通过简化的内嵌编辑器以及全屏格式轻松编辑文本。

[编辑对话框](#edit-dialog)采用有限选项进行联机编辑，全屏编辑对话框中提供完整功能。 使用[设计对话框](#design-dialog)，可以为内容作者的模板配置文本格式选项，如标题、特殊字符和段落样式。

## 版本和兼容性{#version-and-compatibility}

本文档描述了文本组件的v1，最初随AEM 6.3的核心组件版本1.0.0引入。

下表列表了文本组件v1的兼容性。

| AEM 版本 | 文本组件v1 |
|--- |--- |
| 6.3 | 兼容 |
| 6.4 | 兼容 |

>[!CAUTION]
>
>本文档描述文本组件的v1。
>
>有关文本组件的当前版本的详细信息，请参阅[文本组件](/help/components/text.md)文档。

## 示例组件输出{#sample-component-output}

以下是从[We.Retail](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/we-retail.html)取的示例。

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
>从核心组件导出JSON时，需要1.1.0版的核心组件。 有关详细信息，请参阅核心组件v1](/help/versions.md)的[兼容性信息。

## 编辑对话框{#edit-dialog}

编辑对话框优惠用户希望合成文本的标准富文本格式工具。

![](/help/assets/chlimage_1-52.png)

* 粗体

   ![](/help/assets/chlimage_1-53.png)

   用于对选定文本应用粗体格式或大胆设置光标后输入的文本格式。

   **Ctrl+** B可用作键盘快捷键。

* 斜体

   ![](/help/assets/chlimage_1-54.png)

   用于将斜体格式应用于选定文本或在光标后输入的斜体文本。

   **Ctrl+** Ican可用作键盘快捷键。

* 下划线

   ![](/help/assets/chlimage_1-55.png)

   用于将带下划线的格式应用于在光标后输入的选定文本或下划线文本。

   **Ctrl+** Ucan可用作键盘快捷键。

* 下标

   ![](/help/assets/chlimage_1-56.png)

   用于将光标后输入的选定文本或文本格式化为下标。

* 上标

   ![](/help/assets/chlimage_1-57.png)

   用于将光标后输入的选定文本或文本格式化为上标。

* 粘贴文本

   ![](/help/assets/chlimage_1-58.png)

   将任何复制的文本粘贴为纯文本，而不使用任何格式。

   选择此选项时，将打开一个窗口，在该窗口中，文本可以粘贴为纯文本，且在插入文本之前没有预览。 点按或单击复选标记以接受，点按或单击x以取消。

   ![](/help/assets/chlimage_1-59.png)

* 从 Word 粘贴

   ![](/help/assets/chlimage_1-60.png)

   选择此选项时，将打开一个窗口，在将文本插入文本之前，该窗口将保持其格式预览。 点按或单击复选标记以接受，点按或单击x以取消。

   ![](/help/assets/chlimage_1-61.png)

* 超链接

   ![](/help/assets/chlimage_1-62.png)

   使用此选项可将选定文本转换为超链接或修改已定义的链接。 仅当已选择文本并打开一个包含设置链接的其他选项的窗口时，此选项才处于活动状态。

   ![](/help/assets/chlimage_1-63.png)

   * 输入位置

      * 使用“打开选择”对话框在AEM中选择路径
      * 如果链接不在AEM中，请输入绝对URL(非绝对路径解释为相对于AEM的相对路径)
   * 输入链接的替代描述性文本
   * 选择链接行为

      * 目标
      * 相同选项卡
      * 新选项卡
      * 父框架
      * 顶层框架

   点按或单击复选标记以应用链接，或点按x以取消。

* 取消链接

   ![](/help/assets/chlimage_1-64.png)

   使用此选项可删除已应用于所选文本的链接。 仅当已选择链接时，此选项才处于活动状态。

* 查找

   ![](/help/assets/chlimage_1-65.png)

   使用此选项可搜索指定文本字符串的出现次数。 选择此选项将打开一个窗口，用于指定搜索选项。

   ![](/help/assets/chlimage_1-66.png)

   输入要搜索的文本并点按或单击&#x200B;**查找**&#x200B;以开始搜索。 点按或单击x可取消。

   如果要根据大小写进行精确匹配，请在开始搜索之前选择选项&#x200B;**匹配大小写**。

   如果找到匹配项，则突出显示该匹配项，并且搜索对话框灰显。 再次点按或单击灰显对话框中的&#x200B;**查找**&#x200B;按钮，以搜索下一个匹配项。

   ![](/help/assets/chlimage_1-67.png)

   如果未找到其他匹配项，则将显示一条消息，并从文本的开头开始搜索。

   ![](/help/assets/chlimage_1-68.png)

* 替换

   ![](/help/assets/chlimage_1-69.png)

   使用此选项可搜索出现指定文本字符串的文本，并将匹配项替换为其他字符串。 选择此选项将打开一个窗口，用于指定搜索和替换选项。

   ![](/help/assets/chlimage_1-70.png)

   输入要搜索的文本以及应替换的文本。

   点按或单击&#x200B;**查找**&#x200B;以开始搜索。 单击或点按x可取消。

   如果要根据大小写进行精确匹配，请在开始搜索之前选择选项&#x200B;**匹配大小写**。

   如果找到匹配项，则突出显示该匹配项，并且搜索对话框灰显。 再次单击灰显对话框中的&#x200B;**查找**&#x200B;按钮以搜索下一个匹配项，或选择&#x200B;**替换**&#x200B;按钮以替换高亮显示的匹配文本。 请注意，只有匹配后，**替换**&#x200B;按钮才处于活动状态。

   选择&#x200B;**全部替换**&#x200B;以一次替换所有出现的文本。

* 左对齐文本

   ![](/help/assets/chlimage_1-71.png)

   用于将文本与左边距对齐。

* 居中对齐文本

   ![](/help/assets/chlimage_1-72.png)

   用于将文本居中。

* 右对齐文本

   ![](/help/assets/chlimage_1-73.png)

   用于将文本与右边距对齐。

* Bullet

   ![](/help/assets/chlimage_1-74.png)

   用于将选定文本格式化为项目符号列表，或在光标后开始插入项目符号列表。

   要结束项目符号列表，请再次点按或单击&#x200B;**项目符号**&#x200B;按钮，或输入两个回车符。

* 编号

   ![](/help/assets/chlimage_1-75.png)

   用于将选定文本格式化为编号列表，或在光标后开始插入编号列表。

   要结束编号列表，请再次点按或单击&#x200B;**编号**&#x200B;按钮，或输入两个回车符。

* 突出

   ![](/help/assets/chlimage_1-76.png)

   用于降低在光标后输入的选定文本或文本的缩进级别。

   仅当光标的选定文本或位置已缩进时才处于活动状态。

* 缩进

   ![](/help/assets/chlimage_1-77.png)

   用于增加在光标后输入的选定文本或文本的缩进级别。

* 表

   ![](/help/assets/chlimage_1-78.png)

   用于在文本中插入表。 选择此选项将打开一个窗口，用于指定表的详细信息。

   ![](/help/assets/chlimage_1-79.png)

   * **列** -表的列数（必需）
   * **行** -表的行数（必需）
   * **宽度** -表的宽度
   * **高度** -表的高度
   * **单元格**&#x200B;边距——单元格内容周围的空格
   * **单元格间距** -单元格之间的间距
   * **边框** -表边框线的权重
   * 如果表的标题：

      * 应使用第一行
      * 应使用第一列
      * 应使用第一行和第一列
      * 或者不应使用标题。
   * **Caption**  —— 表的描述


* 拼写检查

   ![](/help/assets/chlimage_1-80.png)

   用于检查文本内容的拼写。 可能的拼写错误用破红线加下划线。

* 特殊字符

   ![](/help/assets/chlimage_1-81.png)

   用于在文本中插入特殊字符。 选择此选项将打开一个窗口，其中显示可用字符。

   ![](/help/assets/chlimage_1-82.png)

   点按或单击所需字符，将其插入光标后的文本中。 可插入多个字符。 点按或单击x以关闭选择窗口。

* 编辑源文件

   ![](/help/assets/chlimage_1-83.png)

   用于视图和修改文本的HTML源。

   点按或单击&#x200B;**源编辑**&#x200B;图标，将文本的内容从格式化视图更改为视图原始HTML。 在此模式下，所有其他格式选项都被禁用。 再次点按或单击&#x200B;**源编辑**&#x200B;图标，以返回到格式化视图。

   >[!CAUTION]
   >
   >与访问原始HTML时一样，在使用&#x200B;**源编辑**&#x200B;选项时必须小心！
   >
   >
   >通过&#x200B;**源编辑**&#x200B;输入的HTML将扫描XSS风险，并删除所插入的任何脚本，不会显示在生成的页面上。 但是，在&#x200B;**源代码编辑**&#x200B;中输入的格式错误的HTML可能会中断页面的模板，导致意外的格式或导致生成的页面无法使用。

* 段落格式

   ![](/help/assets/chlimage_1-84.png)

   用于将段落格式应用于选定文本或光标后插入的文本。 选择此选项将打开一个下拉框，从中选择段落格式。

   ![](/help/assets/chlimage_1-85.png)

文本组件也可以联机进行编辑，但由于空间限制，并非所有格式选项都联机可用。 要查看所有选项，请切换到全屏模式。

![](/help/assets/chlimage_1-86.png)

## 设计对话框{#design-dialog}

设计对话框允许模板作者定义内容作者可以使用的文本格式选项。

### 功能 {#features}

![](/help/assets/chlimage_1-28.png)

可以为组件激活或取消激活以下功能。

* 粘贴纯文本
* 过去自词
* 查找和替换
* 拼写检查器
* 源编辑

### 格式化 {#formatting}

![](/help/assets/chlimage_1-29.png)

可以为组件激活或取消激活以下格式选项。

* 表
* 列表
* 对齐
* 粗体、斜体、下划线
* 链接
* 子／上标

### 段落样式 {#paragraph-styles}

![](/help/assets/chlimage_1-30.png)

可以为组件激活或取消激活段落样式。 激活后，可以定义允许的格式。

* 点按或单击&#x200B;**添加**&#x200B;按钮以插入新样式。
* 输入样式的代码以及将在编辑对话框中显示的说明。
* 要删除样式点按或单击&#x200B;**删除**&#x200B;按钮。
* 要重新排列格式的顺序，请点按或单击并拖动手柄。

### 特殊字符 {#special-characters}

![](/help/assets/chlimage_1-31.png)

可以为组件激活或取消激活插入特殊字符的选项。 激活后，可以定义允许的字符。

* 点按或单击&#x200B;**添加**&#x200B;按钮以插入新字符。
* 输入字符的HTML代码和将在编辑对话框中显示的说明。
* 要删除字符点按或单击&#x200B;**删除**&#x200B;按钮。
* 要重新排列字符的点按顺序，请单击或拖动手柄。

## 技术详细信息{#technical-details}

有关文本组件[的最新技术文档可在GitHub](https://github.com/adobe/aem-core-wcm-components/tree/master/content/src/content/jcr_root/apps/core/wcm/components/text/v1/text)上找到。

整个核心组件项目可从GitHub下载。

有关开发核心组件的更多详细信息，请参阅[核心组件开发人员文档](/help/developing/overview.md)。
