---
title: 使用Adobe Client Data Layer集成核心组件和Adobe Analytics
description: 如何配置Adobe Analytics以注册核心组件事件
translation-type: tm+mt
source-git-commit: f930a0d6004a29369b189137dd9c52e637ea3a61
workflow-type: tm+mt
source-wordcount: '1000'
ht-degree: 2%

---


# 使用Adobe Client Data Layer集成核心组件和Adobe Analytics {#analytics-integration}

此文档详细介绍了如何设置基于AEM、Adobe Client Data Layer、Adobe Launch和Adobe Analytics的端对端配置以跟踪：

* 载入页面时存储在Adobe客户端数据层中的页面ID
* 单击图像时存储在Adobe客户端数据层中的图像路径

它以核心组件为例，但可用于您自己的自定义组件。

##  第1步——在Adobe Analytics中创建报表包 {#create-report-suite}

要聚合和分析数据，必须先创建报表包。

1. 转到 `https://analytics.adobe.com`.
1. 使用您的Adobe ID登录。
1. Click the **Analytics** icon.
1. 转至“管 **理员”->“报表包”**。
1. 单击 **新建->报表包**。
1. 填写表单：
   1. **报表包 ID**: `yourSuiteID`
   1. **站点标题**: `Your suite description`
   1. **时区**: 酌情
   1. **起始日期**: 当天或酌情
   1. **估计每天的页面视图**: 100或酌情
1. 单击 **创建报表包**。

如果成功，您将以绿色收到以下消息： `Report Suite <yourReportSuite> has been successfully created.`

## 第2步——使报表包可见 {#make-visible}

要使用新报表包，必须可见。

