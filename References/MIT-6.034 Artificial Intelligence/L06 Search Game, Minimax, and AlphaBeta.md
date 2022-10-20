2022-10-18, 17:23
Status: #reference
Tags: #AI

---

# Search: Game, Minimax, and Alpha-Beta

搜索：博弈，极小极大化， α- β

Approches:

1. Analysis, Strategy, Tactics  --> Move ，象棋国际大师的方式
2. IF-Then Rules
3. Look Ahead and Evaluate
4. British Museum
5. Look ahead as far as possible

Scoring Polymomial  （计分多项式）

Vocabulary：

Depth
    Branching Factor 分支因子
    Terminal Leaf

Progressive Deepening

Dead Horse Principle, （死马原则，在 alpha-beta 中用到，去除无意义的计算）
Marshal Arts Principle （武术原则，将敌人的特征用于对抗敌人）
Anytime algorithms    （随时算法，，在 Progressive Deepening 中用到，它在需要答案的时候总能提供一个答案）

(我自己的想法）
MiniMax 存在两种假设

1. 评估函数正确
2. 博弈双方不会失误

搜索树的加速：剪枝，更好选择分支

alpha-beta algorithm 通过剪枝对 minimax 的优化
为什么叫 alpha-beta ？因为算法中有 alpha beta 两个参数
Deep Cut-off
能用 alpha-beta 一定要用

分支因子会随竞局状态和竞局本身发生变化

博弈程序的通用工作原理：

Minimax plus Alpha-beta plus Progressive Deepening

推土机推土！！
