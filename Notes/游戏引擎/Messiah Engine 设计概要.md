2022-10-20, 11:21
Status: #note
Tags: #game #engine #Messiah

---
# Messiah Engine 设计概要

## 全局设计 & 执行引擎设计

### The Whole Picture

Core

* very thin core
* very flexible extension
* very few data exchagne
* very little code to write
* Script, Network & Rendering & etc. is Not necessary
* Isolation is necessary
* The core will be minimized
* The core will be full featured

Engine is about data exchagne & job dispatching.

* Data Exchange - Representation of any data reflection
* Job Dispatching - Invoke fast, complete fast, organized well

Core Layer

* Module Stack
* C++ Reflection
* Execution & Dispatching
* Mathematics & Data
* File System
* Debugging & Logging

Engine Layers

* Object Model
* Scene Management
* Resource Management

Client Layers

* Game Input
* Graphics Features
* Platform Drivers
* Output Connections
* Startup Management

Plugin Layers

* Character Control
* Python Script
* Asyncore Client
* PhysX Runtime
* recast Navigation
* cocos2d-x UI

Editor & Tools Layers

* CLR/C# Wrapper
* WPF interface Library
* PyQt Wrapper
* Resource Cooking
* Code Generation

![[messiah-1.png]]

Others

* Build System - Generate & build Messiah codes
* Chef - Cook XML resource to binary data  & script
* ShaderMan - Compile shaders into caches
* Incarnation - Process C++ headers for reflections

Conclusion

* Minimize visibility, minimize pollutions
* Assuming game runs all the time
* Anything unnecessary should be a plugin
* Everything is replaceable

### Execution & Dispatching

多线程模型

data coherency

boost.asio - strand

* Organize codes by data coherency
* Distinguish threads not by code types but data writes
* Dispatch functions instead of call functions
* Use completion, eliminate waits & locks

Data coherency

* Writes data in certain strand
* Reads data in any strand but assume it always changed
* Reads data with atomic operations
* Manipulates collection among threads & merge them in certain strand
* Carries completions & signals with data

Write Operation

* volatile is useless
* std::atomic cost too much
* Depend on strand, just write data
* Never depend on the cache or flush

Dispatch Functions - send codes to strands

Lambdas

* Use std::move as much as possible
* Try to cast lambda to function pointer

The Art of Completion

* Use lambda to capture completion & carries it
* Use an atomic decreasing counter among multiple jobs
* Use atomic bit operation to detect complicate status completion

Capture Completion

* thumbnail Update Sample

Multiple Completion State

* FrameDispatcher Sample

Rules to design without lock

* Design data usage carefully
* Dispatch codes to strands
* Keep polling while waiting completion
* Use completion - dispatch & complete at last call

Coroutine in Messiah

* Stack-less (boost.asio)
* For flow controlling
* Fast & low cost
* In-house lock free implementation of boost.asio
* Suspend/resume freature of strand
* Coroutine yields, strand suspends
* Coroutine re-enters, strand resumes

One More Thing..

Thread cached and memory allocation

* tc-malloc is not suitable for mobile platforms
* dl-malloc based injection allocator
* hot-spot optimized allocation
* use localized storage as much as possible

Conclusion

* Code as data, data as constant
* Duplicates data among threads while conflicting
* Lock is EVIL
* Multi-threading NOW

### Rendering Abstraction

Elegant Design

* Write Graphics Algorithm in Very High Level
* Only One Shader!
* Minimum Platform Related Issue
* Very Stable in Architecture

Efficient Performance

* Very FAST Execution and very LOW memory Footprint
* Adapt Platform Related Features
* Benefit From Specific Device Customization
* Detailed in Platform API Usage

* Elegant High Level Design
* Stable Algorithm Code
* Variant Low Level Implementation
* Platform Dependent Call as Much as Possible in Low Level

Abstraction Layer

* Middle Layer
* Detailed Implementation
* Full Functionality
* Dynamic Variation

![[messiah-2.png]]

What is Rendering?

* A Serial of Abstraced Data
* A Description of Presentation
* Transform into Normalized Data

Scene Side Conclusion

