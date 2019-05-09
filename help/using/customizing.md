---
title: 自定义核心组件
seo-title: 自定义核心组件
description: 核心组件实现了允许轻松自定义的几种模式，从简单的样式到高级功能重用。
seo-description: AEM核心组件实现了允许轻松自定义的几种模式，从简单的样式到高级功能重用。
uuid: 38d22b85-4867-4716-817a-10ee2f8de6f5
contentOwner: 用户
content-type: 引用
topic-tags: developing
products: SG_ EXPERIENCE MANAGER/CORECOMMPANES-new
discoiquuid: 3c9e0ade-1ce0-4e34-ae04-8da63 f9 c4 f
translation-type: tm+mt
source-git-commit: 1bbec9b1f109df88964dce051a58d111bf6cafaa

---


# 自定义核心组件{#customizing-core-components}

[核心组件](developing.md) 实现了允许轻松自定义的几种模式，从简单的样式到高级功能重用。

## 灵活的架构 {#flexible-architecture}

核心组件从一开始就设计为灵活且可扩展。查看其架构概述可揭示可进行自定义的位置。

![核心组件体系架构](assets/screen_shot_2018-12-07at093742.png)

* [设计对话框](authoring.md#edit-and-design-dialogs) 定义了作者在编辑对话框中可以或无法执行的操作。
* [编辑对话框](authoring.md#edit-and-design-dialogs) 只向作者显示允许使用的选项。
* [Sling模型](#customizing-the-logic-of-a-core-component) 验证并准备视图的内容(模板)。
* [Sling模型的结果](#customizing-the-logic-of-a-core-component) 可串行化为JSON以供SPA用例使用。
* [HTL渲染HTML](#customizing-the-markup) 服务器端以进行传统的服务器端渲染。
* [HTML输出](#customizing-the-markup) 具有语义、可访问、搜索引擎、简单易用的特点。

所有核心组件都实现 [了样式系统](customizing.md)。

## 自定义模式 {#customization-patterns}

### 自定义对话框 {#customizing-dialogs}

可能需要自定义核心组件对话框中可用的配置选项，即 [设计对话框或编辑对话框](authoring.md)。

每个对话框都具有一致的节点结构。建议在继承组件中重复此结构，以便 [Sling资源合并](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/sling-resource-merger.html) 和 [隐藏条件](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/hide-conditions.html) 可用于隐藏、替换或重新排序原始对话框的章节。要复制的结构定义为选项卡项目节点级别的任何内容。

要与对其当前版本上的对话框所做的任何更改完全兼容，请务必在选项卡项目级别下面的结构(隐藏、添加到、替换、重新排序等)下进行结构。相反，应通过该 `sling:hideResource` 属性隐藏父项中的选项卡项(请参阅 [Sling资源合并属性](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/sling-resource-merger.html))和新增的包含标识配置字段的选项卡项目。`sling:orderBefore` 可用于根据需要重新排序选项卡项目。

下面的对话框演示了建议的对话框结构以及隐藏和替换继承的选项卡的方法：

<!-- 

Comment Type: annotation
Last Modified By: ims-author-CE1E2CE451D1F0680A490D45@AdobeID
Last Modified Date: 2017-04-17T17:43:20.265-0400

Should we provide guidance on how to name their CSS classes, etc. to align to component re-usability best-practices? We tout that we follow bootstrap css naming, should we be counseling customers to align similarly? .cmp- 
<component name="">
  -- 
 <element>
   - 
  <element descriptor="">
    ? 
  </element> 
 </element> 
</component>

 -->

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

核心组件的业务逻辑在Sling模型中实现。使用Sling委托模式可以扩展此逻辑。

例如，标题核心组件使用所请求资源的 `jcr:title` 属性提供标题文本。如果未 `jcr:title` 定义属性，则实现回退到当前页面标题。我们希望更改行为，以便始终显示当前页面的标题。

由于核心组件的模型的实施是私有的，因此必须使用委托模式扩展它们。

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

有关委派模式的更多详细信息，请参阅Sling Model的核心组件GitHub Wiki文章 [委派模式](https://github.com/adobe/aem-core-wcm-components/wiki/Delegation-Pattern-for-Sling-Models)。

### 自定义标记 {#customizing-the-markup}

有时高级样式需要组件的不同标记结构。

通过复制需要从核心组件修改到代理组件的HTL文件，可以轻松完成此操作。

再次执行核心痕迹导航组件的示例，以自定义其标记输出， `breadcrumb.html` 该文件必须复制到特定于核心痕迹导航 `sling:resourceSuperTypes` 组件的站点特定组件中。

<!-- 

Comment Type: annotation
Last Modified By: ims-author-CE1E2CE451D1F0680A490D45@AdobeID
Last Modified Date: 2017-04-17T17:43:20.265-0400

Should we provide guidance on how to name their CSS classes, etc. to align to component re-usability best-practices? We tout that we follow bootstrap css naming, should we be counseling customers to align similarly? .cmp- 
<component name="">
  -- 
 <element>
   - 
  <element descriptor="">
    ? 
  </element> 
 </element> 
</component>

 -->

### 设置组件样式 {#styling-the-components}

自定义的第一种形式是应用CSS样式。

为使这一切变得简单，核心组件渲染语义标记并遵循 [Bootstrap倡导的标准化命名规范](https://getbootstrap.com/)。此外，为了轻松定位和命名各个组件的样式，每个核心组件都封装在一个带有“ `cmp`”和“类”的DIV元素 `cmp-<name>`中。

例如，查看v核心痕迹导航组件的HTL文件： [breadcrumb.html](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v2/breadcrumb/breadcrumb.html)，我们看到元素输出的层次 `ol.breadcrumb > li.breadcrumb-item > a`结构。因此，要确保CSS规则只影响该组件的breadcrumb类，则所有规则都应为命名空间，如下所示：

```shell
.cmp-breadcrumb .breadcrumb {}  
.cmp-breadcrumb .breadcrumb-item {}  
.cmp-breadcrumb a {}
```

此外，每个核心组件都利用AEM [样式系统功能](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/style-system.html) ，它允许模板作者定义可由页面作者应用到该组件的其他CSS类名称。这允许为每个模板定义允许的组件样式列表，以及其中一个模板是否应默认应用于该类型的所有组件。

## 自定义的升级兼容性 {#upgrade-compatibility-of-customizations}

有三种不同的升级方式：

* 升级AEM版本
* 将核心组件升级到新的次要版本
* 将核心组件升级到主要版本

通常，将AEM升级到新版本不会影响核心组件或完成自定义，前提是组件版本还支持正在迁移的新AEM版本，并且自定义不会使用 [已弃用或删除的API](https://helpx.adobe.com/experience-manager/6-5/release-notes/deprecated-removed-features.html)。

只要使用此页面中所述的自定义模式，升级核心组件不会切换到更新的主要版本。

切换到核心组件的较新版本仅适用于内容结构，但可能需要重构自定义。将为每个组件版本发布清除更改日志，以突出显示会影响此页面中所述自定义种类的更改。

## 支持自定义 {#support-of-customizations}

与任何AEM组件一样，您还可以了解有关自定义的许多内容：

1. **永远不要直接修改核心组件的代码。**

   这会使它们完全不受支持，并使组件将来更新成为痛苦的过程。请改用本页中介绍的自定义方法。

1. **自定义代码是您自己的责任。**

   我们的支持计划不涵盖自定义代码以及不能使用vanilla核心组件重现的报告问题，因为记录的 [内容](using.md) 不符合条件。

1. **观看弃用和删除功能。**

   在升级到每个新的AEM版本后，请注意 [已弃用和已删除的功能](https://helpx.adobe.com/experience-manager/6-5/release-notes/deprecated-removed-features.html) 页面，以确保使用的所有API仍是主题。

另请参阅 [核心组件支持](developing.md#core-component-support) 部分。

**阅读下一步：**

* [使用核心组件](using.md) -在您自己的项目中与核心组件快速入门。
* [组件指南](guidelines.md) -了解核心组件的实施模式。
