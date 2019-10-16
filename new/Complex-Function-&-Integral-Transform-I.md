---
title: 复变函数和积分变换(Complex Function & Integral Transform I)
tags: [R]
mathjax: false
copyright: true
date: 2019-05-28 14:28:06
categories: [R,Complex Function & Integral Transform I]
sticky: false
---


@[Toc](数学物理方法)

------

[复变函数和积分变换(Complex Function & Integral Transform I)](https://blog.csdn.net/qq_41518277/article/details/89742631)
[复变函数和积分变换(Complex Function & Integral Transform II)](https://blog.csdn.net/qq_41518277/article/details/99679827)
[复变函数和积分变换(Complex Function & Integral Transform III)](https://blog.csdn.net/qq_41518277/article/details/97121991)

------

> 参考文献：
> mooc国防科技大学《复变函数》
> 王忠仁、张静《工程数学：复变函数和积分变换》
> 焦红伟、尹景本《复变函数与积分变换》
> 梁昆淼《数学物理方法》


<!-- more -->
# 复数与复变函数
## 复数(Complex Number)
==复数==(Complex Number)：形如 $z=x+\text{i}y\quad (x,y\in\R)$，其中 $\text{i}$ 满足 $\text{i}^2=-1$ 称为虚数单位，$x$ 和 $y$ 分别称为复数的实部和虚部，记作$x=\text{Re }z,y=\text{Im }z$。
如果$z=\text{i}y$ 称为纯虚数，$z=x$ 看做实数。
如果两复数实部和虚部分别相等，则两复数相等。
==复数域==(Complex Number Field)： $\Complex=\{z|z=z=x+\text{i}y,\ x,y\in\R\}$
==复平面==(Complex Plane)：由于一个复数与 $z=x+\text{i}y$ 与有序实数对 $(x,y)$ 一一对应
$xOy$ 平面 $\iff$ 复平面 $\Complex$
复数 $z=x+\text{i}y \iff \R^2$上的点 $P(x,y) \iff \R^2$ 上的向量 $\overrightarrow{OP}$
![复平面](https://img-blog.csdnimg.cn/20190705112711269.png)
==复数的模==(modulus)：向量的长度称为复数的模，记作 $|z|=\sqrt{x^2+y^2}$
==复数的幅角==(argument angle)：$Ox$ 轴到 $\overrightarrow{OP}$ 沿逆时针方向所形成的角 $\text{Arg }z=θ+2kπ\quad(k\in \Z)$
==幅角的主值==(principal argument angle)：辐角 $\text{Arg }z=\arg z+2kπ\quad(k\in \Z)$，主值可取 $\arg z\in[0,2π)$ 或 $\arg z\in(-π,π]$
由于反正切函数 $\arctan θ \in(-π/2,π/2)$，于是分段求出辐角主值 $\arg z\in(-π,π]$
$\arg z=\begin{cases} 
\arctan\frac{y}{x} &\text{if } x>0&\text{(I,IV)} \\ 
\frac{π}{2} &\text{if } x=0,y>0 \\
\arctan\frac{y}{x}+π &\text{if } x<0,y⩾0 &\text{(II)} \\ 
-\frac{π}{2} &\text{if } x=0,y<0 \\
\arctan\frac{y}{x}-π &\text{if } x<0,y<0 &\text{(III)}
\end{cases}$
==复数的三角表示==：$z=|z|(\cosθ+\text{i}\sin θ)\quad(θ=\text{Arg }z)$
==复数的指数表示==：由欧拉公式 $\boxed{e^{iθ}=\cosθ+\text{i}\sin θ}$ 得到 $z=|z|e^{iθ}$

- **复数的代数运算**(Arithmetic with Complex Numbers)
设 $z_1=x_1+\text{i}y_1,\ z_2=x_2+\text{i}y_2$
$z_1+z_2=(x_1+x_2)+\text{i}(y_1+y_2)$
$z_1z_2=(x_1x_2-y_1y_2)+\text{i}(x_1y_2+x_2y_1)$
由加法和乘法可以定义减法和除法
$z_1-z_2=(x_1-x_2)+\text{i}(y_1-y_2)$
$\dfrac{z_1}{z_2}=\dfrac{x_1x_2+y_1y_2}{x_2^2+y_2^2}+\text{i}\dfrac{x_2y_1-x_1y_2}{x_2^2+y_2^2}$
由上述规定，可以验证：加法、乘法满足交换律与结合律，乘法对加法满足分配律。由此可知，在实数域里由这些规律推得的恒等式在复数里仍然有效。复数集关于四则运算是封闭的，其代数结构是域。

- **共轭复数(conjugate complex number)及性质**：$\bar z=x-\text{i}y$
(1) $\overline{z_1± z_2}=\bar z_1± \bar z_2,\ \overline{z_1z_2}=\bar z_1\bar z_2,\ \overline{z_1/z_2}=\bar z_1/\bar z_2$
(2) $\bar{\bar z}=z$
(3) $z\bar z=|z|^2=|\bar z|^2$
(4) $x=\dfrac{1}{2}(z+\bar z),\ y=\dfrac{1}{2i}(z-\bar z)$

- **复数的性质**
(1) $z_1z_2=|z_1||z_2|[\cos(θ_1+θ_2)+\text{i}\sin(θ_1+θ_2)]$
(2) $\text{Arg }(z_1z_2)=\text{Arg }z_1+\text{Arg }z_2$
$\text{Arg }(z_1/z_2)=\text{Arg }z_1-\text{Arg }z_2$
(3) $|z_1z_2|=|z_1||z_2|,|z_1/z_2|=|z_1|/|z_2|$
(5) $|z_1+ z_2|^2=|z_1|^2+|z_2|^2+2\text{Re }(z_1\bar z_2)$
三角不等式：$||z_1|-|z_2||⩽ |z_1± z_2| ⩽ |z_1|+|z_2|$

- **乘幂**(power)
设复数 $z=|z|(\cos θ+i\sin θ)=|z|e^{iθ} \quad(θ=\text{Arg }z)$
由三角函数的性质可知 $z^n=|z|^n[\cos(nθ)+i\sin(nθ)]=|z|^ne^{inθ}$
特别的有 $(\cos θ+i\sin θ)^n=\cos(nθ)+i\sin(nθ)$ <kbd>De Moivre formula</kbd>
- **n次方根**(n-th root)
将满足 $z=w^n$ 的$w$称为$z$的$n$次方根，记为 $w=\sqrt[n]{z}\quad(n=1,2,\cdots)$
$\begin{aligned} 
w &=\sqrt[n]{|z|}(\cos\dfrac{θ}{n}+i\sin\dfrac{θ}{n}) \\ 
& =\sqrt[n]{|z|}(\cosφ+i\sinφ)  \\
& =\sqrt[n]{|z|}e^{iφ}
\end{aligned}$
其中 $φ=\dfrac{\arg z+2kπ}{n}$
当 $k=0,1,2,⋯, n-1$ 时，存在 $n$ 个辐角各不相等的根，在几何上，$\sqrt[n]{z}$表示位于复平面上以原点 $O$ 为圆心，以 $\sqrt[n]{|z|}$ 为半径的内接正 $n$ 边形的顶点。

- **复球面与无穷远点**(complex sphere & point at infinity)
![复球面](https://img-blog.csdnimg.cn/20190705145704554.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNTE4Mjc3,size_16,color_FFFFFF,t_70 =250x)
复球面方程 $Σ:x^2+y^2+u^2=1$
对于复平面上任意一点 z，如果用直线连接点 z和复球面北极 N，那么该直线一定与复球面相交于异于N点的另一点 $A'$，复平面上的点 $A(x,y)$ 与复球面上的点 $A'(x',y',u')$ 一一对应
$z=x+\text{i}y=\dfrac{x'+\text {i}y'}{1-u'}$
$x'=\dfrac{z+\bar z}{|z|^2+1},\ y'=\dfrac{z-\bar z}{i(|z|^2+1)},\ u'=\dfrac{|z|^2-1}{|z|^2+1}$
定义北极 $N(0,0,1)$ 在复平面上对应点为无穷远点，记为 $∞$
复平面加上无穷远点后称为==扩充复平面==(extended complex plane)
关于 $∞$ 的运算法则：
$|∞|=+∞ \\ 
a+∞=∞+a=∞ \\
a\cdot∞=∞\cdot a=∞ \\
a/0=∞(a\neq 0),\quad a/∞=0(a\neq ∞)$
其他关于$∞$的运算无定义。

- **几何方程复数表示**
==复数表示圆的一般方程==：$a(x^2+y^2)+bx+cy+d=0\quad(a,b,c,d\in\R,\ a\neq 0)$
$\implies az\bar z+\barβ z+β \bar z+d=0,\quadβ=\frac{1}{2}(b+\text{i}c)$
==过复平面上不同两点 $a,b$ 的直线==： $\text{Im }\dfrac{z-a}{z-b}=0$
==过不共线三点 $a,b,c$ 的圆的方程==：$\text{Im }(\dfrac{z-b}{z-a}\cdot\dfrac{c-a}{c-b})=0$

## 平面点集(Planar Point Set)
- **邻域(neighborhood)和去心邻域**：设 $z_0$为一个定点，$ρ>0$
$U(z_0,ρ)=\{z∣|z−z_0|<ρ,z\in\Complex\} \\
\mathring{U}(z_0,ρ)=\{z∣0<|z−z_0|<ρ,z\in\Complex\}$
- **点与点集的关系**：任意一点 $z_0\in\Complex$与任意一点集 $E⊂\Complex$
内点(interior point)：$∃ ρ>0,U(z_0,ρ)⊂ E$
外点(exterior point)：$∃ ρ>0,U(z_0,ρ)∩ E=\empty$
边界点(boundary point)：若 $z_0$ 的任一邻域 $U(z_0,ρ)$ 中既含 $E$ 的点也含不是 $E$ 的点,则称  $z_0$为 $E$ 的边界，记作 $∂ E$
聚点(point of accumulation)：$∀ ρ>0,\mathring{U}(z_0,ρ)∩ E\neq \empty$
孤立点(isolated point)：$∃ ρ>0,z_0\in E,\mathring{U}(z_0,ρ)∩ E= \empty$
![点集](https://img-blog.csdnimg.cn/20190513151351378.png)
-  **定义一些重要的点集**
开集：$∀ z_0\in E$，$z_0$ 都是E的内点
闭集：$E$ 的全部聚点都属于 $E$
有界集：$∃ U(z_0,ρ),E⊂ U(z_0,ρ)$，点集 $E$为有界集
无界集：不是有界集的点集
连通集：点集E内任何两点都可以用折线连接起来，且该折线上的点都属于E
- **区域和曲线**
区域（或开区域）：连通的开集
闭区域：开区域连同它的边界一起构成的点集 $\bar E=E∪∂ E$
<kbd>定义</kbd>：设 $x(t )$与 $y (t )$ 是定义在区间 $[α ,β ]$上的实函数，曲线 $C$ 在复平面上的点集 $z(t) = x(t) + i y(t)$ ， $z(α )$ 与 $z(β )$ 分别称为曲线 $C$ 的起点与终点。曲线C 的方向规定为参数t 增加的方向，曲线C 的反向曲线记为 $C^-$
==连续曲线==(Continuous curve)：$x(t )$与 $y (t )$ 在区间 $[α ,β ]$上连续
==闭曲线==(Closed curve)：若 $z(α ) = z(β )$，则称 $C$为闭曲线
==简单曲线==(Simple curve)：当且仅当 $t_1=t_2$时，$z(t_1)=z(t_2)$
==Jordon 曲线==：连续的简单曲线
==光滑曲线==(Smooth curve)：$x(t )$与 $y (t )$ 在区间 $[α ,β ]$有连续导数，且 $z'(t)\neq 0$。称由有限条光滑曲线首尾连接而成的曲线为==逐段光滑曲线==(Piecewise smooth curve)。
为方便起见，称逐段光滑的闭曲线为围线．关于围线的方向规定为：逆时针方向为正向，顺时针方向为负向。
<kbd>Jordan 定理</kbd>：任意一条 Jordon 闭曲线C 必将复平面唯一地分成$D_1,C,D_2$ 三个点集，使它们满足：
![Jordon](https://img-blog.csdnimg.cn/20190708161927277.png)
(1) 彼此不相交；
(2) $D_1$ 是一个有界区域(称为曲线C 的内部)；
(3) $D_2$ 是一个无界区域(称为曲线C 的外部)；
(4) $C$ 既是 $D_1$ 的边界又是 $D_2$ 的边界；
(5) 若简单折线(指满足简单曲线定义的折线) $Γ$ 的一个端点属于$D_1$，另一个端点属于$D_2$，则 $Γ$ 必与 $C$ 相交．
设D 为区域，若D 中任意一条 Jordon 闭曲线的内部仍属于D ，则称D 为==单连通区域==(simply connected region)，不是单连通区域的区域称为==多连通区域==(multiply connected region)。
![连通区域](https://img-blog.csdnimg.cn/20190708162606745.png)

- **无穷远点的邻域**：设 $ρ>0$，在扩充复平面上
$U(∞,ρ)=\{z||z|>ρ,z\in\Complex_{∞}\}$
几何意义：表示曲线 $| z |= ρ$ 的外部。
在扩充复平面上，若一个区域内的每一条Jordon 闭曲线的内部或外部(包含无穷远点)都属于这个区域，则称该区域为单连通区域．称不是单连通区域的区域为复连通区域。

## 复变函数(Complex Function)
- ==复变函数==：设 $E$ 为复平面上的点集 $w=f(z),z\in E$ ，定义域为$E$，值域为 $G$
若对映射 $f$ 只有一个确定的w与z 对应，则称 $w = f (z)$为单值函数，如 $w=z^2$。否则，称$w = f (z)$为多值函数，如 $w=\text{Arg }z,w=\sqrt{z}$。
设 $z=x+iy,w=u+iv$，复变函数的实部与虚部均可用二元实值函数来表示 $w=f(z)=u(x,y)+iv(x,y)$
因此，研究复变函数可以转化为研究二元实值函数
由于复变函数$w = f (z)$的几何图形需在四维空间里考虑，所以，不可能有像实值函数 $y = f (x)$ 与$z = f (x, y)$的那种直观的感觉。为了赋予复变函数几何解释，复变函数$w=f(z),z\in E$可看作 $z$  平面点集 $E$ 到 $w$ 平面点集 $G$ 的映射
![映射](https://img-blog.csdnimg.cn/20190710154121809.png)
- **极限**(limit)：设复变函数 $w=f(z)$在 $z_0$的某个去心邻域 $\mathring U(z_0,ρ)$ 内有定义，$A$ 为复常数
若 $∀ϵ>0,∃δ>0(δ<ρ)$，使得 $0<|z-z_0|<δ$时，总有 $|f(z)-A|<ϵ$，则称当 $z$趋近于 $z_0$时 $A$为 $f(z)$的极限，并记作 $\lim\limits_{z\to z_0}f(z)=A$ 或 $f(z)\to A(z\to z_0)$
**极限存在的充要条件**：设 $w=f(z)=u(x,y)+iv(x,y),A=u_0+iv_0,z_0=x_0+iy_0$则
$\lim\limits_{z\to z_0}f(z)=A\iff \lim\limits_{(x,y)\to (x_0,y_0)}u(x,y)=u_0,\lim\limits_{(x,y)\to (x_0,y_0)}v(x,y)=v_0$
**极限运算法则**：设 $\lim\limits_{z\to z_0}f(z)=A,\lim\limits_{z\to z_0}g(z)=B$
$\lim\limits_{z\to z_0}[f(z)± g(z)]=A± B$
$\lim\limits_{z\to z_0}f(z)g(z)=AB$
$\lim\limits_{z\to z_0}f(z)/g(z)=A/B$

- **连续**(continuous)：若 $\lim\limits_{z\to z_0}f(z)=f(z_0)$，则 $w=f(z)$在 $z_0$处连续
若 $f(z)$在点集 $E$的每一个聚点连续，则 $f(z)$在$E$连续
**连续的充要条件**：$f(z)=u(x,y)+iv(x,y)$在 $z_0=x_0+iy_0$处连续$\iff u(x,y),v(x,y)$ 在点 $(x_0,y_0)$处连续
**连续函数的性质**
(1) 连续函数的和、差、积、商（分母不为0）是连续函数;
(2) 连续函数的复合函数是连续函数.
若函数 $f(z)$在有界闭区域 $\bar D$上连续，则
(1) $f(z)$在$\bar D$上为有界函数；
(2) $|f(z)|$ 在$\bar D$上能取到最大值与最小值，即有 $z_1,z_2\in\bar D$，$∀ z\in\bar D,|f(z_1)|⩽ |f(z)|⩽|f(z_2)|$
(3) $f(z)$ 在 $\bar D$ 上一致连续，即$∀ϵ>0,∃δ>0$，使得当$|z_1-z_2|<δ(z_1,z_2\in\bar D)$时，有$|f(z_1)-f(z_2)|<ϵ$

# 解析函数(Analytic Function)
## 导数和解析函数
- **导数**(Derivative)
(1) 复变函数 $w=f(z),z\in D$在 $z_0$处的导数定义为 $$\lim\limits_{Δ z\to0}\dfrac{f(z_0+Δ z)-f(z_0)}{Δ z}$$ 可记作$f'(z_0), f'(z)|_{z=z_0},\dfrac{\mathrm{d}f(z)}{\mathrm{d}z}|_{z=z_0}$
 (2)  如果函数在定义域D内处处可导，则称函数在 D内可导
 (3) 与实函数的一致，复变函数的==微分== $\mathrm{d}w=f'(z)\mathrm{d}z$
 (4) 设 $u=u(z),v=v(z)$都可导
$(u± v)'=u'± v'$
$(uv)'=u'v+uv'$
$(\dfrac{u}{v})'=\dfrac{u'v-uv'}{v^2}(v\neq0)$
复合函数求导法则：$f'(z)=f'(w)g'(z),w=g(z)$
反函数求导：$[f^{-1}(z)]'=\dfrac{1}{f'(z)}$，其中 $f(z)$为单值函数

- **解析函数**(analytic function)
(1) 设函数 $w=f(z),z\in D$，对于点 $z_0\in D$，若$∃ U(z_0,ρ)$，使得函数 $f (z)$ 在该邻域内处处可导，则称函数$f (z)$在点 $z_0$ ==解析==(analytic)。此时称点$z_0$为函数的==解析点==(analytic point)。若函数$f (z)$在点 $z_0$ 不解析，则称$z_0$为==奇点==(singular point)。
(2) 若函数 $f (z)$ 在区域D内每一点都解析，则称函数$f (z)$在区域D内解析，$f (z)$为区域D内的==解析函数==，区域D又称为函数 f (z)的解析区域或解析域。
(3) 解析与可导的关系：函数在一点解析与函数在该点可导不是一回事，函数在一个区域内解析与该函数在这个区域内处处可导则等价。
**解析函数的性质**
(1) 解析函数的和、差、积、商（分母不为0）是解析函数；
(2) 解析函数的复合函数是解析函数.

- **函数解析的充要条件**
函数 $f(z)=u(x,y)+iv(x,y)$ 在区域D内为解析函数的充分必要条件是：
(1) $u(x, y)$ 与 $v(x, y)$ 在D内可微分 [^1]
(2) 且满足<kbd>柯西-黎曼条件</kbd>(Cauchy-Riemann,C-R) 
$\dfrac{∂u}{∂x}=\dfrac{∂v}{∂y},\dfrac{∂u}{∂y}=-\dfrac{∂v}{∂x}$ 
充分性证明：设$z=x+iy$是D内任意一点，设 $Δz=Δx+iΔy,f'(z)=a+ib$
$\begin{aligned} 
Δf=Δu+iΔv & =(\frac{∂u}{∂x}Δx+\frac{∂u}{∂y}Δy)+i(\frac{∂v}{∂x}Δx+\frac{∂v}{∂y}Δy) \\ 
& =(\frac{∂u}{∂x}Δx-\frac{∂v}{∂x}Δy)+i(\frac{∂v}{∂x}Δx+\frac{∂u}{∂x}Δy) \\
& =(\frac{∂u}{∂x}+i\frac{∂v}{∂x})(Δx+iΔy) \\
& =(\frac{∂u}{∂x}+i\frac{∂v}{∂x})Δz 
\end{aligned}$
于是 $f(z)$ 在区域 D内可导，为解析函数。且可求得导数
$$f'(z)=\frac{∂u}{∂x}+i\frac{∂v}{∂x}= \frac{∂v}{∂y}-i\frac{∂u}{∂y}$$


[^1]: 二元函数全微分：若函数$z=f(x,y)$在点$(x,y)$的全增量$Δ z=f(x+Δ x,y+Δ y)-f(x,y)$可表示为$$Δ z=AΔ x+BΔ y+o(ρ)$$其中A和B不依赖于$Δ x和Δ y$而仅与x,y有关，$ρ=\sqrt{(Δ x)^2+(Δ y)^2}$，则称函数在点$(x,y)$==可微分==，$AΔ x+BΔ y$叫做==全微分==，记作$\mathrm{d}z$，即$$\mathrm{d}z=AΔ x+BΔ y$$
<kbd>必要条件</kbd>$函数z=f(x,y)在(x,y)可微分，那该函数在(x,y)偏导数 \dfrac{∂ z}{∂ x}， \dfrac{∂ z}{∂ y}必定存在$，全微分$$\mathrm{d}z=\dfrac{∂ z}{∂ x}Δ x+\dfrac{∂ z}{∂ y}Δ y$$

- **解析函数的像**(imag)
设解析函数为 $f(z)=u(x,y)+iv(x,y)$ 的值域为 G
实部和虚部的等值线分别为 $u(x,y)=u_0,v(x,y)=v_0\quad(u_0+iv_0\in G)$
梯度分别为 $∇u=\dfrac{∂u}{∂x}\mathbf{i}+\dfrac{∂u}{∂y}\mathbf{j},∇v=\dfrac{∂v}{∂x}\mathbf{i}+\dfrac{∂v}{∂y}\mathbf{j}$
由于$∇u\cdot∇v=\dfrac{∂u}{∂x}\dfrac{∂v}{∂x}+\dfrac{∂u}{∂y}\dfrac{∂v}{∂y}=0$ ，即实部和虚部的等值线互相垂直。
例如解析函数 $w=z^2$，实部和虚部等值线 $u=x^2-y^2,v=2xy$
![等值线](https://img-blog.csdnimg.cn/20190802143729298.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNTE4Mjc3,size_16,color_FFFFFF,t_70)

## 初等函数(Elementary Function)
- **指数函数**(Exponential Function)：设 $z=x+iy$
$\exp(z)=e^z=e^x(\cos y+i\sin y)$
性质：
(1) (加法定理)$∀ z_1,z_2\in\Complex,e^{z_1}e^{z_1}=e^{z_1+z_2}$
(2) $e^z$ 在复平面上为解析函数，且有$(e^z)'=e^z$
(3) 对任意复数 $z = x + iy$ ，有 $|e^z| = e^x ，\text{Arg }z = y + 2kπ ( k\in\Z)$
(4) $e^z$ 是只以 $2πi$ 为周期的周期函数
(5) $e^{z_1}=e^{z_2}\iff z_1-z_2=2kπi( k\in\Z)$
(6) **欧拉公式(Euler's Formula)**：$e^{iy}=\cos y+i\sin y$
指数函数（周期函数）的基本周期区域：$B=\{z|z\in \Complex,0<\text{Im }z⩽2π\}$
![基本周期区域](https://img-blog.csdnimg.cn/2019071216264812.png)

- **对数函数**(Logarithmic Function)： 设 $z ≠ 0$，称满足 $e^w = z$ 的 $w$称为对数函数，记作 $w=\text{Ln }z$
设 $z=re^{iθ},w=u+iv$
$\implies e^{u+iv}=re^{iθ}$
$\implies u=\ln r=\ln|z|,v=\text{Arg }z$
$\implies w=\ln|z|+i\text{Arg }z$
由于 $\text{Arg }z=\arg z+2kπ$ 为多值函数，所以对数函数为多值函数。
上式中每固定一个k就确定一个单值函数，称为 $\text{Ln }z$ 的一个==单值分支==(one-valued branch)。
记 $\ln z=\ln|z|+i\arg z$ 为对数==主值==(principal value)，对数函数 $\text{Ln } z=\ln z+2kπ i,k\in \Z$
性质：
(1) $\text{Ln }(z_1z_2)=\text{Ln }z_1+\text{Ln }z_2$，$\text{Ln }(z_1/z_2)=\text{Ln }z_1-\text{Ln }z_2$
等式 $\text{Ln }z^n=n\text{Ln },\text{Ln }\sqrt[n]{z}=\frac{1}{n}\text{Ln }z$ 不再成立
(2) 非零复数的对数有无穷多个值，任何两值之间相差的 $2π i$ 整数倍
(3) 对于主值 $\ln z$，除原点和负实轴外 $\arg z\in(-π,π)$，其他点都是连续的，因为当 $x<0$，$\lim\limits_{y\to0^+}\arg z=π,\lim\limits_{y\to0^-}\arg z=-π$
连接原点O及$∞$的一条简单连续曲线$K_1$，称为==割线==(secant)，形成相应的==割缝区域==(Slit area)：$D_1=\Complex-K_1$。
对数函数在割缝区域$D_1$内的==单值连续分支== $w_k=\ln z+2kπ i$，在区域$D_1$内是解析函数，称为==解析分支==，其他任何分支都只相差 $2π i$的整数倍。
(3) 设 $w_k$ 为对数函数 $w=\text{Ln }z$ 在区域 G内的单值连续分支，则 $w'_k=\frac{1}{z},z\in G$
![割缝区域](https://img-blog.csdnimg.cn/20190715131310602.png)

- **幂函数**(Power Function)：函数 $w=z^α=e^{α\text{Ln z}}$称为幂函数，其中α为常数，$z\neq 0$
由于 $\text{Ln z}$ 是多值函数，一般$w=z^α$也是多值函数。
(1) 当 $α=n\in\Z^+$时，为复数的n次幂，为单值函数。
$w=z^n=e^{n\text{Ln z}}=e^{n[\ln|z|+i(\arg z+2kπ)]}=|z|^ne^{i n\arg z}$
(2) 当 $α=1/n,n\in\Z^+$时，为复数的n次方根，为n值函数。
$w=z^{\frac{1}{n}}=e^{\frac{1}{n}\text{Ln z}}=\sqrt[n]{|z|}e^{i\frac{\arg z+2kπ}{n}}$
(3) 当 $α=0,z^0=e^{0\cdot \text{Ln z}}=1$
(4) 当α为有理数时，表示为 $α=p/q,q>0$且p,q为互质的整数
$w=z^{\frac{p}{q}}=e^{\frac{p}{q}\text{Ln z}}=|z|^{\frac{p}{q}}e^{i\frac{p}{q}(\arg z+2kπ)}$
当 $k=0,1,\cdots,q-1$时，有q 个互异的值。
(5) 若α为无理数或虚数，$z^α$为无穷多值
因为$z^α=e^{α\text{Ln z}}=e^{α\ln z}e^{i2αkπ}$，当$k_1,k_2\in\N$且$k_1\neq k_2$时，$e^{i2αk_1π}\neq e^{i2αk_2π}$，所以此情形下对应无穷多个值。
性质：在除去原点和负实轴的割缝区域内，幂函数$z^α$是解析的，导数 $(z^α)'=αz^{α-1}$

- **三角函数**(Trigonometric Function) ：由欧拉公式我们可以得到
$\sin z=\frac{1}{2i}(e^{iz}-e^{-iz}),\cos z=\frac{1}{2}(e^{iz}+e^{-iz})$
**性质**：
(1) $\sin z,\cos z$在复平面解析 $(\sin z)'=\cos z,(\cos z)'=-\sin z$
(2) 三角学中实变量的三角函数间的已知公式对复变量的三角函数仍然有效，例如
$\sin^2 z+\cos^2 z=1$
互余性 $\begin{cases}
\sin(\frac{π}{2}+z)=\cos z \\
\cos(\frac{π}{2}+z)=-\sin z
\end{cases}$
两角和 $\begin{cases}
\sin (z_1± z_2)=\sin z_1\cos z_2± \cos z_1\sin z_2 \\
\cos (z_1± z_2)=\cos z_1\cos z_2∓ \sin z_1\sin z_2
\end{cases}$
奇偶性 $\begin{cases}
\sin(-z)=-\sin z \\
\cos(-z)=\cos z
\end{cases}$
(3) $\sin z ,\cos z$均以2π为周期
(4) $\sin z$的零点为 $z=kπ$，$\cos z$的零点为 $z=(k+\frac{1}{2})π$
(5) $\sin z ,\cos z$均为单值函数
(6) $\sin z ,\cos z$在复数域是无界的
例如 $\cos iy$，当 $y\to∞$时，模$|\cos iy|$ 也无限增大
其他三角函数可分别定义为
$\tan z=\dfrac{\sin z}{\cos z},\cot z=\dfrac{\cos z}{\sin z},\sec z=\dfrac{1}{\cos z},\csc z=\dfrac{1}{\sin z}$

- **反三角函数**(Inverse Trigonometric Function)：反三角函数是三角函数的反函数，定义如下
若 $\sin w=z$，则 $w=\text{Arccos }z$为反余弦函数
可求得 $\text{Arccos }z=-i\text{Ln }(z+\sqrt{z^2-1})$，可见反余弦为多值函数
同理可定义反正弦函数和反正切函数，且可求得
$\text{Arcsin }z=-i\text{Ln }(iz+\sqrt{1-z^2}),\quad \text{Arctan }z=\dfrac{i}{2}\text{Ln }\dfrac{i+z}{i-z}$

- **双曲函数(Hyperbolic function)与反双曲函数**
定义 $\sh z = \frac{1}{2}(e^z-e^{-z})，\ch z = \frac{1}{2}(e^z+e^{-z})，\th z =\frac{\sh z}{\ch z}，\cth z =\frac{\ch z}{\sh z}$
分别称为复变量z 的双曲正弦函数、双曲余弦函数、双曲正切函数及双曲余切函数。
双曲函数与三角函数之间有下列关系：
 $\sh z = −i\sin iz，\ch z = \cos iz，\th z = −i \tan iz，\cth z = i \cot iz$
由这些关系也可以看出双曲函数是单值的且以虚数2πi 为周期的周期函数. $\sh z$ 为奇函数， $\ch z$ 为偶函数，而且在复平面内均解析，并有
$(\sh z)′ = \ch z ，(\ch z)'=\sh z$
由于双曲函数的周期性决定了它们的反函数——反双曲函数的多值性，这里仅将相应的反双曲函数分列如下：
反双曲正弦函数 $\text{Arsh }z=\text{Ln }(z+\sqrt{z^2+1})$
反双曲余弦函数 $\text{Arch }z=\text{Ln }(z+\sqrt{z^2-1})$
反双曲正切函数 $\text{Arth }z=\dfrac{1}{2}\text{Ln }\dfrac{1+z}{1-z}$
反双曲余切函数 $\text{Arcth }z=\dfrac{1}{2}\text{Ln }\dfrac{z+1}{z-1}$

## 初等函数附表

||Elementary Function <br>$(z=x+\mathrm{i}y)$|Derivative|Properties|
|:---|:---|:---|:---|
|Exponential Function|$e^z=e^x(\cos y+\mathrm{i}\sin y)$<br>$(T=2π\mathrm{i})$|$(e^z)'=e^z$|$e^{z_1}e^{z_1}=e^{z_1+z_2}$
|Logarithmic Function|$\text{Ln } z=\ln z+2kπ\mathrm{i}$<br>$\ln z=\ln\mid z\mid+i\arg z$|$(\ln z)'=\dfrac{1}{z}$|$\text{Ln }(z_1z_2)=\text{Ln }z_1+\text{Ln }z_2 \\ \text{Ln }(z_1/z_2)=\text{Ln }z_1-\text{Ln }z_2$
|Power Function|$z^α=e^{α\text{Ln z}}$<br>$(z\neq 0)$|$(z^α)'=αz^{α-1}$<br>$(z\not\in\R^-)$|
|Trigonometric Function<br>$(T=2π)$|$\sin z=\frac{1}{2\mathrm{i}}(e^{\mathrm{i}z}-e^{-\mathrm{i}z})$<br>$\cos z=\frac{1}{2}(e^{\mathrm{i}z}+e^{-\mathrm{i}z})$|$(\sin z)'=\cos z$<br>$(\cos z)'=-\sin z$|$\sin^2 z+\cos^2 z=1$<br>$\begin{cases}\sin(\frac{π}{2}+z)=\cos z \\ \cos(\frac{π}{2}+z)=-\sin z\end{cases}$<br> $\begin{cases}\sin (z_1± z_2)=\sin z_1\cos z_2± \cos z_1\sin z_2 \\ \cos (z_1± z_2)=\cos z_1\cos z_2∓ \sin z_1\sin z_2 \end{cases}$ <br> $\begin{cases}\sin(-z)=-\sin z \\ \cos(-z)=\cos z\end{cases}$
|Inverse Trigonometric Function|$\text{Arccos }z=-\mathrm{i}\text{Ln }(z+\sqrt{z^2-1})$<br>$\text{Arcsin }z=-\mathrm{i}\text{Ln }(\mathrm{i}z+\sqrt{1-z^2})$
|Hyperbolic Function<br>$(T=2π\mathrm{i})$|$\sh z = \frac{1}{2}(e^z-e^{-z})=−\mathrm{i}\sin \mathrm{i}z$<br>$\ch z = \frac{1}{2}(e^z+e^{-z})=\cos \mathrm{i}z$|$(\sh z)'= \ch z$<br>$(\ch z)'=\sh z$|$\sh(-z)=-\sh z$<br>$\ch(-z)=\ch z$
|Inverse Hyperbolic Function|$\text{Arsh }z=\text{Ln }(z+\sqrt{z^2+1})$<br>$\text{Arch }z=\text{Ln }(z+\sqrt{z^2-1})$


# 复变函数的积分(Integral)
## 积分的概念
- **复变函数积分定义**：设C 为一条起点在a ，终点在b 的有向光滑曲线(或逐段光滑曲线)，其方程为 $w=f(z)$。
![积分](https://img-blog.csdnimg.cn/20190819102612156.png)
(1) 将曲线 C任意分为n个小弧段，分点为 $a=z_0,z_1,\cdots,z_{k-1},z_k,\cdots,z_n=b$，令 $Δz_k=z_k-z_{k-1},λ=\max|Δz_k|$
(2) 在每个小弧段 $\overgroup{z_{k-1}z_k}$上任取一点 $ζ_k$，作和 $S_n=\displaystyle\sum_{k=1}^{n}f(ζ_k)Δz_k$
若极限 $\lim\limits_{λ\to0}S_n$ 存在，且不依赖于C的划分和$ζ_k$的取法，则称此极限为 $f(z)$ 沿曲线 C从a到b的积分，记作$$\displaystyle\int_{C}f(z)dz=\lim\limits_{λ\to0}\sum_{k=1}^{n}f(ζ_k)Δz_k$$
注：C负方向的积分记作 $\displaystyle\int_{C^-}f(z)dz$，若C为闭曲线，积分记作$\displaystyle\oint_{C}f(z)dz$（C的正向为逆时针方向）

- **积分的计算**：
(1) 设 $f(z)=u(x,y)+\text{i }v(x,y)$，可求得 $$\displaystyle\int_{C}f(z)dz=\int_{C}udx-vdy+i\int_{C}vdx+udy$$上述公式可看做 $f(z)=u+iv$与$dz=dx+idy$形式相乘的结果
(2) 还可化为普通的定积分，设曲线C的参数方程为 $z(t)=x(t)+iy(t)\quad(α⩽t⩽β)$，带入可得
$\displaystyle\int_{C}f(z)dz=\int_{α}^{β}f[z(t)]z'(t)dt$

- **复积分的基本性质**：设$f(z),g(z)$在简单曲线上连续
(1) $\displaystyle\int_{C}kf(z)dz=k\int_{C}f(z)dz\quad(k为复常数)$
(2) $\displaystyle\int_{C}[f(z)± g(z)]dz=\int_{C}f(z)dz± \int_{C}g(z)dz$
(3) $\displaystyle\int_{C}f(z)dz=-\int_{C^-}f(z)dz$
(4) 设 C由光滑曲线 $C_1,C_2$ 分段连接而成
$\displaystyle\int_{C}f(z)dz=\int_{C_1}f(z)dz+\int_{C_2}f(z)dz$
(5) $\displaystyle|\int_{C}f(z)dz|⩽\int_{C}|f(z)|ds$
特别的，若在C 上有 $|f(z)|⩽M$，C的长为L，则 $\displaystyle|\int_{C}f(z)dz|⩽ML$
该不等式称为积分估值不等式，提供了一种估计复变函数积分的模的方法

- **复积分实例**：
(1) 设C为连接 a,b 两点的简单曲线，则有
设曲线C的参数方程为 $z(t)=x(t)+iy(t)\quad(α⩽t⩽β)$
$\displaystyle\int_{C}dz=\int_{α}^{β}z'(t)dt=z(t)|_{α}^{β}=b-a$
$\displaystyle\int_{C}zdz=\int_{C}xdx-ydy+i\int_{C}ydx+xdy=\frac{1}{2}(b^2-a^2)$
特别，若为简单闭曲线，则上述积分等于零。
此例揭示了一个很好的性质，函数$f(z)=1,f(z)=z$在曲线C的积分只依赖于C起点与终点，而与C 的形状无关
(2) 设曲线C是以a为圆心，r为半径的正向圆周
 $\displaystyle\oint_{C}\dfrac{1}{(z-a)^n}dz=\begin{cases}
2π i,&n=1 \\
0, &n\neq 1,n\in\Z
\end{cases}$
设C 的参数方程为 $z=a+re^{iθ}\quad(0⩽θ⩽2π)$则
$\displaystyle\oint_{C}\dfrac{1}{(z-a)^n}dz=\int_{0}^{2π}\dfrac{ire^{iθ}}{r^ne^{inθ}}dθ=\dfrac{i}{r^{n-1}}\int_{0}^{2π}e^{-i(n-1)θ}dθ$


## 柯西积分定理(Cauchy Integral Theorem)

通过上节的例子可以发现，有的函数的积分只依赖于积分路径的起点与终点，而与积分路径的形状无关，而有的函数，其积分不仅与积分路径的起点与终点有关，而且与积分路径的形状也有关。深入观察后，可知，前一类函数是解析函数。
- <kbd>柯西积分定理</kbd> 或称 <kbd>柯西－古萨定理</kbd>(Cauchy-Goursat Theorem)
如果函数$f(z)$在单连通区域D内解析，则$f(z)$在D内沿任一简单闭曲线$Γ$积分 $$\displaystyle\oint_{Γ}f(z)dz=0$$ ![柯西积分定理](https://img-blog.csdnimg.cn/20190819105848216.png)
证：$\begin{aligned}
\displaystyle\oint_{Γ}f(z)dz&=\oint_{Γ}udx-vdy+i\oint_{Γ}vdx+udy \\
&\xlongequal[\text{formula}]{\text{Green}} -\iint_G(\dfrac{∂v}{∂x}+\dfrac{∂u}{∂y})+i\iint_G(\dfrac{∂u}{∂x}-\dfrac{∂v}{∂y}) \\
&\xlongequal{\text{C-R}} 0
\end{aligned}$
<kbd>扩展</kbd>如果C是单连通区域D的边界，$f(z)$在D内解析，在 $\bar D=D\cup C$上连续，定理依旧成立。

- <kbd>复合闭路定理</kbd>——多连通区域上的柯西定理
设有$n+1$条简单闭曲线$C_0,C_1,\cdots,C_n$，其中$C_1,\cdots,C_n$均在$C_0$的内区域内，而且它们既不包含也不想交。 $C_0$内部与$C_1,\cdots,C_n$外部围成多连通区域D， 称D的边界 $C=C_0+C_1^-+\cdots+C_n^-$为==复合闭路==(Compound closed path)。在外边界$C_0$，C的正向为逆时针方向，在内边界上，C的正向为顺时针方向。
 D与其边界构成闭区域$\bar D$，设 $f(z)$在$\bar D$上解析，则 $\displaystyle\oint_{C}f(z)dz=0$ 或 $\displaystyle\oint_{C_0}f(z)dz=\sum_{k=1}^{n}\oint_{C_k}f(z)dz$
 ![复合闭路定理](https://img-blog.csdnimg.cn/20190717152423789.png)
证明：以上图为例，在$C_0$内做简单光滑弧 $\overset{\frown}{ab} ,\overset{\frown}{cd} ,\overset{\frown}{ef}$ 连接$C_0,C_1,C_2$，将D分成两个简单单连通区域 $D_1,D_2$，边界分别记作 $L_1,L_2$，由于$f(z)$在$\bar D$上解析，根据柯西积分定理有 $\displaystyle\oint_{L_1}f(z)dz=0,\oint_{L_2}f(z)dz=0$
将两式相加 $\displaystyle\oint_{L_1}f(z)dz+\oint_{L_2}f(z)dz=0$，由于在连接弧上的积分方向相反，刚好相互抵消，即$\displaystyle\oint_{C_0+C_1^-+C_2^-}f(z)dz=\oint_{C}f(z)dz=0$
($\star$) 从定理的证明过程中，可知，在区域内的一个解析函数沿闭曲线的积分，不因闭曲线在区域内做连续变形而改变它的值，只要在变形过程中曲线不经过函数的奇点就行。这一个重要的事实，称为==闭路变形原理==。

- **挖奇点法**：设C为包含a的简单闭曲线，则
 $\displaystyle\oint_{C}\dfrac{1}{(z-a)^n}dz=\begin{cases}
2π i,&n=1 \\
0, &n\neq 1,n\in\Z
\end{cases}$
C内只包含奇点a，做以a为圆心，r为半径的正向圆周 $Γ$，由复合闭路定理知$\displaystyle\oint_{C}\dfrac{1}{(z-a)^n}dz=\oint_{Γ}\dfrac{1}{(z-a)^n}dz$，根据上节的实例证明可得上式。

- **原函数**(Primitive Function)
<kbd>柯西积分定理 - 推论</kbd>若 $z_0,z_1$单连通区域D内任意两点，$C_1,C_2\sub D$为连接$z_0,z_1$ 的任意两条曲线，则 $\displaystyle\int_{C_1}f(z)dz=\int_{C_2}f(z)dz$
可知，解析函数积分与路径无关，仅由起点和终点来确定，即
$\displaystyle\int_{C}f(ξ)dξ=\int_{z_0}^{z_1}f(ξ)dξ$，这里 $z_0,z_1$分别称为积分的上限和下限。
当下限$z_0$固定，让上限$z_1=z$在D内变动，则积分$\displaystyle\int_{z_0}^{ξ}f(ξ)dz$在D内确定了一个单值函数 $F(z)=\displaystyle\int_{z_0}^{z}f(ξ)dξ$，对这个函数我们有
<kbd>定理 1</kbd>：设$f(z)$在单连通区域D内解析， 则函数 $F(z)$ 在区域内一定是解析函数，且 $F'(z)=f(z)$
![原函数](https://img-blog.csdnimg.cn/20190717174642575.png)
证明：设z为D内任意一点，在D内以$δ$为半径，z为圆心作圆，在圆内取点 $z+h$，则有
$F(z+h)-F(z)=\displaystyle\int_{z_0}^{z+h}f(ξ)dξ-\int_{z_0}^{z}f(ξ)dξ=\int_{z}^{z+h}f(ξ)dξ$
上式取$z$到$z+h$的直线段积分，则有
$\displaystyle\dfrac{F(z+h)-F(z)}{h}-f(z)=\dfrac{1}{h}\int_{z}^{z+h}[f(ξ)-f(z)]dξ$
因为$f(z)$在D内解析，所以$f(z)$在D得连续
$∀ϵ>0,\exists δ>0$，使得$|ξ-z|<δ$在圆内恒成立，即当$|h|<δ$时，总有$|f(ξ)-f(z)|<ϵ$。根据积分估值不等式，有
$\begin{aligned}
\displaystyle|\dfrac{F(z+h)-F(z)}{h}-f(z)|&=\dfrac{1}{|h|}\left|\int_{z}^{z+h}[f(ξ)-f(z)]dξ\right| \\
&⩽\dfrac{1}{|h|}\int_{z}^{z+h}|f(ξ)-f(z)|ds \\
&<\dfrac{1}{|h|}\cdotϵ\cdot|h|=ϵ
\end{aligned}$
这说明$\lim\limits_{h\to0}\dfrac{F(z+h)-F(z)}{h}=f(z)$，即$F'(z)=f(z)$
<kbd>原函数</kbd>：在单连通区域D内称满足条件 $F'(z)=f(z)$的称$F(z)$为区域D内$f(z)$的一个==原函数==(Primitive Function)。称 $f(z)$的原函数的全体为 $f(z)$ 的不定积分，记为$\displaystyle\int f(z)dz$。
若$Φ(z),F(z)$同为$f(z)$在区域D的原函数，则$[Φ(z)-F(z)]'=f(z)-f(z)=0$，于是$Φ(z)-F(z)\equiv C$，其中C为任意常数。因此，解析函数存在无穷多个原函数，且任意两个原函数之间只相差一个常数。不定积分为 $\displaystyle\int f(z)dz=Φ(z)+C$
<kbd>定理 2</kbd>：设$f(z)$在单连通区域D内解析，  $F(z)$ 为$f(z)$的一个原函数，对于D内任意两点 $z_0,z_1$ 牛顿-莱布尼茨公式依旧成立，即$$\displaystyle\int_{z_0}^{z_1}f(z)dz=F(z_1)-F(z_0)$$

- **多连通区域上解析函数的原函数**：设$f(z)$在多连通区域D内解析，定义$F(z)=\displaystyle\int_{z_0}^{z}f(ξ)dξ$ ，此函数可能为多值函数。
在D内取一单连通区域 $Δ$， 定点 $z_0,z_1\in Δ$，$C_1$为D内从$z_0$到$z_1$的一条固定的简单曲线，定义 $F_0(z)=\displaystyle\int_{C_1}f(ξ)dξ+\int_{\overset{\frown}{z_1z}}f(ξ)dξ$
则$F_0(z)$为$F(z)$在$Δ$内的一个解析分支
![原函数](https://img-blog.csdnimg.cn/20190717180922855.png)

## 柯西积分公式(Cauchy Integral Formula)
- **引述**：设$f(z)$在单连通区域D内解析，则函数$\dfrac{f(z)}{z-z_0}$在$z_0$处不解析。C为D内围绕$z_0$的闭曲线，所以积分$\displaystyle\oint_C \dfrac{f(z)}{z-z_0}dz$一般不为零。
以$z_0$为中心，$ρ>0$为半径的正向圆周为积分曲线$C_ρ$，根据复合闭路定理，$\displaystyle \oint_C \dfrac{f(z)}{z-z_0}dz= \oint_{C_ρ} \dfrac{f(z)}{z-z_0}dz$
由于$f(z)$的连续性，$f(z)\to f(z_0)\quad(ρ\to 0)$，因而可以猜想，积分
$\displaystyle  \oint_{C} \dfrac{f(z)}{z-z_0}dz\to  f(z_0)\oint_{C_ρ} \dfrac{1}{z-z_0}dz=2πi f(z_0) \quad(ρ\to 0)$
当然，证明过程是复杂的，我们得到如下定理。


- <kbd>柯西积分公式</kbd>：设区域D是以C为边界的单连通区域，函数$f(z)$在区域D内解析，在 $\bar D$连续，$z_0$是D内的任意一点则：$$\displaystyle f(z_0)=\dfrac {1}{2π \text{i}}\oint_C \dfrac{f(z)}{z-z_0}dz$$ 柯西积分公式对于有$n+1$条简单闭曲线组成的复合闭路 $C=C_0+C_1^-+\cdots+C_n^-$围成的多连通区域D 仍然有效。
通过这个公式可以把函数$f(z)$在解析域内任意点的值用他在边界上的积分来表示，这是解析函数的又一特征。
![柯西积分公式](https://img-blog.csdnimg.cn/20190718151554412.png)
<kbd>推论 1 (平均值公式)</kbd>：设 $f(z)$ 在圆盘 $|z-z_0|<ρ$ 上解析，在 $|z-z_0|⩽ ρ$ 上连续，则 $\displaystyle f(z_0)=\dfrac {1}{2π}\int_{0}^{2\pi} f(z_0+ρe^{iθ})dθ$
<kbd>推论 2</kbd>：设区域D由同心圆周$K_1,K_2(K_2$包含于$K_1)$ 所围成的圆环，多连通区域D的边界$Γ=K_1+K_2^-$，函数$f(z)$ 在圆环D内解析，在$\bar D$连续，$z_0$为D内任意一点，则$\displaystyle f(z_0)=\dfrac {1}{2π i}\oint_Γ \dfrac{f(z)}{z-z_0}dz$

- **柯西积分公式的应用**
<kbd>高阶导数公式</kbd>：解析函数的导数仍然为解析函数，它的n阶导数为
$$\displaystyle f^{(n)}(z_0)=\frac {n!}{2\pi i}\oint_C \frac{f(z)}{(z-z_0)^{n+1}}dz \quad(n\in\Z^+)$$其中C为函数$f(z)$的解析域内围绕$z_0$的任意一条简单闭曲线。
可用数学归纳法证明上式。此性质常称为解析函数的==无穷可微性==。
<kbd>柯西不等式</kbd>：设 $f(z)$ 在圆周 $C:|z-z_0|=ρ_0(ρ_0>0)$ 所围成的区域内解析，在 $|z-z_0|⩽ ρ_0$ 上连续，$\displaystyle M(ρ)=\max_{|z-z_0|=ρ}|f(z)|\quad (0<ρ⩽ρ_0)$，则 $\dfrac {f^{(n)}(z_0)}{n!}⩽\dfrac{M(ρ)}{ρ^n}\quad(n\in\Z^+)$
<kbd>最大模原理</kbd>：设 $f(z)$ 在闭区域$\bar D$上解析，则 $|f(z)|$只能在边界 $∂D$上取得极大值。
<kbd>刘维尔(Liouville)定理</kbd>：设函数$f(z)$在整个复平面上的解析且有界，则$f(z)$为一常数。
证明：设存在常数$M>0$ 使得$|f(z)|⩽M$，对于任意$z_0\in\Complex$及任意的$ρ>0$， 有 
$|f'(z_0)|⩽\dfrac{M(ρ)}{ρ}⩽\dfrac{M}{ρ}\to 0\quad(ρ\to+\infty)$
因此 $\forall z_0\in\Complex,f'(z_0)=0$，所以$f(z)$在复平面上为常数。


## 调和函数(Harmonic Function)
<kbd>定义</kbd>：设二元实函数 $φ(x, y)$在定义域D内有二阶连续偏导数，且满足二维拉普拉斯(Laplace)方程$$Δφ=\dfrac{∂^2φ}{∂x^2}+\dfrac{∂^2φ}{∂y^2}=0$$ 则称$φ(x, y)$为D内的==调和函数==(harmonic function)。也记为 $Δφ=φ_{xx}+φ_{yy}=0$

<kbd>定理 1</kbd>：设 $f (z)=u(x,y)+iv(x,y)$在区域D内解析，则实部$u(x,y)$与虚部$u(x,y)$ 均为D内的调和函数。
证明：由于解析函数有任意阶导数， 所以$u,v$在区域D内有任意阶连续偏导数.。由C-R条件 $u_x=v_y,u_y=-v_x$ 有 $u_{xx}=v_{yx},u_{yy}=-v_{xy}$，由此得 $Δu=u_{xx}+u_{yy}=0$，同理可得$Δv=0$

<kbd>定义</kbd>：若区域D内的调和函数$u(x,y),v(x,y)$满足C-R条件 $u_x=v_y,u_y=-v_x$，则称$u(x,y),v(x,y)$为区域D的==共轭调和函数==(conjugate harmonic function)。

**应用**：构造解析函数 $f (z) = u + iv$
(1) 由于共轭调和函数的关系，已知其中一个函数，根据C-R条件便可确定另一个，这种方法称为==偏积分法==。
设已知 $u(x,y)$，则有 $dv=v_xdx+v_ydy=-u_ydx+u_xdy$，由此有
$\displaystyle v(x,y)=\int_{(x_0,y_0)}^{(x,y)}-u_ydx+u_xdy+C=\int_{x_0}^{x}-u_ydx+\int_{y_0}^{y}u_xdy+C$
其中 $(x_0,y_0)$为定点，C为常数。
(2) 设已知 $u(x,y)$，由于要求 $f (z) = u + iv$为解析函数，所以有
$f'(z)=u_x+iv_x=u_x-iu_y$，于是求$f'(z)$的原函数即可。这种方法称为==原函数法==。







