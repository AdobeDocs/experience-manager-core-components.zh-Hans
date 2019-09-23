---
title: Teaser组件
seo-title: Teaser组件
description: Teaser组件可显示图像、标题、富文本以及可选地链接到其他内容。
seo-description: Teaser组件可显示图像、标题、富文本以及可选地链接到其他内容。
uuid: 46989314-df37-448b-8562-c707043f2160
contentOwner: 博纳特
content-type: 引用
topic-tags: 核心组件
discoiquuid: e597c18e-3643-41be-9878-4a7872f1ab90
translation-type: tm+mt
source-git-commit: eef608fb06001485aa2c2c0b574af412ed7f15a4

---


# Teaser组件{#teaser-component}

核心组件Teaser组件可显示图像、标题、富文本以及可选地链接到其他内容。

## 使用情况 {#usage}

Teaser组件允许内容作者使用图像、标题或富文本轻松创建Teaser以进一步内容，并链接到其他内容或其他操作。

模板作者可以使用设 [计对话框](#design-dialog) ，定义创建行动动员和添加链接的选项是否可用以及是否禁用各种显示选项。 内容作者可以使用配 [置对话框](#configure-dialog) ，来设置图像、定义CTA、设置标题和说明以及配置指向单个Teaser的链接。 可 [以访问图像组](image.md#edit-dialog) 件的编辑对 [话框](image.md) ，以修改Teaser图像。

## 版本和兼容性 {#version-and-compatibility}

Teaser组件的当前版本为v1,v1是2018年7月随核心组件版本2.1.0引入的，本文档对此进行了说明。

下表详细列出了组件的所有受支持版本、与组件版本兼容的AEM版本，以及指向先前版本的文档的链接。

| 组件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|---|---|---|---|
| v1 | 兼容 | 兼容 | 兼容 |

## 示例组件输出 {#sample-component-output}

要体验Teaser组件以及查看其配置选项的示例以及HTML和JSON输出，请访问组 [件库](http://opensource.adobe.com/aem-core-wcm-components/library/teaser.html)。

### 技术详细信息 {#technical-details}

有关Teaser组件的最新技术文档 [可在GitHub上找到](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/teaser/v1/teaser)。

有关开发核心组件的更多详细信息，请参阅核 [心组件开发人员文档](developing.md)。

## 配置对话框 {#configure-dialog}

内容作者可以使用配置对话框来定义单个Teaser的属性。 如果选择了Teaser图 [像](#edit-dialog) ，还会显示一个编辑对话框来修改Teaser图像。

### 图像 {#image}

![](assets/screen_shot_2018-07-03at104125.png)

* **图像资产**
   * 从资产浏览器中 [拖放资产](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/author-environment-tools.html) ，或点 **按浏览选项** ，以从本地文件系统上传。
   * 点按或单 **击清除** ，以取消选择当前选定的图像。
   * 点按或单 **击编辑** , [以在资产编辑器中管理资产的演绎版](https://helpx.adobe.com/experience-manager/6-5/assets/using/managing-assets-touch-ui.html) 。

### 文本 {#text}

![](assets/screen_shot_2018-07-03at104138.png)

* **标题**&#x200B;定义要显示为Teaser标题的标题的标题。
* **从链接的页面获**&#x200B;取标题选中后，标题将填充链接页面的标题。
* **说明**&#x200B;定义要显示为Teaser子标题的说明。
* **从链接的页面获**&#x200B;取描述选中此选项后，将填充链接页面的描述。

### 链接和操作 {#links-actions}

![](assets/screen_shot_2018-07-03at104146.png)

* **链接**&#x200B;应用于Teaser的链接。 使用路径浏览器选择链接目标。
* **启用“行动动员**”选中后，将启用“行动动员”的定义。 列表中的第一个行动动员链接用作其他Teaser元素的链接。

## Edit Dialog {#edit-dialog}

Teaser组件将图像渲染委派给图像 [组件](image.md)。 因此， [内容作者可以使用]“图像组件”的编辑对话框(image.md#edit-dialog)来操作Teaser图像。

## 设计对话框 {#design-dialog}

设计对话框允许模板作者定义内容作者使用此组件时具有的Teaser选项。

### Teaser选项卡 {#teaser-tab}

![](assets/screen_shot_2018-07-03at105958.png)

* **行为召唤**
   * **禁用动作调用**&#x200B;隐 **藏内容作者的动作调用** 。
* **元素**
   * **隐藏标题**
      * 隐藏内容作 **者的** “标题”选项
      * 选择后，标题 **类型将隐藏** 。
   * **隐藏描述**&#x200B;隐藏内容作 **者的** “描述”选项
* **标题类**&#x200B;型定义Teaser标题要使用的H标记。
* **链接**
   * **不链接图像选中后**,Teaser图像将不链接
   * **不链接标题选中后**,Teaser标题将不链接

### 样式选项卡 {#styles-tab}

Teaser组件支持AEM样 [式系统](authoring.md#component-styling)。
