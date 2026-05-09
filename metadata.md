---
product: adobe experience manager
solution: Experience Manager, Experience Manager Sites
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
  - id: c45915cf-e157-4af7-a80d-97b905bcb3a5
landing-page-name: experience-manager
landing-page-breadcrumb-title: AEM
type: Documentation
description: Adobe Experience Manager核心组件文档
git-repo: https://github.com/AdobeDocs/experience-manager-core-components.en
index: true
recommendations: noDisplay
source-git-commit: 1525c048c6ab66e6b483e1110ea3dbfd926378be
workflow-type: tm+mt
source-wordcount: 120
ht-degree: 1%

---


# 元数据供内部使用

GitHub创作系统中的元数据是分层的，并定义了以下相对于前一项的递增级别。

1. metadata.md
1. ToC
1. 文章

在metadata.md文件中定义的元数据应用到整个存储库，但可以在ToC和文章级别覆盖。 任何覆盖元数据的操作应在尽可能最低的级别进行。

experience-manager-core-components.en存储库中的元数据是最低要求。

metadata.md

* `product`
* `git-repo`
* `index: true`
* `solution-title`
* `solution-hub-url`
* `getting-started-title`
* `getting-started-url`
* `tutorials-title`
* `tutorials-url`

ToCs

* `sub-product`
* `user-guide-title`

文章

* `title`
* `description`
* `index: false` （仅适用于组件的以前版本）

有关元数据的其他信息可在[内部创作指南中找到。](https://experienceleague.adobe.com/docs/authoring-guide-exl/using/authoring/features/metadata.html#solution)
