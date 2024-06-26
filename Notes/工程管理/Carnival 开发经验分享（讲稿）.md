2022-10-18, 17:53
Status: #note
Tags: #game_dev #carnival 

---

# Carnival 开发经验分享（讲稿）

[PDF](Carnival开发经验分享.pptx)

## 开篇

### page1

大家上午好，我是黄兴，来自上海孵化中心；今天我的分享题目是《Carnival 开发经验分享》，主要讨论下在 Carnival 开发过程中，我们对内容生产和内容生产工具开发的一些经验总结和思考。

### page2

这次分享主要分为四部分内容：首先介绍项目的背景，讨论下内容和资产的关系，然后结合 Carnival 项目，讨论下如何提高内容生产效率，最后做一些总结。

项目背景

### page3,4

这里有个两个比较有代表性核心关卡的视频，大家先看下。（Four minutes later ...）

Carnival 项目有以下的特点，首先是音乐元素驱动，我们最终提炼出的核心概念是：为一首歌制作可交互的MV

表现是丰富多样的，除了这两个视频中展现的表现形式，其实还有其他多种表现形式（PV，双人舞，双人战斗等）

这样的核心关卡体验自然就带来了两个特性：内容制作成本比较高，内容消耗快

这个项目没有被验证的对标产品，只在一些点上有可参考的项目。

由于对核心玩法的探索，需求变化频繁，对程序设计和工具开发提出了挑战。

结合以上特点，Carnival 在项目初期就明确了目标，不仅要制作游戏，同时还要同步探索出高效产出游戏内容的手段。  

因为Carnival是没有经过上线考验的项目，接下来部分内容没有经过验证，也有部分是我自己的总结和思考，和大家一起交流下。

## 内容 & 资产

### page5

在具体讨论 Carnival 的工作之前，先讨论下内容和资产的关系，以及资产的分类。 

### page6

这张图描述了游戏中，制作者，编辑器，资产，游戏，内容，用户的关系。
劳动力：可以是策划，美术，程序等，只要操作够简单可以逐步降低劳动力的要求
生产工具：是 Photoshop，3DMax 等DCC工具，Excel，自主开发的工具编辑器
劳动力使用生产工具产出资产：模型，纹理，配置，脚本 等等

用户消费的是内容，现在游戏形式内容一般通过三种形式产生，

    1. 比较传统的，用户和运行时 + 资产交互，产生内容，这里运行时可能派发给各个玩家，也可能是在云端。
    2. 用户创造内容，Mod，UGC，用户 + 运行时，生产资产；发布到游戏内，其他玩家再通过方式1 产生内容。同时 Mod 和 UGC 也是内容。马里奥制造等
    3. 运行时 + 资产，用户之间产生内容： PVP。竞技游戏

接下来更多讨论第一种形式，如何调高资产生产效率。部分涉及第二种形式，但是不多。第二种和第三种内容更多是策划思考。

### page7

资产有哪些类型，他们各有什么特性呢？

我把资产分为三大类

第一类，基础素材
基础素材包括了 Mesh，Texture，Material，Animation，UI 中 CSD，Spine 等等

第二类，自定义配置
包括了 Prefab， Model， Hero，Skill，Weapon 等

第三类，Gameplay 脚本

右边这个图自定义配置这个圈我画成虚线了，表示的第二类自定义配置和脚本之间的界限是变化的，随着游戏发展，本来在脚本中的逻辑有了数据抽象，就会成为第二类配置

例如 Formula（表达式），技能配置（Timline），行为树（树），Graph （图），蓝图 （图）。

这里很重要啊，因为这决定了前面讨操作生产工具的 Labor 是程序员还是策划。

同样自定义配置的标准形成了行业标准，那就会逐步的变为第一类基础资产，例如 Spine，

### page8

基础素材，有以下特性。

有专用的成熟的生产工具，效率较高，粘性高，想让制作者迁移难度很大，有可能是负收益；

