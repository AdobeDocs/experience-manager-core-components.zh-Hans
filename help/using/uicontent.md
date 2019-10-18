---
title: AEM Project Archetype的ui.content模块
seo-title: AEM Project Archetype的ui.content模块
description: AEM Project Archetype的ui.content模块
seo-description: AEM Project Archetype的ui.content模块
contentOwner: 博纳特
content-type: 参考文件
topic-tags: 核心组件
translation-type: tm+mt
source-git-commit: 3c37b57eb72d1d662cdbd41ca54cdc592919203c

---


# AEM Project Archetype的ui.content模块 {#uicontent-module}

ui.content maven模块(`<src-directory>/<project>/ui.content`)包括和下方的基准内容和 `/content` 配置 `/conf`。 ui.content编译到AEM包中，与ui.apps非常相似。 主要区别在于，存储在ui.content中的节点可以直接在AEM实例上修改。 这包括页面、DAM资产和可编辑的模板。 ui.content模块可用于存储干净实例的示例内容和／或创建一些要在源代码控件中管理的基准配置。

## filter.xml {#filter}

ui. `filter.xml` content模块的文件位于，并 `<src>/<project>/ui.content/src/main/content/META-INF/vault/filter.xml` 包含将随ui.content包一起包含和安装的路径。 请注意， `mode="merge"` 向路径添加了属性。 这可确保通过代码部署部署部署的配置不会自动覆盖在AEM实例上直接创作的内容或配置。

## ui.content/pom.xml

ui.content模块与ui.apps模块一样，使用FileVault包插件。 但是，ui.content pom(`<src>/<project>/ui.content/pom.xml`)包含一个名为的额外配置属 `acHandling`性，设置为 `merge_preserve`。 其中之所以包含这一功能，是因为ui.content模块包含访问控制列表(ACL)，这些列表是权限，决定哪些人可以编辑模板。 要将这些ACL导入AEM，需要 `acHandling` 属性。
