2022-10-18, 16:56
Status: #reference
Tags: #math #calculus

---

**微积分总览**

1. 微积分是函数之间的桥梁
2. 例子：（距离，速度），（高度，斜率）

积分, Integral
微分，Differential
微积分，Calculus

---

**导数总览**
**幂函数**
$$y=x^n, \frac{\mathrm{d}y}{\mathrm{d}x}=nx^{n-1}$$
**三角函数**
$$y=\sin{x}, \frac{\mathrm{d}y}{\mathrm{d}x}=\cos{x}$$
$$y=\cos{x}, \frac{\mathrm{d}y}{\mathrm{d}x}=-\sin{x}$$
**指数函数**
$$y=e^{x}, \frac{\mathrm{d}y}{\mathrm{d}x}=e^{x}$$
**常数**
$$y=c, \frac{\mathrm{d}y}{\mathrm{d}x}=0$$

**极值和二阶导数**
**二阶导数：导数的导数**
一阶导数寻找极值点，二阶导数判断极小值极大值，寻找拐点。

---

**指数函数**

**$e^x$**

性质：
$$e^xe^y=e^{x+y}$$
$$\frac{\mathrm{d}y}{\mathrm{d}x}=y$$
指数级数（数学中第二重要的无穷级数）：
$$e^x=1+x+\frac{1}{2}x^2+\frac{1}{3!}x^3+\dots+\frac{x^n}{n!}+\dots$$
最重要的级数是什么呢？几何级数
$$f(x)=1+x+x^2+x^3+\dots+x^n+\dots$$
**计算e**, 设 x=1
$$e=1+1+\frac{1}{2}+\frac{1}{6}+\dots+\frac{1}{n!}+\dots$$
约等于 2.71828...

**用复利推导e**

$$\lim_{x \to \infty}(1+\frac{1}{n})^n=e$$

考察导数
$$\frac{\mathrm{d}y}{\mathrm{d}x}=cy$$
c为利率
$$y(x)=e^{cx}$$

**二项式定理**
又称牛顿二项式定理

---
**积分总览**
已知导数求原函数
- 反过来想想什么函数的导数是它。
- $y(x)=\int s(x)dx$

微分是差过程，积分是逆过程，是求和。
从有限思想扩展到无限，推导出不定积分求原函数。

**推导不定积分**
$$\sum(\Delta y)=y_{end}-y_{start}$$
$$\sum(\frac{\Delta y}{\Delta x})\Delta x=y_{end}-y_{start}$$
$$\Delta{x}\to 0$$
$$\int\frac{dy}{dx}dx=y_{end}-y_{start}$$

y = area under s(x) curve

---
**极限**
趋近于，取 $\epsilon$，值落在 $(A-\epsilon, A+\epsilon)$
**连续**

---
弧度制，更自然地度量角度。用单位圆的弧长表示。

**sinx的导数**
**cosx的导数**

---
**乘法法则**
$$p(x)=f(x)g(x)$$
$$\frac{dp}{dx}=f(x)\frac{dg}{dx}+g(x)\frac{df}{dx}$$

**除法法则**
$$q(x)=\frac{f(x)}{g(x)}$$
$$\frac{dq}{dx}=\frac{g\frac{df}{dx}-f\frac{dg}{dx}}{g^2}$$

**幂法则**
$$f(x)=x^n$$
$$\frac{df}{dx}=nx^{n-1}$$

---
复合函数 y=g(x), z=f(y)

**链式法则**
$$\frac{dz}{dx}=\frac{dz}{dy}\frac{dy}{dx}$$

**偶函数**
$$f(x)=f(-x)$$

**奇函数**
$$f(x)=-f(-x)$$

例子，钟形曲线，正态分布
$$z=e^{-\frac{x^2}{2}}$$

---
**逆函数**
$$y=f(x),x=f^{-1}(y)$$

**对数**
$$y=e^x, x=\ln{y}$$
$$\ln{xy}=\ln{y}+\ln{x}$$
$$\ln{y^n}=n\ln{y}$$

> 代数的思想是抽象地一次性处理所有数。

$$y=\ln{x}$$
$$\frac{dy}{dx}=\frac{1}{x}$$

---
**对数的导数**
> 没有幂函数能给出-1次方的导数，对数的导数填补了

**反三角函数的导数**
$$x=\sin^{-1}{y}=\arcsin{y}$$
$$\frac{d\arcsin{x}}{dx}=\frac{1}{\sqrt{1-x^2}}$$
$$\frac{d\arccos{x}}{dx}=\frac{-1}{\sqrt{1-x^2}}$$
以上两个都用链式法则推导
$$f^{-1}(f(x))=x$$

---
**增长率**
线性增长（Linear），$cx$
多项式增长（Pdynomial），$x^n$
指数增长（Exponential），$2^x,e^x,10^x$
阶乘增长（Factorial），$x!, x^x$

**对数图，对数尺度**

---
导数的应用