产出有标准化，纹理格式大小，模型面数，等等

因为产出标准化，那就可以独立调试，检查和验收

### page9

项目自定义配置，一般是对基础素材的配置和组织，例如定义角色的模型外观

还有一类是Gameplay 中自定义的数据抽象，例如：技能，关卡，卡牌装备

这一类的配置资产伴随开发过程迭代，逐步形成，各项目差别比较大

缺少成熟工具

缺少调试和验收环境

程序员负责的逻辑脚本

    引擎层之上，它实现的是内容生成器 Generator，资产 + 外部输入 -》引擎 -》内容；更依赖经验，人

    我们产出的资产 != 代码，资产 == 系统功能， 代码是系统功能的翻译是负债。。

### page10

前面讨论的是比较虚的内容，接下来会结合 Carnival 项目的实践，资产如何生产的

### page11

基础素材确定标准，相信

产品提出需求，工单

开发，调试

在游戏中验收，验收以游戏中效果验收，音效，模型

所有基础素材通过 id 进行索引，在每个种类提供验收环境，

对于基础素材生产，Carnival 也是策划人工对接管理。

最近天下在开发工业化工具，参考影视行业，把需求，开发，版本，检查，验收等内容管理起来。减少策划和制作人员的对接。

### page12

在介绍项目自定义配置前，我想先介绍下需求的重要性。

因为不理解需求，就没法做出归一化的程序设计，也就没法做出合适的数据抽象。

首先第一点，可能也是最重要的一点，要理解原始需求。

这点在我们项目初期是有过真实案例的。

有一个周版本一个策划提出需求：角色在关卡内按一定路径点漫游，在过程中可以识别路径中的物理障碍，动态得到下一个路径点。用切面判断往左拐还是右拐。

最后沟通下来，他的核心需求其实是在关卡内漫游要有随机性，且尽量少编辑。但是他给的这个需求，其实更像解决方案，没有考虑音乐元素，交互读谱，动画实现等等细节。

最终的合适的方案是：逻辑路点，逻辑通路，通路上定义多种通过行为。

在这个方案上我们浪费了一周多。

有些原始需求策划是不会提的，需要主动去提炼。举例 Camera，丰富的镜头语言。 从影视行业学习，虚拟相机，机位。还有我们以Scene拍戏来组织关卡。

策划不会一上来说我要一套这样的系统，如果他说了，大概率也是错误的方向。

第二点积极管理需求，原因是策划提的需求可能是伪需求，或者是很后置的需求，就需要程序深入理解，积极和策划沟通，一起理顺需求优先级等内容。

需要对游戏的了解不比策划少，否则，人家一句某某游戏就是这么做的，就被pk了。

积极管理的含义也是需要程序积极告诉策划同学我们在做什么，我们的程序设计是怎么样的。

对需求有了深入的理解，才可能做出归一化的程序设计，数据抽象的表达能力才更高。

最后是以产品为导向的，最终是以版本日包体效果为准；快速建立最小迭代模型，每周发布功能。

### page13

下面介绍下 carnival 的程序设计，分为总体设计和关卡核心玩法的设计

总体设计比较简单，基于 Messiah Engine 和 Messiah Server，在脚本层包含一些基础模块，工具上主要是基于 Sunshine， CE & SE， UE4 to Messiah Plugin

应用层通过系统划分，角色展示，UGC，账号角色，曲包，Concert（Battle）

### page14

Concert 的程序设计

Clock 驱动时间，Sequencer 是核心，它的数据是多轨道的纸带的拼接，组合。Track 上有多个数据孔，这些孔，有点，有的是一段时间。

基于 Sequencer core，实现了音符，Scene（一场戏的调度数据）。Note 的设计是基于 Timeline，多轨道。

通过 signal 向外部发信号，例如音符的判定元素，演出的调度信息。

判定器，统计器，虚拟输入层

