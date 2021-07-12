---
title: AEM项目原型的ui.content模块
description: AEM项目原型的ui.content模块
feature: 核心组件、 AEM项目原型
role: Architect, Developer, Admin
exl-id: af019cd8-c733-4b53-bb57-321dd9451178
source-git-commit: 3ebe1a42d265185b36424b01844f4a00f05d4724
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 0%

---

# AEM项目原型的ui.content模块 {#uicontent-module}

ui.content maven模块(`<src-directory>/<project>/ui.content`)包含基线内容和`/content`和`/conf`下的配置。 ui.content会编译到AEM包中，与ui.apps非常类似。 主要区别在于，可以直接在AEM实例中修改存储在ui.content中的节点。 这包括页面、DAM资产和可编辑的模板。 ui.content模块可用于存储清理实例的示例内容和/或创建一些要在源代码管理中管理的基线配置。

## filter.xml {#filter}

ui.content模块的`filter.xml`文件位于`<src>/<project>/ui.content/src/main/content/META-INF/vault/filter.xml`，其中包含将随ui.content包一起包含和安装的路径。 请注意，路径中已添加`mode="merge"`属性。 这可确保通过代码部署部署的配置不会自动覆盖直接在AEM实例上创作的内容或配置。

## ui.content/pom.xml

ui.content模块与ui.apps模块类似，使用FileVault包插件。 但是， ui.content pom(`<src>/<project>/ui.content/pom.xml`)包含一个名为`acHandling`的额外配置属性，该属性设置为`merge_preserve`。 之所以会包含此权限，是因为ui.content模块包含访问控制列表(ACL)，这些列表是权限，可决定谁可以编辑模板。 要将这些ACL导入AEM，需要`acHandling`属性。
