---
title: aem Project Archetype的ui.content模块
description: aem Project Archetype的ui.content模块
translation-type: tm+mt
source-git-commit: 93a7ba6b8a972d111fb723cb40b0380cea9b5a9a
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 0%

---


# aem Project Archetype {#uicontent-module}的ui.content模块

ui.content maven模块(`<src-directory>/<project>/ui.content`)包括`/content`和`/conf`下的基线内容和配置。 ui.content编译到AEM包中，与ui.apps非常相似。 主要区别在于存储在ui.content中的节点可以直接在AEM实例上修改。 这包括页面、DAM资产和可编辑的模板。 ui.content模块可用于存储干净实例的示例内容和／或创建一些要在源代码控件中管理的基线配置。

## filter.xml {#filter}

ui.content模块的`filter.xml`文件位于`<src>/<project>/ui.content/src/main/content/META-INF/vault/filter.xml`，其中包含随ui.content包一起包含和安装的路径。 请注意，`mode="merge"`属性已添加到路径。 这可确保通过代码部署部署部署的配置不会自动覆盖直接在AEM实例上创作的内容或配置。

## ui.content/pom.xml

ui.content模块（如ui.apps模块）使用FileVault包插件。 但是，ui.content pom(`<src>/<project>/ui.content/pom.xml`)包含一个名为`acHandling`的额外配置属性，该属性设置为`merge_preserve`。 其中之所以包含此选项，是因为ui.content模块包含访问控制列表(ACL)，这些权限决定了哪些人可以编辑模板。 要将这些ACL导入AEM，需要`acHandling`属性。
