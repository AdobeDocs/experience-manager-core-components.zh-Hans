---
title: 电子邮件页面组件
description: 电子邮件页面组件
role: Architect, Developer, Admin, User
exl-id: 17fd0f5e-2b85-41a1-abaf-8ad190a5341a
source-git-commit: 33976c0e745ad091a142109f70541f01a31edc5b
workflow-type: ht
source-wordcount: '804'
ht-degree: 100%

---


# 电子邮件页面组件 {#email-page-component}

电子邮件页面组件是指可扩展的页面组件，设计用于[模板编辑器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=zh-Hans)，允许使用模板编辑器来组装页眉/页脚和结构组件，为创建 Adobe Campaign 内容量身定制。

## 用途 {#usage}

电子邮件页面组件构成了使用电子邮件核心组件以及可编辑模板设计的所有页面的基础。 利用电子邮件页面组件，可以使用其他电子邮件核心组件将页眉、页脚和页面结构定义为模板。

* 使用[“设计”对话框，](#design-dialog)可以为页面定义自定义客户端库。
* 与可从组件直接访问编辑对话框的其他组件不同，由于电子邮件页面组件是页面本身，其[“编辑”对话框](#edit-dialog)是页面属性窗口。

## 版本和兼容性 {#version-and-compatibility}

电子邮件页面组件的当前版本是 v1，此版本随 2022 年 10 月的电子邮件核心组件发行版本 X 的发布引入，具体说明见本文档。

下表详细说明了该组件的所有受支持版本、与该组件的版本兼容的 AEM 版本以及指向早期版本文档的链接。

| 组件版本 | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | 兼容 | 兼容 |

有关电子邮件核心组件版本的更多信息，请参阅文档[电子邮件核心组件版本](/help/email/versions.md)

### 技术详细信息 {#technical-details}

[在 GitHub 上可找到](https://adobe.com/go/aem_cmp_tech_email_page_v1_cn)有关页面组件的最新技术文档。

在[核心组件开发人员文档](/help/developing/overview.md)中可找到有关开发核心组件的其他详细信息。

## “编辑”对话框 {#edit-dialog}

由于该组件呈现整个页面，通常位于编辑对话框中的设置可在[页面属性](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html)窗口中找到。

### 云服务选项卡 {#cloud-services}

为了使电子邮件核心组件能够检索活动变量和数据，该页面必须链接到 Adobe Campaign 配置。

![电子邮件页面属性](/help/email/assets/email-page-properties.png)

在 **Cloud Service 配置**&#x200B;标题下，在下拉列表中选择&#x200B;**添加配置**。

在 **Adobe Campaign** 标题下面，选择与 Adobe Campaign 集成的配置。

有关设置电子邮件核心组件的更多信息，请参阅文档[使用电子邮件核心组件](/help/email/using.md)。

### 电子邮件选项卡 {#email-tab}

电子邮件选项卡根据此页面的内容（例如电子邮件主题和纯文本内容）定义通过 Adobe Campaign 发送的电子邮件的属性。

![电子邮件页面属性](/help/email/assets/email-page-properties-email.png)

* **主题** – Adobe Campaign 基于此页面发送的电子邮件主题
   * 单击&#x200B;**选择 Adobe Campaign 变量**&#x200B;图标，打开[选择 Adobe Campaign 变量](/help/email/campaign-variables.md)对话框并插入来自 Adobe Campaign 的动态内容。
* **预标题**
   * 单击&#x200B;**选择 Adobe Campaign 变量**&#x200B;图标，打开[选择 Adobe Campaign 变量](/help/email/campaign-variables.md)对话框并插入来自 Adobe Campaign 的动态内容。
* **纯文本** – Adobe Campaign 发送的电子邮件的纯文本版本
   * 单击&#x200B;**选择 Adobe Campaign 变量**&#x200B;图标，打开[选择 Adobe Campaign 变量](/help/email/campaign-variables.md)对话框并插入来自 Adobe Campaign 的动态内容。
* **参考 URL**

## “设计”对话框 {#design-dialog}

由于该组件呈现整个页面，在编辑页面模板时，通过&#x200B;**页面信息 -> 页面策略**&#x200B;访问“设计”对话框。

![页面策略](/help/assets/page-policy.png)

### “属性”选项卡 {#properties-tab}

使用“页面设计”窗口，您可以定义要加载的客户端库，以及页面的 Web 资源库。

![电子邮件页面组件设计对话框](/help/email/assets/email-page-design.png)

* **客户端库** - 这定义要加载的客户端库类别。JavaScript 添加到正文结尾，CSS 添加到页头。
* **客户端库 JavaScript 页头** – 定义要在页头中加载的 JavaScript 客户端库类别。
   * 在此处定义并在&#x200B;**客户端库**&#x200B;字段中存在的类别，将在页头而非正文结尾加载 JavaScript。
   * 除非该类别还存在于&#x200B;**客户端库**&#x200B;字段中，否则不加载 CSS。
* **异步加载 JavaScript 库** – 如果启用，自定义 JavaScript 库将异步加载。
* **Web 资源客户端库** - 用于提供 favicon 等 Web 资源的客户端库类别。
* **跳到主内容元素选择器** - 用作可访问性功能，以直接跳到页面的主内容。

可以同时为&#x200B;**客户端库**&#x200B;和&#x200B;**客户端库 JavaScript 页头**&#x200B;字段配置库，如下所示：

* 要添加新字段，请单击或点击字段下的&#x200B;**“添加”**&#x200B;按钮。
* 要移除字段，请单击或点击要移除的字段旁边的垃圾桶图标。
* 要重新设置加载顺序，请单击或点击要移动的字段并拖动旁边的手柄。

有关使用客户端库的更多信息，请参阅[使用客户端库。](https://helpx.adobe.com/cn/experience-manager/6-5/sites/developing/using/clientlibs.html)

### “样式”选项卡 {#styles-tab}

页面组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。
