---
title: 自定义核心组件
description: 利用核心组件实施的多种模式，可以轻松执行从简单的样式设计到高级功能重用在内的自定义设置。
role: Architect, Developer, Admin
exl-id: ec4b918b-bc70-4d72-ba84-a24556aedb41
source-git-commit: 2ac16b15718128feefbe903e92f276b16fe96f69
workflow-type: tm+mt
source-wordcount: '1100'
ht-degree: 98%

---

# 自定义核心组件{#customizing-core-components}

利用[核心组件](overview.md)实施的多种模式，可以轻松进行从简单的样式设计到高级功能重用的自定义设置。

## 灵活的架构 {#flexible-architecture}

核心组件从一开始就被设计为灵活且可扩展。大致了解其架构便能获知可在何处进行自定义设置。

![核心组件架构](/help/assets/screen_shot_2018-12-07at093742.png)

* [“设计”对话框](/help/get-started/authoring.md#edit-and-design-dialogs)定义作者在“编辑”对话框中可执行的操作或无法执行的操作。
* [“编辑”对话框](/help/get-started/authoring.md#edit-and-design-dialogs)仅向作者显示他们能够使用的选项。
* [Sling 模型](#customizing-the-logic-of-a-core-component)验证并准备视图（模板）的内容。
* 对于 SPA 使用案例，[Sling 模型的结果](#customizing-the-logic-of-a-core-component)可序列化为 JSON。
* 对于传统的服务器端渲染，[HTL 渲染 HTML](#customizing-the-markup) 服务器端。
* [HTML 输出](#customizing-the-markup)具有语义化、可访问、经搜索引擎优化、样式易设置的特征。

所有核心组件都实施[样式系统](#styling-the-components)。

## AEM 项目原型 {#aem-project-archetype}

[AEM 项目原型](/help/developing/archetype/overview.md)创建一个规模最小的 Adobe Experience Manager 项目作为您项目的起点，包括一个带 SlingModel 的自定义 HTL 组件示例，可用于带建议的代理模式的核心组件的逻辑和正确实施。

## 自定义模式 {#customization-patterns}

### 自定义对话框 {#customizing-dialogs}

可能需要自定义核心组件对话框（[“设计”对话框或“编辑”对话框](/help/get-started/authoring.md)）中提供的配置选项。

每个对话框均具有一致的节点结构。建议在继承组件中复制此结构，以便使用 [Sling 资源合并器](https://helpx.adobe.com/cn/experience-manager/6-4/sites/developing/using/sling-resource-merger.html)和[隐藏条件](https://helpx.adobe.com/cn/experience-manager/6-5/sites/developing/using/hide-conditions.html)来隐藏、替换或重新排序原始对话框的各个部分。要复制的结构定义为选项卡项节点级别下的任何内容。

要与对当前版本的对话框所做的任何更改完全兼容，请不要触及选项卡项级别下的结构（隐藏、添加到、替换、重新排序等），这一点非常重要。相反，父级中的选项卡项应通过 `sling:hideResource` 属性隐藏（请参阅 [Sling 资源合并器属性](https://helpx.adobe.com/cn/experience-manager/6-5/sites/developing/using/sling-resource-merger.html)），并且添加的新选项卡项包含定制的配置字段。`sling:orderBefore` 可用于对选项卡项重新排序（如有必要）。

下面的对话框演示了建议的对话框结构以及如何隐藏和替换上述继承的选项卡：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<jcr:root xmlns:sling="https://sling.apache.org/jcr/sling/1.0"
          xmlns:jcr="https://www.jcp.org/jcr/1.0"
          xmlns:nt="https://www.jcp.org/jcr/nt/1.0"
          xmlns:granite="https://www.adobe.com/jcr/granite/1.0"
          jcr:primaryType="nt:unstructured">
    <content jcr:primaryType="nt:unstructured">
        <items jcr:primaryType="nt:unstructured">
            <tabs jcr:primaryType="nt:unstructured">
                <items jcr:primaryType="nt:unstructured">
                        <originalTab
                                jcr:primaryType="nt:unstructured"
                                sling:hideResource="true"/>
                        </originalTab>
                        <myTab
                               jcr:primaryType="nt:unstructured"
                               jcr:title="My Tab"
                               sling:resourceType="granite/ui/components/coral/foundation/container"/>
                               <!-- myTab content -->
                        </myTab>
                </items>
            </basic>
        </items>
    </content>
</jcr:root>
```

### 自定义核心组件的逻辑 {#customizing-the-logic-of-a-core-component}

在 Sling 模型中实施核心组件的业务逻辑。可使用 Sling 委托模式扩展此逻辑。

例如，标题核心组件使用请求的资源的 `jcr:title` 属性来提供标题文本。如果未定义 `jcr:title` 属性，将对当前页面标题进行回调。我们需要更改行为，以便始终显示当前页面的标题。

由于核心组件模型的实施是私有的，因此必须使用委托模式对其进行扩展。

```java
@Model(adaptables = SlingHttpServletRequest.class,
       adapters = Title.class,
       resourceType = "myproject/components/pageHeadline")
public class PageHeadline implements Title {
    @ScriptVariable private Page currentPage;
    @Self @Via(type = ResourceSuperType.class)
    private Title title;
    @Override public String getText() {
        return currentPage.getTitle();
    }
    @Override public String getType() {
        return title.getType();
    }
}
```

有关委托模式的其他详细信息，请参阅核心组件 GitHub Wiki 文章 [Sling 模型的委托模式](https://github.com/adobe/aem-core-wcm-components/wiki/Delegation-Pattern-for-Sling-Models)。

### 自定义标记 {#customizing-the-markup}

有时，高级样式设置需要组件的其他标记结构。

通过将需要修改的 HTL 文件从核心组件复制到[代理组件](guidelines.md#proxy-component-pattern)，可轻松实现此目标。

再次以核心痕迹导航组件为例，要定义其标记输出，必须将 `breadcrumb.html` 文件复制到站点特定的组件，该组件的 `sling:resourceSuperTypes` 指向核心痕迹导航组件。

### 设置组件的样式 {#styling-the-components}

自定义设置的第一种形式是应用 CSS 样式。

为了轻松实现此目标，核心组件将渲染语义标记并遵循由 [Bootstrap](https://getbootstrap.com/) 触发的标准化命名约定。此外，为了轻松地为各个组件定位和命名样式，每个核心组件都包装在一个带有“`cmp`”和“`cmp-<name>`”类的 DIV 元素中。

例如，对于 v1 核心痕迹导航组件的 HTL 文件 [breadcrumb.html](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v2/breadcrumb/breadcrumb.html)，可以看到元素输出的层级为 `ol.breadcrumb > li.breadcrumb-item > a`。因此，为了确保 CSS 规则仅影响该组件的痕迹导航类，应命名所有规则，如下所示：

```shell
.cmp-breadcrumb .breadcrumb {}  
.cmp-breadcrumb .breadcrumb-item {}  
.cmp-breadcrumb a {}
```

此外，每个核心组件都利用 AEM [样式系统功能](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/style-system.html)，此功能可让模板作者定义可由页面作者应用于组件的其他 CSS 类名称。这将允许为每个模板定义一个允许的组件样式列表，并定义其中的某个组件样式是否默认应用于该类型的所有组件。

## 升级自定义设置的兼容性 {#upgrade-compatibility-of-customizations}

可以执行三种不同的升级：

* 升级 AEM 的版本
* 将核心组件升级到新的次要版本
* 将核心组件升级到主要版本

通常，将 AEM 升级到新版本不会影响核心组件或已完成的自定义设置，前提是组件的版本也支持正在迁移到的新 AEM 版本，并且自定义设置不使用[已弃用或被删除](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/deprecated-removed-features.html)的 API。

在不切换到更新的主要版本的情况下升级核心组件不会影响自定义设置，前提是使用本页所述的自定义设置模式。

切换到更新的主要版本的核心组件仅适用于内容结构，但可能需要重构自定义设置。将为每个组件版本发布清楚的更改日志，以突出显示将影响此页面上描述的自定义设置类型的更改。

## 支持自定义设置 {#support-of-customizations}

与任何 AEM 组件一样，有大量关于自定义设置的注意事项：

1. **绝不要直接修改核心组件的代码。**

   这将导致核心组件完全不受支持，并会使组件的将来更新成为一个痛苦的过程。相反，请使用此页面上描述的自定义设置方法。

1. **自定义代码由您自行负责。**

   我们的支持计划不会涵盖自定义代码，并且无法通过[按文档说明使用](/help/get-started/using.md)的 vanilla 核心组件重现的已报告问题不符合条件。

1. **查看已弃用和被删除的功能。**

   随着每个新 AEM 版本的升级，请密切关注[已弃用和被删除的功能](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/deprecated-removed-features.html)页面，确保所有使用的 API 仍是常用的。

另请参阅[核心组件支持](overview.md#core-component-support)部分。

**阅读下一篇文章：**

* [使用核心组件](/help/get-started/using.md) - 在您自己的项目中启动并运行核心组件。
* [组件指南](guidelines.md) - 了解核心组件的实施模式。
