2022-10-18, 18:44
Status: #reference
Tags: #game #AI

---

# C5 Decision Making

Most games use very simple decision making system: state machines and decision trees. Rule-based systems are rarer, but important.

5.1 Overview of Dicision Making
![[ai_for_games_5_1.png]]
5.2 Decision Trees

5.3 State Machines
Hierarchical State Machine
Combining decision trees and state machines

5.4 Behavior Trees
Task: Conditions, Actions, Composites (Selector, sequence), Decorators.
In the context of behavior tree, a Decorator is a type of task that has on single child task and modifies its behavior in some way.
Behavior trees implement a very simple form of planning, sometimes called reactive planning.
Blackboard
Reusing Trees
Limitations of behavior trees

5.5 Fuzzy Logic
模糊变量：隶属函数，限制词
模糊集合：模糊集合运算符
模糊规则
模糊推理
去模糊化

Fuzzy Sets
Membership of Multiple Sets
Fuzzy Rules
Fuzzification
Defuzzification
    Using the Highest Membership
    Blending Based on Membership
    Center of Gravity
    Choosing a Defuzzification Approach, to Boolean Value, Enumerated Value.

Fuzzy State Machine

There are several things we can do with fuzzy logic in order to make decisions. We can use it in any system where we'd normally have traditional logic AND, NOT, and OR. It can be used to determine if transitions in a state machine should fire.

5.6 Markov Systems

5.7 Goal-Oriented Behavior

Goal-Oriented behavior is a blanket term that covers any technique taking into accout goals or desires.

Goals
    A character may have one or more goals, also called motives. Each goal has a level of importance (often called insistence amont GOB aficionados) represented by a number.
Actions
    In Addition to a set of goals, we need a suite of possible actions to choose from.

Overall Utility. The previous algorithm worked in two steps. It first considered which goal to reduce, and then it decide the best way to reduce it. Unfortunately, dealing with the most pressing goal might have side effects on others.

Timing, In order to make an informed decision as to which action to take, the character needs to know how long the action will take to carry out.

Overall Utility GOAP
We consider multiple actions in sequence and try to find the sequence that best meets the character's goals in the long term.

5.8 Rule-Based Systems
是专家系统的一种应用，通常有两部分，包含很多用于AI的知识数据库，if-then 规则集合，有些基于规则的系统还包括 Arbiters（仲裁模块）决定哪些规则可用。

专家系统可以通过 前向链或者反向链实现

5.9 Blackboard Architectures
为了让多种不同技术实现的 AI 决策者之间可以交流

5.10 Scripting
选择逻辑脚本

5.11Action Execution
行为执行，Action应该是抽象的。
This section looks at actions in general and how they can scheduled and executed through a general action manager.

Single Action, Interrupting Actions, Compound Actions, Script Actions
