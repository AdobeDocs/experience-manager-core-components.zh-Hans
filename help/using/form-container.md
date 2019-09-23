---
title: 表单容器组件
seo-title: 表单容器组件
description: 'null'
seo-description: 核心组件表单容器组件允许创建简单的提交表单。
uuid: 9d556daf-3fe7-4b2a-b5ae-6926acb267a9
contentOwner: 用户
content-type: 引用
topic-tags: 创作
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-新
discoiquuid: 3d33fe60-a0ac-4ff2-a865-d600b5448aeb
disttype: dist5
gnavtheme: 浅色
groupsectionnavitems: 否
hidemerchandisingbar: 继承
hidepromocomponent: 继承
modalsize: 426 x 240
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 62643e5bd49ab006230f65004bb9374822dcc017

---


# 表单容器组件{#form-container-component}

核心组件表单容器组件允许创建简单的提交表单。

## 使用情况 {#usage}

表单容器组件支持简单的WCM表单，并使用嵌套结构允许其他表单组件，从而支持构建简单的信息提交表单和功能。

通过使用配 [置对话框](#configure-dialog) ，内容编辑器可以定义由表单提交触发的操作、提交的内容应存储在何处以及是否应触发工作流。 模板作者可以使用设 [计对话框](#design-dialog) ，定义允许的组件及其映射，这与模板编辑器中标准布局容器 [的设计对话框类似](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)。

>[!NOTE]
>
>表单容器组件的核心组件仅支持使用核心组件表单组件（按钮、文本、隐藏等）。 不支 [持在核心组件](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/default-components-foundation.html) （或反之）内使用基础组件表单组件。

## 版本和兼容性 {#version-and-compatibility}

表单容器组件的当前版本为v2,v2是2018年1月随核心组件版本2.0.0一起引入的，本文档对此进行了说明。

下表详细列出了组件的所有受支持版本、与组件版本兼容的AEM版本，以及指向先前版本的文档的链接。

| 组件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v2 | 兼容 | 兼容 | 兼容 |
| [v1](form-container-v1.md) | 兼容 | 兼容 | 兼容 |

有关核心组件版本和版本的详细信息，请参阅文档核 [心组件版本](versions.md)。

## 技术详细信息 {#technical-details}

有关表单容器组件的最新技 [术文档可在GitHub上找到](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/form/container/v2/container)。

有关开发核心组件的更多详细信息，请参阅核 [心组件开发人员文档](developing.md)。

## 配置对话框 {#configure-dialog}

配置对话框允许内容作者定义提交组件时要执行的操作。

![](assets/screen_shot_2018-01-12at122046.png)

根据所选的操 **作类型**，容器中的可用选项将发生更改。 可用的操作类型有：

* [邮件](#mail)
* [存储内容](#store-content)
* [提交订单](#submit-order)
* [更新订单](#update-order)

无论类型如何，都有 [适用于每个](#general-settings) 操作的常规设置。

### 邮件 {#mail}

提交表单后，邮件操作类型将向指定的收件人发送电子邮件。

![](assets/screen_shot_2018-01-12at122554.png)

* **主题**&#x200B;提交表单时将发送的电子邮件主题
* **发件人**&#x200B;将在提交表单时发送的电子邮件的发件人电子邮件地址
* **收件人**&#x200B;在提交表单后将收到电子邮件的收件人的地址

   * 点按或单击添 **加按钮** ，添加其他地址
   * 点按或单击删 **除按钮** ，以删除电子邮件地址
* **CC**&#x200B;收到表单提交时发送的电子邮件副本的收件人地址
   * 点按或单击添 **加按钮** ，添加其他地址
   * 点按或单击删 **除按钮** ，以删除电子邮件地址

### 存储内容 {#store-content}

提交表单后，表单的内容将存储在指定的存储库位置。

![](assets/screen_shot_2018-01-12at122538.png)

* **内容路径**&#x200B;存储已提交内容的内容存储库路径
* **查看数据**&#x200B;点按或单击以JSON形式查看存储的已提交数据
* **启动工作流**&#x200B;配置为在提交表单时启动将存储的内容作为有效负荷的工作流

### 提交订单 {#submit-order}

提交表单后，将提交订单。

![](assets/chlimage_1-3.png)

### 更新订单 {#update-order}

提交表单后，订单将更新。

![](assets/chlimage_1-4.png)

### 常规设置 {#general-settings}

无论选择何种操作类型，都始终可以定义感谢页面。

![](assets/chlimage_1-5.png)

表单提交完成后，用户将被重定向到指定页面。

* 使用选择对话框在AEM中选择资源。
* 如果感谢页面不在AEM中，请指定绝对URL。 非绝对URL将解释为相对于AEM。
* 留空可在提交后重新显示表单。

## 设计对话框 {#design-dialog}

设计对话框允许模板作者为容器定义允许的组件及其映射，这与模板编辑器中标准布局容器的设 [计对话框类似](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/templates.html)。