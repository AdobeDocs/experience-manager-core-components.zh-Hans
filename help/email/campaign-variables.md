---
title: 促销活动变量
description: 使用促销活动变量作为占位符来撰写个性化电子邮件内容。
role: Architect, Developer, Admin, User
hidefromtoc: true
index: false
source-git-commit: 8bebe3ca036557f3f7c6b8ec0e65d6d104d5ffae
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 促销活动变量 {#campaign-variables}

使用促销活动变量撰写个性化电子邮件内容。 促销活动变量用作Adobe Campaign值的占位符，您可以将这些值插入到电子邮件内容中。 通过Adobe Campaign发送内容时，Campaign会将这些变量替换为收件人的个性化内容。

## 用途 {#usage}

电子邮件核心组件通过常用文本字段旁边的个性化按钮，使营销活动变量易于访问。 按下该键后，将显示一个对话框，您可以从中选择个性化字段。

可用的个性化字段列表已与您的Adobe Campaign实例同步。 这些字段在架构的Adobe Campaign中进行管理 `nms:seedMember`. 中的所有字段 `nms:seedMember` 收件人表中也必须存在。

## 选择Adobe Campaign变量对话框 {#dialog}

选择Adobe Campaign变量对话框在电子邮件核心组件的许多编辑对话框中可用。 要使用它，只需单击 **选择Adobe Campaign变量** 图标。 此图标可采用两种形式。

![Adobe Campaign按钮](/help/email/assets/campaign-button.png)
![选择Adobe Campaign变量图标](/help/email/assets/select-adobe-campaign-variable-icon.png)

单击两个图标将打开 **选择Adobe Campaign变量** 对话框。

![选择Adobe Campaign变量对话框](assets/select-campaign-variable-dialog.png)

使用列视图可查找要插入的变量。 单击列中的节点会在右侧的新列中显示其子项。 这样，您就可以导航变量内容结构。

选择要插入的变量，然后单击对话框右上角的复选标记。

![Adobe Campaign变量已选择](assets/select-campaign-variable-dialog-selected.png)

然后，该变量会插入到电子邮件核心组件的编辑对话框的字段中。

![插入到编辑对话框的促销活动变量](assets/campaign-variable.png)

随时单击对话框左上角的X以取消和关闭对话框。
