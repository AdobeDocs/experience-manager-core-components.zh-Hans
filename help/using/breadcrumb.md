---
title: 痕迹导航组件
seo-title: 痕迹导航组件
description: 'null'
seo-description: 核心组件痕迹导航组件是一个导航组件，它根据页面在内容层次结构中的位置构建了链接痕迹导航。
uuid: 13e858d5-24ad-4144-adc4-0fa1 ffd257 c1
contentOwner: 用户
content-type: 引用
topic-tags: 创作
products: SG_ EXPERIENCE MANAGER/CORECOMMPANES-new
discoiquuid: ed237df-08b8-4deb-9881-66a1f0d65ef3
modalsize: 426 x 240
translation-type: tm+mt
source-git-commit: 1243d6cc1b0b015ee2f37ae89d0e2e42d366cc02

---


# 痕迹导航组件{#breadcrumb-component}

核心组件痕迹导航组件是一个导航组件，它根据页面在内容层次结构中的位置构建了链接痕迹导航。

## 使用情况 {#usage}

痕迹导航组件显示站点层次结构中当前页面的位置，允许页面访问者从其当前位置导航页面层次结构。这通常集成到页眉或页脚中。

可在 [设计对话框中由模板作者定义可用选项，如默认导航级别以及显示当前页面或隐藏页面的能力](#design-dialog)。内容编辑器随后可以选择是否应显示隐藏页面以及 [编辑对话框中组件的实际导航级别](#edit-dialog)。

## 版本和兼容性 {#version-and-compatibility}

Breadcrumb Component的当前版本是v2，它是在2018年月核心组件发行版中引入的，它在本文档中进行了介绍。

下表详细说明了组件的所有支持版本、组件版本的AEM版本以及以前版本的文档链接。

| 组件版本 | AEM 6.3 | AEM 6.4 | AEM 6.5 |
|--- |--- |--- |--- |
| v2 | 兼容 | 兼容 | 兼容 |
| [v1](breadcrumb-v1.md) | 兼容 | 兼容 | 兼容 |

有关核心组件版本和版本的更多信息，请参阅文档 [核心组件版本](versions.md)。

## 示例组件输出 {#sample-component-output}

以下示例取自 [We. Retail](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/we-retail.html)。

### 屏幕快照 {#screenshot}

![](assets/chlimage_1.png)

### HTML {#html}

```
<nav class="cmp-breadcrumb">
    <ol class="cmp-breadcrumb__list">
        <li class="cmp-breadcrumb__item">
            <a href="/content/we-retail/us.html" class="cmp-breadcrumb__item-link">
                United States
            </a>
        </li>
    
        <li class="cmp-breadcrumb__item">
            <a href="/content/we-retail/us/en.html" class="cmp-breadcrumb__item-link">
                English
            </a>
        </li>
    
        <li class="cmp-breadcrumb__item cmp-breadcrumb__item--active">
            
                Experience
            
        </li>
    </ol>
</nav>
```

### JSON {#json}

```
"breadcrumb":{  
                     "columnClassNames":"aem-GridColumn aem-GridColumn--default--12",
                     "items":[  
                        {  
                           "page":{  
                              "path":"/content/we-retail/us",
                              "pageTitle":null,
                              "name":"us",
                              "description":null,
                              "title":"United States"
                           },
                           "active":false
                        },
                        {  
                           "page":{  
                              "path":"/content/we-retail/us/en",
                              "pageTitle":null,
                              "name":"en",
                              "description":null,
                              "title":"English"
                           },
                           "active":false
                        },
                        {  
                           "page":{  
                              "path":"/content/we-retail/us/en/experience",
                              "pageTitle":null,
                              "name":"experience",
                              "description":null,
                              "title":"Experience"
                           },
                           "active":true
                        }
                     ],
                     ":type":"weretail/components/content/breadcrumb"
                  }
```

>[!NOTE]
>
>从核心组件版本2.1.0开始，痕迹导航组件支持 [schema.org微数据](https://schema.org/BreadcrumbList)。

### 技术详细信息 {#technical-details}

有关痕迹导航组件 [的最新技术文档可在GitHub](https://github.com/adobe/aem-core-wcm-components/blob/master/content/src/content/jcr_root/apps/core/wcm/components/breadcrumb/v2/breadcrumb)上找到。

有关开发核心组件的更多详细信息，请参阅 [核心组件开发人员文档](developing.md)。

## 编辑对话框 {#edit-dialog}

编辑对话框允许内容作者禁止痕迹导航中的隐藏和活动页面以及纵向应显示的层次结构中的深度。

![](assets/screen_shot_2018-01-12at124250.png)

* **导航开始级别** -在层次结构中，痕迹导航组件应开始向下导航到当前页面。例如We. Retail：

   * 开始时开始 `/content`

   * 开始1 `/content/we-retail`
   * 开始时开始 `/content/we-retail/<country>`

* **显示隐藏的导航项目** -在痕迹导航中显示标记为隐藏的页面(默认情况下不显示它们)
* **隐藏当前页面**-禁止痕迹导航中的当前页面(默认情况下将显示它)

## 设计对话框 {#design-dialog}

设计对话框允许模板作者定义默认值，这些值用于禁止痕迹导航中隐藏和活动页面的隐藏以及其应显示的层次结构中的深度。

### 主选项卡 {#main-tab}

![](assets/screen_shot_2018-01-12at124437.png)

* **导航开始级别** -定义在将痕迹导航组件添加到页面时痕迹导航组件应开始向下导航至当前页面的默认值。
* **显示隐藏的导航项目** -定义将痕迹导航组件添加到页面时 **显示隐藏导航项目** 选项的默认值。

   * 它不为作者启用或禁用选项。它只设置默认值。

* **隐藏当前页面**-在将痕迹导航组件添加到页面时，定义 **隐藏当前页面** 选项的默认值。

   * 它不为作者启用或禁用选项。它只设置默认值。

### 样式选项卡 {#styles-tab}

痕迹导航组件支持AEM [Style System](authoring.md#component-styling)。