**线性近似**
有函数 f(x), 设 x=a，有 $\frac{df}{dx}=f^{'}(a)$
$$f(x)\approx f(a)+(x-a)f^{'}(a)$$

给定x值，求沿着近似点的切线求近似值

**牛顿法**
有函数 $F(x)$，求解 $F(x)=0$

$$x=a-\frac{F(a)}{F^{'}(a)}$$

求出近似解后再迭代多次，逼近解

---
**泰勒级数**
$$f(x)=a_0+a_1x+a_2x^2+a_3x^3+\dots$$
$a_i$ 为 f 的n阶导数在x=0时的值。

可以对所有函数进行泰勒展开

$$e^x=1+x+\frac{x^2}{2}+\frac{x^3}{6}+\dots+\frac{x^n}{n!}+\dots$$
$$sinx=x-\frac{x^3}{3!}+\frac{x^5}{5!}+\dots$$
$$cosx=1-\frac{x^2}{2!}+\frac{x^4}{4!}+\dots$$

**欧拉公式**
将 $e^x, sinx, cosx$ 三个级数联系起来
引入虚数 i，$i^2$=-1

将 $e^x$ 级数中的 x 考虑为虚数，x 考虑为 ix

$$e^{ix}=1+ix+\frac{(ix)^2}{2!}+\frac{(ix)^3}{3!}+\dots$$

分离实部，虚部
$$\text{实部}=1-\frac{x^2}{2!}+\frac{x^4}{4!}+\dots$$
$$\text{虚部}=ix-i\frac{x^3}{3!}+i\frac{x^5}{5!}$$

可得
$$e^{ix}=\cos{x}+i\sin{x}$$

$$e^{i\theta} =\cos{\theta}+i\sin{\theta}$$
$$\theta=\pi, e^i=-1$$
几何图像为 **复平面**上的单位圆

---
微分方程的应用
**运动**

$$m\frac{d^2y}{dt^2}+2r\frac{dy}{dt}+ky=0$$

特例1，m=0, 
$$\frac{dy}{dt}=ay$$
$$y=ce^{at}$$

特例2，r=0
$$\frac{d^2y}{dt^2}=-\omega^2y, \omega^2=k/m$$
$$y=C\cos{\omega t}+D\sin{\omega t}$$

特例3，r=0, k=0，m=1
$$\frac{d^2y}{dt^2}=0$$
$$y=C+Dt$$

这个方程是，简谐振动方程
求解：
$$my{''}+2ry{'}+ky=0$$
尝试 $y=e^{\lambda t}$
$$m\lambda^2e^{\lambda t}+2r\lambda e^{\lambda t}+ke^{\lambda t}=0$$
$$m\lambda^2+2r\lambda+k=0$$

求解 $\lambda$ 
两个不同实特征解，
$$y=Ce^{\lambda_1t}+De^{\lambda_2t}$$
两个不同虚特征解，应用欧拉公式可消除虚部
$$y=Ae^{\lambda t}\cos{t}+Be^{\lambda t}\sin{t}$$
如果只有一个特征根
$$y=Ae^{\lambda t}+Bte^{\lambda t}$$

> 结论：线性常系数微分方程，可以通过 $e^{\lambda t}可以全部搞定$

---
**增长**
例1
$$\frac{dy}{dt}=cy$$
$$y(0)=given start$$
$$y(t)=y(0)e^{ct}$$

例2
$$\frac{dy}{dt}=cy+s$$
$$\frac{d(y+s/c)}{dt}=c(y+s/c)$$
$$y(t)+s/c=(y(0)+s/c)e^{ct}$$

> 所有线性方程的解为 特解+B通解

**应用，人口增长**
人口函数 P(t)
$$\frac{dP}{dt}=cP-sP^2$$

尝试
$$y=\frac{1}{P}$$

$$\frac{dy}{dt}=-\frac{\frac{dP}{dt}}{P^2}=\frac{cP-sP^2}{P^2}=s-\frac{c}{P}=s-cy$$
$$y-s/c=(y(0)-s/c)e^{-ct}$$
$$P(y)-s/c=(\frac{1}{P(0)}-s/c)e^{-ct}$$

---
**六函数**
幂函数
$$\frac{x^{n+1}}{n+1}\rightarrow x^n \rightarrow nx^{n-1}$$
正弦函数
$$-\cos{x} \rightarrow \sin{x} \rightarrow \cos{x}$$
余弦函数
$$\sin{x} \rightarrow \cos{x} \rightarrow -\sin{x}$$
指数函数
$$e^{cx}/c \rightarrow e^{cx} \rightarrow ce{cx}$$
对数函数
$$x\ln{x}-x \rightarrow \ln{x} \rightarrow \frac{1}{x}$$
冲激函数

**六法则**
加法
$$af(x)+bg(x) \rightarrow a\frac{df}{dx}+b\frac{dg}{dx}$$
乘法
$$f(x)g(x) \rightarrow f(x)\frac{dg}{dx}+g(x)\frac{df}{dx}$$
除法
$$\frac{f(x)}{g(x)} \rightarrow [g(x)\frac{df}{dx}-f(x)\frac{dg}{dx}]g^{-2}$$
逆函数
$$x=f^{-1}(y) \rightarrow \frac{dx}{dy}=\frac{1}{dy/dx}$$
链式法则
$$f(g(x)) \rightarrow \frac{df}{dy}\frac{dy}{dx}$$
洛必达法则
当 x=a, f(x), g(x) -> 0，
$$\frac{f(x)}{g(x)} \rightarrow \frac{df/dx}{dg/dx}$$

**六定理**
- 全值定理
![[wjfvd-1.png]]
- 中值定理和泰勒级数
![[wjfvd-2.png]]
- 二项定理，二项系数
![[wjfvd-3.png]]
二项级数是泰勒级数的特例