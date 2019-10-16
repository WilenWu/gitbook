---
title: 常微分方程(Ordinary Differential Equation)
tags: [R]
mathjax: false
copyright: true
date: 2019-05-02 12:36:35
categories: [R,Ordinary Differential Equation]
sticky: false
---



------

[常微分方程(Ordinary Differential Equation)](https://blog.csdn.net/qq_41518277/article/details/89703473)
[偏微分方程(Partial Differential Equation)](https://blog.csdn.net/qq_41518277/article/details/90295633)

------

> 参考文献：
> 丁同仁《常微分方程教程》
> MOOC同济大学《高等数学》
> MOOC国防科技大学《高等数学》

<!-- more -->
# 微分方程(Differential Equation)

**微分方程**：包含未知函数及其导数的方程叫做==微分方程==((Differential Equation))。未知函数导数的最高阶数称为该==微分方程的阶==(order)。
1. **常微分方程(ODE)**：若未知函数是一元函数的微分方程称为常微分方程(Ordinary Differential Equation, ODE)  。
一般的 ==n 阶常微分方程==的形式(也称隐式表达式)为$$F(x,y,y',y'',\dots,y^{(n)})=0 \tag{1}$$ 如果微分方程是关于未知函数及各阶导数的线性表达式 $$y^{(n)}+a_1(x)y^{(n-1)}+\cdots+a_{n-1}(x)y'+a_n(x)y=f(x)\tag{2}$$  则称为 ==n 阶线性(linearity)常微分方程==。
2. **偏微分方程(PDE)**：若未知函数是多元函数，方程中含有自变量的偏微分，称之为偏微分方程(Partial Differential Equations, PDE)。


**微分方程的解**：如果将一个函数$y=φ(x)$其各阶导数代入微分方程 (1) 得到恒等式$F(x,φ(x),φ'(x),φ''(x),\dots,φ^{(n)}(x))\equiv0$，则称$y=φ(x)$为上述方程的一个==解==(solution)。
1. **通解**：n 阶微分方程 (1) 的解 $y=φ(x,C_1,C_2,\cdots,C_n)$ 含有 n 个相互独立的任意常数 $C_1,C_2,\cdots,C_n$ ，则称为该微分方程的==通解==(general solution)。
其中任意常数相互独立是指每一个常数对解的影响是其他常数所不能代替的，即雅克比行列式(Jacobian)满足 $$\cfrac{D(φ,φ',\cdots,φ^{(n-1)})}{D(C_1,C_2,\cdots,C_n)}=
\begin{vmatrix}
\frac{∂ φ}{∂ C_1} &\frac{∂ φ}{∂ C_2} & \cdots &\frac{∂ φ}{∂ C_n} \\ 
\frac{∂ φ'}{∂ C_1} &\frac{∂ φ'}{∂ C_2} &\cdots &\frac{∂ φ'}{∂ C_n} \\ 
\vdots &\vdots &\ddots &\vdots \\ 
\frac{∂ φ^{(n)}}{∂ C_1} &\frac{∂ φ^{(n)}}{∂ C_2} &\cdots &\frac{∂ φ^{(n)}}{∂ C_n} \\ 
\end{vmatrix}\neq 0$$
2. **特解**：我们称不包含任意常数的解为==特解==(particular solution)。
3. **初值问题**：通常为了解决实际问题，确定常数的值，需要引入初值条件(initial conditions)。初值条件联合微分方程组成==初值问题==(Initial Value Problem, IVP)或柯西问题。
一阶常微分方程的初值问题通常记作 $\begin{cases}y'=f(x,y) \\ 
y(x_0)=y_0\end{cases}$
4. **隐式解与隐式通解**：如果关系式 $\Phi(x,y)=0$ 所确定的隐函数 $y=φ(x)$ 为微分方程 (1) 的解，则称 $\Phi(x,y)=0$ 是方程的一个==隐式解==(implicit solution)。对于 n个相互独立常数的解  $\Phi(x,y,C_1,C_2,\cdots,C_n)=0$ 的解为隐式通解。
5. **积分曲线**：微分方程的解对应的曲线称为==积分曲线==(integral curve)。
初值问题 $\begin{cases}y'=f(x,y) \\ 
y(x_0)=y_0\end{cases}$ 的解对应过点$(x_0,y_0)$的一条积分曲线，该曲线在点$(x_0,y_0)$ 处的切线的斜率为 $f(x_0,y_0)$，切线方程为 $y=y_0+f(x_0,y_0)(x-x_0)$
若不给定初始条件，微分方程的通解在几何上对应着一族积分曲线，称为==积分曲线族==(family of integral curves)。

6. **线素场**：考虑微分方程 $y'=f(x,y)$，若 $f(x,y)$ 的定义域为平面区域G，在G 内每一点 $P(x,y)$ 作斜率为 $f(x,y)$ 的单位线段，则称该线段为点 $P(x,y)$的==线素==。G 内所有的线素构成由微分方程确定的==线素场==(line element field)或==方向场==(direction field)。
在构造微分方程 $y'=f(x,y)$ 的线素场时，通常利用斜率关系式 $f(x,y)=k$ 确定曲线 $L_k$，称它为线素场的==等斜线==(isocline)。显然，等斜线$L_k$上各点的斜率都等于 $k$，简化了线素场逐点构造的方法。
7. **奇异点**：设一阶微分方程为 $P(x,y)dx+Q(x,y)dy=0$，函数$P(x,y),Q(x,y)$在区域G是连续的，若 $P(x_0,y_0)=Q(x_0,y_0)=0,,(x_0,y_0)\in G$，线素场在点$(x_0,y_0)$处便失去意义，我们称这样的点为==奇异点==(singular point)。

- **示例**：作微分方程 $y'=y/x$ 和 $y'=-x/y$的线素场。
(1) $y'=y/x$ 的等斜线为 $L_k:y=kx$，说明线素斜率为 k 的所有点都集中在直线 $y=kx$ 上，也可求得方程的积分曲线簇为射线 $\tanθ=y/x,θ$为任意常数，原点 O为奇异点。
(2) $y'=-x/y$的等斜线为 $L_k:y=-\frac{1}{k}x$，说明线素斜率为 k 的所有点都集中在直线 $y=-\frac{1}{k}x$ 上，且线素斜率和等斜线垂直相交，也可求得方程的积分曲线簇为同心圆 $x^2+y^2=C^2$，原点 O为奇异点。
![积分曲线](https://img-blog.csdnimg.cn/20190822161742447.png =160x)![积分曲线](https://img-blog.csdnimg.cn/20190822161807118.png =160x)

# 一阶常微分方程(First-Order Ordinary Differential Equations)

## 可分离变量方程(Equations of separated variables)

对于形如$$\frac{\mathrm{d}y}{\mathrm{d}x}=g(x)h(y)\tag{1}$$的微分方程，称为==可分离一阶方程==(separable first-order equations)，方程可化为$\cfrac{1}{h(y)}\mathrm{d}y=g(x)\mathrm{d}x$，对方程两边积分$\displaystyle\int \cfrac{1}{h(y)}\mathrm{d}y=\int g(x)\mathrm{d}x$
设$H(y),G(x)$分别为$\cfrac{1}{h(y)},g(x)$的原函数，可知隐式通解为 $H(y)=G(x)+C$
这种通过分离变量求方程通解的方法叫做==分离变量法==(Separation of variables)



## 一阶线性微分方程(First-order linear differential equation)

形如$$\frac{\mathrm{d}y}{\mathrm{d}x}+P(x)y=Q(x)\tag{1}$$的方程称为==一阶线性微分方程==(First-order linear differential equation) ，其特点是未知函数y 和它的一阶导数都是一次的。
如果$Q(x)\equiv0$，称为==齐次线性方程==，$Q(x)\not\equiv0$，称为==非齐次线性方程==。

- **齐次线性方程**：$$\frac{\mathrm{d}y}{\mathrm{d}x}+P(x)y=0\tag{2}$$ 是可分离变量的，对方程两边积分得 
$\ln|y|=-\int P(x)\mathrm{d}x+C_1$ 或 $y=Ce^{-\int P(x)\mathrm{d}x}\quad(C=± e^{C_1})$
- **非齐次线性方程**：解非齐次方程 (1) 常用的方法是==常数变易法==[^1](method of variation of constant)，
(1) 解对应的齐次方程 (2) 通解
(2) 将齐次方程通解中的常数$C$ 换成未知函数$u(x)$，做变换 $$\displaystyle y=ue^{-\int P(x)\mathrm{d}x}\tag{3}$$ 带入方程 (1) 便可求得  $\displaystyle u=\int Q(x)e^{-\int P(x)\mathrm{d}x}\mathrm{d}x+C$  
(3) 将 u 带入方程 (3)，便求得非齐次方程的通解
$\displaystyle y=e^{-\int P(x)\mathrm{d}x}[\int Q(x)e^{-\int P(x)\mathrm{d}x}\mathrm{d}x+C]$

[^1]: 常数变易法：是解线性微分方程行之有效的一种方法。它是拉格朗日十一年的研究成果，我们所用仅是他的结论，并无过程。

## 变量替换法 

- **一阶齐次微分方程**：可化为
$$\frac{\mathrm{d}y}{\mathrm{d}x}=φ(\frac{y}{x})\tag{1}$$ 的方程称为==一阶齐次微分方程==。
引入中间函数 $u=\cfrac{y}{x}$，则 $y=ux$，由此 $\dfrac{\mathrm{d}y}{\mathrm{d}x}=x\cfrac{\mathrm{d}u}{\mathrm{d}x}+u$
带入原方程 $u+x\cfrac{\mathrm{d}u}{\mathrm{d}x}=φ(u) \implies \cfrac{\mathrm{d}u}{φ(u)-u}=\cfrac{\mathrm{d}x}{x}$
得到可分离变量的微分方程，求隐式通解即可。
**齐次方程等价形式**：微分方程 $$P(x,y)\mathrm{d}x+Q(x,y)\mathrm{d}y=0\tag{2}$$中的函数$P(x,y),Q(x,y)$都是 $x,y$ 的同次(例如 k 次)齐次函数，即
$P(tx,ty)=t^kP(x,y),Q(tx,ty)=t^kQ(x,y)$
比如，线性代数中出现的二次型 $f(x, y)=ax^2+bxy+cy^2$ 就是一个二次齐次函数，它满足 $f(tx, ty)=t^2f(x,y)$ 
根据齐次函数的定义，我们有 $\begin{cases}
P(x,y)=x^kP(1,y/x) \\
Q(x,y)=x^kQ(1,y/x) \\
\end{cases}$
从而方程 (2) 化为下面的形式
$x^kP(1,y/x)\mathrm{d}x+x^kQ(1,y/x)\mathrm{d}y=0$
整理可得
$\cfrac{\mathrm{d}y}{\mathrm{d}x}=-\cfrac{P(1,y/x)}{Q(1,y/x)}=φ(\cfrac{y}{x})$
方程化为了齐次方程标准形式，齐次二字来源于齐次函数的定义，所以与齐次线性方程中的齐次不同。

- **可化为齐次的类型 I**
$$\frac{\mathrm{d}y}{\mathrm{d}x}=f(ax+by+c)\tag{3}$$ 引入新变量 $u=ax+by+c$ ，则 $\dfrac{\mathrm{d}u}{\mathrm{d}x}=a+b\dfrac{\mathrm{d}y}{\mathrm{d}x}$
带入原方程 $\dfrac{\mathrm{d}u}{\mathrm{d}x}=a+bf(u)$
这是可分离变量的微分方程，求隐式通解即可。

- **可化为齐次的类型 II**
$$\frac{\mathrm{d}y}{\mathrm{d}x}=f(\frac{ax+by+c}{a_1x+b_1y+c_1})\tag{4}$$ (1) 当$c=c_1=0$时，是齐次方程。
(2) 非齐次情形时，令$x=X+h,y=Y+k$，于是$\mathrm{d}x=\mathrm{d}X,\mathrm{d}y=\mathrm{d}Y$，方程化为
$$\frac{\mathrm{d}Y}{\mathrm{d}X}=f(\frac{aX+bY+ah+bk+c}{a_1X+b_1Y+a_1h+b_1k+c_1})$$如果方程组$$\begin{cases}ah+bk+c=0 \\ a_1h+b_1k+c_1=0\end{cases}$$ (i) 系数行列式$\begin{vmatrix}a&b\\a_1&b_1\end{vmatrix}\neq0$，即$\dfrac{a_1}{a}\neq\dfrac{b_1}{b}$，则可求出$h,k$，方程可化为$$\frac{\mathrm{d}Y}{\mathrm{d}X}=f(\frac{aX+bY}{a_1X+b_1Y})$$求出齐次方程的通解后，带入$X=x-h,Y=y-k$ 即可。
(ii) 当$\dfrac{a_1}{a}=\dfrac{b_1}{b}$时，令$\dfrac{a_1}{a}=\dfrac{b_1}{b}=λ$，从而$$\frac{\mathrm{d}y}{\mathrm{d}x}=f(\frac{ax+by+c}{λ(ax+by)+c_1})$$引入$v=ax+by$，则$\dfrac{\mathrm{d}v}{\mathrm{d}x}=a+b\dfrac{\mathrm{d}y}{\mathrm{d}x}$，方程化为可分离变量的方程$$\frac{\mathrm{d}v}{\mathrm{d}x}=a+bf(\frac{v+c}{λ v+c_1})$$

- **伯努利方程**：形如 $$\frac{\mathrm{d}y}{\mathrm{d}x}+P(x)y=Q(x)y^n\tag{5}$$ 的微分方程称为==伯努利方程==(Bernoulli differential equation)
引入变量 $u=y^{1-n}$，方程可转化为线性方程 $\dfrac{\mathrm{d}u}{\mathrm{d}x}+(1-n)P(x)u=(1-n)Q(x)$，可求得通解。

## 恰当方程(Exact equation)
- **恰当方程**：对称形式的微分方程 $$P(x,y)\mathrm{d}x+Q(x,y)\mathrm{d}y=0\tag{1}$$ 等价于其显示形式 $\cfrac{\mathrm{d}y}{\mathrm{d}x}=-\cfrac{P(x,y)}{Q(x,y)}=f(x,y)$
若存在可微函数 $F(x,y)$，使得它的全微分为 $$\mathrm{d}F(x,y)=P(x,y)\mathrm{d}x+Q(x,y)\mathrm{d}y$$ 亦即偏导数为 $$\cfrac{∂F}{∂x}=P(x,y),\quad \cfrac{∂F}{∂y}=Q(x,y)$$ 则称方程 (1) 为==恰当方程== (Exact equation) 或全微分方程。
那么原方程等价于 $\mathrm{d}F(x, y)=0$，即 $F(x,y)=C$ 就是原方程隐式通解，$F(x,y)$称为==原函数==。
<kbd>定理</kbd>：函数 $P(x,y)$ 和 $Q(x,y)$ 在区域 $R:a<x<b,c<y<d$ 上连续且有连续的一阶偏导数，则微分方程 (1) 是恰当方程的充要条件是 $$\cfrac{∂P}{∂y}=\cfrac{∂Q}{∂x}$$ 必要性：若 (1) 式为恰当方程，则存在函数 $F(x,y)$，满足 $\cfrac{∂F}{∂x}=P(x,y),\cfrac{∂F}{∂y}=Q(x,y)$
则 $\cfrac{∂P}{∂y}=\cfrac{∂}{∂y}(\cfrac{∂F}{∂x})=\cfrac{∂^2F}{∂x∂y},\quad \cfrac{∂Q}{∂x}=\cfrac{∂}{∂x}(\cfrac{∂F}{∂y})=\cfrac{∂^2F}{∂y∂x}$
由P 和Q 具有连续一阶偏导数，可知上述混合偏导数连续且相等，因此必有 $\cfrac{∂P}{∂y}=\cfrac{∂Q}{∂y}$
充分性：设函数 $P(x,y)$ 和 $Q(x,y)$满足条件 $\cfrac{∂P}{∂y}=\cfrac{∂Q}{∂x}$
(1) 我们来构造函数 $F(x, y)$ 满足 $\cfrac{∂F}{∂x}=P(x,y),\quad \cfrac{∂F}{∂y}=Q(x,y)$，首先函数
$$\displaystyle F(x, y)=\int P(x,y)dx+g(y)\tag{2}$$ 函数$g(y)$待定，对任意 $g(y)$ 都满足 $\cfrac{∂F}{∂x}=P(x,y)$。
(2) 为确定 $g(y)$，计算第二个偏导数
$\displaystyle \cfrac{∂F}{∂y} =\cfrac{∂}{∂y}\int P(x,y)dx+g'(y)=Q$
所以 $\displaystyle g'(y)=Q-\cfrac{∂}{∂y}\int P(x,y)dx$
(3) 为了说明存在这样的函数 $g(y)$，仅与 $y$ 有关，与 $x$ 无关，只需证明 $g'(y)$ 关于 x 的导数恒为零。根据假设，有
$\begin{aligned}
\cfrac{∂}{∂x}\left[Q-\cfrac{∂}{∂y}\int P(x,y)dx\right] &= \cfrac{∂Q}{∂x}-\cfrac{∂}{∂x}\left[\cfrac{∂}{∂y}\int P(x,y)dx\right] \\
&= \cfrac{∂Q}{∂x}-\cfrac{∂}{∂y}\left[\cfrac{∂}{∂x}\int P(x,y)dx\right] \\
&= \cfrac{∂Q}{∂x}- \cfrac{∂P}{∂y} \equiv 0
\end{aligned}$
于是积分可得到 $\displaystyle g(y)=\int \left[Q-\cfrac{∂}{∂y}\int P(x,y)dx\right]dy$
带入可求得 $$\displaystyle F(x, y)=\int P(x,y)dx+\int \left[Q-\cfrac{∂}{∂y}\int P(x,y)dx\right]dy\tag{3}$$ 因此满足条件的 (1) 式即为恰当方程，并且隐式通解为 $$\displaystyle \int P(x,y)dx+\int \left[Q-\cfrac{∂}{∂y}\int P(x,y)dx\right]dy=C\tag{4}$$

- **分项凑微分法**：往往在判断是恰当方程后，并不需要按照上述一般方法来求解，而是采用更简便的分项凑全微分的方法求解，这种方法要求熟记一些简单的全微分。
例如：求解方程 $(2x\sin y+3x^2y)dx+(x^3+x^2\cos y+3y^2)dy=0$
$\begin{aligned}
& (2x\sin y+3x^2y)dx+(x^3+x^2\cos y+3y^2)dy \\
=& (2x\sin y dx+x^2\cos y dy)+(3x^2ydx+x^3dy)+3y^2dy \\
=&(\sin y dx^2+x^2d\sin y)+(ydx^3+x^3dy)+3y^2dy \\
=&d(x^2\sin y)+d(x^3y)+d(y^3) \\
=&d(x^2\sin y+x^3y+y^3)
\end{aligned}$
所以通解为 $x^2\sin y+x^3y+y^3=C$

|部分全微分|
|:---|
|$ydx+xdy=d(xy)$|
|$\cfrac{ydx-xdy}{y^2}=d(\cfrac{x}{y})$|
|$\cfrac{ydx-xdy}{xy}=d(\ln\mid\cfrac{x}{y}\mid)$|
|$\cfrac{ydx-xdy}{x^2+y^2}=d(\arctan\cfrac{x}{y})$|
|$\cfrac{ydx-xdy}{x^2-y^2}=d(\ln\mid\cfrac{x-y}{x+y}\mid)$|
|$-\sin(x+y)(dx+dy)=d\cos(x+y)$|
|$\cos(x+y)(dx+dy)=d\sin(x+y)$|



- **积分因子**：对于恰当方程，我们有多种方法求解，比如偏积分法、分项凑微分法等。因此，能否通过一些恒等变形，将非恰当方程化为恰当方程来求解呢？
首先，看一下前面讲的变量分离方程
$\cfrac{\mathrm{d}y}{\mathrm{d}x}=g(x)h(y) \iff g(x)h(y)\mathrm{d}x-\mathrm{d}y=0$
两端同乘非零函数 $μ(x,y)=\cfrac{1}{h(y)}$ 可得恰当方程 
$g(x)\mathrm{d}x-\cfrac{1}{h(y)}\mathrm{d}y=0$
然后再看下线性方程 
$\cfrac{\mathrm{d}y}{\mathrm{d}x}+P(x)y=Q(x) \iff [P(x)y-Q(x)]\mathrm{d}x+\mathrm{d}y=0$
两端同乘非零函数 $μ(x,y)=e^{\int P(x)dx}$ 可得恰当方程 
$M(x,y)\mathrm{d}x+N(x,y)\mathrm{d}y=0$
其中 $M(x,y)=e^{\int P(x)dx}[P(x)y-Q(x)] ,N(x,y)=e^{\int P(x)dx}$
$\cfrac{∂M}{∂y}=P(x)e^{\int P(x)dx}=\cfrac{∂N}{∂x}$
现在我们尝试将这种方法一般化：对一般的微分方程 $$P(x,y)\mathrm{d}x+Q(x,y)\mathrm{d}y=0\tag{1}$$如果存在一个连续可微的非零函数 $μ=μ(x,y)$，使得 $$μP\mathrm{d}x+μQ\mathrm{d}y=0\tag{2}$$ 为恰当方程，即 $\frac{∂(μP)}{∂y}=\frac{∂(μQ)}{∂x}$，则称 $μ(x,y)$ 为微分方程 (1) 的==积分因子==(integrating factor)。整理可得积分因子满足方程 $$Q\frac{∂μ}{∂x}-P\frac{∂μ}{∂y}=(\frac{∂P}{∂y}-\frac{∂Q}{∂x})μ\tag{3}$$ 同一方程，可以有不同的积分因子，可以证明，只要方程有解存在，则必有积分因子存在，且不是唯一的。
一般情况下，求解方程 (3) 比求解微分方程 (1) 本身还要难！但是，在某些特殊情形，求解 (3) 还是可以实现的。
例如，如果存在只与 $x$ 有关的积分因子 $μ=μ(x)$ 则 (3) 式变为 $$Q\frac{dμ}{dx}=(\frac{∂P}{∂y}-\frac{∂Q}{∂x})μ$$ 整理可得 $$\frac{1}{μ}\frac{dμ}{dx}=\frac{1}{Q}(\frac{∂P}{∂y}-\frac{∂Q}{∂x})\tag{4}$$它的左端只与 $x$ 有关，所以右端亦然，因此，方程 (1) 存在只与 $x$ 有关的积分因子的必要条件是：$$\frac{1}{Q}(\frac{∂P}{∂y}-\frac{∂Q}{∂x})=G(x)\tag{5}$$ 只与 $x$ 有关。由此可得到积分因子 $$μ(x)=e^{\int G(x)dx}\tag{6}$$ 
<kbd>定理 1</kbd>：微分方程 (1) 存在仅依赖于 $x$ 的积分因子的充要条件是表达式 (5) 只与 $x$ 有关，而与 $y$ 无关。而且函数 (6) 就是一个积分因子。
类似的，我们得到下面的平行结果。
<kbd>定理 2</kbd>：微分方程 (1) 存在仅依赖于 $y$ 的积分因子的充要条件是表达式 $\displaystyle\frac{1}{P}(\frac{∂Q}{∂x}-\frac{∂P}{∂y})=H(y)$ 只与 $y$ 有关，而与 $x$ 无关。而且函数 $μ(y)=e^{\int H(y)dy}$ 就是一个积分因子。

等角轨线族family of isogonal trajectories
正交轨线族family of orthogonal trajectories

## 一阶隐式微分方程(First-order implicit differential equation)
克莱罗微分方程Clairaut differential equation

## 奇解(singular solution)

## 可降阶的高阶微分方程
高阶微分方程differential equation of higher order
降阶法method of reduction of order

-  ==$y^{(n)}=f(x)$ 型微分方程==
可看出方程右端仅含有自变量x，只要把$z=y^{(n-1)}$作为新的未知函数，可化为一阶微分方程$z'=f(x)$，求得$y^{(n-1)}=\int f(x)\mathrm{d}x+C_1$，同理可依次求得$y^{(n-2)},\cdots,y',y$

- ==$y''=f(x,y')$ 型微分方程==
设$p=y'$方程可化为$p'=f(x,p)$，求解一阶微分方程即可

- ==$y''=f(y,y')$ 型微分方程==
设$p=y'$利用复合函数的求导法则，方程可化为$p\dfrac{\mathrm{d}p}{\mathrm{d}y}=f(y,p)$，求解一阶微分方程即可

# 一阶线性微分方程组(First-order Linear Differential Equation System)

柯西存在和唯一性定理Cauchy existence and uniqueness theorem
Matrix Exponential(矩阵指数)
Wronskian Determinants Solutions(朗斯基行列式解)

皮卡序列Picard sequence
佩亚诺存在定理Peano existence theorem
欧拉折线Euler polygons
卡拉泰奥多里存在定理Carathe&1&odory existence theorem
利普希茨唯一性条件Lipschitz uniqueness condition
奥斯古德唯一性条件Osgood uniqueness condition
卡姆克唯一性条件Kamke uniqueness condition

最大存在区间maximum interval of existence

最大解maximum solution
最小解minimum solution

齐次线性微分系统homogeneous linear differential system
基本解组fundamental system of solutions
朗斯基行列式准则criterion via Wronski determinant

# 高阶线性微分方程
降阶法method of reduction of order

- **n阶方程**$$y^{(n)}+a_1(x)y^{(n-1)}+\cdots+a_{n-1}(x)y'+a_n(x)y=f(x)\tag{1}$$如果$f(x)\equiv0$，称为n阶齐次线性方程，$f(x)\not\equiv0$，称为n阶非齐次线性方程。

- **解的结构**
==二阶齐次方程==$$y''+P(x)y'+Q(x)y=0\tag{2}$$
<kbd>**定理 1**</kbd> 若$y_1(x)$和$y_2(x)$是二阶齐次方程(2)的两个解，那那$y=C_1y_1(x)+C_2y_2(x)$也是二阶齐次方程(2)的解
<kbd>**定理 2**</kbd> 若$y_1(x)$和$y_2(x)$是二阶齐次方程(2)的两个**线性无关**[^3]的特解，那么$$y=C_1y_1(x)+C_2y_2(x)$$是二阶齐次方程(2)的**通解**
<kbd>**推论**</kbd> 若$f_1(x),f_2(x),\cdots,f_n(x)$是n阶齐次线性方程(1)的n个**线性无关**的特解，那么$$y=C_1y_1(x)+C_2y_2(x)+\cdots+C_ny_n(x)$$是方程(1)的**通解**
==二阶非齐次方程==$$y''+P(x)y'+Q(x)y=f(x)\tag{3}$$
<kbd>**定理 3**</kbd> 若$y^*(x)$是二阶非齐次方程(3)的一个特解，$Y(x)$是对应的齐次方程(2)的通解，那么$$y=Y(x)+y^*(x)$$是二阶非齐次方程(3)的通解
<kbd>**定理 4 叠加原理**</kbd> 若$y_1^*(x),y_2^*(x)$依次是方程$y''+P(x)y'+Q(x)y=f_1(x)$和$y''+P(x)y'+Q(x)y=f_2(x)$的特解，则$$y=y_1^*(x)+y_2^*(x)$$是方程$$y''+P(x)y'+Q(x)y=f_1(x)+f_2(x)$$的特解

[^3]: 函数线性无关：设n个函数$f_1(x),f_2(x),\cdots,f_n(x),x\in I$，如果存在n个不全为0的常数$k_1,k_2,\cdots,k_n$，使得$k_1f_1(x)+k_2f_2(x)+\cdots+k_nf_n(x)\equiv0,x\in I$，则这n个 函数线性相关，否则线性无关。

常数变易法method of variation of constant
微分算子法method of differential operator
- **常数变易法**[^2]
已知齐次方程(2)的通解为$y=C_1y_1(x)+C_2y_2(x)$，用常数变易法去求非齐次方程(3)的通解，令$$y=v_1(x)y_1(x)+v_2(x)y_2(x)$$满足非齐次方程(3)，求得$v_1,v_2$，可得通解式为$$y=C_1y_1+C_2y_2-y_1\int\frac{y_2f}{W}\mathrm{d}x+y_2\int\frac{y_1f}{W}\mathrm{d}x$$ 其中$W=\begin{vmatrix} y_1 & y_2 \\ y_1' & y_2'\end{vmatrix}=y_1y_2'-y_2y_1'\neq0$

## 常系数齐次线性微分方程
- **二阶方程** $$y''+py'+qy=0\tag{1}$$ 其中$p,q$为常数
- **求解步骤**
(1) 根据定理我们只需要求得方程(1)的两个线性无关的特解$y_1,y_2$，那么$y=C_1y_1+C_2y_2$即是方程的通解
(2) 由于$e^x$导数的特殊性，尝试$y=e^{rx},r是常数$是方程的解。
求导$y'=re^{rx},y''=r^2e^{rx}$，并带入方程(1)得$(r^2+pr+q)e^{rx}=0$
由于$e^{rx}\neq0$，只要$r$满足方程$r^2+pr+q=0$（特征方程），即可得到通解。

特征方程$r^2+pr+q=0$的两个根$r_1,r_2$|微分方程$y''+py'+qy=0$的通解
:---|:---
$r_1\neq r_2且r_1,r_2\in\R$|$y=C_1e^{r_1 x}+C_2e^{r_2 x}$
$r_1=r_2且r_1,r_2\in\R$|$y=(C_1+C_2x)e^{r_1 x}$
$r_{1,2}=α±β i,r_{1,2}\in\Complex$(共轭复根)|$e^{α x}(C_1\cosβ x+C_2\sinβ x)$

- **n阶常系数齐次线性微分方程** $$y^{(n)}+p_1y^{(n-1)}+\cdots+p_{n-1}y'+p_ny=0\tag{2}$$ 其中$p_1,p_2,\cdots,p_n$为常数
(1) 引入微分算子[^4]，记号D，方程(2)记作$$(D^n+p_1D^{n-1}+\cdots+p_{n-1}D+p_n)y=0$$ 记$L(D)=D^n+p_1D^{n-1}+\cdots+p_{n-1}D+p_n$，称为微分算子$D$的$n$次多项式，方程简写为$$L(D)y=0$$
(2) 如同讨论二阶方程那样，引入$y=e^{rx}$，由于$Dy=re^{rx},\cdots,D_y^n=r^ne^{rx}$，故$L(D)e^{rx}=L(r)e^{rx}$，带入方程(2)得$$L(r)e^{rx}=0$$

[^4]: 微分算子：记号D，表示对x求导的运算$\dfrac{d}{\mathrm{d}x},\ Dy=\dfrac{\mathrm{d}y}{\mathrm{d}x},D^n_y=\dfrac{\mathrm{d}^ny}{\mathrm{d}x^n}$

特征方程$L(r)=0$的根|微分方程$L(D)y=0$ 通解的对应项
:---|:---
单实根$r$|给出一项：$Ce^{rx}$
一对单复根$r_{1,2}=α±β i$|给出两项：$e^{α x}(C_1\cosβ x+C_2\sinβ x)$
k重实根$r$|给出k项：$e^{rx}(C_1+C_2x+\cdots+C_kx^{k-1})$
一对k重复根$r_{1,2}=α±β i$|给出2k项：$e^{α x}[(C_1+C_2x+\cdots+C_kx^{k-1})\cosβ x+(D_1+D_2x+\cdots+D_kx^{k-1})\sinβ x]$
n个根|给出通解：$C_1e^{r_1x}+C_2e^{r_2x}+\cdots+C_ne^{r_nx}$

## 常系数非齐次线性微分方程


- **二阶方程** $$y''+py'+qy=f(x)\tag{1}$$ 其中$p,q$为常数，由解的结构一章定理可知二阶非齐次线性微分方程通解，归结为求对应齐次方程$$y''+py'+qy=0\tag{2}$$的通解和非齐次方程的一个特解$y^*$。
由于对应齐次方程的通解上节已介绍，本节只讨论$f(x)$两种特殊形式时求$y^*$的方法，这种方法的特点是不用积分就能求出特解，称为**待定系数法**。

- ==$f(x)=e^{λ x}P_m(x)$==，其中$λ$是常数，$P_m(x)$是x的m次多项式$P_m(x)=a_0x^{m}+a_1x^{m-1}+\cdots+a_{m-1}x+a_m$
(1) 考虑到右端指数函数$e^{λ x}$和多项式$P_m(x)$的导数仍然是指数函数和多项式的乘积，因此要想使等式恒成立，推测$$y^*=R(x)e^{λ x}$$，然后考虑选取适当的多项式满足方程(1)
(2) 将$y^* ,y^*\ ',y^*\ ''$带入方程(1)，并消去$e^{λ x}$得 $$R''(x)+(2λ+p)R'(x)+(λ^2+pλ+q)R(x)=P_m(x)\tag{3}$$  $\text{\textcircled a}$ 如果$λ$不是对应d的齐次方程$r^2+pr+q=0$的根，即$r^2+pr+q\ne0$，由于$P_m(x)$是x的m次多项式，要想使等式两端恒成立，可令$R(x)$是另一个m次多项式$$R_m(x)=b_0x^{m}+b_1x^{m-1}+\cdots+b_{m-1}x+b_m$$，比较等式两端x的同次幂，就得到以$b_0,b_1,\cdots,b_m$为未知数的m+1方程组，从而求得$b_i$，获得特解$y^*$
$\text{\textcircled b}$  如果$λ$是对应d的齐次方程$r^2+pr+q=0$的**单根**，即$r^2+pr+q=0,2λ+p\ne0$，要想使等式两端恒等，$R'(x)$必须是m次多项式，此时可令$$R(x)=xR_m(x)$$ 并且用同样的方法确定系数$b_i$
$\text{\textcircled c}$  如果$λ$是对应d的齐次方程$r^2+pr+q=0$的**重根**，即$r^2+pr+q=0,2λ+p=0$，要想使等式两端恒等，$R''(x)$必须是m次多项式，此时可令$$R(x)=x^2R_m(x)$$ 并且用同样的方法确定系数$b_i$
(3) 综上所述，方程$y''+py'+qy=e^{λ x}P_m(x)$的特解$$y^*=x^kR_m(x)e^{λ x}$$，$R_m(x)与P_m(x)$是同次多项式。

$k$的值|$λ和特征方程r^2+pr+q=0的根$
:---|:---
$k=0$|$λ$不是特征方程的根
$k=1$|$λ$是特征方程的单根
$k=2$|$λ$是特征方程的重根

- ==$f(x)=e^{λ x}[P_l(x)\cosω x+Q_n(x)\sinω x]$==，其中$λ,ω$是常数，$ω \ne0$，$P_l(x)和Q_n(x)$是x的l和n次多项式，且仅有一个可为0
(1) 应用欧拉公式$$\cosθ=\frac{1}{2}(e^{iθ}+e^{-iθ}),\sinθ=\frac{1}{2i}(e^{iθ}+e^{-iθ})$$把$f(x)$变成复指数形式$$f(x)=P(x)e^{(λ+ω i)x}+\bar{P}(x)e^{(λ-ω i)x}$$其中$P(x)=\dfrac{P_l}{2}-\dfrac{Q_n}{2}i,\bar{P}(x)=\dfrac{P_l}{2}+\dfrac{Q_n}{2}i$，是共轭的m次多项式（即对应的次数是共轭复数），而$m=\max\{l,n\}$
(2) 应用上一目的结果，对于$f(x)$的第一项$P(x)e^{(λ+ω i)x}$，可求出m次多项式$R_m(x)$，使得$y_1^*=x^kR_m(x)e^{(λ+ω i)x}$是方程$$y''+py'+qy=P(x)e^{(λ+ω i)x}$$的特解
(3) 由于$f(x)$的第一项$P(x)e^{(λ+ω i)x}$与第二项$\bar{P}(x)e^{(λ-ω i)x}$共轭，所以与$y_1^*$成共轭的函数$y_2^*=x^k\bar{R}_m(x)e^{(λ+ω i)x}$必然是方程$$y''+py'+qy=\bar{P}(x)e^{(λ+ω i)x}$$的特解
(4) 应用**叠加原理**，方程具有特解$$\begin{aligned} y^*&=x^kR_m(x)e^{(λ+ω i)x}+x^k\bar{R}_m(x)e^{(λ+ω i)x} \\ 
& =x^ke^{λ x}[R_m^{(1)}(x)\cosω x+R_m^{(2)}\sinω x]
\end{aligned} $$ 其中$R_m^{(1)}(x),R_m^{(2)}(x)$是m次多项式，$m=\max\{l,n\}$，而$k$按$λ+ω i$或$λ-ω i$不是特征方程的根，是特征方程的根，依次取0,1

- **n阶常系数非齐次线性微分方程** $$y^{(n)}+p_1y^{(n-1)}+\cdots+p_{n-1}y'+p_ny=f(x)$$ 其中$p_1,p_2,\cdots,p_n$为常数
(1) 当$f(x)=e^{λ x}P_m(x)$，特解$y^*=x^kR_m(x)e^{λ x}$，$k$是特征方程含根$λ$的重复次数（$λ$不是特征方程的根，$k=0$，$λ$是特征方程的s重根，$k=s$）
(2) 当$f(x)=e^{λ x}[P_l(x)\cosω x+Q_n(x)\sinω x]$，特解$y^*=x^ke^{λ x}[R_m^{(1)}(x)\cosω x+R_m^{(2)}\sinω x]$，$k$是特征方程中含根$λ+ω i$或$λ-ω i$的重复次数

## 欧拉方程
其中变系数微分方程，形如$$y^{(n)}+p_1x^{n-1}y^{(n-1)}+\cdots+p_{n-1}xy'+p_ny=f(x)$$ 的方程（其中$p_1,p_2,\cdots,p_n$为常数），叫做欧拉方程。
做变换$x=e^t$，将自变量x换为t[^5]，求得
$$\begin{aligned}
&\dfrac{\mathrm{d}y}{\mathrm{d}x}=\dfrac{1}{x}\dfrac{\mathrm{d}y}{dt} \\ 
&\dfrac{\mathrm{d}^2y}{\mathrm{d}x^2}=\dfrac{1}{x^2}(\frac{\mathrm{d}^2y}{\mathrm{d}t^2}-\dfrac{\mathrm{d}y}{\mathrm{d}t}) \\
&\dfrac{\mathrm{d}^3y}{\mathrm{d}x^3}=\dfrac{1}{x^3}(\dfrac{\mathrm{d}^3y}{\mathrm{d}t^3}-3\dfrac{\mathrm{d}^2y}{\mathrm{d}t^2}+2\dfrac{\mathrm{d}y}{\mathrm{d}t})\end{aligned}$$引入微分算子D[^4]，上述计算结果可表示为
$$\begin{aligned}
&xy'=Dy \\
&x^2y''=D(D-1)y \\
&x^3y'''=D(D-1)(D-2)y
\end{aligned}$$
一般得有$x^ky^{(k)}=D(D-1)\cdots(D-k+1)y$，把他带入欧拉方程，便得到一个以t为自变量得常系数线性微分方程。

[^5]: 这里仅在$x>0$范围内求解，若$x<0$，可变化为$x=-e^t$，所得结果类似。


# 非线性微分方程基本理论
- **里卡蒂方程**：形如 的微分方程称为 ==里卡蒂方程== (Riccati equation)

微分方程解析理论analytic theory of differential equation
代数微分方程algebraic differential equation
潘勒韦理论Painleve&1& theory
Nonlinear systems


# 定性理论与分支方法初步
定性理论qualitative theory
Equilibria and limit cycles(平衡与极限环)
Hyperbolic equilibria and stable limit cycle (双曲平衡与稳定极限环)
Chaos and the Lorenz attractor(混沌与洛伦兹吸引子)

流动奇点movable singular point
Perturbation Method(摄动法; 微扰方法)
Phase Portraits(相图; 相轨迹;)

相空间(Phase Space)
相即是状态(state)

> [常微分方程的“动力系统”（相空间）分析简介](http://bbs.21ic.com/icview-2599270-1-1.html)
> 百度百科：[相空间](https://baike.baidu.com/item/%E7%9B%B8%E7%A9%BA%E9%97%B4/8172498#viewPageContent)
> 百度百科： [相空间表述](https://baike.baidu.com/item/%E7%9B%B8%E7%A9%BA%E9%97%B4%E8%A1%A8%E8%BF%B0/22687295) (量子力学)
> 知乎：[什么是相空间？](https://www.zhihu.com/question/264986355?sort=created)

# 边值问题(boundary value problem)
边值条件boundary value condition
自伴边值问题self-adjoint boundary value problem