* IPrimitive is Most High Level Abstraction of Object
* RenderObject Presents Instance of Rendering
* IRendererElement Defines How We Draw an Object
* IRendererPipeline Defines How We Draw a Scene
* We cut Details and Make Operations More Generalized
![[messiah-3.png]]
![[messiah-4.png]]

SceneData : More Abstracted, Very Adaptive, Changes Every Frame
Render Resource Data : General Format, Exists Shortly, Update While Changes
Device Specific Data : Platform Related, Mostly Immutable, Replace While Changes

Render Executive : Performs High Level Rendering Execution
Device Executive : Platform Dependent Driver to Execute Draw Call

RenderContext

IRenderOperation
IRenderResource
IRenderExecutive

## 反射

## 构建系统

Python Build System

## 文件系统

## 资源管理 & Patch 系统

ResourceObject
ResourceItem

资源分类：
1. 仓库资源：Mesh，SkinSkeleton，Texture，Material，Model，Effect，Terrain，NavigateMap，Physics，PointClound，VisibilityCube，Sound，Curve
2. 角色动画相关：graph，skeleton，animation
3. worlds，Script，cocos，audio，video，Font，

Repository

物理地址为： \Package\Repository，子目录为各个仓库。每个仓库有 resource.repository 文件描述了当前仓库的元信息，此文件为 xml 格式，引擎启动时会加载所有仓库的元信息。

逻辑路径为 Package/Name/Item
引擎内部使用 GUID 标识
初始化载入所有资源元信息

XML & Binary

* 编辑器使用 xml 格式，Game 使用 binary

Reflection

* XML格式资源基于反射，基于 boost:mpl/boost:fustion/std::type_traits 实现的动态对象系统

Class -> Clang Parser -> Incarnation

Texture

* LOD friendly binary

IWorld

* 描述大世界场景，EnvVolume & Physics & ILevel[...]

打包流程

* UI 贴图 -> Chef 导入 -> SVN
* 资源检查 -> 资源选择 -> Chef 处理

Patch > Package

Patch 目标

* 资源皆可更新，patch 系统为引擎初始化的一部分
* 降低更包体成本，小包
* 自身也可以更新，大部分用 python 实现，可远程配置特性，可 hotfix

Patch 策略回顾

* G4 增量 patch，和首包npk对比，分段hash生成patch，下载量最小。缺点：不同首包要大不同的patch
* H21 文件级增量patch，对比本地和服务器npk的文件列表，决定下载哪些文件。缺点：对比时间比较长
* G37、G50 基于版本控制的文件级patch 策略，每个版本和上个版本npk的diff生成patch，缺点：跨版本更新会浪费下载资源

Messiah 的 Patch

* 周版本上传全量资源，客户端计算文件级 diff 进行更新
* 存在版本号，只用于 == 判断
* 针对不同机型，资源分档
* 临时修 bug 上传增量资源
* 大文件下载改善小包体验
* iOS 后台下载改善 iOS 小包体验

Messiah Patch 流程

* Engine Modules initialization : Native UI, Netework status interface, Unisdk,CrashHunter, Detect, Driver, texture format, etc.
* MLauncher, prerequisite
* launch.py
* Engine modules post initialization: Resource Module, Shader Module ...
* MChecker -> main.py

隐患：本地的 patchlist 不代表本地资源情况，解决方案：修复客户端

小包构成：<= 50M

* 平台相关文件 info.plist, manifest etc
* 引擎可执行文件
* 引擎 Config 文件
* prerequisite + patch python 脚本
* 可选 CG / sticker

小包优势：

* 更换包体成本低
* 针对不同机型下载不同的资源，更好的适配

增量 Patch

Big Patch List 解决小文件过多，http 连接多，下载慢的问题

## 引擎启动，模块管理

## 内存管理

## 脚本系统

## 跨平台

## 多线程 Job System

## 渲染模块

## 场景模块

## 实体与组件

## 物理

## 粒子特效

## 骨骼与动画

## 声音

## UI

## 曲线系统

## 剧情系统

## 地形与植被

## 调试及开发工具

## Shader


