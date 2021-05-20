---
title: 自定义核心组件
description: 核心组件实施了多种模式，从简单的样式到高级功能重用，这些模式可轻松进行自定义。
role: Architect, Developer, Administrator
exl-id: ec4b918b-bc70-4d72-ba84-a24556aedb41
source-git-commit: b5b77f21cbeaa46622cef85f3bbaa549f17f1a06
workflow-type: tm+mt
source-wordcount: '1106'
ht-degree: 2%

---

# 自定义核心组件{#customizing-core-components}

[核心组件](overview.md)实施了多种模式，从简单的样式到高级功能重用，这些模式可轻松进行自定义。

## 灵活的架构{#flexible-architecture}

核心组件从一开始就设计得灵活且可扩展。 查看其架构的概述，即可找到可进行自定义的位置。

![核心组件架构](/help/assets/screen_shot_2018-12-07at093742.png)

* [“设计”](/help/get-started/authoring.md#edit-and-design-dialogs) 对话框定义作者可以在编辑对话框中执行或不能执行的操作。
* [编辑对](/help/get-started/authoring.md#edit-and-design-dialogs) 话框仅显示作者允许使用的选项。
* [Sling模型](#customizing-the-logic-of-a-core-component) 会验证并准备视图（模板）的内容。
* [Sling模型的结果可](#customizing-the-logic-of-a-core-component) 以序列化为JSON以用于SPA用例。
* [HTL在服务器端呈](#customizing-the-markup) 现HTML，以便进行传统的服务器端呈现。
* [HTML输出](#customizing-the-markup) 具有语义、可访问、经过优化的搜索引擎，且易于设计。

所有核心组件都实施[样式系统](#styling-the-components)。

## AEM 项目原型 {#aem-project-archetype}

[AEM项目原](/help/developing/archetype/overview.md) 型将最小的Adobe Experience Manager项目视为您自己项目的起点，包括一个使用SlingModels的自定义HTL组件示例，该示例可用于逻辑和使用推荐的代理模式正确实施核心组件。

## 自定义模式{#customization-patterns}

### 自定义对话框{#customizing-dialogs}

可能需要自定义核心组件对话框中可用的配置选项，无论是[设计对话框还是编辑对话框](/help/get-started/authoring.md)。

每个对话框都具有一致的节点结构。 建议在继承组件中复制此结构，以便使用[Sling Resource Mober](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/sling-resource-merger.html)和[Hide Conditions](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/hide-conditions.html)来隐藏、替换或重新排序原始对话框的部分。 要复制的结构定义为选项卡项目节点级别以下的任何内容。

要完全兼容对其当前版本对话框所做的任何更改，请务必不接触选项卡项目级别下的结构（隐藏、添加到、替换、重新排序等）。 相反，应通过`sling:hideResource`属性（请参阅[Sling资源合并器属性](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/sling-resource-merger.html)）隐藏父项中的制表符项，并添加了新的包含定制配置字段的制表符项。 `sling:orderBefore` 可以根据需要对制表符项进行重新排序。

下面的对话框演示了建议的对话框结构，以及如何隐藏和替换继承选项卡，如上所述：

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

核心组件的业务逻辑在Sling模型中实施。 可以使用Sling委派模式扩展此逻辑。

例如，标题核心组件使用所请求资源的`jcr:title`属性来提供标题文本。 如果未定义`jcr:title`属性，则会实施到当前页面标题的回退。 我们希望更改行为，以便始终显示当前页面的标题。

由于核心组件模型的实施是私有的，因此必须使用委派模式来扩展它们。

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

有关委派模式的更多详细信息，请参阅核心组件GitHub Wiki文章[Sling模型的委派模式](https://github.com/adobe/aem-core-wcm-components/wiki/Delegation-Pattern-for-Sling-Models)。

### 自定义标记{#customizing-the-markup}

有时，高级样式需要组件的标记结构不同。

通过将需要修改的HTL文件从核心组件复制到[代理组件中，可以轻松地完成此操作。](guidelines.md#proxy-component-pattern)

再以核心痕迹导航组件为例，要自定义其标记输出，必须将`breadcrumb.html`文件复制到站点特定的组件中，该组件具有指向核心痕迹导航组件的`sling:resourceSuperTypes`。

### 组件的样式{#styling-the-components}

第一种形式的自定义是应用CSS样式。

为了简化此过程，核心组件会渲染语义标记并遵循受[Bootstrap](https://getbootstrap.com/)启发的标准化命名约定。 此外，为了轻松定位和命名各个组件的样式，每个核心组件都封装在DIV元素中，并带有“ `cmp`”和“ `cmp-<name>`”类。

例如，查看v1核心痕迹导航组件的HTL文件：[痕迹导航.html](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v2/breadcrumb/breadcrumb.html)，我们看到元素输出的层次结构为`ol.breadcrumb > li.breadcrumb-item > a`。 因此，要确保CSS规则仅影响该组件的痕迹导航类，所有规则都应命名，如下所示：

```shell
.cmp-breadcrumb .breadcrumb {}  
.cmp-breadcrumb .breadcrumb-item {}  
.cmp-breadcrumb a {}
```

此外，每个核心组件都利用AEM [样式系统功能](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/sites/authoring/features/style-system.html)，该功能允许模板作者定义可由页面作者应用于组件的其他CSS类名称。 这允许为每个模板定义允许的组件样式列表，以及其中一个样式是否默认应用于此类型的所有组件。

## 自定义项的升级兼容性{#upgrade-compatibility-of-customizations}

可以进行三种不同的升级：

* 升级AEM版本
* 将核心组件升级到新的次要版本
* 将核心组件升级到主版本

通常，将AEM升级到新版本不会影响核心组件或完成的自定义设置，前提是组件版本也支持要迁移到的新AEM版本，且自定义设置不使用[已弃用或已删除的](https://docs.adobe.com/content/help/zh-Hans/experience-manager-cloud-service/release-notes/deprecated-removed-features.html) API。

只要使用此页面中描述的自定义模式，在不切换到较新版本的情况下升级核心组件不应影响自定义设置。

切换到核心组件的较新主要版本仅与内容结构兼容，但可能需要重构自定义设置。 将为每个组件版本发布清除更改日志，以突出显示可能影响此页面中所述自定义类型的更改。

## 支持自定义{#support-of-customizations}

与任何AEM组件一样，有关自定义的许多事项需要注意：

1. **切勿直接修改核心组件的代码。**

   这会使组件完全不受支持，并且会使组件在将来的更新过程变得十分痛苦。 请改用本页中描述的自定义方法。

1. **自定义代码由您自行负责。**

   我们的支持计划不涵盖自定义代码，并且报告的问题无法通过[用作文档的](/help/get-started/using.md)原有核心组件重现。

1. **观看已弃用和已删除的功能。**

   将每个新AEM版本升级到后，请注意[已弃用和已删除的功能](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/release-notes/deprecated-removed-features.html)页面，以确保所有使用的API仍然是热门的。

另请参阅[核心组件支持](overview.md#core-component-support)部分。

**阅读下一篇文章：**

* [使用核心组件](/help/get-started/using.md)  — 在您自己的项目中开始使用核心组件并运行。
* [组件准则](guidelines.md)  — 了解核心组件的实施模式。
