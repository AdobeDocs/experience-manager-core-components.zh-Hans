---
title: 使用Adobe Client Data Layer集成核心组件和Adobe Launch
description: 如何配置Adobe Launch以使用Adobe Launch注册核心组件事件
translation-type: tm+mt
source-git-commit: f930a0d6004a29369b189137dd9c52e637ea3a61
workflow-type: tm+mt
source-wordcount: '1160'
ht-degree: 1%

---


# 使用Adobe Client Data Layer集成核心组件和Adobe Launch {#launch-integration}

核心组件可以通过使用Adobe客户端数据层与Adobe Launch集成。 本文档以图像组件为例，介绍如何配置Adobe Launch以跟踪单击事件。

配置后，当单击核心图像组件时，Launch将在浏览器控制台中生成以下输出。

![控制台输出示例](/help/assets/launch-console-output.png)

## Launch与AEM集成 {#launch-aem}

首先，必须将Adobe Launch与您的AEM站点集成。

### 步骤1 —— 在Adobe I/O中创建集成 {#create-io-integration}

首先登录Adobe I/O以开始配置集成。

1. 转到 `https://console.adobe.io`.
1. 使用您的Adobe ID登录。
1. 在“快速开始”部分，单击“ **创建集成**”。
1. Select **Access an API** and click **Continue**.
1. 在Adobe **Experience Platform下选择** Experience Platform Launch API，然后单击 **继续**。

### 第2步——在AEM中创建IMS配置 {#ims-configuration}

在AEM中，您需要定义在Adobe I/O中开始配置的集成。

1. 转到AEM主页，单击 **工具->安全-> Adobe IMS配置**。
1. 单击&#x200B;**创建**。
1. 作为 **云解决方案**，选择 **Adobe Launch**。
1. 选中 **创建新证书**。
1. 输入证书的别名， **如aem-launch-certificate**。
1. 单 **击“Create** certificate **（创建证书）” ，然后在弹出** 窗口中单击“OK（确定）”以创建证书。
1. 单 **击“下载公钥** ”，然后在弹出窗口中单击“ **下载”**。

### 步骤3 —— 完成Adobe I/O配置 {#finish-io}

使用在AEM IMS配置中创建的证书和密钥，您可以完成Adobe I/O配置。

