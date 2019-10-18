---
title: 自定义核心组件
seo-title: 自定义核心组件
description: 核心组件实现了多种模式，从简单的样式设计到高级功能重用，这些模式可轻松实现自定义。
seo-description: AEM核心组件实现了多种模式，从简单的样式设计到高级功能重用，这些模式都允许轻松自定义。
uuid: 38d22b85-4867-4716-817a-10ee2f8de6f5
contentOwner: 用户
content-type: 参考
topic-tags: 开发
products: SG_EXPERIENCEMANAGER/CORECOMPONENTS-new
discoiquuid: 3c9e0ade-1ce0-4e34-ae04-8da63f9b6c4f
translation-type: tm+mt
source-git-commit: 683b4f4705c226275439a408423cbf1b23bea66f

---


# 自定义核心组件{#customizing-core-components}

核心 [组件实施了多种模式](developing.md) ，从简单的样式设计到高级功能重用，这些模式可轻松自定义。

## 灵活的架构 {#flexible-architecture}

核心组件从一开始就设计为灵活且可扩展。 查看其架构的概述，可了解可在何处进行自定义。

![核心组件架构](assets/screen_shot_2018-12-07at093742.png)

* [设计对话框定义](authoring.md#edit-and-design-dialogs) ，作者可以在编辑对话框中执行或无法执行的操作。
* [编辑对话框](authoring.md#edit-and-design-dialogs) ，仅向作者显示允许他们使用的选项。
* [Sling模型验证](#customizing-the-logic-of-a-core-component) ，并为视图（模板）准备内容。
* [Sling模型的结果可以序列化为JSON](#customizing-the-logic-of-a-core-component) ，以供SPA用例使用。
* [HTL在服务器端呈现HTML](#customizing-the-markup) ，以实现传统的服务器端呈现。
* [HTML输出具有语义](#customizing-the-markup) 、可访问性、经过优化的搜索引擎并且易于设置样式。

所有核心组件都实现 [样式系统](customizing.md)。

## AEM Project Archetype {#aem-project-archetype}

[AEM Project Archetype将创建一个最小的Adobe Experience Manager项目作为您自己项目的起点，包括一个包含SlingModels的自定义HTL组件的简单示例，用于逻辑和正确实施包含推荐代理模式的核心组件。](overview.md)

## 自定义模式 {#customization-patterns}

### 自定义对话框 {#customizing-dialogs}

可能需要自定义核心组件对话框中可用的配置选项，无论是设计对 [话框还是编辑对话框](authoring.md)。

每个对话框都具有一致的节点结构。 建议在继承组件中复制此结构，以便 [Sling Resource Mergare](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/sling-resource-merger.html) and [Hide Conditions](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/hide-conditions.html) （合并和隐藏条件）可用于隐藏、替换或重新排序原始对话框的各个部分。 要复制的结构定义为跳位项节点级别以下的任何内容。

为了与对对话框当前版本所做的任何更改完全兼容，务必不要改动选项卡项目级别下的结构（隐藏、添加到、替换、重新排序等）。 相反，父项中的选项卡项应通过属性(请参阅 `sling:hideResource`[Sling Resource Mergare Properties](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/sling-resource-merger.html))隐藏，并添加了新的包含定制配置字段的选项卡项。 `sling:orderBefore` 可用于根据需要对选项卡项重新排序。

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

### 自定义核心组件的逻辑 {#customizing-the-logic-of-a-core-component}

核心组件的业务逻辑在Sling Models中实现。 此逻辑可通过使用Sling委托模式来扩展。

例如，标题核心组件使用所请 `jcr:title` 求资源的属性提供标题文本。 如果未 `jcr:title` 定义任何属性，则将实现对当前页面标题的回退。 我们希望更改行为，以便始终显示当前页面的标题。

由于核心组件模型的实施是私有的，因此必须使用委托模式来扩展它们。

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

有关委托模式的更多详细信息，请参阅核心组件GitHub wiki文章Sling [模型的委托模式](https://github.com/adobe/aem-core-wcm-components/wiki/Delegation-Pattern-for-Sling-Models)。

### 自定义标记 {#customizing-the-markup}

有时，高级样式需要组件的不同标记结构。

这可以通过将需要修改的HTL文件从核心组件复制到代理组件中来轻松完成。

再以核心痕迹导航组件的示例为例，要自定义其标记输出，必须将文件复制到站点特定的组件中，该组件具有指向核心痕迹导航 `breadcrumb.html``sling:resourceSuperTypes` 组件的组件。

### 设置组件样式 {#styling-the-components}

第一种自定义形式是应用CSS样式。

为了简化这一过程，核心组件渲染语义标记并遵循由 [Bootstrap启发的标准化命名惯例](https://getbootstrap.com/)。 此外，为了轻松定位和命名各个组件的样式，每个核心组件都包装在一个DIV元素中，并带有“ `cmp`”和“ `cmp-<name>`”类。

例如，查看v1核心痕迹导航组件的HTL文件：Breadcrumb.html [，我们会看到元素输出的层次结构](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v2/breadcrumb/breadcrumb.html)`ol.breadcrumb > li.breadcrumb-item > a`。 因此，要确保CSS规则仅影响该组件的痕迹导航类，所有规则的命名应如下所示：

```shell
.cmp-breadcrumb .breadcrumb {}  
.cmp-breadcrumb .breadcrumb-item {}  
.cmp-breadcrumb a {}
```

此外，每个核心组件还利用AEM [Style System功能](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/style-system.html) ，该功能允许模板作者定义其他CSS类名称，这些名称可由页面作者应用于组件。 这允许为每个模板定义一个允许的组件样式列表，以及其中一个样式是否应默认应用于该类型的所有组件。

## 自定义的升级兼容性 {#upgrade-compatibility-of-customizations}

有三种不同的升级方式：

* 升级AEM版本
* 将核心组件升级到新的次要版本
* 将核心组件升级到主要版本

通常，将AEM升级到新版本不会影响核心组件或完成的自定义，前提是组件的版本还支持要迁移到的新AEM版本，且自定义不使用已弃用或删除 [的API](https://helpx.adobe.com/experience-manager/6-5/release-notes/deprecated-removed-features.html)。

只要使用本页所述的自定义模式，在不切换到较新的主要版本的情况下升级核心组件不会影响自定义。

切换到核心组件较新的主要版本仅对内容结构兼容，但可能需要重新构建自定义。 将为每个组件版本发布清除更改日志，以突出显示将影响本页所述自定义类型的更改。

## 支持自定义 {#support-of-customizations}

与任何AEM组件一样，在自定义方面需要注意许多事项：

1. **切勿直接修改核心组件的代码。**

   这会使组件完全不受支持，并使组件的未来更新成为一个痛苦的过程。 请改用本页中介绍的自定义方法。

1. **自定义代码由您自行负责。**

   我们的支持计划不涵盖自定义代码，并且报告的问题无法与文档中使用的 [vanilla核心组件复制](using.md) 。

1. **观看已弃用和已删除的功能。**

   在将每个新AEM版本升级到的情况下，通过关注已弃用和已删除的功能页面，确保所有使用的API仍 [然是热门的](https://helpx.adobe.com/experience-manager/6-5/release-notes/deprecated-removed-features.html) 。

另请参阅核 [心组件支持](developing.md#core-component-support) 。

**阅读下一篇文章：**

* [使用核心组件](using.md) -在您自己的项目中开始使用核心组件。
* [组件准则](guidelines.md) -了解核心组件的实施模式。
