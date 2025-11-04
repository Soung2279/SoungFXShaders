A201-Shaders Collection  

简介
===========================

本仓库是为``Unity``的 ``URP`` 环境下使用的 **着色器合集**。其中，大部分着色器(下称shader)与粒子**特效**制作相关。  *(此处的粒子特效特指Unity内置的Shuriken粒子系统及其团结引擎的升级版Infinity粒子系统，不适用于Unity VEG)*

本仓库的shader基本基于Unity插件 ``ASE`` 生成，部分特殊shader进行了性能调优和可读化调整。这对于切换渲染管线或是移植到其它引擎有利。

若您有一定技术美术知识，您可自行查阅shader中的片段代码，并将其迁移到其它引擎或是适配不同的渲染管线。

查阅此仓库，您可以快捷的获取Unity特效制作相关的shader，同时可参考一些特殊效果的实现案例。

### 仓库前身

<details>

<summary>一些碎碎念</summary>

本仓库建立之初，是[本人](https://github.com/Soung2279)对学习和工作生涯中，对制作、收集的各种shader进行统一收录。其初衷是方便自用存取，同时也想分享一些技术案例。

在一开始的特效学习中，美术出身的我对于特效shader中的功能和模块不满意，想要实现一个效果需要若干个单项功能的shader和不同材质来实现，这使得我有了制作自己的通用shader的想法。有了这个苗头后，我便开始陆续收集相关的shader。

但是，在漫长的工作生涯中，我认识到，shader并不在于多，而在于精。兼容性强、泛用性广和性能平衡是尤为常见的特效shader需求。

虽然以往 [V1](https://github.com/Soung2279/Unity-Shaders-Collection/releases/tag/StandardV1.8.7) 收集的shader数量很多，但是大部分功能都重合了，并且由于代码风格不一，不便于功能迁移。所以，V2.0及以后的版本，会秉持简约的理念，尽可能收录一些通用的，快速上手的shader。

此仓库发展到现在，已经有了一个经历4个项目迭代，历时3年的通用特效shader，同时仍然有各种特殊的shader不断收录。我想，这才是创建这个仓库的最终意义。

 ##### *特效艺术家应该回归到对美术效果本身的钻研，降低对shader等技术向内容的学习成本。*

 ###### *A201指我最早开始接触特效学习的学校工作室门牌号。在这个几十平方的工作室中，我踏上了特效制作与技术美术学习的道路。*

</details>

### 文件说明

- [V1](https://github.com/Soung2279/Unity-Shaders-Collection/releases/tag/StandardV1.8.7) 版本已进行归档。不再维护。若无特殊说明，本仓库后续的相关内容均只适用于 [V2.0+]() 的内容。


文件的路径结构应该如下所示：
```
/V2
 -/Editor
 -/Render
 -/Scripts
 -/Shaders
   -/Soung_URP_AllEffect.shader
   -/...
```

其中，``/Shaders`` 里存放的是整合的shader内容。本仓库的核心内容位于此目录。

``/Editor`` 里存放的是shader相关材质面板GUI的脚本文件。此内容可以优化shader的材质面板显示，提高可读性。

``/Render`` 里存放的是一些特殊效果的Render Feature。此内容提供了一些特殊的效果需求，例如URP下的热扭曲、深度高度雾等。

``/Scripts`` 里存放的是与特殊效果的Render Feature相关的脚本。此内容提供了一些必要搭配使用的脚本。


所有的shader目录路径(Shader Path)均 **统一** 为 **Soung/** 路径下，并按着色器的使用类型进行了分类。
- 目前存在的分类有如下：
/Effect：用于粒子特效制作的相关shader
/Post：用于全屏后处理特效相关的shader
/Geometry：用于3d模型渲染相关的shader
/UI：用于UI动效相关的shader
/...

因游戏行业发展迅速，技术日新月异，本仓库的shader仅在以下环境适用：

- [x] // **推荐** //
[![Unity](https://img.shields.io/badge/Unity%20-2022%2B-black?style=flat-square&logo=unity)](https://unity.com/cn)
[![Static Badge](https://img.shields.io/badge/UniversalRenderPipeline%20-14%2B-black?style=flat-square)](https://docs.unity3d.com/cn/Packages/com.unity.render-pipelines.universal@12.1/manual/index.html)


- [ ] // 最低 //
[![Unity](https://img.shields.io/badge/Unity%20-2018%2B-black?style=flat-square&logo=unity)](https://unity.com/cn)
[![Static Badge](https://img.shields.io/badge/UniversalRenderPipeline%20-7%2B-black?style=flat-square)](https://docs.unity3d.com/cn/Packages/com.unity.render-pipelines.universal@12.1/manual/index.html)


- 理论上支持 ``Unity 6.000`` 和 ``TuanJie 1.0+``, ``Universal Render Pipeline 17.0`` 及以上。


本仓库收录的shader可实现下列需求：
- 特效用单贴图着色器
- 程序化粒子着色器
- 通用特效着色器
- 后期处理 **屏幕扭曲/色差/晕影/黑白闪** 着色器

并且，[V2.0+]() 版本的shader均进行过性能调优和中文参数适配，**可直接用于大部分移动端项目和PC项目**。对于小程序项目，请根据 ``WebGL`` 或 ``OpenGL ES2.0`` 的相关限制自行适配。


开始使用
===========================

##### 太长不看一句话描述

*下载Release包，解压，直接导入Unity工程中即可。*

<details>

 **<summary> 0. 确认您的项目需求 </summary>**

- 在使用本仓库提供的shader前，请先确认您的Unity项目是否支持可使用第三方shader (请询问项目组的技美大佬/客户端)，并确认您的Unity项目使用通用渲染管线 (Universal Render Pipeline, 简称URP)。请在确认后进行后续步骤。

</details>

#### 1. 下载本仓库整合包

- A - 请查看本仓库的 [Release列表](https://github.com/Soung2279/Unity-Shaders-Collection/releases/) ，并下载最新的 Release包 。正确的包 应该是 "``A201-Shader.V.2.x.x_20xx_xx_xx_Full.zip``" 这类命名的 ``.zip`` 压缩包。

- B - 将下载的包解压，并将其复制到您的Unity项目中。如果您不知道放哪个目录下，请直接放在 ``Asset/`` 目录下。

> (可选) 下载后的包可按需导入项目。如果您只想使用基本的shader功能，请只将 ``/Shaders`` 内的文件导入进项目。其它目录的文件都是对此部分功能的扩展与优化。

#### 2. 打开Unity工程确认

- A - 正常情况下，导入包并打开工程并后，控制台窗口(Console)仅会出现黄色警告信息，**不会出现红色错误信息**。 如果出现红色报错，请先点击报错日志查看来源。如果无法处理，请 **直接删除** **除 -/Shaders** 之外的包内容。仅保留基本功能。

- B - 如果想在保留完整功能的前提下使用shader包，请先检查下载过程中是否有错误。然后检查当前Unity使用的 **何种版本渲染管线** 。绝大部分错误都是由于版本不适配而导致的。推荐的版本为 [![Unity](https://img.shields.io/badge/Unity%20-2022%2B-black?style=flat-square&logo=unity)](https://unity.com/cn)[![Static Badge](https://img.shields.io/badge/UniversalRenderPipeline%20-14%2B-black?style=flat-square)](https://docs.unity3d.com/cn/Packages/com.unity.render-pipelines.universal@12.1/manual/index.html)

#### 3. 开始使用

- 所有的shader都可以在材质窗口处，切换着色器时，选择 ``Soung/`` 使用。具体的分类说明，请查看 **[文件说明](#文件说明)** 。

> 包中附带了供特效通用shader使用的shaderGUI，如果发现shaderGUI失效，请先查看 **工程中有无其它脚本相关报错** 。因脚本执行顺序原因，工程中存在错误时，可能会导致shaderGUI不工作。

#### 4. 后续更新

- 通常情况下，本仓库整合包不会有较大变更，在 [Release](https://github.com/Soung2279/Unity-Shaders-Collection/releases) 处选择对应文件下载，解压后直接 **覆盖原文件更新** 即可。

- 特殊情况下，在 [更新日志]() 中应有对应的更新指南，按指南操作即可。

- 若日志中没有给出更新方法，而您更新后在Unity材质面板中找不到shader。请使用 ``notepad++``, ``Windows记事本`` 或 ``VSCode`` 等IDE打开shader，查看新的shader目录路径(Shader Path)（通常在文件的前5行）。

- 使用ASE编辑：若您想使用ASE编辑现有shader (包括但不限于切换管线、增减功能、更改变量名等)，推荐的 ``ASE`` 版本为 V1.9.9.4+ 。

说明
========================

1. Shader使用：在Unity材质球处切换Shader时，选择"Soung/"目录下的Shader即可，Shader已做分类处理。

2. 部分shader可能存在变体较多的情况。请根据您的需求自行取舍。

3. ``Soung_URP_AllEffect.shader`` 是 **特效通用着色器**，因其参数复杂，推荐配合Editor中的shaderGUI使用。

4. 所有的屏幕后效shader，必须配合Render中的 ``GrabPassFeature.cs`` 使用。使用方式是：导入后，在URP管线中的RenderAsset中启用此 RenderFeature 。

## 特别鸣谢

在收录/整理/自编写过程中，参考并使用了以下开源内容和教程。

[![GitHub](https://img.shields.io/badge/Github-UnityURPToonLitShader-6666CC?style=flat-square&logo=github)](https://github.com/ColinLeung-NiloCat/UnityURPToonLitShaderExample)
[![GitHub](https://img.shields.io/badge/Github-LearnUnityShader-6666CC?style=flat-square&logo=github)](https://github.com/csdjk/LearnUnityShader)
[![GitHub](https://img.shields.io/badge/Github-Awesome_Unity_Shader-6666CC?style=flat-square&logo=github)](https://github.com/QianMo/Awesome-Unity-Shader)
[![GitHub](https://img.shields.io/badge/Github-URP_ASE_Tutorial-6666CC?style=flat-square&logo=github)](https://github.com/xuetaolu/URP_ASE_Tutorial)
[![BiliBili](https://img.shields.io/badge/BiliBili-多喝热水嗝嗝嗝-FB7299?style=flat-square&logo=bilibili)](https://space.bilibili.com/2537966)
[![BiliBili](https://img.shields.io/badge/BiliBili-Cz_wang-FB7299?style=flat-square&logo=bilibili)](https://space.bilibili.com/15396626)
[![BiliBili](https://img.shields.io/badge/BiliBili-永远的孤月-FB7299?style=flat-square&logo=bilibili)](https://space.bilibili.com/442123027)