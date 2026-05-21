---
title: 使用电子邮件核心组件
description: 了解电子邮件核心组件的基本安装、配置和使用。
role: Developer, Admin, User
exl-id: 0e79ca8f-eb0a-4519-b1e8-a9d3b0b99987
index: false
TQID: https://experienceleague.adobe.com/wNHEXDBErMNRfSs-N6vAhQl9jnzMJJnGTPBUFEMZHY8
product_v2:
  - id: c45915cf-e157-4af7-a80d-97b905bcb3a5
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a642c50e-80eb-4fc1-a5d2-f3762d1f841d
  - id: e2c1b6d3-bb7e-4fe8-8c72-f7b403298e91
subfeature_v2:
  - id: a6c0bfb4-91d0-4952-9c1d-c7f39e7705c4
  - id: de0934a4-5275-4727-b871-497a72ae8500
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 73aa5234ac63fa3be99feebce448bb6722513838
workflow-type: tm+mt
source-wordcount: 683
ht-degree: 100%

---

# 使用电子邮件核心组件 {#using}

了解电子邮件核心组件的基本安装、配置和使用。

## 安装电子邮件核心组件 {#installation}

电子邮件核心组件可与 AEM 6.5 一起使用。 有关更多信息，请参阅[电子邮件核心组件简介文档的要求部分](introduction.md#requirements)。

### 安装核心组件 {#core-components}

电子邮件核心组件基于 AEM 核心组件构建。 由于 AEM 6.5 未随附核心组件，因此您必须先安装 AEM 核心组件，然后再安装电子邮件核心组件。

有关如何安装核心组件的详细信息，请参阅文档使用核心组件的[下载和安装](/help/get-started/using.md#download-and-install)部分。

### 安装电子邮件核心组件 {#email-core-components}

在您的实例中安装核心组件后，您还必须同样安装电子邮件核心组件。 电子邮件核心组件还不是 AEM Project 原型的一部分，因此您需要手动将它们添加到您的项目中。 按照[电子邮件核心组件 GitHub wiki 中的文档进行安装。](https://github.com/adobe/aem-core-email-components/wiki/Adding-to-Existing-Project)

如果您希望调整现有项目以使用电子邮件核心组件，您可以按照这些相同的说明进行操作。

## 配置 {#configuration}

安装核心组件后，您应该完成两个重要的配置步骤。

### 配置 Campaign {#configure-campaign}

您必须设置 AEM-Adobe Campaign 集成才能使这两个解决方案进行通信。

* 配置 Adobe Campaign 集成
   * Adobe Campaign Classic：[与 Adobe Campaign Classic 集成](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignonpremise.html)
   * Adobe Campaign Standard：[与 Adob&#x200B;&#x200B;e Campaign Standard 集成](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html)
* [链接 Adobe Campaign 集成配置](/help/email/components/page.md#cloud-services-tab)到您将使用电子邮件核心组件的内容页面

### 为电子邮件组件添加 AEM 资源类型过滤器 {#aem-resource-filter}

为了使 Adobe Campaign 能够基于电子邮件核心组件呈现电子邮件，必须在 Campaign 中调整过滤器。

1. 使用客户端控制台以管理员身份登录 Adobe Campaign。

1. 从菜单栏选择&#x200B;**“工具”** -> **“资源管理器”**。

1. 在资源管理器中，导航到&#x200B;**管理** -> **Platform** -> **选项**&#x200B;节点。

1. 从列表中选择 `AEMResourceTypeFilter` 选项。

1. 在&#x200B;**值**&#x200B;字段中，如果尚不存在 `core/email/components/page/<v1>/page`，则附加该字段。

   * 将 `<v1>` 替换为电子邮件核心组件[页面组件](/help/email/components/page.md)的当前版本，例如 `v1`。
   * 请注意，**值**&#x200B;字段中的值必须用逗号分隔。

1. 单击“**保存**”。

## 使用电子邮件核心组件 {#using-components}

安装电子邮件组件并配置与 Adobe Campaign 的集成后，您可以使用电子邮件组件在 AEM 中创建电子邮件内容，然后使用 Adobe Campaign 将该内容发送给收件人。 以下是工作流程的概述。

| 步骤 | 描述 | 解决方案 |
|---|---|---|
| 1 | 作者将文件夹和电子邮件内容创建为页面的自由格式层次结构。 | AEM |
| 2 | 通过[模板编辑器，](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/templates.html?lang=zh-hans)作者可配置电子邮件页眉和/或页脚，该页眉和页脚将在此页面模板生成的所有电子邮件页面之间共享。 | AEM |
| 3 | 作者使用[页面编辑器](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/editing-content.html)中的文本编辑器创建电子邮件内容，在文本编辑器中，作者可以在其中选择 Adobe Campaign 变量，并使用分段组件在收件人满足特定条件时有条件地显示信息。 | AEM |
| 4 | 电子邮件内容完成后，[运行工作流](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/workflows/overview.html)以审批内容并发送到 Campaign。 | AEM |
| 5 | 创建投放，定义收件人列表。 | 营销活动 |
| 6 | 在 AEM 中创建的内容被选为投放的内容。 | 营销活动 |
| 7 | 内容将发送给收件人，将 Adobe Campaign 变量替换为收件人的个性化信息。 | 营销活动 |

有关在 AEM 中创建电子邮件内容并在 Adobe Campaign 中投放的示例，请参阅以下资源。

* AEM 6.5：[使用 Adobe Campaign Classic 和 Adobe Campaign Standard](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/campaign.html)
