2022-10-18, 15:42
Status: #reference
Tags: #math #LinearAlgebra

---

# Ax=b, 可解性及解的结构

$$\begin{bmatrix}1&2&2&3\\0&0&2&4\\0&0&0&0\end{bmatrix}x=\begin{bmatrix}b1\\b2\\b3\end{bmatrix}$$

step1，列出增广矩阵, $\begin{bmatrix}A&b\end{bmatrix}$
step2，消元

有解条件为：仅当 b 属于 A 的列空间时成立

---

求 $Ax=b$ 的解

1. 求特解，设所有自由变量为0，解出 $Ax=b$ 的主变量
2. 所有解为，$x=x_{particular}+x_{nullspace}$

**对于方程组某解，其与零空间内任意向量之和仍为解。**

m by n matrix A of rank r.

- r=m=n, R=I, 对任意b有唯一解
- r=n<m, $R=\begin{bmatrix}I\\0\end{bmatrix}$, 0或1个解
- r=m<n, $R=\begin{bmatrix}I&F\end{bmatrix}$，无穷多解
- r<m, r<n, $R=\begin{bmatrix}I&F\\0&0\end{bmatrix}$, 0或无穷解

**矩阵的秩决定了方程组解的数目。**