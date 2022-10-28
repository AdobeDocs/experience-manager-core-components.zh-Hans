---
title: 电子邮件体验片段组件
description: 电子邮件体验片段组件允许内容作者在支持本地化内容结构的同时，在其内容中放置体验片段变量。
role: Architect, Developer, Admin, User
hidefromtoc: true
index: false
source-git-commit: 8bebe3ca036557f3f7c6b8ec0e65d6d104d5ffae
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 电子邮件体验片段组件 {#email-experience-fragment-component}

电子邮件体验片段组件允许内容作者在支持本地化内容结构的同时，在其内容中放置体验片段变量。

## 用途 {#usage}

电子邮件体验片段组件允许内容作者从现有体验片段变量中进行选择，然后在内容中放置一个。 体验片段是包含内容和布局的一组内容，可跨渠道重复使用。

* 组件的属性可在[“配置”对话框](#configure-dialog)中定义。
* 将组件添加到内容时，该组件的默认值可在 [设计对话框](#design-dialog).

电子邮件体验片段组件支持本地化的站点结构。

## 版本和兼容性 {#version-and-compatibility}

电子邮件体验片段组件的当前版本为v1，该版本于2022年10月随电子邮件核心组件X版引入，在本文档中进行了描述。

下表详细说明了该组件的所有受支持版本、与该组件的版本兼容的 AEM 版本以及指向早期版本文档的链接。

| 组件版本 | AEM 6.5 | AEM as a Cloud Service |
|---|---|---|
| v1 | 兼容 | 兼容 |

有关电子邮件核心组件版本和版本的更多信息，请参阅此文档 [电子邮件核心组件版本。](/help/email/versions.md)

## 本地化网站结构支持 {#localized-site-structure}

电子邮件体验片段组件是对本地化的内容结构进行自适应的，并根据内容的本地化来呈现正确的体验片段。 要实现此目的，体验片段必须满足以下条件。

* 电子邮件体验片段组件已添加到 [页面模板。](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/features/templates.html)
* 该模板用于创建新的内容页面，这些页面是 `/content/<site>` 以下的本地化结构的一部分。
* 内容页面上引用的体验片段是下面本地化的体验片段结构的一部分 `/content/experience-fragments` 模式与下面站点相同 `/content/<site>` 包括使用相同的组件名称。

在本例中，具有相同本地化([语言、Blueprint或Live Copy](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/administering/reusing-content/msm-and-translation.html))，因为当前页面将作为模板的一部分呈现。

此行为仅限于添加到模板的电子邮件体验片段组件。 添加到单个内容页面的体验片段组件将呈现该组件中配置的确切体验片段演绎版。

* 有关体验片段组件的本地化功能如何工作的示例，请参阅 [以下部分](#example).
* 有关核心组件的本地化功能如何配合使用的示例，请参阅[核心组件页面的本地化功能](/help/get-started/localization.md)。

### 示例 {#example}

假设您的内容与以下内容类似：

```
/content
+-- experience-fragments
   \-- wknd
      +-- language-masters
      +-- us
         +-- en
            +-- footerTextXf
            \-- headerTextXf
         \-- es
            +-- footerTextXf
            \-- headerTextXf
      \-- ch
         +-- de
            +-- footerTextXf
            \-- headerTextXf
         +-- fr
            +-- footerTextXf
            \-- headerTextXf
         \-- it
            +-- footerTextXf
            \-- headerTextXf
+-- wknd
   +-- language-masters
   +-- us
      +-- en
      \-- es
   +-- ch
      +-- de
      +-- fr
      \-- it
+-- wknd-events
\-- wknd-shop
```

请注意，`/content/experience-fragments/wknd` 以下的结构镜像了 `/content/wknd` 的结构。

在本例中，如果电子邮件体验片段组件 `/content/experience-fragments/wknd/us/en/footerTextXf` 置于模板上，则基于该模板创建的本地化页面将自动呈现与本地化内容页面对应的本地化体验片段。

因此，如果您要导航到 `/content/wknd/ch/de` 下使用同一模板的内容页面，则将渲染 `/content/experience-fragments/wknd/ch/de/footerTextXf` 而不是 `/content/experience-fragments/wknd/us/en/footerTextXf`。

### 回退 {#fallback}

电子邮件体验片段组件将尝试按以下顺序查找相应的本地化组件。

1. 首先尝试查找语言根。
1. 如果未找到，则尝试查找 Blueprint。
1. 如果未找到，则尝试查找实时副本。
1. 如果未找到，则默认使用组件中配置的体验片段。

## 示例组件输出 {#sample-component-output}

要体验电子邮件体验片段组件并查看其配置选项以及HTML和JSON输出的示例，请访问 [组件库。](https://adobe.com/go/aem_cmp_library_email_xf)

## 技术详细信息 {#technical-details}

有关体验片段组件的最新技术文档 [可在GitHub上找到。](https://adobe.com/go/aem_cmp_email_tech_xf_v1)

有关开发核心组件的更多详细信息，请参阅 [核心组件开发人员文档。](/help/developing/overview.md)

## “配置”对话框 {#configure-dialog}

配置对话框允许内容作者选择应在内容中呈现的体验片段变量。

![电子邮件体验片段组件的编辑对话框](/help/email/assets/email-experience-fragment-edit.png)

使用 **打开选择对话框** 按钮以打开组件选择器，以选择要添加到内容页面的体验片段组件变量。

如果您将电子邮件体验片段组件添加到模板，则它将自动本地化，前提是体验片段已本地化，因此页面上呈现的内容可能与您明确选择的组件有所不同。 有关更多信息，[请参阅以上示例](#example)。

您还可以定义 **ID**。此选项允许控制HTM中组件的唯一标识符。

* 如果留空，则会自动为您生成唯一ID，并且可以通过检查生成的内容来找到该ID。
* 如果指定一个 ID，作者有责任确保它是唯一的。
* 更改ID可能会对CSS产生影响。

### 样式选项卡 {#styles-tab-edit}

电子邮件体验片段组件支持AEM [样式系统。](/help/get-started/authoring.md#component-styling)

使用下拉菜单选择要应用于该组件的样式。在“编辑”对话框中所做的选择与从组件工具栏中选择的操作效果相同。

必须在 [设计对话框](#design-dialog) 以使选项卡可用。

## “设计”对话框 {#design-dialog}

设计对话框允许模板作者定义可供使用电子邮件体验片段组件的内容作者使用的选项，以及在放置电子邮件体验片段组件时设置的默认值。

### 样式选项卡 {#styles-tab}

电子邮件体验片段组件支持AEM [样式系统。](/help/get-started/authoring.md#component-styling)
