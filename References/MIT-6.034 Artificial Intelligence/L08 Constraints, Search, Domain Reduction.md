2022-10-18, 17:26
Status: #reference 
Tags: #AI 

---
# L08 Constraints: Search, Domain Reduction

约束：搜索、域缩减

案例：地图着色问题

Variable    V:  Something That can have assignment
Value    X: Something that can be assignment
Domain    D : Bag of Values
Constraint    C  : Limit on variable Values

For Each DFS Assignment

    For Each Variable Vi Considered
        For Each Xi in Di
            For Each Constraint C( Xi, Xj) where Xj 存在于 Dj
                If 不存在 Xj 使得 C(Xi, Xj) satisfied
                    Remove Xi From Di
                If Di Empty
                    Backup

(Domain Reduction Algorithm)

Consider:

    Nothing
    Assignment
    Neigbors
    Through V with D reduced to one Value (域缩减到只剩下一个值的变量进行传播）
    Propate Checking Throgh V with reduced D (让已缩减的域在变量之间传播）
    Everthing

对事物的改变进行一些传播总会更好

在DFS中我们应该优先选择约束更多的还是更少的节点？ 选择约束更多的更好
  
还对资源规划问题很有用（heng：对于在地图中摆放资源是不是比较有用？）

**案例：航班规划**  
总使用最多约束优先
域缩减为 1 时总是使用约束传播
如果要求解最小所需资源数量，可以使用夹逼法，给出一个合理的答案