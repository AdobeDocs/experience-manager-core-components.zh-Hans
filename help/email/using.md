---
title: 使用电子邮件核心组件
description: 了解电子邮件核心组件的基本安装、配置和使用情况。
role: Architect, Developer, Admin, User
hidefromtoc: true
index: false
source-git-commit: 8bebe3ca036557f3f7c6b8ec0e65d6d104d5ffae
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 使用电子邮件核心组件 {#using}

了解电子邮件核心组件的基本安装、配置和使用情况。

## 安装电子邮件核心组件 {#installation}

电子邮件核心组件可与AEM 6.5一起使用。请参阅 [电子邮件核心组件简介文档的“要求”部分](introduction.md#requirements) 以了解更多信息。

### 安装核心组件 {#core-components}

电子邮件核心组件是基于AEM核心组件构建的。 由于核心组件未随AEM一起提供，因此您必须先安装AEM核心组件，然后再安装电子邮件核心组件。

请参阅部分 [下载并安装](/help/get-started/using.md#download-and-install) 使用核心组件一节，以了解有关如何安装核心组件的详细信息。

### 安装电子邮件核心组件 {#email-core-components}

在实例中安装核心组件后，您必须同样安装电子邮件核心组件。 电子邮件核心组件尚未包含在AEM项目原型中，因此您需要手动将它们添加到您的项目。 请按照 [要安装的电子邮件核心组件GitHub Wiki。](https://github.com/adobe/aem-core-email-components/wiki/Adding-to-Existing-Project)

如果您希望调整现有项目以使用电子邮件核心组件，则可以按照相同的说明进行操作。

## 配置 {#configuration}

安装核心组件后，您应完成两个重要的配置步骤。

### 配置Campaign {#configure-campaign}

您必须设置AEM-Adobe Campaign集成，才能使这两个解决方案进行通信。

* 配置Adobe Campaign集成
   * Adobe Campaign Classic: [与Adobe Campaign Classic集成](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignonpremise.html)
   * Adobe Campaign Standard: [与Adobe Campaign Standard集成](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html)
* [链接Adobe Campaign集成配置](/help/email/components/page.md#cloud-services-tab) 到内容页面，在该页面中，您将使用电子邮件核心组件

### 为电子邮件组件添加AEM资源类型过滤器 {#aem-resource-filter}

为了Adobe Campaign能够根据电子邮件核心组件呈现电子邮件，必须在Campaign中调整过滤器。

1. 使用客户端控制台以管理员身份登录 Adobe Campaign。

1. 从菜单栏选择&#x200B;**“工具”** -> **“资源管理器”**。

1. 在资源管理器中，导航到 **管理** -> **平台** -> **选项** 节点。

1. 选择 `AEMResourceTypeFilter` 选项。

1. 在 **值** 字段，附加 `core/email/components/page/<v1>/page` 如果它尚不存在。

   * 替换 `<v1>` 与当前版本的电子邮件核心组件 [页面组件](/help/email/components/page.md) 例如 `v1`.
   * 请注意， **值** 字段，必须以逗号分隔。

1. 单击“**保存**”。

## 使用电子邮件核心组件 {#using-components}

安装电子邮件组件并配置与Adobe Campaign的集成后，您可以使用电子邮件组件在AEM中创建电子邮件内容，然后使用Adobe Campaign将该内容发送给收件人。 以下是工作流的概述。

| 步骤 | 描述 | 解决方案 |
|---|---|---|
| 1 | 作者将文件夹和电子邮件内容创建为页面的自由格式层次结构。 | AEM |
| 2 | 使用 [模板编辑器，](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=zh-Hans) 作者配置要在从此页面模板生成的所有电子邮件页面之间共享的电子邮件页眉和/或页脚。 | AEM |
| 3 | 作者使用 [页面编辑器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/editing-content.html) 要使用文本编辑器创建电子邮件内容，用户可以在文本编辑器中选择Adobe Campaign变量，并在收件人满足特定条件时使用分段组件以条件方式显示信息。 | AEM |
| 4 | 电子邮件内容完成后， [工作流已运行](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/workflows/overview.html) 以批准内容并发送到Campaign。 | AEM |
| 5 | 随即会创建投放，以定义收件人列表。 | 营销活动 |
| 6 | 选择在AEM中创建的内容作为投放的内容。 | 营销活动 |
| 7 | 内容会发送给收件人，用收件人的个性化信息替换Adobe Campaign变量。 | 营销活动 |

有关在AEM中创建电子邮件内容并在Adobe Campaign中投放的示例，请参阅以下资源。

* AEMas a Cloud Service: [使用AEM创建Campaign新闻稿](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/campaign/creating-newsletters.html)
* AEM 6.5: [使用Adobe Campaign Classic和Adobe Campaign Standard](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/campaign.html)

