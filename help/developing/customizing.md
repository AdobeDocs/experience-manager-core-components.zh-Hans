---
title: 自定义核心组件
description: 核心组件采用多种模式，从简单的样式设计到高级功能重用，这些模式允许轻松定制。
role: 架构师、开发人员、管理员
translation-type: tm+mt
source-git-commit: d01a7576518ccf9f0effd12dfd8198854c6cd55c
workflow-type: tm+mt
source-wordcount: '1109'
ht-degree: 2%

---


# 自定义核心组件{#customizing-core-components}

[核心组件](overview.md)实现了多种可轻松自定义的模式，从简单的样式到高级功能重用。

## 灵活的架构{#flexible-architecture}

核心组件从一开始就设计为灵活且可扩展。 查看其架构的概述，可了解可在何处进行自定义。

![核心组件架构](/help/assets/screen_shot_2018-12-07at093742.png)

* [设计对](/help/get-started/authoring.md#edit-and-design-dialogs) 话框定义作者在编辑对话框中可以或不能执行的操作。
* [编辑对](/help/get-started/authoring.md#edit-and-design-dialogs) 话框仅向作者显示允许他们使用的选项。
* [Sling模型](#customizing-the-logic-of-a-core-component) 验证并准备视图（模板）的内容。
* [Sling模型的结果可](#customizing-the-logic-of-a-core-component) 以序列化为SPA用例的JSON。
* [HTL呈现HTML服](#customizing-the-markup) 务器端，用于传统的服务器端呈现。
* [HTML输出具](#customizing-the-markup) 有语义性、可访问性、经过优化的搜索引擎，并且易于设置样式。

所有核心组件都实现[样式系统](#styling-the-components)。

## AEM 项目原型 {#aem-project-archetype}

[AEM Project Archety将最](/help/developing/archetype/overview.md) 小的Adobe Experience Manager项目视为您自己项目的起点，包括一个包含SlingModels的自定义HTL组件的示例，用于逻辑和使用推荐的代理模式正确实施核心组件。

## 自定义模式{#customization-patterns}

### 自定义对话框{#customizing-dialogs}

可能需要自定义核心组件对话框中的可用配置选项，无论是[设计对话框还是编辑对话框](/help/get-started/authoring.md)。

每个对话框都具有一致的节点结构。 建议在继承组件中复制此结构，以便[Sling Resource Mergare](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/sling-resource-merger.html)和[ Hide Conditions](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/hide-conditions.html)可用于隐藏、替换或重新排序原始对话框的各个部分。 要复制的结构定义为跳位项节点级别以下的任何内容。

为了与对对话框当前版本所做的任何更改完全兼容，切勿触及选项卡项目级别下的结构（隐藏、添加到、替换、重新排序等）非常重要。 相反，应通过`sling:hideResource`属性隐藏父项中的选项卡项（请参阅[Sling资源合并属性](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/sling-resource-merger.html)），并添加了新的包含定制配置字段的选项卡项。 `sling:orderBefore` 可用于根据需要对选项卡项重新排序。

下面的对话框演示了建议的对话框结构以及如何隐藏和替换继承的选项卡，如上所述：

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

### 自定义核心组件{#customizing-the-logic-of-a-core-component}的逻辑

核心组件的业务逻辑在Sling Models中实现。 此逻辑可通过使用Sling委派模式进行扩展。

例如，标题核心组件使用所请求资源的`jcr:title`属性来提供标题文本。 如果未定义`jcr:title`属性，则将实现对当前页面标题的回退。 我们希望更改行为，以便始终显示当前页面的标题。

由于核心组件模型的实施是私有的，因此必须使用委托模式进行扩展。

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

有关委派模式的更多详细信息，请参阅核心组件GitHub Wiki文章[ Sling模型的委派模式](https://github.com/adobe/aem-core-wcm-components/wiki/Delegation-Pattern-for-Sling-Models)。

### 自定义标记{#customizing-the-markup}

有时，高级样式需要组件的不同标记结构。

这可以通过将需要修改的HTL文件从核心组件复制到代理组件中来轻松完成。

再举核心痕迹导航组件的示例，要自定义其标记输出，必须将`breadcrumb.html`文件复制到站点特定的组件中，该组件具有指向核心痕迹导航组件的`sling:resourceSuperTypes`。

### 设置组件{#styling-the-components}的样式

第一种自定义形式是应用CSS样式。

为了简化这一过程，核心组件渲染语义标记并遵循由[Bootstrap](https://getbootstrap.com/)启发的标准命名约定。 此外，为了轻松目标和命名空间各个组件的样式，每个核心组件都打包在DIV元素中，并带有“ `cmp`”和“ `cmp-<name>`”类。

例如，查看v1核心痕迹导航组件的HTL文件：[breadcrumb.html](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v2/breadcrumb/breadcrumb.html)，我们看到元素输出的层次结构为`ol.breadcrumb > li.breadcrumb-item > a`。 因此，要确保CSS规则仅影响该组件的痕迹导航类，所有规则都应按如下方式命名：

```shell
.cmp-breadcrumb .breadcrumb {}  
.cmp-breadcrumb .breadcrumb-item {}  
.cmp-breadcrumb a {}
```

此外，每个核心组件都利用AEM [样式系统功能](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/style-system.html)，该功能允许模板作者定义其他CSS类名称，这些名称可由页面作者应用到组件。 这允许为每个模板定义允许的组件样式的列表，以及默认情况下是否应将其中一种样式应用于此类的所有组件。

## 自定义{#upgrade-compatibility-of-customizations}的升级兼容性

有三种不同的升级方式：

* 升级AEM版本
* 将核心组件升级到新的次要版本
* 将核心组件升级到主版本

通常，将AEM升级到新版本不会影响核心组件或完成的自定义，前提是组件版本还支持要迁移到的新AEM版本，且自定义不使用[已弃用或已删除的](https://docs.adobe.com/content/help/zh-Hans/experience-manager-cloud-service/release-notes/deprecated-removed-features.html) API。

只要使用本页中描述的自定义模式，在不切换到较新的主要版本的情况下升级核心组件不会影响自定义。

切换到核心组件较新的主要版本仅与内容结构兼容，但可能需要重构自定义。 将针对每个组件版本发布清除更改日志，以突出显示将影响本页所述自定义类型的更改。

## 支持自定义{#support-of-customizations}

与任何AEM组件一样，在自定义方面有许多注意事项：

1. **切勿直接修改核心组件的代码。**

   这将使它们完全不受支持，并使组件的未来更新成为一个痛苦的过程。 请改用本页中介绍的自定义方法。

1. **自定义代码由您自行负责。**

   我们的支持项目不涵盖自定义代码，而且无法使用[用作文档的](/help/get-started/using.md)vanilla核心组件复制的报告问题不符合条件。

1. **观察已弃用和已删除的功能。**

   将每个新AEM版本升级到后，请注意[已弃用和已删除功能](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/release-notes/deprecated-removed-features.html)页面，确保所有使用的API仍然是热门的。

另请参阅[核心组件支持](overview.md#core-component-support)部分。

**阅读下一篇文章：**

* [使用核心组件](/help/get-started/using.md)  — 在您自己的项目中开始使用核心组件。
* [组件准则](guidelines.md)  — 了解核心组件的实施模式。
