# Changelog

## 2025.11.4 | 更新说明 | Standard V2.0.0

### 新增

新增 V2.0 的着色器集合。

新增 VFXTool 小工具脚本。用于检查特效性能、模型大小等。

### 说明
为方便维护，V2.0 版本**不再适配内置管线(Bulit-in)**。此版本的着色器将只支持[![Unity](https://img.shields.io/badge/Unity%20-2022%2B-black?style=flat-square&logo=unity)](https://unity.com/cn)[![Static Badge](https://img.shields.io/badge/UniversalRenderPipeline%20-14%2B-black?style=flat-square)](https://docs.unity3d.com/cn/Packages/com.unity.render-pipelines.universal@12.1/manual/index.html)

*在低于此版本的Unity编辑器和URP环境中运行shader不会完全失效，但不保证显示效果无误。*


## 2025.4.9 | 更新说明 | Obsoleted V1.9.0

### 更新

更新全功能着色器（双管线）及其shaderGUI.

更新ASE包至1.9.81

### 说明
此次更新后，V.1.9.0 Release包将作为最后一个 V1 版本发布。**不再进行后续维护**。此仓库着色器将以 V2 版本继续更新。

## 2023.12.29 | 更新说明 | Preview - Standard V1.8.7

### 新增

新增 **个人制作** 分类下的全部shader URP版本

新增带ShaderGUI的全功能着色器（双管线）

### 说明
此次更新仅作临时备份上传，非正式更新。（但所有已上传shader均通过可行性验证）
另，此次更新较为完整，将作为最新Release包

## 2023.12.20 | 更新说明 | Preview - Standard V1.8.4

### 新增

代码雨、像素风格、通用贴图变换、双三角护盾

UI控边溶解、故障扰动、霓虹灯闪烁、转场

builtin转场、故障扰动、双面材质面具、控边溶解、霓虹灯

此次新增15项，其中6项为UI适用。

*TODO:*
目前个人制作的着色器数量已达37个（包含UI用），**在未来会取消此分类结构，重构着色器路径**，简化不必要的轻量效果并以更高可读性的目录结构展示。

### 说明

此次更新仅作临时备份上传，非正式更新。（但所有已上传shader均通过可行性验证）

## 2023.12.13 | 更新说明 | Standard 1.8

**重要更新：新增 UI 分类**

### 新增

Buit-in | 序列帧屏幕扭曲、通用程序粒子材质、Flowmap软溶解

UI | 叠加纹理流动、*间隔流光、遮罩扰动与溶解等

URP | 序列帧屏幕扭曲、遮罩流动

### 修复

修复简易菲尼尔护盾在切换渲染管线后显示不正确的问题 (Built-in&URP)

### 优化

优化了部分shader的材质属性，清理了未使用的节点

去除了重复的风格化水面包 (URP)

### 其它

考虑到目前 个人制作 分类下的shader较多，在未来会删除此分类并将shaders分配到对应分类下

目前Release分类较多 (Built-in、UI、URP)，在未来可能以更合理的方式重新分类。

因目前shader较多，功能较复杂，在未来会编写一份对应使用说明。目前请暂时通过 [更新说明](#更新日志) 查看使用方法

*间隔流光：请使用黑底图用以流光纹理，在 [说明](#说明) 处已给出了一张示例图。

## 2023.11.7 | 更新说明 | Standard 1.7

新增：风格化卡通火焰与其简化版、风格化卡通地裂与其简化版、菲涅尔护盾和适用于URP的风格化水面包

修复：修复了序列帧材质边缘切线问题 [issue #2](https://github.com/Soung2279/Unity-Shaders-Collection/issues/2)

#定位了一个问题，此问题导致使用ASE重新编辑本仓库shader后会使汉化失效。

## 2023.10.12 | 更新说明 | Standard 1.6

新增：Panda熊猫shaderURP版，雨天地面，雨幕折射与屏幕模糊，雪地轨迹地面，简单序列帧材质，built-in

**重要更新**：Panda熊猫10.10 最新V2.3改。提供 [熊猫最新版发布地址](https://www.magesbox.com/article/detail/id/1321.html)

#个人制作shader均使用ASE 1.9.1.5 制作。

#简单序列帧材质 ``FlipAddtive`` 与 ``FlipAlphaB`` 建议配合修复遮罩贴图使用。详见 →→ **[查看说明](#说明)**

## 2023.9.3 | 更新说明 | Standard 1.5.1

新增：风格化水面与屏幕扫描(脚本驱动)，可在 [Post-Processing-Scan - MirzaBeig](https://github.com/MirzaBeig/Post-Processing-Scan) 查看屏幕扫描使用方法。

修复：修复了 [Standard V1.5 Release](https://github.com/Soung2279/Unity-Shaders-Collection/releases/tag/StandardV1.5) 错误的版本号。

## 2023.9.3 | 更新说明 | Standard 1.5.1

^更新：已全部汉化原ShaderGraph系列shader并部分优化。

*优化：优化了URP适用的 ``SinC_BlendURP``、``SinC_PBRURP`` 并完全汉化。

优化了着色器路径目录，现在URP适用的shader将单独显示在URP分支中。

^因数据更新，在旧版本的ShaderGraph上，着色器表现可能有差异。同时，请勿使用 ``ASE`` 编辑此着色器，这会导致着色器失效。

*因汉化与 ASE 冲突，请勿通过 ASE 编辑此shader。

## 2023.8.25 | 更新说明 | Standard 1.4

新增：屏幕后期处理、BA式卡通渲染、星星缩放、流麻Flow(URP)等shader。

#建议使用前在项目中导入ASE环境。

更新了基础特效制作环境。[Release](https://github.com/Soung2279/Unity-Shaders-Collection/releases/tag/RESOURCES_1) 处查看。

## 2023.7.31 | 更新说明 | Standard 1.3

新增：适用于URP管线的溶解（消融）、纹理叠加（遮罩）、简易描边等Shaders。

本次更新仅适用于URP项目。

考虑到项目制作需要，今后会将偏向更新适用于URP环境的shaders。

## 2023.6.9 | 更新说明 | Standard 1.2

说明：添加合集版本号，方便归档。

新增：新增额外菲涅尔、多重遮罩溶解、标准PBR、额外色差与屏幕扭曲Shaders。

修复：修复部分Shader功能失效的错误。

优化：将SinC_Blend进行性能优化。

汉化：完整汉化新增Shader，并进行归纳排版。

请导入文件目录下的Amplify Shader Editor(ASE)包来修复报错问题。

此次更新将Built-in/URP/HDRP等渲染管线平行分离，此次更新仅适用于Built-in。

## 2023.5.18 | 更新说明 | Standard 1.1

新增：新增屏幕扭曲shader，使用法线贴图来控制屏幕扭曲效果。

~~已知故障：进阶处理-多功能溶解ADD/Alpha Double的自定义顶点流可能失效，等待ShaderForge重置修复。~~

## 2023.5.4 | 更新说明 | Standard 1.0

资源优化：移除了部分失效Shader。

目录层级重构：现在所有Shader均按使用类型放置在 **A201-Shader/** 目录下。

更新：更新后期处理shader到最新版本，更新LTY-shader到最新版本。

增添：部分复杂Shader在面板中添加了导航链接。

重构：使用UnityPackage打包资源，而非直接以文件夹形式传输。


## 2023.4.17 | 更新说明 | Beta 0.2

修复：修复了"RongJieSD"持续提示缺失GUI脚本的错误。

更新：新增三个URP特供卡通着色Shader。

完善：完善了README，重归类文件目录结构。