1. 转到 `https://adminconsole.adobe.com`.
1. 使用您的Adobe ID登录。
1. 单击 **Adobe Analytics - &lt;您的站点>卡**
1. 单击“ **Adobe Analytics - &lt;您的站点>** ”链接
1. Select the **Permissions** tab
1. 单击“ **报表** 包”行 **的“编辑** ”按钮
1. 单击您 **在** 步骤1中创建的报表包的+ [按钮](#create-report-suite) ，将其添加到“包 **含的权限项** ”类别。
1. 单击&#x200B;**保存**。

## 步骤3 —— 将AEM站点与Adobe Launch集成 {#integrate-launch}

必须将Launch与AEM站点集成，才能生成数据。

按照使用Adobe Client Data [层中的步骤集成核心组件和Adobe Launch](launch-integration.md) 文档。

## 第4步——在Adobe Launch中安装和配置Adobe Analytics扩展 {#install-extension}

Adobe Analytics Extension支持Analytics与Launch的集成。

1. 在Adobe Launch中，选择您在步骤3中创建的新 [添加属性。](#integrate-launch)
1. 导航到“扩 **展** ”选项卡并选 **择目录**。
1. 搜索 **Adobe Analytics**。
1. 单击&#x200B;**安装**。
1. 配置扩展。
   1. 输入在 **步骤1中为相应**[环境创建的](#create-report-suite) Analytics Report Suite ID
   1. 将字 **符集设** 置为UTF-8
1. 单击保存

## 第5步——在Adobe Launch中为页面ID创建数据元素 {#create-data-element}

启动项中需要数据元素才能跟踪页面ID。

1. 在Adobe Launch中，选择在步骤3中创建 [的属性。](#integrate-launch)
1. 选择“数 **据元素** ”选项卡，然 **后单击“添加数据元素**:
   1. **名称**: `dl-page-id`
   1. **扩展**: **核心**
   1. **数据元素类型**: **自定义代码**
1. 单击“ **打开编辑器”**
1. 在编辑器中，输入代码： `return adobeDataLayer.getState().page.id;`
1. 单击&#x200B;**保存**。
1. 单击 **保存** ，以创建数据元素。

## 第6步——在Adobe Launch中创建规则以在Analytics中跟踪页面ID {#track-page}

规则允许跟踪Analytics中的页面ID等浏览属性。

重复使用Adobe Client Data Layer集 [成核心组件和Adobe Launch文档第5b部分中的步骤](launch-integration.md#launch-rule) ，在Adobe Launch中添加以下规则：

* **名称**: `track-dl-page-id`
* 事件:
   * **扩展**: **核心**
   * **事件类型**: **页面底部**
* 操作1:
   * **扩展**: **Adobe Analytics**
   * **操作类型**: **设置变量**
   * **prop1**: `%dl-page-id%`
* 操作2:
   * **扩展**: **Adobe Analytics**
   * **操作类型**: **发送信标**
   * 检 **查s.t(): 将数据发送到Adobe Analytics并视其为页面视图**

## 第7步——在Adobe Launch中创建规则以注册图像单击事件 {#register-click}

规则允许跟踪浏览属性，如Analytics中的单击事件。

重复使用Adobe Client Data Layer集 [成核心组件和Adobe Launch文档第5b部分中的步骤](launch-integration.md#launch-rule) ，在Adobe Launch中添加以下规则：

* **名称**: `register-dl-image-click`
* 事件:
   * **扩展**: **核心**
   * **事件类型**: **页面底部**
* 操作1:
   * **扩展**: **核心**
   * **操作类型**: **自定义代码**
   * 编辑器： 输入以下代码

      ```
      var myListener = function(event) {
        _satellite.track('dlImageClicked', event.info.path);
      };
      adobeDataLayer.addEventListener('image clicked', myListener());
      ```

## 第8步——在Adobe Launch中创建规则以跟踪Analytics中的图像单击事件 {#track-click}

规则允许跟踪浏览属性，如Analytics中的单击事件。

重复使用Adobe Client Data Layer集 [成核心组件和Adobe Launch文档第5b部分中的步骤](launch-integration.md#launch-rule) ，在Adobe Launch中添加以下规则：

* **名称**: `track-dl-image-click`
* 事件:
   * **扩展**: **核心**
   * **事件类型**: **直接呼叫**
   * **标识符**: `dlImageClicked`
* 操作1:
   * **扩展**: **Adobe Analytics**
   * **操作类型**: **设置变量**
   * **prop2**: 设置为 `%event.detail%`
* 操作2:
   * **扩展**: **Adobe Analytics**
   * **操作类型**: **发送信标**
   * 检 **查s.t(): 将数据发送到Adobe Analytics并视其为页面视图**

## 第9步——将启动代码发布到您的网站 {#publish-launch}

要在启动项中启用对这些规则和属性的跟踪，必须发布代码。

1. 在Adobe **Launch选项卡** ，选择“发 **布”选** 项卡。
1. 单击“ **添加新库”**。
1. 输入 **名称** : `data-layer-analytics-1`.
1. 作为 **环境** , **选择开发（开发）**。
1. 单击“ **添加所有更改的资源”**。
1. 对于以下三个规则(`track-dl-page-id`、 `register-dl-image-click` 和 `track-dl-image-click`):
1. 选择 **规则->规则->最新** ，然后 **单击选择并创建新修订**。
1. 单击&#x200B;**保存并构建用于开发**。

## 第10步——触发页面将信息发送到Adobe Analytics {#trigger-page}

在此步骤中，您将安装Chrome扩 **展Launch和DTM Switch**。 借助此扩展，您只需构建启动代码并将其部署到开发环境。 无需部署暂存和生产环境。

1. 从Discovery安装Chrome **扩展Launch和DTM** Switch。
1. 单击“ **启动开关** ”图标，将“调试”设 *置为ON*。
1. 重新加载页面 `http://<host>:<port>/content/core-components-examples/library/image.html`.
1. 打开浏览器控制台，您会看到类似以下内容的内容。

![Analytics控制台输出](/help/assets/analytics-console-output.png)

>[!TIP]
>
>您还可以安装 **Chrome的Experience Cloud** Debugger扩展，以视图Adobe Launch和Analytics有关页面的特定信息。

## 第11步——在Adobe Analytics中视图跟踪信息 {#view-info}

现在，您可以视图在Adobe Analytics中触发的事件。

1. 转到 `https://analytics.adobe.com`.
1. 使用您的Adobe ID登录。
1. Click the **Analytics** icon.
1. Select the **Reports** tab.
1. 在右上方的下拉菜单中，选择您在步骤1中创建的 [报表包。](#create-report-suite)
1. 在第一列中，选 **择自定义流量->自定义流量1-10 ->自定义分析** 1以视图数据层中存储的跟踪页面ID（路径）。 它应类似于以下内容。

   ![自定义分析1](/help/assets/custom-insight-1.png)

1. 访问 **Custom Insight 2** ,视图数据层中存储的跟踪图像路径。 它应类似于以下内容。

   ![自定义分析2](/help/assets/custom-insight-2.png)
