2022-10-18, 17:38
Status: #reference
Tags: #AI

---

# Learning: Neural Nets, Back Propagation

学习：神经网络、反向传播

让输出对输入的导数可以用输出本身来表示

反向传播算法

    一种局部计算 Local Computation
    对于固定数目的神经元，再一列中，对于列数，计算是线性的

凡事问五次为什么

一，What is the technology actually doing?

> It's got some desired outputs, is trying to contort the ways to give you actual outputs that are like the desired output, so it's fitting a curve（曲线拟合）.
> 曲线拟合有很多种方式，你可以用傅里叶变换，为什么说这比傅里叶变换好？

二， 如果有一个赛马相关的问题如何将参数编码到输入向量中，以此反映出问题的实质？

> 这才是最难的部分，曲线拟合倒很简单，只要初始输入表示对了就行，但神经网络理论做不到这点。

Phenomenon of the overfitting (过度拟合）

三，速率太高，这里有一个正反馈回路，开始振荡。你需要选择调整速率常数，否则无法收敛到答案，你会爆掉。