演出模块，舞台，演员，布景，相机；Sequencer 中 Secene 的调度信息对演出进行调度，实现静态剧情。有些演出对象有动态逻辑，通过状态机 + 判定结果，进行状态切换。

### page15

由程序设计就得到了需要那些数据抽象，相应的也就需要对应的编辑工具。

Note，
Stage，Camera（机位），Performer，Scenery，
Scene，Score

传统的编辑方式，Excel + Dev Tool，这些工具基本上是面向底层数据的

制作流程：盲编 Excel，配置属性； 本地导出游戏使用的配置；运行游戏看效果，如果配置有问题，回到第一步。

缺点：

    面向底层数据，编辑机位（只是想让角色在屏幕空间（0，0）点，但是 Yaw-Pitch-Roll Fov 等太复杂了）
    数据结构简单，嵌套结构，索引复杂，Hero->Equipment->Skill->Buff->Effect->Formula
    存在口传心授，或者被记录在某个没人打开过的文档中的规约，容易出现bug，不容易调试
    修改数据后最终运行效果链条长
    提交冲突，合并困难

All-in-One

    可视化编辑
    局部编辑，局部调试。例如编辑角色
    内化潜在规约和文档，索引直接跳转
    冲突比较容易解决，json，编辑有局部性
    可以对数据进行封装
    通用基础服务器：文件管理器，资源管理器（双击直接跳转到编辑窗口），筛选，undo/redo 等

### page16

进行 PGC Editor 演示，演示了编辑一个最简单的关卡。Seek，play，所见即所得。

可以调试，有了这个功能，可以让策划debug了

这是最上层的关卡编辑器。基于 sunshine 对应自定义配置，开发了对应的编辑器插件，还有 Scene，音轨，舞台，Camera，角色，音符 等等

### page17

为了增加内容产出，产品设计了 UGC 模块。

演示 UGC 模块 [ 3 minutes later ... ]

为玩家开放了一些编辑接口，产出的关卡内容和 PGC 编辑器产出的关卡完全一样。

Mod 部分有讨论预研，但是没有落地开发

### page18

总结一下制作资产有哪些方面可以提高资产生产效率

缩短管线长度。有了标准后就可以在这个节点验收，那么管线的长度也就短了。

提高并行度，减少等待。以 UI 和程序制作为例，引入 UIEdit，MVC，UI逻辑和样式制作可以并行开发。当发现一个流程制作完了之后需要等待另外流程完成然后联调才能验收，就需要考虑在节点处设立标准，提高并行度。

各职能在各自局部节点上工作。降低各节点的调试成本，也可以提升效率。

作为程序员我们知道工作中大量的时间花费在调试环节。其他岗位产出资产也是一样。基础素材产出还好，项目自定义配置一般由策划生产，调试手段缺失则效率会很低。

例如我们做过 QTE，QTE UI节点要和演员严格对上，没有可视化编辑和调试方式，可想而知制作效率是很低的。

降低人的因素。是人就会犯错，如果可以在编辑层面辅助进行一些正确性判断，可以极大降低bug率。

### page19

这部分简单提下项目流程方面的内容。大家都有丰富的经验了。这里简单说下 carnival 在实践中切实感觉到提升了工作效率的几点。

自动化，引擎发布，项目打包，发布，可以自动化就花点时间落到脚本中，popo -> jenkins -> script 直接搞定

生产环境隔离，Trunk 开发，Art 分支，

周版本迭代，

需求前置，这部分在carnival 的实践中从理想开始后才开始推进，各种现实原因，推进效果不好。

## 总结

经过 Carnival 的开发，

首先需要从需求出发，

把编辑器作为独立产品进行设计开发

从使用者视角进行开发

现在大家都在讨论工业化

工业化的基本过程是 标准化，建立流水线，自动化

总体反思游戏的工业化目前还在标准化和建立流水线这一步

然后工业化的特点：是“工业化的内生性特点，就是资本增密，技术增密，由此势必是排斥劳动的”

从其他成熟行业学习，影视，动画