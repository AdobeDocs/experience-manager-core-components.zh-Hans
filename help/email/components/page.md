---
title: 电子邮件页面组件
description: 电子邮件页面组件
role: Architect, Developer, Admin, User
hidefromtoc: true
index: false
source-git-commit: 8bebe3ca036557f3f7c6b8ec0e65d6d104d5ffae
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 电子邮件页面组件 {#email-page-component}

电子邮件页面组件是一个可扩展的页面组件，旨在与 [模板编辑器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=zh-Hans) 和允许使用模板编辑器来组装页眉/页脚和结构组件，这些组件是为创建Adobe Campaign内容而量身定制的。

## 用途 {#usage}

电子邮件页面组件构成了使用电子邮件核心组件和可编辑模板设计的所有页面的基础。 通过使用电子邮件页面组件，页眉、页脚和页面结构可以定义为使用其他电子邮件核心组件的模板。

* 使用 [设计对话框，](#design-dialog) 可以为页面定义自定义客户端库。
* 与具有可直接从组件访问的编辑对话框的其他组件不同，因为电子邮件页面组件本身就是页面， [编辑对话框](#edit-dialog) 电子邮件页面组件的页面属性窗口。

## 版本和兼容性 {#version-and-compatibility}

电子邮件页面组件的当前版本为v1，该版本于2022年10月随电子邮件核心组件X版引入，该版本在本文档中进行了描述。

下表详细说明了该组件的所有受支持版本、与该组件的版本兼容的 AEM 版本以及指向早期版本文档的链接。

| 组件版本 | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | 兼容 | 兼容 |

有关电子邮件核心组件版本和版本的更多信息，请参阅此文档 [电子邮件核心组件版本](/help/email/versions.md)

### 技术详细信息 {#technical-details}

有关页面组件的最新技术文档 [可在GitHub上找到。](https://adobe.com/go/aem_cmp_tech_email_page_v1)

在[核心组件开发人员文档](/help/developing/overview.md)中可找到有关开发核心组件的其他详细信息。

## “编辑”对话框 {#edit-dialog}

由于该组件呈现整个页面，通常位于编辑对话框中的设置可在[页面属性](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/fundamentals/page-properties.html)窗口中找到。

### Cloud Services选项卡 {#cloud-services}

要使电子邮件核心组件能够检索促销活动变量和数据，页面必须链接到Adobe Campaign配置。

![电子邮件页面属性](/help/email/assets/email-page-properties.png)

在 **Cloud Service配置** 标题，在下拉菜单中选择 **添加配置**.

在 **Adobe Campaign** 标题中，选择与Adobe Campaign集成的配置。

查看文档 [使用电子邮件核心组件](/help/email/using.md) 有关设置电子邮件核心组件的更多信息。

### “电子邮件”选项卡 {#email-tab}

“电子邮件”选项卡根据此页面的内容（如电子邮件主题和纯文本内容）定义通过Adobe Campaign发送的电子邮件的属性。

![电子邮件页面属性](/help/email/assets/email-page-properties-email.png)

* **主题** -Adobe Campaign根据本页发送的电子邮件的主题
   * 单击 **选择Adobe Campaign变量** 图标以打开 [选择Adobe Campaign变量](/help/email/campaign-variables.md) 对话框，以从Adobe Campaign插入动态内容。
* **预报头**
   * 单击 **选择Adobe Campaign变量** 图标以打开 [选择Adobe Campaign变量](/help/email/campaign-variables.md) 对话框，以从Adobe Campaign插入动态内容。
* **纯文本**  — 由Adobe Campaign发送的电子邮件的纯文本版本
   * 单击 **选择Adobe Campaign变量** 图标以打开 [选择Adobe Campaign变量](/help/email/campaign-variables.md) 对话框，以从Adobe Campaign插入动态内容。
* **引用Url**

## “设计”对话框 {#design-dialog}

由于该组件呈现整个页面，在编辑页面模板时，通过&#x200B;**页面信息 -> 页面策略**&#x200B;访问“设计”对话框。

![页面策略](/help/assets/page-policy.png)

### “属性”选项卡 {#properties-tab}

使用“页面设计”窗口，您可以定义要加载的客户端库，以及页面的 Web 资源库。

![电子邮件页面组件设计对话框](/help/email/assets/email-page-design.png)

* **客户端库** - 这定义要加载的客户端库类别。JavaScript 添加到正文结尾，CSS 添加到页头。
* **客户端库JavaScript页面头**  — 这定义要在页面标题中加载的JavaScript客户端库类别。
   * 在此处定义并在&#x200B;**客户端库**&#x200B;字段中存在的类别，将在页头而非正文结尾加载 JavaScript。
   * 除非该类别还存在于&#x200B;**客户端库**&#x200B;字段中，否则不加载 CSS。
* **异步加载JavaScript库**  — 如果启用，将异步加载自定义JavaScript库。
* **Web 资源客户端库** - 用于提供 favicon 等 Web 资源的客户端库类别。
* **跳到主内容元素选择器** - 用作可访问性功能，以直接跳到页面的主内容。

可以同时为&#x200B;**客户端库**&#x200B;和&#x200B;**客户端库 JavaScript 页头**&#x200B;字段配置库，如下所示：

* 要添加新字段，请单击或点按 **添加** 按钮。
* 要删除字段，请单击或点按要删除的字段旁边的垃圾桶图标。
* 要重新设置加载顺序，请单击或点击要移动的字段并拖动旁边的手柄。

有关使用客户端库的更多信息，请参阅 [使用客户端库。](https://helpx.adobe.com/cn/experience-manager/6-5/sites/developing/using/clientlibs.html)

### “样式”选项卡 {#styles-tab}

页面组件支持 AEM [样式系统](/help/get-started/authoring.md#component-styling)。
