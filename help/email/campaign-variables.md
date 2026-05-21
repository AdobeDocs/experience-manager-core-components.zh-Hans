---
title: Campaign 变量
description: 使用 Campaign 变量作为占位符来撰写个性化的电子邮件内容。
role: Developer, Admin, User
exl-id: 124ff5bf-6612-4baf-b0ff-6b1a95b455c1
index: false
TQID: https://experienceleague.adobe.com/MB6K-S4DZbsD3puXls8w4rWi6posFFLxJRewKORMkxA
product_v2: id: c45915cf-e157-4af7-a80d-97b905bcb3a5id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: eb3ad9f8-54a2-45f3-abb1-d3976415a718
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: ce44533e-8ec8-4e11-a9e9-78b0fe561832id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 73aa5234ac63fa3be99feebce448bb6722513838
workflow-type: tm+mt
source-wordcount: 296
ht-degree: 100%

---

# Campaign 变量 {#campaign-variables}

使用 Campaign 变量来撰写个性化的电子邮件内容。 Campaign 变量充当您可以插入到电子邮件内容中的 Adobe Campaign 值的占位符。 通过 Adobe Campaign 发送内容时，Campaign 会将这些变量替换为收件人的个性化内容。

## 用途 {#usage}

电子邮件核心组件可通过常用文本字段旁边的个性化按钮轻松访问 Campaign 变量。 按下时，会出现一个对话框，您可以从中选择个性化字段。

可用个性化字段列表与您的 Adobe Campaign 实例同步。 这些字段在 Adobe Campaign 中的架构 `nms:seedMember` 中进行管理。 `nms:seedMember` 中的所有字段也必须出现在您的收件人表中。

## 选择 Adobe Campaign 变量对话框 {#dialog}

选择 Adobe Campaign 变量对话框在电子邮件核心组件的许多编辑对话框中可用。 要使用它，只需单击适用字段旁边的&#x200B;**选择 Adobe Campaign 变量**&#x200B;图标。 这个图标可以有两种形式。

![Adobe Campaign 按钮](/help/email/assets/campaign-button.png)
![选择 Adobe Campaign 变量图标](/help/email/assets/select-adobe-campaign-variable-icon.png)

单击这两个图标将打开&#x200B;**选择 Adobe Campaign 变量**&#x200B;对话框。

![选择 Adobe Campaign 变量对话框](assets/select-campaign-variable-dialog.png)

使用列视图定位您要插入的变量。 单击列中的节点会在右侧的新列中显示其子节点。 通过这种方式，您可以导航可变的内容结构。

选择要插入的变量，然后单击对话框右上角的复选标记。

![已选择 Adobe Campaign 变量](assets/select-campaign-variable-dialog-selected.png)

然后将该变量插入到电子邮件核心组件的编辑对话框的字段中。

![Campaign 变量插入到编辑对话框中](assets/campaign-variable.png)

随时单击对话框左上角的 X 可取消并关闭对话框。