1. 按步骤1返回Adobe I/O控 [制台。](#create-io-integration)
1. 在创 **建新集成窗口** ，输入名称和说明，如 **AEM Launch数据层**。
1. 在“ **公钥证书**”下，上传您在步骤2中创建 [的证书。](#ims-configuration)
1. 选择“ **启动——产品”用户档案**。
1. Click **Create integration**.
1. 单击“ **继续”以查看集成详细信息**。 您以后需要这些详细信息才能在AEM实例中完成IMS配置。

### 第4步——完成IMS配置 {#finish-ims}

通过Adobe I/O集成详细信息，您可以完成AEM IMS配置。

1. 在AEM选项卡的步骤2 **的Adobe IMS技术帐户配** 置选项卡中 [，单](#ims-configuration) 击下一 **步**。
1. 输入标题，如 **Adobe Launch的IMS配置**。
1. 在Adobe I/O选项卡中，复制 **API密钥（客户端ID）**。
1. 在AEM选项卡中，将前一个复制的密钥粘贴到API **密钥字段中**。
1. 在Adobe I/O中，单击“检 **索客户端机密** ”并复制它。
1. 在AEM选项卡中，将其粘贴到“客户端 **机密** ”字段。
1. 在Adobe I/O选项卡中，选择 **JWT** 选项卡并复制URL，如 `https://ims-na1.adobelogin.com`。
1. 在AEM选项卡中，将URL粘贴到“授权服 **务器”字** 段中。
1. 在Adobe I/O选项卡中，复制JWT有效负荷（大括号之间的代码）。
1. 在AEM选项卡中，将其粘贴到“有效 **负荷** ”字段。
1. 单击 **创建** ，在AEM中创建IMS配置。

### 第5a步——在Adobe Launch中创建属性 {#create-property}

属性定义Launch可以注入到您的站点的功能。

1. 请访问 `https://launch.adobe.com`Adobe Launch。
1. 使用您的Adobe ID登录。
1. 单击 **新建属性**。
1. 输入名称，如 **启动AEM数据层**。
1. 输入您的域。
1. 单击&#x200B;**保存**。

### 第5b步——在启动项中创建规则 {#launch-rule}

使用您创建的属性，您可以定义规则，该规则指定在发生操作时应发生的情况。

1. 单击步骤5启动AEM数 [据层](#create-property)**中新添加的属性**。
1. 选择“规 **则** ”选项卡，然 **后单击“创建新规则”**。
1. 输入名称，如 **按住图像单击**。
1. 单击 **事件** 下的+ **按钮**。
1. 选择 **核心** ，作 **为扩展**, **单击即** 事件类型和进 ************&#x200B;入和。cmp-image选择器。
1. 单击 **保留更改**。
1. 单击“ **操作** ”下的 **+按钮**。
1. 选择 **核心** ，作 **为扩展**，自定 **义代码，作** 为操作类型和 ********&#x200B;点击Open Editor。
1. 在编辑器中，输入以下代码： `console.log("DOM click event tracked by Launch for image: ", event.target.src);`
1. 单击&#x200B;**保存**。
1. 单击 **保留更改**。
1. 单击 **保存** ，以创建新规则。

### 第6步——发布启动规则 {#publish-rule}

要使新规则可用于您的AEM站点，您需要发布它。

1. 在Adobe **Launch选项卡** ，选择“发 **布”选** 项卡。
1. 单击“ **添加新库”**。
1. 根据需要 **输入** “名称”, **如demo-1**。
1. 对于 **环境** ，根据需要选择， **如开发（开发）**。
1. 单击 **添加资源**。
1. 选择 **规则->图像——单击->最新** ，然 **后单击选择并创建新修订**。
1. 单击&#x200B;**保存并构建用于开发**。
1. 在弹出窗口中，单击“ **应用更新”并继续**。
1. 构建库时，单击省略号图标，然后选择“ **提交以供审批**”。
1. 在弹出窗口中单击 **提交**。
1. 单击省略号图标，然后选 **择“构建以进行升级**”。
1. 生成完成后，单击省略号图标，然后选择“ **批准发布”**。
1. 在弹出窗口中单击 **批准**。
1. 单击省略号图标，然后选 **择构建并发布到生产**。
1. 在弹出窗口中单击 **发布**。

### 第7步——为您的站点启用云配置 {#enable-configurations}

要使用集成，需要在AEM中将其分配为云配置。

1. 在AEM控制台中，单击 **工具->常规->配置浏览器**。
1. 检查核心 **组件示例** ，然后单 **击属性**。
1. 检查云 **配置** ，然后单 **击保存并关闭**。

### 第8步——在AEM中创建与站点的Launch集成 {#create-launch-integration}

AEM需要与Launch集成才能与Launch结合使用

1. 在AEM控制台中，单 **击工具->云服务-> Adobe Launch配置**。
1. 选择 **核心组件示例** ，然后单 **击创建**。
1. 输入标 **题** ，如 **启动配置**。
1. 选择您在步骤4中创建的 [IMS配置。](#finish-ims)
1. 根据 **公司** ，根据需要进行选择。
1. 作为 **属性** ，选择在步骤5中创建的新添 [加的启动属性。](#create-property)
1. 将“作 **者上的包含生产代码** ”滑块移到右侧，然后单击“下 **一步”**。
1. 单击&#x200B;**下一步**。
1. 单击&#x200B;**下一步**。
1. 单击&#x200B;**创建**。

### 第9步——将AEM站点连接到启动项集成 {#connect-aem}

要使AEM使用Launch集成，需要将其分配为云配置。

1. 在AEM控制台中，单击“ **站点** ”并检查 **核心**&#x200B;组件站点。
1. 单击&#x200B;**属性**.
1. Select the **Advanced** tab.
1. 在云 **配置中**，选择核 **心组件示例** ，然后单 **击选择**。
1. Click **Save &amp; Close**.

### 第10步——验证启动逻辑是否应用于页面 {#verify-launch}

测试到目前为止的步骤是否成功。

1. 在预览模式下打开核心组件库的图像页面： `http://<lhost&gt;:<port&gt;/editor.html/content/core-components-examples/library/page-authoring/image.html`
1. 单击图像并验证消息是 `A Core Image was clicked` 否显示在浏览器控制台中。

## 启动与AEM和数据层的集成 {#data-layer-launch}

现在，AEM与Launch之间的集成已设置完毕，我们可以与数据层集成。

### 第1步——在Adobe Launch中创建规则 {#create-rule}

重复第5步 [中的步骤](#launch-rule) ，以使用以下值在Adobe Launch中添加新规则。

* 名称: `image-click-data-layer`
* 事件:
   * 扩展： 核心
   * 事件类型: DOM就绪
* 操作:
   * 扩展： 核心
   * 操作类型： 自定义代码
   * 代码：

      ```
        function onImageClick(event) {
          console.log("Data layer click event tracked by Launch for image: " + event.info.path);
          console.log("dataLayer.getState(): ", adobeDataLayer.getState()); 
        }
        adobeDataLayer.addEventListener('image clicked', onImageClick);
      ```

### 第2步——发布启动规则，使其可用于您的AEM站点 {#publish-rule-2}

重复第6步 [中的步骤](#publish-rule) ，发布新规则。

### 第3步——验证启动逻辑是否已应用于页面 {#verify}

1. 在预览模式下打开核心组件库的图像页面： `http://<host&gt;:<port&gt;/editor.html/content/core-components-examples/library/page-authoring/image.html`
1. 单击图像并验证以下消息是否显示在浏览器控制台中：

   ![数据层控制台输出](/help/assets/data-layer-console-output.png)
