2022-10-18, 17:40
Status: #reference
Tags: #AI

---

# Learning, Genetic Algorithms

学习：遗传算法

一种仿生尝试，模仿进化的一种很朴素的尝试

有丝分裂

There are lots of choices in there and that means there are lots of choices to intervene.

	Population
	Mutation
	Crossover
	Genotype -> Phenotype
	Individuals
	Fitness
	Probability
	Selection
	NextNewGeneration

决定哪些活到下一代

主要在 Fitness，Probability 阶段进行选择

思路

1. 概率空间， Pi = Fi / Sum(F)
2. 排序空间， 考虑候选者适应性的排序，

    P1 = Pc
    P2 = (1-Pc)*Pc
    ...
    Pn = (1-Pc)^(n-1)

有时物种会锁定在一种状态，五六亿年不变，像鲨鱼。被困在局部最大值，步长不足。

增加步长，这就像将铁加热，所有原子的振动都会增强，步长更大。这类过程可以从大步长开始，然后逐步缩小到小步长。这叫模拟退火（Simulated Annealing)。

问题：适应性机制决定了事物会驱往局部最大值，种群会失去多样性

3. 选择时不仅要考虑适应性，还要考虑多样性。选择适应性排序最高 & 多样性排序最高的个体，不过不存在，可以画等优线

启发：

> What does mutation do ? It's basically hill climbing. It's producing a little spread out, and you're using the fitness thing to climb the hill.
>
> What does crossover do? It kinda combines strong features of multiple individuals into one individual maybe.

Ask Where The Credit lies?

问题：

It's naive nature and 就进化理论而言这很糟糕，很朴素。So we like to use real evolutionary theory, but we dont have real evolutionary theory, and evolution is still a mystery.

一些应用：

> What kinda problem does a good front piece combine with a good backpiece to produce a good thing overall.
>
> And the answer is when you're making a plan.

1. 做计划的应用，将染色体转换为多个步骤的计划
2. 赛马预测，可突变和互换的专家系统
3. 模拟生物进化

真实的贡献在于：空间的丰富性和编程者的聪明才智，而不是遗传算法本身有多好