2022-10-18, 17:13
Status: #reference
Tags: #AI

---

# L04 Search Depth-First, Hill Climbing, Beam

搜索：深度优先，爬山，束搜索

The British Museum Approach 大英博物馆算法，找到所有可能的路径

Search != Maps， search is about choice

Hill Climbing, 根据哪个节点离目标近来选择分支

If you've got some kind of heuristic that tells you that you're going closer to the goal, you should use it.

连续空间中的问题：局部性，电线杆问题，被愚弄

Beam search, is a complement, addition of breadth first search

| -              | Back Tracking | Use extended list filter | Informed |
| -------------- | ------------- | ------------------------ | -------- |
| British Museum | x             | x                        | x        |
| Depth First    | o             | o                        | x        |
| Breadth First  | x             | o                        | x        |
| Hill Climbing  | o             | o                        | o        |
| Beam           | x             | o                        | o        |

应用领域：make a plan
