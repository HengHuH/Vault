2022-10-19, 14:50
Status: #note
Tags: #game #AI 

---
# Helen AI 系统学习记录

**原有**：事件驱动的行为树+黑板
问题：树的膨胀，子树，决策与执行耦合

## 方法论

- [[GOAP]] 支持 Single AI，Squad AI；[[HTN]] 支持小队AI Strategy Executor 
- 上下文检查：每个Action绑定一个，可复用；一般是动态的，不宜用世界状态划分的要素
- 效用系统: [[Utility System]]，增加运行时随机性
- 优化：引入规划结果池，用缓存，LRU；短行动链条

## Action 行动

^ebddea

- 世界状态判定用二进制表示
- ActionUnit，可用以切换AI配置，从远程小怪切换到近战小怪
- 多通道，同时执行多个Action Chain，可实现上下半身执行不同 Action Chain

## 感知

- 黑板环境收集，Service，AI可定制化 Service，关注知识表示，AI的Service会覆盖黑板的Service
- 视觉，普通视野，视野专注区，视野模糊区域（动态线性）
- 听觉，距离
- 第六感

## Behavior 行为

对行为的理解
- NPC 自己的功能，而非 AI 的功能，不依赖 AI 也可以工作。
- NPC 的表现 = AI + 行为
- 行为可能会改变世界状态
- 行为要尽可能简单，要正交

行为状态控制
- AI 不参与 NPC 动作的中断、结束等
- AI 告诉 NPC 做什么，状态控制告诉 NPC 能做什么
- 修改 FSM 为 LSM（逻辑状态机）
