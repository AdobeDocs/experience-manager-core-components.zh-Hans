---
title: AEM Forms 核心组件版本
description: 核心组件作为发行版本发布，发行版本可能包含相同核心组件的多个版本。本文档介绍了什么是发行版本和版本，以及如何了解核心组件与 AEM 的兼容性。
role: Architect, Developer, Admin, User
exl-id: 8146a5b1-acf6-4b54-ad6b-6e1747a137f6
source-git-commit: e0ed415bd7f45fdca6fbbb8ba409604d9e82a647
workflow-type: tm+mt
source-wordcount: '876'
ht-degree: 62%

---

# 核心组件版本 {#core-components-versions}

核心组件的当前发行版本是 2.0.10，与 [AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/landing/home.html?lang=zh-Hans) 兼容，核心组件 1.1.12 版与[内部部署 AEM 6.5 Form 以及 AMS](https://experienceleague.adobe.com/docs/experience-manager-65/user-guide/home.html?lang=zh-Hans) 安装兼容。

## AEM as a Cloud Service 版本历史 {#aem-as-cs-version-history}

下表列出了可在 [GitHub 上获取的与 AEM 云服务兼容的核心组件版本及其版本的全面详细信息](https://github.com/adobe/aem-core-forms-components/releases)。

| 发行版本 | 描述 | AEM as a Cloud Service | Java | 发布日期 |
|---|---|---|---|---|
| [2.0.74](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.74) | 使用此版本时，AEM Forms中的提交操作会更新提交错误。 | 连续 | 8, 11 | 2023年11月15日 |
| [2.0.70](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.70) | 此版本添加了对处理表单容器中的站点页面语言的支持。 | 连续 | 8, 11 | 2023年11月10 |
| [2.0.64](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.64) | 支持富文本作为单选框/复选框组件的标签。 此发行版本还包括对条款和条件组件的修复。 | 连续 | 8, 11 | 2023年11月6 |
| [2.0.62](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.62) | 通过此版本，添加了对“条款和条件”组件的支持。 还在核心组件中添加了对限定名称的支持。 | 连续 | 8, 11 | 2023年10月16日 |
| [2.0.60](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.60) | 此版本包括与自定义属性功能、向导和日期选取器组件相关的修复。 | 连续 | 8, 11 | 2023 年 9 月 12 日 |
| [2.0.56](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.56) | 通过这种版本，可以添加对所有核心组件的自定义属性的支持。 | 连续 | 8, 11 | 2023 年 9 月 12 日 |
| [2.0.54](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.54) | 此版本修复了与使用日期选取器组件进行本地化相关的问题。 | 连续 | 8, 11 | 2023 年 30 月 8 日 |
| [2.0.52](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.52) | 支持在自适应表单中使用复选框组件。 | 连续 | 8, 11 | 2023 年 25 月 8 日 |
| [2.0.50](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.50) | 在此版本中添加了对自适应表单中表单片段的支持。 | 连续 | 8, 11 | 2023 年 4 月 8 日 |
| [2.0.48](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.48) | 此版本中的主要改进与Lighthouse性能有关。 | 连续 | 8, 11 | 2023年7月25日 |
| [2.0.42](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.42) | 该版本在编程端进行了改进。 | 连续 | 8, 11 | 2023年7月18日 |
| [2.0.38](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.38) | 此版本改进了辅助功能。 | 连续 | 8, 11 | 2023年7月17日 |
| [2.0.36](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.36) | 在此版本中，您可以使用规则编辑器的调用服务来使用自定义错误处理程序。 | 连续 | 8, 11 | 2023年7月3日 |
| [2.0.34](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.34) | 添加了对默认错误消息的本地化支持，以及对可重复组件的添加/删除按钮。 | 连续 | 8, 11 | 2023 年 28 月 6 日 |
| [2.0.32](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.32) | 在此版本中，为自适应Forms添加了验证码支持。 | 连续 | 8, 11 | 2023 年 15 月 6 日 |
| [2.0.26](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.26) | 支持在AEM Sites中添加自适应表单。 | 连续 | 8, 11 | 2023 年 7 月 6 日 |
| [2.0.18](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.18) | 在此版本中，支持折叠组件的可重复性。 | 连续 | 8, 11 | 2023 年 5 月 6 日 |
| [2.0.10](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.10) | 在此版本中，Sites 编辑器中引入了对自适应表单容器组件的支持。 | 连续 | 8, 11 | 2023 年 3 月 17 日 |
| [2.0.8](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.8) | 此版本中引入了向导组件的可重复性功能。 | 连续 | 8, 11 | 2023 年 3 月 3 日 |
| [2.0.6](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.6) | 此版本中引入了数字输入核心组件的多种格式。 | 连续 | 8, 11 | 2023 年 2 月 8 日 |
| [2.0.4](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-2.0.6) | 此版本中引入了对 AEM as a Cloud Service 核心组件的支持。 | 连续 | 8, 11 | 2023 月 1 月 30 日 |

## AEM 6.5 Forms 版本历史记录 {#aem-as-form-version-history}

下表列出了可在 [GitHub 上获取的与内部部署 AEM 6.5 Form 以及 AMS 兼容的核心组件版本及其版本的全面详细信息](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-1.1.12)。

| 发行版本 | 描述 | AEM 6.4 | AEM 6.5 | Java | 发布日期 |
|---|---|---|---|---|---|
| [1.1.32](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-1.1.32) | 此版本更新了AEM Service Pack 6.5.18.0的包信息。 | - | 6.5.16.0+ | 8, 11 | 2023年10月15日 |
| [1.1.28](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-1.1.28) | 支持富文本作为单选框/复选框组件的标签。 此发行版本还包含对条款和条件组件的支持。 | - | 6.5.16.0+ | 8, 11 | 2023年10月15日 |
| [1.1.26](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-1.1.26) | 此发行版本添加了对“自适应表单”复选框组件的支持。 其中还包括灯塔性能的改进。 此版本中还包括使用规则编辑器的调用服务的自定义错误处理程序。 | - | 6.5.16.0+ | 8, 11 | 2023年10月15日 |
| [1.1.24](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-1.1.24) | 添加了对默认错误消息的本地化支持，以及对可重复组件的添加/删除按钮。 另外还增加了在自适应Forms中对recaptcha的支持。 | - | 6.5.16.0+ | 8, 11 | 2023 年 29 月 6 日 |
| [1.1.22](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-1.1.22) | 支持在AEM Sites中添加自适应表单。 在向导和垂直选项卡组件的“编辑”对话框中添加了“项”选项卡。 | - | 6.5.16.0+ | 8, 11 | 2023 年 07 月 6 日 |
| [1.1.12](https://github.com/adobe/aem-core-forms-components/releases/tag/core-forms-components-reactor-1.1.12) | 此版本中引入了对内部部署 AEM Forms 和 AMS 核心组件的支持。 | - | 6.5.16.0+ | 8, 11 | 2023 年 2 月 8 日 |

## 另请参阅 {#see-also}

{{see-also}}