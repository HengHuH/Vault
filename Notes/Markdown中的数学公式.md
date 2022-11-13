2022-10-30, 16:13
Status: #note
Tags:

---

# Markdown中的数学公式

## MathJax
---
inline: \$...\$
displayed formulas: \$\$...\$\$

## 希腊字母
---
$$\alpha,\beta,\gamma,\delta,\epsilon,\zeta,\eta,\theta,\iota,\kappa,\lambda,\mu,\mu,\xi,o,\pi,\rho,\tau,\upsilon,\phi,\chi,\psi,\omega$$
$$A,B,\Gamma,\Delta,E,Z,H,\Theta,I,K,\Lambda,M,N,\Xi,O,\Pi,P,T,\Upsilon,\Phi,X,\Psi,\Omega$$

## 上下标
---
使用 ==^==, ==_==，例如 ==x_i^2==:_$x_i^2$, ==\\log_2 x==: $\log_2 x$

## 空格
---
小空格：==\\,== : $a\,b$, ==\\;== : $a\;b$
大空格：==\\quad== : $a\quad b$,  ==\\qquad== : $a\qquad b$

## 常用符号
$$\dots, \cdots, \vdots, \ddots $$
## 算数
$$\times, +,\div, -, \frac{2}{4}, a\cdot b,\dbinom{n}{r},a \bmod b,\pmod{m}, \sqrt{X}, \sqrt[n]{X},  $$
$$\sum_{k=1}^{N}k^2, \prod_{i=1}^Nx_i$$
## 函数

$$\sin,\arcsin,\lim_{a\to b},\cos,\max,\lg,\cos,\arccos,\min,\log,\det,\dim,\tan,\arctan,\ln,\log_a$$
## 集合
$$\forall, \in, \subseteq, \cup, \sqsupset, \exists, \ni, \supset, \varnothing, \notin, \supseteq, \subset, \simeq, \cong, \dot=, \pm, \mp$$

## 关系
$$=,\ne,\gt,\lt,\ge,\le,$$

## 微分
$$\nabla, \partial, \mathrm{d}x, \dot x, \ddot x$$

## 积分
$$x',x^\prime,\int_{-N}^{N}e^x\,dx, \iint_{D}^{W}\,dxdy, \oint_{a}^{b}dx$$

## 向量

$$\vec{x}, \overrightarrow{ab}, \overleftarrow{ab}$$

## 矩阵
---
行列式 
$$\begin{vmatrix}
a & b \\
c & d
\end{vmatrix}, \det{A}$$
矩阵
$$
\begin{pmatrix}
a & b \\
c & d
\end{pmatrix}
\qquad
\begin{bmatrix}a & b \\ c & d\end{bmatrix}
\qquad
\begin{Bmatrix}a & b \\ c & d\end{Bmatrix}$$

## Tag
标签
$$a:=x^2-y^3 \tag{1}$$

## 字体
### 黑板粗体
可用于表示空间
$$\mathbb{ABCDEFGHIJKLMNOPQRSTUVWXYZ}$$