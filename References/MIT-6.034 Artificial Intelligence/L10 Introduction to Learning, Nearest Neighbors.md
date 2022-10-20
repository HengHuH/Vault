2022-10-18, 17:31
Status: #reference
Tags: #AI

---

# L10 Introduction to Learning, Nearest Neighbors

学习介绍、最近邻

两类学习方法：

    Regularity 基于观测和规律性的学习，这类分支可看成是推土机式计算
            Pattern Recognitions 模式识别,  Neighbors 最近邻
            Neural nets  神经网络， mimic biology 仿生尝试
            Boosting 理论研究
    Constraint 基于约束的，可称之为类似于人类的方式
            One Shot 一次性学习
            Explanation based  基于解释的
  
Camera -> FeatureDetector -> Comparator + Library ->Recognition

案例：识别插座

空间分割，decision boundaries 决策边界, Voronoi Polygon

Rumpelstiltskin Effect, when you have a name you get power over it.

Principle:

There is a kind of weak principle of if something is similar in some respects, it's likely to be similar in other respects.

案例：信息检索领域，识别相似的文章

使用向量夹角，而不是欧几里得距离，进行度量

案例：简单机械臂

科里奥利力（Coriolis Force)，以牛顿力学为基础
解析解不是一个可应用的方案

实际应用方案：建立巨大表格，学习更新表格，根据特征值查表取得马达的扭矩

案例：投球手

问题：

1. 样本空间不均匀。希望数据散布再所有维度都大致相同。解决：Normalize 正规化数据
2. What Matters 问题
3. 答案完全不依赖数据，巧妇难为无米之炊（No Cake Without Flower)

关于睡眠，睡眠不足会严重降低能力！！！！

不可以混淆相关性和因果性
