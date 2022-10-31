2022-10-18, 15:41
Status: #reference
Tags: #math #LinearAlgebra

---

# A的 LU 分解

**Great way to look at Gaussian elimination.**

- Inverse of $AB, A{T}$
- Product of elimination matinces, $A=LU$, no row exchanges.

$$AA^{-1}=1=A^{-1}A$$
$$(AB)^{-1}=B^{-1}A^{-1}$$
$$(A^{-1})^{T}=(A^T)^{-1}$$

$AA^{-1}=I$，转置等式两边，$(A^{-1})^TA^T=I$

$$\because EA=U, and A=LU \implies L=E^{-1}$$

**Diagonal Matrix, 对角矩阵，D，对角线为主元（Pivot）**

**DEF. 转置矩阵**

**nxn matrix, 消元总共进行了多少次？**
Ans.
$$\int_1^n{n^2}\,{\rm d}x= \frac{1}{3}n^3$$

**把b加入消元步骤进行回代，需要 $n^2$ 次。**

**DEF. 置换矩阵, 用来进行行互换的矩阵， Permutations,  P，$P^{-1}=P^T$，A 的所有置换矩阵组成了一个群**
