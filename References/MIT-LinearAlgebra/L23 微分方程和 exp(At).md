2022-10-18, 15:54
Status: #reference 
Tags: #math #LinearAlgebra 

---
解一阶导数常系数线性方程
**常系数线性方程的解是指数形式的**

例子：

$$\frac{du_1}{dt}=-u_1+2u_2$$
$$\frac{du_2}{dt}=u_1-2u_2$$

转化为矩阵形式
$$A=\begin{bmatrix}-1&2\\1&-2\end{bmatrix}$$
$$\frac{du}{dt}=Au$$
$$u(0)=\begin{bmatrix}1\\0\end{bmatrix}$$

求 A 特征值，$\lambda=0,-3$
特征向量，$x_1=(2,  1)^T, Ax_1=0x_1, x_2=(1,-1)^T, Ax_2=-3x_2$

$$u(t)=c_1e^{\lambda_1t}x_1+c_2e^{\lambda_2t}x_2$$
带入初始状态，求得 $c_1, c_2$