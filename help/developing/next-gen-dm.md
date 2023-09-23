---
title: 下一代Dynamic Media支持
description: 了解如何配置核心组件图像和Teaser组件以支持远程新一代Dynamic Media资源。
role: Architect, Developer, Admin, User
source-git-commit: 9b8930c2e268f52a1377906725db9a05a089e233
workflow-type: tm+mt
source-wordcount: '470'
ht-degree: 1%

---


# 下一代Dynamic Media支持 {#next-gen-dm-support}

了解如何配置核心组件图像和Teaser组件以支持远程新一代Dynamic Media资源。

## 获取最新的AEM版本 {#latest}

支持新一代Dynamic Media远程资产需要：

* AEM 6.5 SP 18+或AEMas a Cloud Service
* 核心组件2.23.2版或更高版本

## 配置 HTTPS {#https}

通常建议使用HTTP来运行所有生产AEM实例。 但是，您的本地开发环境可能未进行此类设置。 但是，新一代Dynamic Media远程资产需要使用HTTPS才能正常运行。

[使用本指南](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/security/use-the-ssl-wizard.html) 以配置您想要使用远程资产（包括开发环境）的HTTPS。

## 配置OSGi {#osgi}

必须在OSGi配置中定义远程资源的位置。 配置 **新一代Dynamic Media配置** OSGi配置如下所示，将值替换为您的远程资产环境的值。

```text
imsClient="<ims-client-name>"
enabled=B"true"
imsOrg="<ims-org>@AdobeOrg"
repositoryId="<repo-id>.adobeaemcloud.com"
```

![下一代Dynamic Media配置OSGi配置窗口](/help/assets/remote-assets-osgi.png)

有关如何配置OSGi的详细信息，请参阅以下文档：

* [为Adobe Experience Manager as a Cloud Service配置OSGi](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/deploying/configuring-osgi.html) 适用于AEM的as a Cloud Service
* [配置OSGi](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/configuring/configuring-osgi.html) 适用于AEM 6.5的

## 验证配置 {#verify}

现在，您可以验证新一代Dynamic Media远程资产功能是否正在运行。 为此，您可以安装WKND示例站点和核心组件。

* [核心组件](https://github.com/adobe/aem-core-wcm-components/releases/download/core.wcm.components.reactor-2.23.2/core.wcm.components.all-2.23.2.zip) 需要2.23.2版或更高版本。
* [WKND示例站点](https://github.com/adobe/aem-guides-wknd/releases/download/aem-guides-wknd-3.2.0/aem-guides-wknd.all-3.2.0-classic.zip) 需要版本3.2.0或更高版本。

安装核心组件和WKND站点后，您可以在任何WKND页面上测试该功能。

1. 使用HTTPS访问AEM实例。

1. 在页面编辑器中打开WKND演示页面，例如 `https://<host>:<httpsPort>/editor.html/content/wknd/language-masters/en/magazine/arctic-surfing.html`

1. 向页面中添加图像组件。

1. 在组件的“配置”对话框中，取消选中选项 **从页面继承精选图像** 在 **资产** 选项卡，然后单击 **选取**.

1. 如果配置正确，将显示一个下拉列表，其中包含选项 **本地** 和 **远程**. 选择 **远程**.

   ![用于图像选择的远程和本地拾取选项](/help/assets/remote-asset-selection.png)

1. 此时将打开一个对话框，您需要对远程服务进行身份验证。

1. 一旦通过身份验证，将打开远程服务的资产浏览器。 选择所需的资产，然后点按或单击 **选择**.

   ![选择远程资产](/help/assets/remote-asset-picker.png)

远程资产将会添加到本地AEM页面，并且您已验证该功能是否已正确配置。

## 使用远程资产 {#using}

配置后，可以选择远程资产，其中您可以使用核心组件选择资产，例如 [图像组件](/help/components/image.md) 和 [Teaser组件。](/help/components/teaser.md)
