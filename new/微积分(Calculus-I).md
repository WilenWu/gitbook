---
title: 微积分(Calculus I)
tags: [R]
mathjax: false
copyright: true
date: 2019-04-24 14:52:57
categories: [R,Calculus I]
sticky: false
---


------

[微积分(Calculus I)](https://blog.csdn.net/qq_41518277/article/details/89397964)
[微积分(Calculus II)](https://blog.csdn.net/qq_41518277/article/details/89761069)
[微积分(Calculus III)](https://blog.csdn.net/qq_41518277/article/details/90029881)

------


> 本文参考MOOC同济大学和国防科技大学《高等数学》课程。
> 友情链接：[数学分析-简书](https://www.jianshu.com/c/4ec5a35f71e5)

<!-- more -->
# 集合和映射(Set and Map)
- **集合**：将具有某种特定性质的对象的全体称为集合. 组成集合的对象
称为元素。$a\in A$ 或者 $a\not\in A$
- **集合的两种表示方法**
(1) 枚举法：$A=\{a_1,a_2,\dots,a_n\}$
(2) 描述法：$B=\{x|x满足条件P\}$
- **集合的关系**
相等：$A=B$
子集：$A⊂ B$
空集：$\emptyset$

- **常见数集的表示方法**
自然数：$\N=\{1,2,\dots\}$
整数：$\Z=\{0,±1,±2,\dots\}$
有理数：$\Bbb{Q}=\{p/q\mid p,q\in\Z,q\neq0\}$
实数：$\Reals$
复数：$\Complex$
- **集合的运算**
并集：$A∪ B=\{x\mid x\in A或x\in B\}$
交集：$A∩ B=\{x\mid x\in A\ 且\ x\in B\}$
差集：$A-B=\{x\mid x\in A且x\notin B\}$
补集：$\bar A=Ω-A$
直积(笛卡儿积)：$A× B=\{(x,y)\mid x\in A,y\in B\}$

- **区间**(interval)：设$a,b\in \R, 且a<b$
开区间(open interval)：$(a,b)=\{x\mid a<x<b\}$
闭区间(closed interval)：$[a,b]=\{x\mid a⩽ x⩽ b\}$
半开半闭区间：$(a,b]=\{x\mid a< x⩽ b\}和[a,b)=\{x\mid a⩽ x< b\}$
无限开区间$(a,+∞)=\{x\mid x>a\}和(-∞,b)=\{x\mid x<b\}$
无限闭区间：$[a,+∞)=\{x\mid x⩾ a\}和(-∞,b]=\{x\mid x⩽ b\}$
全体实数的集合：$\R=(-∞,+∞)$

- **邻域**(neighborhood)：以点a 为中心的任何开区间，记作：$U(a)$
$δ$ 邻域(δ neighborhood)：$U(a,δ)=\{x\mid 0⩽\mid x-a\mid<δ\}$
去心邻域(punctured neighbourhood)：$\mathring{U}(a,δ)=\{x\mid 0<\mid x-a\mid<δ\}$

- **映射**(map)：设$A,B$是两个非空集合，若对A中的任一元素$x$，依照某种规律（或法则）$f$，恒有$B$中的==唯一确定==的元素$y$与之对应，则称对应规律$f$为一个从$A$到$B$的映射，记作$f: A\to B$

# 函数和极限(Function and Limit)
- **函数**(function)：设$D$是$\R$中的非空子集，称映射$f: D\to \R$为定义在$D$上的一元函数(function of one variable)。通常记作：$y=f(x),x\in D$，x为自变量(independent variable)，y是因变量，D为定义域。
自然定义域：函数表达式在实数域中有意义的所有自变量的集合
实际定义域：问题的实际背景所要求的自变量的取值范围


- **函数的性质**
反函数(inverse)：$f^{-1}(y)=x,x\in f(D)$
复合函数(composite)： $f\circ g=f[g(x)]$
偶函数(even)： $f(x)=f(-x)$
奇函数(odd)： $f(x)=-f(x)$
周期函数(periodic function)： $f(x± T)=f(x)$

- **初等函数**(elementary function)：由常数和基本初等函数经有限次四则运算和有限次函数复合构成的函数，称为初等函数。
==基本初等函数==包括下面五种函数：
(1) 幂函数(power function)：$y=x^{μ}(μ \in \R)$
(2) 指数函数(exponential function)：$y=a^x(a>0且a\neq 1)$
(3) 对数函数(logarithm function)：$y=\log_ax(a>0且a\neq 1)$
(4) 三角函数(trigonometric function)：$y=\sin x,\cos x,\tan x,\cdots$
(5) 反三角函数：$y=\arcsin x, \arccos x, \arctan x,\cdots$

- **函数极限的概念和性质**
$(1)\lim\limits_{x \to x_0} f(x)=a  \iff ∀ ϵ>0, ∃δ>0, 当0<|x-x_0|<δ时, 有|f(x)-a|<ϵ$
$(2)\lim\limits_{x \to ∞} f(x)=a  \iff ∀ ϵ>0, ∃δ>0, 当|x|>δ时, 有|f(x)-a|<ϵ$
$(\star)\lim\limits_{x \to x_0} f(x)=a  \iff \lim\limits_{x \to x_0^+} f(x)=\lim\limits_{x \to x_0^-} f(x)=a$
极限的性质：若极限存在则唯一，函数局部有界且保号。

![极限](https://img-blog.csdnimg.cn/2019051510482814.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNTE4Mjc3,size_16,color_FFFFFF,t_70 =250x)  ![极限](https://img-blog.csdnimg.cn/20190515104900112.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNTE4Mjc3,size_16,color_FFFFFF,t_70 =380x) 

- **极限运算**
(1) 若 $\lim f(x)=A, \lim g(x)=B$
$\lim[f(x)± g(x)]=\lim f(x) ± \lim g(x)=A± B \\
\lim[f(x)\cdot g(x)]=\lim f(x) \cdot \lim g(x)=A\cdot B \\
\lim\dfrac{f(x)}{g(x)}=\dfrac{\lim f(x)}{\lim g(x)}=\dfrac{A}{B} (B\neq0)$
(2) 复合函数 ，若$\lim\limits_{x \to x_0} f(x)=u_0, \lim\limits_{u \to u_0} g(u)=A \\ 
\lim\limits_{x \to x_0} f[g(x)]=\lim\limits_{u \to u_0} g(u)=A, x\in \mathring{U}(x_0,δ_0)$
(3) 设$C$为常数，$\lim f(x)=A$
$\lim C=C \\
 \lim Cf(x)=C\lim f(x) \\
 \lim[f(x)]^n=[\lim f(x)]^n$

- **极限存在准则和两个重要极限**
 (1) ==准则一==或称夹逼准则(squeeze theorem)
若$g(x)⩽ f(x)⩽ h(x),\lim g(x)=\lim h(x)=A \implies \lim f(x)=A$
$$\lim\limits_{x\to 0} \dfrac{\sin x}{x}=1$$
(2) ==准则二==
若 $∃δ>0,x\in (x_0-δ,x_0)$时，$f(x)$单调有界$\implies$左极限$f(x_0^-)$存在
$$\lim\limits_{x\to ∞} (1+\dfrac{1}{x})^x=e$$
($\star$) $f(x)$在点$x_0$处极限存在$\iff f(x_0^-)=f(x_0^+)$
![夹逼准则](https://img-blog.csdnimg.cn/20190515105349414.png)


- **无穷小和无穷大的概念**
(1) $\lim f(x)=\begin{cases} 0 &\text{infinitesimal} \\ ∞ & \text{infinity}\end{cases}$
(2) 无穷小 ($0$) 和无穷大 ($∞$) 的关系：$∞=\dfrac{1}{0},0=\dfrac{1}{∞}$
(3) 无穷小和函数极限的关系：$\lim f(x)=A\iff f(x)=A+α(x)$，其中$α(x)$是无穷小量
(4) 有限个无穷小的和是无穷小
有限个无穷小的乘积是无穷小
有界函数和无穷小的乘积是无穷小

- **无穷小阶的比较**：设 $\lim f(x)=0,\lim g(x)=0$
(1) 若$\lim \dfrac{g(x)}{f(x)}=\begin{cases}0 & 则 g(x)是比f(x)高阶的无穷小,记作g(x)=o(f(x))\\
∞ & 则 g(x)是比f(x)低阶的无穷小 \\
c\neq0 & 则 g(x)是与f(x)同阶的无穷小\\
1 & 则 g(x)是与f(x)等价的无穷小，记作f(x)∼ g(x)
\end{cases}$
(2) 若 $\lim \dfrac{g(x)}{[f(x)]^k}=c\neq0  \implies g(x)是f(x)的k阶无穷小$
(3) 设$α,β$为无穷小
==定理 I==： $β∼ α\iff β=α+ o(α)$
==定理 II==(无穷小等价代换)： $α∼ \tilde{α},β∼\tilde{β}\Rightarrow\lim\dfrac{β}{α}=\lim\dfrac{\tilde{β}}{\tilde{α}}$


- **函数的连续性**(continuous)
 (1) $f(x)在点x_0连续\iff \lim\limits_{Δ x\to 0}[f(x+Δ x)-f(x)]=0$
 (2) $f(x)在点x_0连续\iff \lim\limits_{x\to x_0}f(x)=f(x_0)$
- **连续函数的运算**
若$f(x)和g(x)在点x_0连续$
 (1) 则$f± g, f\cdot g, \dfrac{f}{g}$都在$x_0$点连续
(2) 反函数$x=f^{-1}(y)$在$f(x_0)$点连续
(3) 复合函数$f[g(x)]$在$x_0$点连续
($\star$) 初等函数在定义区间内都连续

- **零点定理和介值定理**
<kbd>零点定理</kbd>(zero theorem) 若$f(x)$在闭区间$[a,b]$上连续，且$f(a)\cdot f(b)<0$，则 至少存在一点$ξ\in(a,b)$，使$f(ξ)=0$
<kbd>介值定理</kbd>(intermediate value theorem) 若$f(x)$在闭区间$[a,b]$上连续，$f(a)=A,f(b)=B$，则对 $∀ C\in(A,B),∃ ξ\in(a,b)$，使得$f(ξ)=C$

![零点定理](https://img-blog.csdnimg.cn/20190510183255935.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNTE4Mjc3,size_16,color_FFFFFF,t_70 =250x)![介值定理](https://img-blog.csdnimg.cn/20190510182900242.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNTE4Mjc3,size_16,color_FFFFFF,t_70 =250x)
- **一致连续**(uniformly continuous)：若$f(x)在[a,b]$上连续，则$f(x)在[a,b]$上一致连续

# 导数和微分(Derivative and Differentiation)
## 导数(derivative)
 (1) $y=f(x)在点(x_0,y_0)$的导数定义为$$y'\mid_{x=x_0}=\lim\limits_{Δ x\to0}\dfrac{f(x_0+Δ x)-f(x_0)}{Δ x}$$ 可记作$y'\mid_{x=x_0}, f'(x)\mid_{x=x_0}, \dfrac{\mathrm{d}y}{\mathrm{d}x}\mid_{x=x_0}, \dfrac{\mathrm{d}f(x)}{\mathrm{d}x}\mid_{x=x_0}$
 (2)  相应的可定义$x$在定义域的导函数(derived function) $y'$，可记作$f'(x), \dfrac{\mathrm{d}y}{\mathrm{d}x}, \dfrac{\mathrm{d}f(x)}{\mathrm{d}x}$
 (3) 二阶导数$$y''=(y')'或\dfrac{\mathrm{d}^2y}{\mathrm{d}x^2}=\dfrac{\mathrm{d}}{\mathrm{d}x}\left(\dfrac{\mathrm{d}y}{\mathrm{d}x}\right)$$
 (4) 高阶导数(derivative of higher order)：一般(n-1)阶的导数叫做n阶导，记作$$y''',y^{(4)},\cdots,y^{(n)}$$或$$\dfrac{\mathrm{d}^3y}{\mathrm{d}x^3},\dfrac{\mathrm{d}^4y}{\mathrm{d}x^4},\cdots,\dfrac{\mathrm{d}^ny}{\mathrm{d}x^n}$$
(5) 导数的几何意义
$f'(x_0)$就是曲线$y=f(x)$在点$(x_0,y_0)$处切线的的斜率，切线方程为$y-y_0=f'(x_0)(x-x_0)$



- **导数表**

一阶导数|一阶导数
:---|:---
$(C)'=0\quad$|$(x^{μ})'=μ x^{μ-1}$
$(a^x)'=a^x\ln a(a>0,a\neq1)$|$(e^x)'=e^x$
$(\log_a x)'=\dfrac{1}{x\ln a}(a>0,a\neq1)$|$(\ln x)'=\dfrac{1}{x}$
$(\sin x)'=\cos x$|$(\cos x)'=-\sin x$
$(\tan x)'=\sec^2x$|$(\cot x)'=-\csc^2x$
$(\sec x)'=\sec x\tan x$|$(\csc x)'=-\csc x\cot x$
$(\arcsin x)'=\dfrac{1}{\sqrt{1-x^2}}$|$(\arccos x)'=-\dfrac{1}{\sqrt{1-x^2}}$
$(\arctan x)'=\dfrac{1}{1+x^2}$|$(\mathrm{arccot}\ x)'=-\dfrac{1}{1+x^2}$

高阶导数|高阶导数
:--|:---
$(a^x)^{(n)}=a^x(\ln a)^n$|$(e^x)^{(n)}=e^x$|
$(x^{μ})^{(n)}=\displaystyle\prod_{i=0}^{n-1}(μ-i)\cdot x^{μ-n}$|$(\ln x)^{(n)}=(-1)^{n-1}\dfrac{(n-1)!}{x^n}$|
$(\sin x)^{(n)}=\sin(x+n\cdot \dfrac{π}{2})$|$(\cos x)^{(n)}=\cos(x+n\cdot \dfrac{π}{2})$


- **求导法则**

设$u=u(x), v=v(x)$都可导，$C$是常数
一阶导数|高阶导数
:---|:---
$(u± v)'=u'± v'$|$(u± v)^{(n)}=u^{(n)}± v^{(n)}$
$(Cu)'=Cu'$|$(Cu)^{(n)}=Cu^{(n)}$
$(uv)'=u'v+uv'$|$(uv)^{(n)}=\displaystyle\sum_{k=0}^n ∁^k_n u^{(n-k)}v^{(k)}$(莱布尼茨公式)
$(\dfrac{u}{v})'=\dfrac{u'v-uv'}{v^2}(v\neq0)$|

- **反函数的求导法则**
设$x=f(y)$在区间$I_y$内单调可导，且$f'(y)\neq0$，则反函数$f^{-1}(x)$
$[f^{-1}(x)]'=\dfrac{1}{f'(y)} 或 \dfrac{\mathrm{d}y}{\mathrm{d}x}=\dfrac{1}{\dfrac{\mathrm{d}x}{\mathrm{d}y}}$

- **复合函数的求导法则** - 链式法则(chain rule)
设$y=f(u),u=g(x)都可导,则复合函数y=f[g(x)]导数$
$y'(x)=f'(u)\cdot g'(x)或\dfrac{\mathrm{d}y}{\mathrm{d}x}=\dfrac{\mathrm{d}y}{\mathrm{d}u}\cdot\dfrac{\mathrm{d}u}{\mathrm{d}x}$

## 隐函数及参数方程(implicit function & parametric equation)
- **隐函数的概念**
(1) 形如$y=f(x)$表示变量$y$与$x$之间的关系，称为显函数
(2) 由方程$F(x,y)=0$可确定一个函数$y=f(x)$，称为隐函数

- **隐函数的导数**
(1) 一般对等式左右两边分别求导，来获得$\dfrac{\mathrm{d}y}{\mathrm{d}x}$
对椭圆$\dfrac{x^2}{a^2}+\dfrac{y^2}{b^2}=1$求导
$\dfrac{2x}{a^2}+\dfrac{2y}{b^2}\cdot\dfrac{\mathrm{d}y}{\mathrm{d}x}=0 \implies\dfrac{\mathrm{d}y}{\mathrm{d}x}=-\dfrac{b^2x}{a^2y}$
(2) 在某些场景，构造隐函数，进行对数求导法比一般求导更简便些
对一般幂指函数求导 $y=u^v(u>0),u=u(x),v=v(x)$
$\ln y=v\ln u \implies\dfrac{1}{y}\dfrac{\mathrm{d}y}{\mathrm{d}x}=v'\ln u+v\dfrac{u'}{u}\implies(u^v)'=u^v(v'\ln u+\dfrac{vu'}{u})$

- **参数方程的导数**
参数方程$\begin{cases} x=φ(t) \\ y=ψ(t)\end{cases}$，可转化为$y=ψ[φ^{-1}(x)]$，导数
$$\dfrac{\mathrm{d}y}{\mathrm{d}x}=\dfrac{ψ'(t)}{φ'(t)}$$
$ψ'(t)$与$φ'(t)$之间相互依赖的变化率叫做相关(dependent)变化率

## 微分(differential)
- **微分的定义**
(1) 若函数$y=f(x)$在点$x_0$的增量$Δ y=f(x_0+Δ x)-f(x_0)$可表示为$$Δ y=AΔ x+o(Δ x)$$ 其中A是不依赖于$Δ x$的常数，则称函数在点$x_0$可微(differentiable)，$AΔ x$叫做自变量增量$Δ x$的微分(differential)，记作$\mathrm{d}y$，$$\mathrm{d}y=AΔ x$$
(2) $A=\dfrac{Δ y}{Δ x}-\dfrac{o(Δ x)}{Δ x}$，当$Δ x\to0$时，$$A=\lim\limits_{Δ x\to0}\dfrac{Δ y}{Δ x}=f'(x_0)$$
(3) 当$f'(x_0)\neq0$时，$\lim\limits_{Δ x\to0}\dfrac{Δ y}{\mathrm{d}y}=\dfrac{1}{f'(x_0)}\lim\limits_{Δ x\to0}\dfrac{Δ y}{Δ x}=1$，即等价无穷小$Δ y∼ \mathrm{d}y$ $$Δ y=\mathrm{d}y+o(\mathrm{d}y)$$
(4) 当$|Δ x|$很小时，有近似等式$Δ y\approx \mathrm{d}y$
$(\star)$ 函数$f(x)$在点$x_0$处可导$\iff$函数$f(x)$在点$x_0$处可微分(differentiable)

- **函数的微分**
通常把自变量x的增量$Δ x$，称作自变量的微分，记作$\mathrm{d}x$，函数的微分$$\mathrm{d}y=f'(x)\mathrm{d}x$$从而有$\dfrac{\mathrm{d}y}{\mathrm{d}x}=f'(x)$，称作微商(derivative)。函数的微分可通过导数公式直接求得

- **微分形式不变性**
复合函数$y=f[g(x)],u=g(x)$的微分$\mathrm{d}y=f'(u)g'(x)\mathrm{d}x=f'(u)\mathrm{d}u$，从中看出无论u是自变量还是中间变量，微分的形式保持不变。

## 微分中值定理(mean value theorem)

0. **费马引理**(Fermat's theorem)：$∀ x\in U(x_0), f(x)⩽ f(x_0)或f(x)⩾ f(x_0)\Rightarrow f'(x_0)=0$
1. **罗尔中值定理**(Rolle mean value theorem)：$f(x)在[a,b]上连续,(a,b)内可导,两端点处f(a)=f(b)\Rightarrow∃ ξ\in(a,b), f'(ξ)=0$（导数等于零的点称为函数的==驻点==, 或==稳定点==）
2. **拉格朗日中值定理**(Lagrange mean value theorem)：$f(x)在[a,b]上连续,(a,b)内可导\Rightarrow$ 
$$f(b)-f(a)=f'(ξ)(b-a)$$
![罗尔定理](https://img-blog.csdnimg.cn/20190510183701155.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNTE4Mjc3,size_16,color_FFFFFF,t_70 =200x)  ![拉格朗日中值定理](https://img-blog.csdnimg.cn/20190510183730503.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNTE4Mjc3,size_16,color_FFFFFF,t_70 =250x)
3. **柯西中值定理**(Cauchy mean value theorem)：$f(x)和F(x)在[a,b]上连续;(a,b)内可导;∀ x\in(a,b),F'(x)\neq0\Rightarrow∃ ξ\in(a,b),$
$$\dfrac{f(b)-f(a)}{F(b)-F(a)}=\dfrac{f'(ξ)}{F'(ξ)}=0$$

- **洛必达法则**(L′Hospital rule)：两个无穷小之比或两个无穷大之比的极限可能存在，也可能不存在，通常把这种极限叫做未定式，简记为$\dfrac{0}{0}或\dfrac{∞}{∞}$。还有其他不定式，如$0\cdot∞,1^{∞},0^0,∞^0,∞-∞$等类型，经过简单变换，它们一般均可化为$\dfrac{0}{0}或\dfrac{∞}{∞}$。
$f(x)和F(x)都趋于0或∞$ $$\dfrac{f(x)}{F(x)}=\dfrac{f'(x)}{F'(x)}$$
这种在一定条件下通过分子分母分别求导再求极限来确定未定式值的方法，叫做洛必达法则。

## 泰勒公式(Taylor formula)
$$\begin{aligned}
f(x)&=f(x_0)+f'(x_0)(x-x_0)+\dfrac{f''(x_0)}{2!}(x-x_0)^2+\cdots+\dfrac{f^{(n)}(x_0)}{n!}(x-x_0)^n+R_n(x) \\
&=\displaystyle\sum_{i=0}^{n}\dfrac{f^{(i)}(x_0)}{i!}(x-x_0)^i+R_n(x)
\end{aligned}$$  (1) $当f(x)在x_0处有n阶导,R_n(x)=o[(x-x_0)^n]$ 叫做佩亚诺余项(Peano remainder)
(2) 当$f(x)在U(x_0,δ)内具有n+1阶导,R_n(x)=\dfrac{f^{(n+1)}(ξ)}{(n+1)!}(x-x_0)^{n+1},ξ介于x和x_0之间$，叫做拉格朗日型余项(Lagrange remainder)
(3) 当$n=0$时，即为拉格朗日中值定理；
当$x_0=0$时，称为麦克劳林公式(Maclaurin formula)

## 导数的应用(applications)

- **函数的单调性**(monotone)
$f(x)在[a,b]内连续,(a,b)内可导,∀ x\in(a,b)\\
f'(x)\begin{cases}⩾0,& \text{monotone increasing} \\ ⩽0,& \text{monotone decreasing}
\end{cases} (f'(x)\not\equiv0)$
- **曲线的凹凸性**
==(定义)==：$f(x)在区间I连续，∀ x_1,x_2\in I，恒有\\
\begin{cases} f(\dfrac{x_1+x_2}{2})<\dfrac{f(x_1)+f(x_2)}{2},&f(x)在I上图形为凹弧
\\ f(\dfrac{x_1+x_2}{2})>\dfrac{f(x_1)+f(x_2)}{2},&f(x)在I上图形为凸弧
\end{cases}$
==(定理)==：$f(x)在区间[a,b]连续，在(a,b)具有二阶导数，若\\
\begin{cases}f''(x)>0,&f(x)凹弧\\f''(x)<0,&f(x)凸弧\end{cases}$
一般的，若函数经过点$(x_0,f(x_0))$函数的凹凸性改变了，点$(x_0,f(x_0))$就称为==拐点==(inflection point)。
![凹凸性](https://img-blog.csdnimg.cn/20190510191435922.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNTE4Mjc3,size_16,color_FFFFFF,t_70 =450x)
- **函数的极值**(extremum)
==(定义)==：$∀ x\in\mathring{U}(x_0),f(x)<f(x_0)$ 或 $f(x)>f(x_0)$，称$f(x_0)$ 是函数的一个极大值(maximum)或极小值(minimum)
==(必要条件)==：设$f(x)$在$x_0$处可导，$f(x_0)$为极值$\implies f'(x_0)=0$
==(第一充分条件)==：$设f(x)在x_0处连续,\\
∃ δ>0,∀ x_1\in(x_0-δ,x_0),x_2\in(x_0,x_0+δ),\\
f'(x_1)\cdot f'(x_2)\begin{cases}<0,
&f(x)在点x_0取得极值 \\>0,&f(x)在点x_0没有极值
\end{cases}$
==(第二充分条件)==：$设f'(x_0)=0,f''(x_0)\neq0,若\\
f''(x_0)\begin{cases}<0,&f(x)在点x_0取得极大值\\>0,&f(x)在点x_0取得极小值
\end{cases}$
![极值](https://img-blog.csdnimg.cn/20190513114243282.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNTE4Mjc3,size_16,color_FFFFFF,t_70 =450x)
- **曲率**(curvature)
(0) 光滑曲线：若函数$f(x)$在$[a,b]$上有连续导数，则称曲线$Γ: y=f(x),x\in[a,b]$为光滑曲线.
(1) [弧微分公式][1]：$\mathrm{d}s=\sqrt{1+y'^2}\mathrm{d}x$
(2) ==[曲率][2]==(curvature): 弧$\overset{\frown}{MM'}$的切线转角$Δα$与该弧长$Δ s$之比的绝对值称作该弧的平均曲率，记作$\overline{K}=\mid\dfrac{Δα}{Δ s}\mid$，
当$Δ s\to0,即M'\to M$时，上述$\overline{K}$的极限称作点M的曲率，记作$K=\lim\limits_{Δ\to0}|\dfrac{Δα}{Δ s}|=|\dfrac{\mathrm{d}α}{\mathrm{d}s}|$
$$K=\dfrac{|y''|}{(1+y'^2)^{3/2}}$$
(3) ==曲率圆==(circle of curvature)：曲率圆的半径$ρ$叫曲率半径$$ρ=\dfrac{1}{K}$$
曲率圆的中心$D(α,β)$叫曲率中心(center of curvature)
$$\begin{cases}α=x-\dfrac{y'(1+y'^2)}{y''} \\ 
β=y+\dfrac{1+y'^2}{y''}
\end{cases}$$
(4) ==渐屈线和渐伸线==：当点M沿曲线f(x)移动时，相应的曲率中心D的轨迹曲线
 G称为f(x)的渐屈线(evolute)，曲线f(x)叫做曲线G的渐伸线(involute)。
 ![曲率](https://img-blog.csdnimg.cn/20190429110759906.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNTE4Mjc3,size_16,color_FFFFFF,t_70 =220x)  ![曲率圆](https://img-blog.csdnimg.cn/20190429110817884.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNTE4Mjc3,size_16,color_FFFFFF,t_70 =220x)

- [**方程的近似解**][3]

# 不定积分(Indefinite Integral)
## 不定积分的概念(concept)
- **原函数**(primitive function)：$∀ x\in I,F'(x)=f(x)或dF(x)=f(x)\mathrm{d}x$，那么$F(x)$就叫做$f(x)$在区间$I$上的一个原函数。
(1) 连续函数一定有原函数。
(2) 当$F(x)$是一个原函数时，$[F(x)+C]'=f(x)$。
- **不定积分**(indefinite integral)：在区间$I上,f(x)$的带有任意常数项的原函数称为f(x)的不定区间$$\int f(x)\mathrm{d}x=F(x)+C$$ $f(x)$称为被积函数(integrand)，$x$为积分变量。

## 基本积分表(basic integral table)
[基本积分表][t0]：由导数公式得到的基本积分公式

[t0]: https://baike.baidu.com/item/%E7%A7%AF%E5%88%86%E8%A1%A8

基本积分|基本积分
:---|:---
$\int k\mathrm{d}x=kx+C$|$\int x^{μ} \mathrm{d}x=\dfrac{x^{μ+1}}{μ+1}+C$
$\int a^x\mathrm{d}x=\dfrac{a^x}{\ln a}+C$|$\int e^x\mathrm{d}x=e^x+C$
$\int \dfrac{\mathrm{d}x}{x}=\ln \mid x\mid +C$|
$\int \dfrac{\mathrm{d}x}{1+x^2}=\arctan x+C$|$\int \dfrac{\mathrm{d}x}{\sqrt{1-x^2}}=\arcsin x+C$
$\int \cos x\mathrm{d}x=\sin x+C$|$\int \sin x\mathrm{d}x=-\cos x+C$
$\int \dfrac{\mathrm{d}x}{\cos^2x}=\int \sec^2x\mathrm{d}x=\tan x+C$|$\int \dfrac{\mathrm{d}x}{\sin^2x}=\int \csc^2x\mathrm{d}x=-\cot x+C$
$\int \sec x\tan x\mathrm{d}x=\sec x+C$|$\int \csc x\cot x\mathrm{d}x=-\csc x+C$
$\int \sh x\mathrm{d}x=\ch x+C$|$\int \ch x\mathrm{d}x=\sh x+C$

## 积分方法(integration)
- **不定积分的性质**
$\int[f(x)± g(x)]\mathrm{d}x=\int f(x)\mathrm{d}x±\int g(x)\mathrm{d}x$
$\int kf(x)\mathrm{d}x=k\int f(x)\mathrm{d}x$

- **第一类换元法**(integration by substitution)
$\int f[φ(x)]φ'(x)\mathrm{d}x=[\int f(u)\mathrm{d}u]_{u=φ(x)}$
- **第二类换元法**(integration by substitution)
$\int f(x)\mathrm{d}x=[\intψ(t)ψ'(t)\mathrm{d}t]_{t=ψ^{-1}(x)}$
- **分部积分法**(integration by parts)
$\int u\mathrm{d}u=uv-\int v\mathrm{d}u$

- **有理函数的积分**：是指由两个多项式函数的商所表示的函数，其一般形式为$$R(x)=\dfrac{P(x)}{Q(x)}=\dfrac{a_0x^n+a_1x^{n-1}+\cdots+a_n}{b_0x^m+b_1x^{m-1}+\cdots+a_m}(n,m\in \N^+,a_0,b_0\neq0)$$
(1) 若m>n，则称它为真分式；若m≤n，则称它为假分式。由多项式的除法可知，假分式总能化为一个多项式与一个真分式之和。由于多项式的不定积分是容易求得的，因此只需研究真分式的不定积分，不妨设上式为真分式。
(2) 任意真分式都可化为部分分式之和，分解后的部分分式只有两类
$\dfrac{1}{(x-a)^k}和\dfrac{Ax+B}{(x^2+px+q)^l}(其中p^2-4q<0)$，分别求积分即可[^1]。

[^1]: [有理函数积分的分类讨论及一般理论总结](https://jingyan.baidu.com/article/a948d651cd9a350a2ccd2e43.html)

# 定积分(Definite Integral)
## 定积分的概念和性质(concept and property)
- **引入意义**
曲边梯形$y=f(x)$，在区间$x\in[a,b]$上的面积$A=\lim\limits_{λ\to0}\displaystyle\sum_{i=1}^{n}f(ξ_i)Δ x_i$
变速$v=v(t)$直线运动在时间段内$t\in[T_1,T_2]$的路程$s=\lim\limits_{λ\to0}\displaystyle\sum_{i=1}^{n}v(τ_i)Δ t_i$
![定积分](https://img-blog.csdnimg.cn/20190429182528612.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNTE4Mjc3,size_16,color_FFFFFF,t_70 =220x)

- **定义**：设函数$f(x)$ 在区间$[a,b]$上连续
将区间$[a,b]$分成n个子区间($x_0=a,x_n=b$)
$$[x_0,x_1], (x_1,x_2], (x_2,x_3], …, (x_{n-1},x_n]$$各区间的长度依次是$$Δ x_1=x_1-x_0,Δ x_2=x_2-x_1,\cdots,Δ x_n=x_n-x_{n-1}$$在每个子区间$(x_{i-1},x_i]$中任取一点$ξ_i$，作函数$f(ξ_i)$与小区间长度$Δ x_i$的乘积$f(ξ_i)Δ x_i(i=1,2,\cdots,n)$，并作出求和$$S=\displaystyle\sum_{i=1}^{n}f(ξ_i)Δ x_i$$  记$λ=\max\{Δ x_1,Δ x_2, \cdots,Δ x_n\}$，如果当$λ\to0$时，积分和的极限存在，且与闭区间$[a,b]$的分法及点$ξ_i$的取法无关，则这个极限叫做函数$f(x)$ 在区间$[a,b]$的定积分，记为$$\int_a^bf(x)\mathrm{d}x=\lim\limits_{λ\to0}\displaystyle\sum_{i=1}^{n}f(ξ_i)Δ x_i$$ $[a,b]$ 称为积分区间(integral interval)，$f(x)$是被积函数(integrand)。
$(\star)$ 之所以称其为定积分，是因为它积分后得出的值是确定的，是一个常数， 而不是一个函数。这里应注意定积分与不定积分仅仅在数学上有一个计算关系（牛顿-莱布尼茨公式），其它一点关系都没有！

定积分主要性质|
:---|
$\int_a^a f(x)\mathrm{d}x=0$|
$\int_a^b f(x)\mathrm{d}x=-\int_b^a f(x)\mathrm{d}x$|
$\int_a^b kf(x)\mathrm{d}x=k\int_a^b f(x)\mathrm{d}x$|
$\int_a^b [f(x)± g(x)]\mathrm{d}x=\int_a^b f(x)\mathrm{d}x ± \int_a^b g(x)\mathrm{d}x$|
$\int_a^b f(x)\mathrm{d}x=\int_a^c f(x)\mathrm{d}x + \int_c^b f(x)\mathrm{d}x$|


- **定积分中值定理**：$f(x)在区间[a,b]上连续\Rightarrow∃ξ\in[a,b],$ $$\int_a^bf(x)\mathrm{d}x=f(ξ)(b-a)$$ $f(ξ)$称为$f(x)$在区间$[a,b]$上的平均值。


- **定积分函数**：$f(x)$在区间$[a,b]$上连续，积分函数
$Φ(x)=\int_a^xf(t)\mathrm{d}t$
$Φ'(x)=\dfrac{d}{\mathrm{d}x}\int_a^xf(t)\mathrm{d}t=f(x)$

## 定积分的方法(definite integration)
- **微积分基本定理**(fundamental theorem of the calculus)又称牛顿-莱布尼茨公式(Newton-Leibniz formula)：
$如果F(x)是连续函数f(x)在区间[a,b]上的原函数，则$ $$\int_a^b f(x)\mathrm{d}x=F(x)|_a^b=F(b)-F(a)$$

- **换元法**(integration by substitution)
$\int_a^b f(x)\mathrm{d}x=\int_{α}^{β}φ(t)φ'(t)\mathrm{d}t \quad φ(α)=a,φ(β)=b$

- **分部积分法**(integration by parts)
$\int_a^b u\mathrm{d}u=uv|_a^b-\int_a^b v\mathrm{d}u$

## 反常积分(improper integral)
- **无穷区间的反常积分**
$\int_a^{+∞}f(x)\mathrm{d}x=\lim\limits_{t\to+∞}\int_a^t f(x)\mathrm{d}x\\
\int^b_{-∞}f(x)\mathrm{d}x=\lim\limits_{t\to-∞}\int^a_t f(x)\mathrm{d}x\\
\int^{+∞}_{-∞}f(x)\mathrm{d}x=\int^0_{-∞}f(x)\mathrm{d}x+\int^{+∞}_0f(x)\mathrm{d}x$

- **无界函数的反常积分**
(1) 如果函数$f(x)$在点a的任意邻域内都无界，那么点a称为瑕点（无界间断点），无界函数的反常积分又称瑕积分。
(2) 设c为瑕点，通常瑕积分仍记作
$\int_c^b f(x)\mathrm{d}x=\lim\limits_{t\to c^+}\int_t^b f(x)\mathrm{d}x,x\in(c,b]\\ 
\int_a^c f(x)\mathrm{d}x=\lim\limits_{t\to c^-}\int_a^t f(x)\mathrm{d}x,x\in[a,c) \\
\int_a^b f(x)\mathrm{d}x=\int_a^c f(x)\mathrm{d}x + \int_c^b f(x)\mathrm{d}x,x\in[a,c)∪(c.b]$

- **$Γ$函数**
$Γ(s)=\int_0^{+∞}e^{-x}x^{s-1}\mathrm{d}x\quad(s>0)$
==递推公式==：$Γ(s+1)=sΓ(s)$
推广阶乘：$s!\overset{def}{=} Γ(s+1),s>0$
==余元公式==：$Γ(s)Γ(1-s)=\dfrac{π}{\sinπ s}$
==概率论常用积分==：
$Γ(s)$换元推导出$\int_0^{+∞}e^{-u^2}\mathrm{d}u=\dfrac{\sqrt π}{2}$


## 定积分的应用(applications)

- 求椭圆的面积：参数方程$\begin{cases}x=a\cos t \\ y=b\sin t\end{cases}$
$A=4A_1=4\int_0^a y\mathrm{d}x=π ab$

- 计算阿基米德螺线的面积（极坐标）：$ρ=aθ\quad(a>0)$
$\mathrm{d}A=\dfrac{1}{2}(aθ)^2\mathrm{d}θ \Rightarrow A=\int_0^{2π}\mathrm{d}A=\dfrac{4}{3}a^2π^3$

- 旋转体的体积：曲线$y=f(x)$
$\mathrm{d}V=π[f(x)]^2\mathrm{d}x \Rightarrow V=\int_a^b π[f(x)]^2\mathrm{d}x$

- 平面曲线的弧长
(1) 直角坐标$y=f(x)\Rightarrow s=\int_a^b\sqrt{1+y'^2}\mathrm{d}x$
(2) 极坐标$ρ=ρ(θ)\Rightarrow s=\int_{α}^{β}\sqrt{ρ^2(θ)+ρ'^2(θ)}\mathrm{d}θ$

![椭圆](https://img-blog.csdnimg.cn/20190513133325697.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNTE4Mjc3,size_16,color_FFFFFF,t_70 =250x200)    ![旋转体](https://img-blog.csdnimg.cn/2019051313334118.png =250x)

  [1]: https://jingyan.baidu.com/article/67508eb47596589cca1ce49f.html
  [2]: https://baike.baidu.com/item/%E6%9B%B2%E7%8E%87/9985286?fr=aladdin
  [3]: https://jingyan.baidu.com/article/7f41ecec213810593d095c28.html



