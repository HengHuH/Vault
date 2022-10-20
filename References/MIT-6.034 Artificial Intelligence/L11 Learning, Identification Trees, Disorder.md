2022-10-18, 17:37
Status: #reference
Tags:

---

# Learning, Identification Trees, Disorder

学习：识别树、无序

案例：识别吸血鬼

与最近邻问题有些不同，

- Symbolic， 数据集的显著差别：Not numerical data, this is symbolic （不是数值数据，而是符号数据）
- Some Don't Matter
- Some Matter only Some time
- Cost, 有些测试比其他测试代价更大
  
需要建立一棵测试树，The question become how do you arrage the tests in a tree, so as to do the identification that you want to do.

Identification Tree 和 Decision Tree 类似

大英博物馆算法：NP 问题

什么是好的识别树

    Small
    启发式
    最简单的，而不是复杂的，奥卡姆剃刀原则
    Cost 最小
  
给测试的质量一个度量，将度量优的先测试，

大数据集的情况

    没有测试能够立刻得到任何同质子集，刚开始度量都会是0，没法开始。需要更精妙的方式来衡量 --> 衡量数据 How disordered this data is or how disordered these sets are that you find at the bottom of the tree branches.

    如何度量无序度？ --> Find the entropy （求熵）--> Thermodynamics， 求熵是热力学本质问题；也是信息论的本质

    Q(Test) = Sum( D(Set) * (number of Samples in Set) / The Number of Samples handle by test) )

优点：  
Don't use all the tests, use only the test that seems to be doing some useful work
  
启发：  
Now the first heuristic of a good life is when you have a problem to solve, ask somebody who knows the answer.

信息论中度量无序度：设一系列二进制值的集合

    Positive，Nagitive, Total

    D(set) = - P/T Log2(P/T) - N/T Log2(N/T)

如果数据是数值的也是可用的
  
L'Hospital's Rule 洛必达法则

高斯曲

启发：

    It's not about the math, it's about the intuition and intuition is you want to build a tree that's as simple as possible. And you can build the tree that's as simple as possible if you look at the data ans say well which test does the best job of splitting things up.

如何将识别树转化为一系列规则？将每个分支走到头，then 简化规则