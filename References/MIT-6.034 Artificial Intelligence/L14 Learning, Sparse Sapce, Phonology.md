2022-10-18, 17:43
Status: #reference 
Tags: #AI 

---
# Learning: Sparse Sapce, Phonology

学习：稀疏空间、音韵学

Winston: These ideas like neural nets, genetic algrathms, I classify them as picayunes(一文不值的）because getting them to do something is rather like getting a dog to walk on tied legs. You can make it happend but they never do it very well, and you have to take a lot of trickery training to make it happen.

Focus on Problem rather on the mechanism

讨论哪些领域已经被很好解决了。

案例：单词复数化，音韵规则

二进制区别性特征向量，14位

McGurk Effect 麦格克效应，视觉对听觉有强大影响

描述了一套音韵系统（Sussman-Yip Machine)

问题变为了如何学习（找到），音韵学规则

解：

选择正例和反例，选择种子

不考虑某个因子，逐步扩展，直到包括了反例

核心目的：如何在稀疏空间中进行搜索？正解，其实是对空间进行束搜索

Why did it work?

Yip 认为它能奏效的原因在于这是一个稀疏空间，对于高维稀疏空间，很容易就能将一个超平面放到空间中，将两组例子和另一组例子区分开。

空间维度越高，找到区分数据的平面就越容易

#1 对稀疏空间的一种解释是可学习性
#2 如果你有一个稀疏空间，点随机分布在空间中，根据中央极限定理，他们之间的距离会大致相等。这就确保了音素在说话时很容易区分

大卫·马尔，Marr's Catechism 马尔的问答法

当你处理 AI 问题时

#1 Specify the Problem 明确问题
#2 Devise a representation suited the Problem 设计一种表达方式适用于问题
#3 Determine an approach, somtimes a thought of this, a method  确定一个处理方式，一种思路，一种方法
#4 Pick a mechanism or devise an algorithm  选一个机制，或者说算法
#5 Experiment 实验

当然过程不会像这样线性往下流动，中间可能会有很多回路

但搞AI的人一般不大喜欢按照这样来做，他们喜欢抓住特定机制（算法）不放，然后把这些机制生搬硬套到所有问题上。

什么是优良的表示 what is a good representation

#1 表示要明确表示正确的东西 Explicit
#2 是否能让约束条件暴露出来？因为需要这些约束条件才能通过处理得到答案。
#3 局部性标准，通过吸管一样看到正确答案，比分散到四处的表示要好。