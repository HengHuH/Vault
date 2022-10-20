---
aliases: [Lua Code Style]
---

2022-10-18, 16:28
Status: #note
Tags: #Lua #Code

---

# Lua 风格指南

## 1. 背景

本风格指南的目的是增加代码的一致性。让程序员都可以快速读懂项目代码。

- 部分风格需要延续项目原有风格。
- 需要部分兼顾 C# 命名规范。
- 格式规则基于 [EmmyLuaCodeStyle](https://github.com/CppCXY/EmmyLuaCodeStyle)，它也是 VSCode 中 使用最多的 Lua Language Server 插件（Lua by sumneko）选择的格式化工具。

## 2. 格式

每个人都可能有自己的代码风格和格式，但如果一个项目中的所有人都遵循同一风格的话，这个项目就能更顺利地进行。每个人未必能同意下述的每一处格式规则，而且其中的不少规则需要一定时间的适应，但整个项目服从统一的编程风格是很重要的，只有这样才能让所有人轻松地阅读和理解代码。

### 文件

- 默认使用 `crlf` 作为行结束符。
- 使用`UTF-8`编码。
- 建议每行代码字符数不超过`120`。
- 文件以新的换行结束。

### 缩进

- 使用 4 个空格缩进。
- 单行语句换行时，次行比上一行多一次缩进。
- 空行不要有缩进。
- 注释的缩进应当与上下文缩进保持一致。

### 垂直留白

- 函数前后加空行，文件头后，require 区域后，使用空行分隔代码逻辑块。
- 函数体首尾不要有空行。
- 最大空行数 1。

```lua
-- MyFile.lua
-- This is my file.
-- @author Heng(huangxing03@corp.netease.com)

local Camera = CS.UnityEngine.Camera

local GameScene = require "Game.Scenes.GameScene"

local MyFile = {}

function MyFile.Save(self, content)
    -- do something
    ...

    -- do something else
    ...
end

return MyFile

```

### 水平留白

- 水平留白的使用根据在代码中的位置决定。永远不要在行尾添加没有意义的空格。
- 通用

```lua
-- , 前无空格，后有空格
local a, b = 10, 20
-- 行注释如果与代码在同一行，需要与代码相距一个空格
local a = c + b * c -- 说明复杂的工作
```

- 表达式

```lua
-- 赋值运算符前后总是有空格
local x = 0

-- 其它二元操作符也前后恒有空格
local a = c + b

-- 在参数和一元操作符之间不加空格
local length = #list
```

- Table

```lua
-- 花括号和元素之间如果有空格，两边都要加上
local list = {1, 2, 3}
local apple = { name = "a", weight = 2 }
-- 中括号前后不用空格
b['name'] = "hello"
-- 取值运算符 . 两边都没有空格
b.name = "hello"
b:NotExistFunction()
```

### 函数

- 函数定义像这样：

```lua
-- 左圆括号总是和函数名在同一行
-- 函数体另起一行，end 另起一行
-- 函数名和左圆括号之间没有空格
-- 圆括号和参数间没有空格
-- 一行文本太多，放不下所有参数，参数换行，每行与第一个参数对齐
function MyFunctionName(arg1, arg2)
    ...
end

```

- 函数调用：

```lua
-- 左圆括号前后，右圆括号前不要有空格
-- 如果一行放不下，参数可换行，每行与第一个实参对齐
MyFunctionName(a, b, c)
```

## 3. 命名约定

### 通用命名规则

尽可能使用描述性的命名，别心疼空间，毕竟相比之下让代码易于新读者理解更重要。不要用只有项目开发者能理解的缩写。也不要通过砍掉几个字母来缩写单词。
这份[Cheatsheet](https://github.com/kettanaito/naming-cheatsheet)也许可以帮到你。

几种命名方式：

- 大写下划线， `HOST_IP`
- 小写下划线，`server_id`
- `PascalCase`
- `camelCase`

### 基本原则

- 私有成员与方法使用 camelCase。
- 任何命名不得覆盖内置对象或者关键字，例如 require, false 等。
- 一些特定的广为人知的缩写是允许的， 例如 num，id，i 等。

### 范例

```lua
-- 文件夹，文件命名，PascalCase
-- Blog/Base/BlogComment.lua

-- 模块命名，PascalCase
local Logging = {}

-- 常量命名，大写下划线
local ROOM_AMOUNT_MAX = 10

-- 枚举命名，枚举名是类型，所以使用，PascalCase, E前缀(可选)
local EColor = {
    RED = 1,
    GREEN = 2,
    BLUE = 3,
}

-- 类型命名，PascalCase
local ListItem = class("ListItem")

-- 成员命名，PascalCase：Public，camelCase：Private
function ListItem.ctor(self, name)
    -- private，封闭性原则，数据成员默认私有
    self.name = name
end

-- Public
function ListItem.ChangeName(self, name)
    self.name = name
end

-- 变量命名，camelCase
local itemRemoved = nil

```

## 4. 注释

注释虽然写起来很痛苦，但对保证代码可读性至关重要。下面的规则描述了如何注释以及在哪儿注释，当然也要记住：注释固然很重要, 但最好的代码应当本身就是文档。有意义的类型名和变量名，要远胜过要用注释解释的含糊不清的名字。你写的注释是给代码读者看的，也就是下一个需要理解你的代码的人，所以慷慨些吧，下一个读者可能就是你！

### 通用

- 普通注释使用 `--` 或 `--[[]]`，统一就好。
- 使用 [EmmyLua](https://emmylua.github.io/) 注解功能写文档注释和类型注解。
- 每个文件开头加入文件头，描述文件，作者等信息。
- 模块和类的接口方法要写详细的文档注释，描述功能，如何使用，注意坑点。
- 对于代码中巧妙的，晦涩的，有趣的，重要的地方加以注释。
- 不要用注释来弃用代码，直接删掉它们。
- 注释要描述功能逻辑而不是运算逻辑，代码表达的就是运算逻辑，不需要再用自然语言说一遍。
- 书写 TODO 时，一定要写清楚具体的内容，以及计划完成时间，不要只写一个 TODO 进行占位。

### 范例

```lua
-- FILE: Game.lua

-- Game module
-- Author: Heng (huangxing03@corp.netease.com)
-- Time: 2022/10/12

--- This function do very complex job
---@param arg1 string
---@param arg2 int
---@param arg3 boolean | nil
---@return bool
local function ComplexJob(arg1, arg2, arg3)
    -- do step 1
    ...

    -- do step 2
    ...

    return true
end

--- Game class
---@class Game
local Game = class("Game")

--- Start game.
---@param self Game
function Game.Start(self)
    -- TODO: (Heng) implement me later!
end

return Game

```

## 5. Lua

### require

- 在文件头注释后空一行加入 require 代码块。
- 依次 require，C#模块，Unity，Lua 模块，用空行分隔。
- 删除没有用到的模块。

```lua
-- MyFile.lua
-- This is my file.
-- Author: Heng (huangxing03@corp.netease.com)

local Path = System.IO.Path

local FileHelper = CS.Framework.FileHelper
local MD5Cal = CS.Framework.MD5Calc

local PathUtils = require "Common.Utils.PathUtils"

...
```

### 模块

- 将模块接口放在一起，模块开始的显著位置。

### 类型

- 保持类型简单，
- Public 成员，Private 成员分类放一起，
- Pubic 成员在 Private 成员前面，
- 功能相近的成员应该放在相近代码区域。

### 方法

- 保持方法简单，
- 很多时候可选参数可以使用两个合适名字的不同函数替代。
