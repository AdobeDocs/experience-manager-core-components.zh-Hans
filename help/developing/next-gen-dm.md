---
title: 支持新一代 Dynamic Media
description: 了解如何配置核心组件图像和 Teaser 组件以支持远程新一代 Dynamic Media 资源。
role: Architect, Developer, Admin, User
source-git-commit: 9b8930c2e268f52a1377906725db9a05a089e233
workflow-type: tm+mt
source-wordcount: '470'
ht-degree: 100%

---


# 支持新一代 Dynamic Media {#next-gen-dm-support}

了解如何配置核心组件图像和 Teaser 组件以支持远程新一代 Dynamic Media 资源。

## 获取最新的 AEM 版本 {#latest}

支持新一代 Dynamic Media 远程资源需要：

* AEM 6.5 SP 18 和更高版本或 AEM as a Cloud Service
* 核心组件版本 2.23.2 或更高版本

## 配置 HTTPS {#https}

一般建议使用 HTTP 运行所有生产 AEM 实例。但是，可能并未这样设置您的本地开发环境。但是，新一代 Dynamic Media 远程资源需要 HTTPS 才能正常运行。

[使用本指南](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/security/use-the-ssl-wizard.html)在您要使用远程资源的任何地方（包括开发环境）配置 HTTPS。

## 配置 OSGi {#osgi}

必须在 OSGi 配置中定义远程资源的位置。按如下所示配置&#x200B;**新一代 Dynamic Media 配置** OSGi 配置，并将这些值替换为您远程资源环境的那些值。

```text
imsClient="<ims-client-name>"
enabled=B"true"
imsOrg="<ims-org>@AdobeOrg"
repositoryId="<repo-id>.adobeaemcloud.com"
```

![新一代 Dynamic Media 配置 OSGi 配置窗口](/help/assets/remote-assets-osgi.png)

有关如何配置 OSGi 的详细信息，请参见以下文档：

* 为 AEM as a Cloud Service [配置 Adobe Experience Manager as a Cloud Service 的 OSGi](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/deploying/configuring-osgi.html)
* 为 AEM 6.5 [配置 OSGi](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/configuring/configuring-osgi.html)

## 验证配置 {#verify}

现在可验证新一代 Dynamic Media 远程资源功能是否发挥作用。为此，可安装 WKND 示例站点和核心组件。

* 需要[核心组件](https://github.com/adobe/aem-core-wcm-components/releases/download/core.wcm.components.reactor-2.23.2/core.wcm.components.all-2.23.2.zip) 2.23.2 版本或更高版本。
* 需要 [WKND 示例站点](https://github.com/adobe/aem-guides-wknd/releases/download/aem-guides-wknd-3.2.0/aem-guides-wknd.all-3.2.0-classic.zip) 3.2.0 版本或更高版本。

安装核心组件和 WKND 站点后，可在任何 WKND 页面上测试该功能。

1. 使用 HTTPS 访问 AEM 实例。

1. 在页面编辑器中打开一个 WKND 演示页面，如 `https://<host>:<httpsPort>/editor.html/content/wknd/language-masters/en/magazine/arctic-surfing.html`

1. 将图像组件添加到该页面。

1. 在组件的“配置”对话框中，取消选中&#x200B;**资源**&#x200B;选项卡上的&#x200B;**从页面继承特色图像**&#x200B;选项，然后单击&#x200B;**选取**。

1. 如果配置正确无误，则将出现一个下拉菜单，其中具有&#x200B;**本地**&#x200B;和&#x200B;**远程**&#x200B;选项。选择&#x200B;**远程**。

   ![用于选择图像的远程和本地选取选项](/help/assets/remote-asset-selection.png)

1. 随后将打开一个对话框，而您将需要向远程服务进行身份验证。

1. 经过身份验证后，将打开远程服务的资源浏览器。选择所需的资源，然后点击或单击&#x200B;**选择**。

   ![选择远程资源](/help/assets/remote-asset-picker.png)

此时已将远程资源添加到您的本地 AEM 页面，并且您已确认正确配置了该功能。

## 使用远程资源 {#using}

配置后，可在您要使用核心组件（如[图像组件](/help/components/image.md)和 [Teaser 组件](/help/components/teaser.md)中）选择资源的地方选择远程资源。
