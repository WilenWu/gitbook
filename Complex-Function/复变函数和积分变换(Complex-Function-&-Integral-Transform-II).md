---
title: 复变函数和积分变换(Complex Function & Integral Transform II)
tags: [R]
mathjax: false
copyright: true
date: 2019-08-16 15:53:44
categories: [R,Complex Function & Integral Transform II]
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
# 级数(Series)
## 复变函数项级数(Complex Function Series)
- **复数项级数**(complex number series)：设$\{z_n\}=z_1,z_2,\cdots,z_n,\cdots$ 为一复数序列。
(1) 称表达式$\displaystyle\sum_{n=1}^{∞}z_n=z_1+z_2+\cdots+z_n+\cdots$ 为复数项无穷级数。
(2) 称$S_n=z_1+z_2+\cdots+z_n$为级数的部分和
(3) 若极限$\lim\limits_{n\to∞}S_n=S$ 存在( S 为有限数)，则称级数是收敛的， S 称为级数的和；如果序列$\{S_n\}$不收敛，则称级数是发散的。
<kbd>复数项级数收敛的充要条件</kbd>：设 $z_n=x_n+iy_n(n\in\Z^+)$ ，则 $\displaystyle\sum_{n=1}^{∞}z_n$收敛$\iff \displaystyle\sum_{n=1}^{∞}x_n,\sum_{n=1}^{∞}y_n$都收敛
<kbd>复数项级数收敛的必要条件</kbd>：$\lim\limits_{n\to∞}z_n=0\implies\displaystyle\sum_{n=1}^{∞}z_n$ 收敛
<kbd>定理 1</kbd>：如果$\displaystyle\sum_{n=1}^{∞}|z_n|$ 收敛，则$\displaystyle\sum_{n=1}^{∞}z_n$ 收敛，并且 $\displaystyle|\sum_{n=1}^{∞}z_n|⩽\sum_{n=1}^{∞}|z_n|$ 
(1) 如果 $\displaystyle\sum_{n=1}^{∞}|z_n|$ 收敛，则称级数 $\displaystyle\sum_{n=1}^{∞}z_n$==绝对收敛==(absolutely convergent)。
(2) 非绝对收敛的收敛级数称为==条件收敛==(conditionally convergent)。
由于$\displaystyle\sum_{n=1}^{∞}|z_n|$是正项级数，其收敛性可以用正项级数的相关定理来进行判别。另外，还可得到$\displaystyle\sum_{n=1}^{∞}|z_n|$收敛的充要条件是$\displaystyle\sum_{n=1}^{∞}x_n,\sum_{n=1}^{∞}y_n$都绝对收敛

- **复变函数项级数**：设区域D上的函数列$\{f_n(z)\}=f_1(z),f_2(z),\cdots,f_n(z),\cdots$
(1) 称$\displaystyle\sum_{n=1}^{∞}f_n(z)=f_1(z)+f_2(z)+\cdots+f_n(z)+\cdots$为区域D 内的复变函数项==级数==(series)。
(2) 该级数的前n 项和 $S_n(z)$ 称为这个级数的==部分和==((partial sum))。
(3) 如果对于区域D 内的某一点$z_0$ ，极限$\lim\limits_{n\to∞}S_n(z_0)=S(z_0)$存在，则称级数$\displaystyle\sum_{n=1}^{∞}f_n(z)$在$z_0$点==收敛==(convergence)，称$S(z_0)$为它的==和==(sum)。 
(4) 如果级数在 D 内处处收敛，那么它的和一定是与z有关的一个函数 $S(z) = f_1(z)+f_2(z)+\cdots+f_n(z)+\cdots$，这个函数称为级数的==和函数==(summable function)。
关于复数项级数与复变函数项级数，由于这两类级数的有关定义、性质与判别法与高等数学的相应部分极为相似，所以，不再赘述。
(5) ==一致收敛==(uniform convergence)：如果对于任意$ϵ>0$ ，存在$N>0$，对于任何的$z\in D$，当$n>N$时，恒有$|\displaystyle\sum_{k=1}^{n}f_k(z)-f(z)|<ϵ,∀ x\in D$，则称级数$\displaystyle\sum_{n=1}^{∞}f_n(z)$在D上一致收敛于函数$f(z)$
<kbd>定理</kbd> (Weierstrass M-test)：如果级数$\displaystyle\sum_{n=1}^{∞}f_n(z)$在区域$D$满足条件：
(i) $∀ z\in D,|f_n(z)|⩽ M_n(n=1,2,\cdots)$
(ii)正项级数$\displaystyle\sum_{n=1}^{∞}M_n$收敛
则级数$\displaystyle\sum_{n=1}^{∞}f_n(z)$在区间$D$上一致收敛
(6) ==内闭一致收敛==(Closed uniform convergence)：设函数$f_n(z)(n\in\Z^+)$ 定义在区域G 内，若级数$\displaystyle\sum_{n=1}^{∞}f_n(z)$在G 内任意一个有界闭集上均一致收敛，则称该级数在区域G 内内闭一致收敛于$f(z)$。
<kbd>定理</kbd>：如果级数$\displaystyle\sum_{n=1}^{∞}f_n(z)$在区域$D$内解析，级数$\displaystyle\sum_{n=1}^{∞}f_n(z)$在D内内闭一致收敛于$f(z)$，则
(i) $f(z)$在D内解析
(ii) $f^{(p)}(z)=\displaystyle\sum_{n=1}^{∞}f_n^{(p)}(z)\quad(p\in\Z^+)$


## 幂级数(Power Series)
- **幂级数**(Power Series)：称形如$\displaystyle\sum_{n=0}^{∞}a_n(z-z_0)^n=a_0+a_1(z-z_0)+\cdots+a_n(z-z_0)^n+\cdots$的级数称为幂级数，其中$z_0,a_0,a_1,\cdots,a_n,\cdots$为复常数。
特别令$z_0=0$ 有$\displaystyle\sum_{n=0}^{∞}a_nz^n$，只要做变换 $ξ=z-z_0$即可化为一般形式，为了方便常讨论此形式。

- **幂级数的收敛圆**(circle of convergence)
<kbd>阿贝尔(Abel)定理</kbd>：若级数$\displaystyle\sum_{n=0}^{∞}a_nz^n$在点 $a (a≠0)$ 收敛，则它在圆域$K : |z|<|a|$ 内绝对收敛；在闭圆 $K_1 : |z| ⩽ρ (ρ < a )$上一致收敛。
若级数$\displaystyle\sum_{n=0}^{∞}a_nz^n$在点 $b (b≠0)$ 发散，则它在 $|z| > |b|$ 时发散。
有了阿贝尔定理便可弄清幂级数的收敛范围。
首先，幂级数在点z =0 是收敛的。
其次，幂级数在z ≠0 时只有三种可能：
(1) 幂级数在复平面所有的点收敛(如$1+\frac{z}{1!}+\frac{z^2}{2!}+\cdots+\frac{z^n}{n!}+\cdots$)；
(2) 幂级数在复平面所有的点发散(如 $1+ 2z + 2^2 z^2 +\cdots+ 2^n z^n +\cdots$)；
(3) 存在一个圆域 $|z|<R$，幂级数在圆域内收敛(且绝对收敛)，在$|z|>R$上幂级数发散。圆周 $C : |z| = R$称为该级数的==收敛圆==(circle of convergence)，R称为该级数的==收敛半径==(radius of convergence)。
为了统一起见，对于幂级数在复平面收敛，规定 $R = +∞$，对于幂级数仅在一点 z =0 收敛，规定$R = 0$。
<kbd>定理 1</kbd>：设幂级数为 $\displaystyle\sum_{n=0}^{∞}a_nz^n$，幂级数收敛半径的具体求法，同实函数一样，比值法和根值法是最常用的有效方法。
(1) 比值法：若$\lim\limits_{n\to∞}|\dfrac{a_{n+1}}{a_n}|=λ$ 则收敛半径为$R=\dfrac{1}{λ}$
(2) 根值法：$\lim\limits_{n\to∞}\sqrt[n]{|a_n|}=ρ$ 则收敛半径为$R=\dfrac{1}{ρ}$

**实例**：
1. 求幂级数$\displaystyle\sum_{n=0}^{∞}z^n$的收敛半径
解：级数的部分和 $S_n=\dfrac{1-z^n}{1-z}\quad(z\neq 1)$
(1) 当 $|z|<1$时，有$\lim\limits_{n\to∞}z^n=0$，从而$\lim\limits_{n\to∞}S_n=\dfrac{1}{1-z}$，级数收敛
(2) 当 $|z|⩽1$时，级数的一般项 $z^n$不趋近于零，级数发散。
由阿贝尔定理知级数的收敛半径为 $R=1$，并且函数 $\dfrac{1}{1-z}=\displaystyle\sum_{n=0}^{∞}z^n\quad(|z|<1)$
2. 函数 $\dfrac{1}{z-b}$也可通过变换表示成幂级数
$\dfrac{1}{z-b}=\dfrac{1}{(z-a)-(b-a)}=-\cfrac{1}{b-a}\cdot\cfrac{1}{1- \cfrac{z-a}{b-a}}$
当 $|\dfrac{z-a}{b-a}|<1$时，即$|z-a|<|b-a|$，可以得到
$\displaystyle\dfrac{1}{z-b}=-\sum_{n=0}^{∞}\dfrac{1}{(b-a)^{n+1}}(z-a)^n$


- **和函数的解析性**
<kbd>定理 2</kbd>：设幂级数 $\displaystyle\sum_{n=0}^{∞}a_n(z-z_0)^n$的收敛半径为R，则
(1) 它的和函数 $f(z)$ 在收敛圆内解析
(2) 幂级数在收敛圆内可逐项求导任意次，即 $f^{(k)}(z)=\displaystyle\sum_{n=0}^{∞}[a_n(z-z_0)^n]^{(k)}$
(3) 幂级数在收敛圆内任一曲线C 上逐项积分，即
$\displaystyle\int_{C}f(z)dz=\int_{z_0}^zf(z)dz=\sum_{n=0}^{∞}\dfrac{a_n}{n+1}(z-z_0)^{n+1}$

## 泰勒级数(Taylor Series) 
- <kbd>泰勒定理</kbd>：若函数$f(z)$在区域D内解析，圆域 $K:|z-z_0|<R$含于D，则在K内有
$f(z)=\displaystyle\sum_{n=0}^{∞}a_n(z-z_0)^n$，其中 $a_n=\dfrac{1}{n!}f^{(n)}(z_0)\quad (n=0,1,2,\cdots)$
且上述展开式是唯一的，上式被称为==泰勒展开式==(Taylor expansion)，它右端的级数称为泰勒级数。
![泰勒级数](https://img-blog.csdnimg.cn/2019072313032890.png)
证明： 取一点 $z\in K$，做圆周 $C:|z-z_0|=ρ$ 包含点 z
由柯西积分公式有$\displaystyle f(z)=\dfrac{1}{2\pi i}\oint_C \frac{f(ξ)}{ξ-z}dξ$ 
由于 $|\dfrac{z-z_0}{ξ-z_0}|<1$，有上节实例可知$\displaystyle\dfrac{1}{ξ-z}=\sum_{n=0}^{∞}\dfrac{(ξ-z_0)^n}{(z-z_0)^{n+1}}$ ，带入上式可得
$f(z)=\displaystyle\sum_{n=0}^{∞}a_n(z-z_0)^n$，其中 $a_n=\dfrac{1}{n!}f^{(n)}(z_0)$
关于展开式的唯一性，证明略。
<kbd>推论</kbd>：将泰勒定理和上节的定理2结合，可以得到一个重要结论
函数$f(z)$在一点$z_0$处解析的充要条件是：它在$z_0$的某一邻域内有幂级数展开式 $f(z)=\displaystyle\sum_{n=0}^{∞}a_n(z-z_0)^n$
这个性质从级数的角度深刻反映了解析函数的本质。

- **函数在 z=0 处的泰勒展开式**
$\begin{aligned} 
& e^z=\displaystyle\sum_{n=0}^{∞}\dfrac{1}{n!}z^n & (z\in\Complex) \\
& \sin z=\displaystyle\sum_{n=0}^{∞}\dfrac{(-1)^n}{(2n+1)!}z^{2n+1} & (z\in\Complex) \\
& \cos z=\displaystyle\sum_{n=0}^{∞}\dfrac{(-1)^n}{(2n)!}z^{2n} & (z\in\Complex) \\
& \dfrac{1}{1-z}=\displaystyle\sum_{n=0}^{∞}z^n &  (|z|<1) \\
& \dfrac{1}{(1+z)^2}=\displaystyle\sum_{n=0}^{∞}(-1)^{n-1}nz^{n-1}  & (|z|<1)
\end{aligned}$
$\text{Ln }(1+z)$的主值支 $\ln (1+z)=\displaystyle\sum_{n=0}^{∞}\dfrac{(-1)^n}{n+1}z^{n+1}\quad (|z|<1)$
$(1+z)^α$的主值支 $e^{α\ln(1+z)}=1+αz+\binom{α}{2}z^2+\cdots+\binom{α}{n}z^n+\cdots \quad(|z|<1)$
其中 $\binom{α}{n}=\frac{α(α-1)\cdots(α-n+1)}{n!}$



## 洛朗级数(Laurent Series)
- **洛朗级数**(Laurent Series)：称形如$\displaystyle\sum_{n=-∞}^{+∞}a_n(z-z_0)^n=\cdots+a_{-n}(z-z_0)^{-n}+\cdots+a_{-1}(z-z_0)^{-1}+a_0+a_1(z-z_0)+\cdots+a_n(z-z_0)^n+\cdots$的级数称为洛朗级数，其中$z_0,a_n(n\in\Z)$为复常数。
洛朗级数由正幂次项$\displaystyle\sum_{n=0}^{∞}a_n(z-z_0)^n$和负幂次项$\displaystyle\sum_{n=-1}^{-∞}a_n(z-z_0)^n$组成，分别称为洛朗级数的==解析部分==和==主要部分==。若解析部分和主要部分在点$z=ξ$收敛，则洛朗级数在点$z=ξ$收敛。

- **收敛圆环**(ring of convergence)：显然洛朗级数的收敛域是解析部分和主要部分收敛域的交集。
(1) 对于解析部分，设其收敛半径为R，其收敛圆域为$|z-z_0|<R$
(2) 对于主要部分，令$ξ=(z-z_0)^{-1}$，并令$b_n=a_{-n}$，则级数变形为ξ的幂级数$\displaystyle\sum_{n=1}^{∞}b_nξ^n$，设它的收敛半径为$R_1$，其收敛圆域为$|ξ|<R_1$
于是对于洛朗级数主要部分，当$|\frac{1}{z-z_0}|<R_1$即$|z-z_0|>\frac{1}{R_1}$ 时收敛。
(3) 令 $r=\frac{1}{R_1}$，由上面的讨论可知
若 $r<R$，则洛朗级数的收敛域为 $r<|z-z_0|<R$，此圆环称为收敛圆环。且知它在该圆环内绝对收敛，在闭圆环 $r < r'⩽ z − z_0 ⩽R' < R$上一致收敛。

- <kbd>洛朗定理</kbd>：设$f(z)$在圆环域 $D:R_1<|z-z_0|<R_2$ 内解析，则$f(z)$在此圆环内一定能展开为 $f(z)=\displaystyle\sum_{n=-∞}^{+∞}a_n(z-z_0)^n$ ，并且系数$a_n$被$f(z)$及圆环唯一确定。
其中$\displaystyle a_n=\dfrac{1}{2\pi i}\oint_C \dfrac{f(ξ)}{(ξ-z_0)^{n+1}}dξ(n\in\Z)$ ，C为此圆环内围绕$z_0$的任何一条正向简单闭曲线，此公式称为==洛朗展开式==(Laurent expansion)。
![洛朗定理](https://img-blog.csdnimg.cn/20190819124424762.png)


**实例**
1. 求函数$f(z)=\dfrac{1}{(z-1)(z-2)}$分别在下列圆环的洛朗展开式
$(1)\ 0<|z|<1 ;\quad (2)\ 1<|z|<2;\quad (3)\ 2<|z|<+∞$
![洛朗展开](https://img-blog.csdnimg.cn/2019081912533384.png)
解：部分分式分解 $f(z)=\dfrac{1}{1-z}-\dfrac{1}{2-z}$ 
(1) 在 $0<|z|<1$中有$|z|<1,|\frac{z}{2}|<1$，由上一章的实例知
$\displaystyle\frac{1}{1-z}=\sum_{n=0}^{∞}z^n;\quad \frac{1}{2-z}=\sum_{n=0}^{∞}\frac{z^n}{2^{n+1}}$
于是 $\displaystyle f(z)=\sum_{n=0}^{∞}z^n-\sum_{n=0}^{∞}\frac{z^n}{2^{n+1}}=\sum_{n=0}^{∞}(1-\frac{1}{2^{n+1}})z^n$
上述结果中不含 z 的负幂项，原因在于$f(z)$在$z=0$处解析。
(2) 在 $1<|z|<2$中有$|\frac{1}{z}|<1,|\frac{z}{2}|<1$，由上一章的实例知
$\displaystyle\frac{1}{1-z}=-\sum_{n=0}^{∞}\frac{1}{z^{n+1}};\quad \frac{1}{2-z}=\sum_{n=0}^{∞}\frac{z^n}{2^{n+1}}$
于是 $\displaystyle f(z)=-\sum_{n=0}^{∞}\frac{1}{z^{n+1}}-\sum_{n=0}^{∞}\frac{z^n}{2^{n+1}}$
(3) 在 $2<|z|<+∞$ 中有$|\frac{1}{z}|<1,|\frac{2}{z}|<1$，由上一章的实例知
$\displaystyle\frac{1}{1-z}=-\sum_{n=0}^{∞}\frac{1}{z^{n+1}};\quad \frac{1}{2-z}=-\sum_{n=0}^{∞}\frac{2^n}{z^{n+1}}$
于是 $\displaystyle f(z)=\sum_{n=0}^{∞}\frac{2^n-1}{z^{n+1}}$
2. 求函数在 $f(z)=\dfrac{\sin z}{z}$在$0<|z|<∞$的洛朗展开式
$\displaystyle f(z)=\dfrac{\sin z}{z}=\dfrac{1}{z}\sum_{n=0}^{∞}\dfrac{(-1)^n}{(2n+1)!}z^{2n+1}=\sum_{n=0}^{∞}\dfrac{(-1)^n}{(2n+1)!}z^{2n}$
3. 计算 $\displaystyle\oint_C e^{\frac{1}{z}}dz$，其中C 为正向圆周 $|z|=1$
由于 $\displaystyle e^{\frac{1}{z}}=1+\frac{1}{z}+\frac{1}{2!z^2}+\cdots+\frac{1}{n!z^n}+\cdots$
在洛朗展开式的系数中，在$n=-1$时，有$\displaystyle a_{-1}=\dfrac{1}{2\pi i}\oint_C f(z)dz$
于是有$\displaystyle\oint_C e^{\frac{1}{z}}dz=2\pi i$


## 孤立奇点(Isolated Singular Point)

<kbd>孤立奇点</kbd>：设函数 $f (z)$ 在$z_0$不解析，但在$z_0$的某个去心邻域 $0 < |z − z_0| < R$内解析，则称点$z_0$为函数 $f(z)$ 的==孤立奇点==(isolated singular point)。


- **孤立奇点的类型**：设点$z_0$为函数$f(z)$的孤立奇点
(1) 若 $f(z)$ 在点$z_0$的洛朗级数的主要部分为零，则称点$z_0$为 $f(z)$ 的==可去奇点(removable singularity)==；
(2) 若 $f(z)$ 在点$z_0$的洛朗级数的主要部分有限多项，即存在正整数m，$a_{-m}\neq 0$，当$n<-m,a_{n}=0$，则称点$z_0$为 $f(z)$ 的==m级(阶)极点(m-order pole)==；
(3) 若 $f(z)$ 在点$z_0$的洛朗级数的主要部分有无限多项，则称点$z_0$为 $f(z)$ 的==本性奇点(essential singularity)==
依定义，$z=0$是$\frac{\sin z}{z}$的可去奇点，$z=0$是$\frac{\sin z}{z^2}$的一阶极点，$z=0$是$e^\frac{1}{z}$的本性奇点。

- **孤立奇点类型判定**
<kbd>可去奇点判定</kbd>：设点$z_0$为函数$f(z)$的孤立奇点，则下列三个条件是等价的：
(1) 点$z_0$为 $f(z)$的可去奇点；
(2) $\lim\limits_{z\to z_0}f(z)=C_0$，其中$C_0$为一复常数；
(3) 函数 $f(z)$在点$z_0$的某个去心邻域内有界。
<kbd>m 阶极点判定</kbd>：$z_0$为函数 $f(z)$的m阶极点的充要条件是 $f(z)=\frac{1}{(z-z_0)^m}φ(z)$，其中$φ(z)$在$z_0$解析且$φ(z_0)\neq 0$
<kbd>极点判定</kbd>：$z_0$为函数 $f(z)$的极点的充要条件是$\lim\limits_{z\to z_0}f(z)=∞$
<kbd>本性奇点判定</kbd>：$z_0$为函数 $f(z)$的本性奇点的充要条件是$\lim\limits_{z\to z_0}f(z)$不存在，也不趋于∞
<kbd>本性奇点判定 2</kbd>：若点$z_0$为 $f(z)$的本性奇点，且$\lim\limits_{z\to z_0}f(z)\neq 0$，则点$z_0$必为 $\frac{1}{f(z)}$的本性奇点。

- **函数的零点[^2]与极点的关系**
<kbd>定理 1</kbd>：若$z_0$是$f(z)$的m级极点，则$z_0$是$\frac{1}{f(z)}$的m级零点，反之亦然。
<kbd>定理 2</kbd>：设$z_0$分别是函数$φ(z),ψ(z)$的m级零点和n级零点，$f(z)=\frac{φ(z)}{ψ(z)}$，则有
(1) 当 $m>n$ 时，$z_0$是 $f(z)$的 $m-n$级零点；
(2) 当 $m<n$ 时，$z_0$是 $f(z)$的 $n-m$级零点；
(3) 当 $m=n$ 时，$z_0$是 $f(z)$可去奇点。

[^2]: <kbd>零点(zero point)</kbd>：若不恒等于零的解析函数$f(z)$在$z_0$的邻域内可以表示成$f(z)=(z-z_0)^mg(z)$，其中$g(z)$在$z_0$解析且$g(z_0)\neq 0$，则称$z_0$为$f(z)$的==m级(阶)零点==。
由$g(z_0)\neq 0$和$g(z)$的连续性可推得，不恒为零的解析函数的零点是孤立的。
<kbd>零点判定</kbd>：若$f(z)$在$z_0$解析，则$z_0$为函数 $f(z)$的m级零点的充要条件是 $f^{(k)}(z_0)=0(k=0,1,\cdots,m-1);\quad f^{(m)}(z_0)\neq 0$

- **函数在无穷远点的性质**
在扩充复平面上讨论函数的奇点，若无特殊声明，则约定无穷远点 ∞为任意函数的奇点。
<kbd>定义 1</kbd>：设函数$f(z)$在无穷远点的邻域 $r<|z|<+∞$内解析，则无穷远点∞就称为函数$f(z)$的==孤立奇点==。
**函数在无穷远点的洛朗级数**
设$ξ=0$是$h(ξ)$的孤立奇点，则有
$h(ξ)=\displaystyle\sum_{n=-∞}^{+∞}b_nξ^n=\sum_{n=0}^{∞}b_nξ^n+\sum_{n=1}^{∞}b_{-n}ξ^{-n}\quad (0<|ξ|<\frac{1}{r})$
若令 $ξ=\frac{1}{z}$，则有
$f(z)=h(\frac{1}{z})=\displaystyle\sum_{n=0}^{∞}b_nz^{-n}+\sum_{n=1}^{∞}b_{-n}z^n\quad (r<|z|<+∞)$
若再令$a_n=b_{-n}(n\in\Z)$，则有
$f(z)=\displaystyle\sum_{n=0}^{∞}a_{-n}z^{-n}+\sum_{n=1}^{∞}a_nz^n\quad (r<|z|<+∞)$
称此级数为$f(z)$在点$z=∞$的洛朗级数，称其中的级数$\displaystyle\sum_{n=1}^{∞}a_nz^n$为主要部分，级数$\displaystyle\sum_{n=0}^{∞}a_{-n}z^{-n}$为解析部分。
注意：与函数$f(z)$在有限远点的情况相反，函数 $f(z)$在无穷远点的罗朗级数的解析部分是由非正幂项组成，而主要部分是由正幂项组成。
<kbd>定义 2</kbd>：设$h(ξ)=f(\frac{1}{ξ})$，如果 $ξ=0$是$h(ξ)$的可去奇点、m级极点或本性奇点，则称$z=∞$是$f(z)$的可去奇点、m级极点或本性奇点。
**无穷远点孤立奇点的分类**：设点$z =∞$为函数 $f(z)$的孤立奇点，若函数在$z =∞$处的洛朗级数
(1) 不含正幂项，则无穷远点$z =∞$是$f(z)$的可去奇点；
(2) 含有有限个正幂项，且$z^m$为最高正幂，则无穷远点$z =∞$是$f(z)$的m阶奇点；
(3) 含有无穷多正幂项，无穷远点$z =∞$是$f(z)$的本性奇点。


# 留数(Residue)

## 留数的概念与计算
- **引述**：当函数$f(z)$在邻域$|z-z_0|<δ$内解析时，由柯西-古萨特定理知$\displaystyle\oint_{C}f(z)dz=0$，其中C是该邻域内围绕$z_0$的任何一条正向简单闭曲线。
但是，如果$z_0$是一个孤立奇点，则积分一般不等于零。设$f(z)$在$z_0$去心领域$0<|z-z_0|<δ$内的洛朗展开式为$f(z)=\displaystyle\sum_{n=-∞}^{+∞}a_n(z-z_0)^n$，对此项逐项积分，利用前一章实例的结果$\displaystyle\oint_{C}(z-z_0)^ndz=\begin{cases}2π i,&n=-1 \\0, &n\neq -1,n\in\Z\end{cases}$，可以得到$\displaystyle\oint_{C}f(z)dz=2π i a_{-1}$
这表明，$f(z)$的洛朗展开式沿围绕孤立奇点的正向简单闭曲线积分后，只留下$(z-z_0)$的负一次幂,，接下来我们就来研究此系数$a_{-1}$

- **留数**(Residue)
<kbd>留数定义</kbd>：设$z_0$是$f(z)$的孤立奇点，即$f(z)$在去心邻域$0<|z-z_0|<δ$内解析，则$f(z)$在$z_0$的洛朗展开式的负一次幂的系数$a_{-1}$，称为留数，记作$\text{Res}(f,z_0)$，即$$\text{Res}(f,z_0)=\displaystyle\dfrac{1}{2π i}\oint_{C}f(z)dz$$其中C是该去心邻域内围绕$z_0$的任何一条正向简单闭曲线。
<kbd>留数定理</kbd>：设函数$f(z)$在区域D内除有限个孤立奇点$z_1,z_2,\cdots,z_n$外处处解析，C是D内包围所有奇点的一条正向简单闭曲线，则$$\displaystyle\oint_{C}f(z)dz=2π i \sum_{k=1}^{n}\text{Res}(f,z_k)$$
![留数定理](https://img-blog.csdnimg.cn/20190730125652243.png)
证明：如图，由复合闭路定理有$\displaystyle\oint_{C}f(z)dz=\sum_{k=1}^{n}\oint_{Γ_k}f(z)dz=2π i \sum_{k=1}^{n}\text{Res}(f,z_k)$

- **无穷远点的留数**
<kbd>无穷远点的留数</kbd>：$\text{Res}(f,∞)=\displaystyle\dfrac{1}{2π i}\oint_{C^-}f(z)dz=-a_{-1}$
其中C是围绕原点$z=0$的任何一条正向简单闭曲线。
<kbd>无穷远点留数定理</kbd>：$\displaystyle\sum_{k=1}^{n}\text{Res}(f,z_k)+\text{Res}(f,∞)=0$
其中C是围绕原点且包围所有孤立奇点$z_1,z_2,\cdots,z_n$的一条正向简单闭曲线。

**留数的计算**
1. 如果$z_0$是$f(z)$的可去奇点 $\text{Res}(f,z_0)=0$
2. 如果$z_0$是$f(z)$的本性奇点，只能用洛朗展开式法求$a_{-1}$
3. 如果$z_0$是$f(z)$的极点
$\text{Res}(f,z_0)=\begin{cases}
  \lim\limits_{z\to z_0}(z-z_0)f(z) &\text{if 1-order pole} \\
  \displaystyle\dfrac{1}{(m-1)!}\lim_{z\to z_0}\dfrac {\text{d}^{m-1}}{\text{d}z^{m-1}}[(z-z_0)^mf(z)] &\text{if m-order pole}
  \end{cases}$
4. 如果$f(z)=\frac{P(z)}{Q(z)}$，$P(z),Q(z)$均在$z_0$解析，且$P(z_0)\neq 0,Q(z_0)\neq 0,Q'(z_0)\neq 0$，则$z_0$是$f(z)$的一阶极点 $\text{Res}(f,z_0)=\frac{P(z_0)}{Q'(z_0)}$
5. 无穷远点的留数 $\text{Res}(f,∞)=-\text{Res}[f(\frac{1}{z})\cdot\frac{1}{z^2},0]$

**实例**
1. 计算积分 $\displaystyle\oint_{C}\dfrac{ze^z}{z^2-1}dz$，C为正向圆周 $|z|=2$
被积函数有两个一阶极点 $\pm1$，而这两个极点都在圆周C内，所以
$\displaystyle\oint_{C}\dfrac{ze^z}{z^2-1}dz=2π i[\text{Res}(f,1)+\text{Res}(f,-1)]=2π i(\dfrac{e}{2}+\dfrac{e^{-1}}{2})=π i(e+e^{-1})$
2. 计算积分 $\displaystyle\oint_{C}\dfrac{e^z}{z(z-1)^2}dz$，C为正向圆周 $|z|=2$
被积函数有一个一阶极点$z=0$和一个二阶极点$z=1$，所以
 $\displaystyle\oint_{C}\dfrac{e^z}{z(z-1)^2}dz=2π i[\text{Res}(f,0)+\text{Res}(f,1)]=2π i$
3. 求 $f(z)=z^{-1}$在 ∞ 点的留数
 $\text{Res}(z^{-1},∞)=-\text{Res}[f(\frac{1}{ξ})\cdot\frac{1}{ξ^2},0]=-\text{Res}(\frac{1}{ξ},0)=-1$

## 留数在定积分计算中的应用(Application of Residue in Definite Integral)
<kbd>引理 1</kbd>：设函数$f(z)$在闭区域$D=\{z|α⩽\arg z⩽β(0⩽α⩽β⩽π)\}$上连续，$C_R$为圆周 $C : |z| = R$ 在D内的一段弧，若对$C_R$上的任意的点 z 均有 $\lim\limits_{z\to ∞}zf(z)=k$，则 $\displaystyle\lim\limits_{R\to∞}\int_{C_R}f(z)dz=k(β−α)i$
![引理1](https://img-blog.csdnimg.cn/20190730154950228.png)

<kbd>引理 2</kbd>：设函数$f(z)$在闭区域$D=\{z|α⩽\arg (z-z_0)⩽β(0⩽α⩽β⩽π),|z|⩽r_0\}$上连续，$C_r$为圆周 $C : |z-z_0| = r(r<r_0)$ 在D内的一段弧，若对$C_r$的任意的点 z 均有 $\lim\limits_{z\to z_0}(z-z_0)f(z)=k$，则 $\displaystyle\lim\limits_{r\to0}\int_{C_r}f(z)dz=k(β−α)i$
![引理2](https://img-blog.csdnimg.cn/20190730155011817.png)

<kbd>若尔当(Jordan)引理</kbd>：设函数$f(z)$在闭区域$D=\{z|α⩽\arg z⩽β(0⩽α⩽β⩽π),0<R_0⩽|z|<+ ∞\}$上连续，$C_R$为圆周 $C : |z| = R(R>R_0)$ 在D内的一段弧，若对$C_R$上的任意的点 z 均有 $\lim\limits_{z\to ∞}f(z)=0$，则对于任意 $a>0$有 $\displaystyle\lim\limits_{R\to∞}\int_{C_R}f(z)e^{iaz}dz=0$

**积分计算**
1. 形如 $\displaystyle\int_{0}^{2π}R(\cosθ,\sinθ)dθ$ 的积分
这里讨论的被积函数$R(\cosθ,\sinθ)$是有理函数
另 $z=e^{iθ}$，则$dz=ie^{iθ}dθ=izdθ$
$\sinθ=\dfrac{z^2-1}{2iz},\quad \cosθ=\dfrac{z^2+1}{2z}$
所以 $\displaystyle\int_{0}^{2π}R(\cosθ,\sinθ)dθ=\int_{|z|=1}R(\dfrac{z^2+1}{2z},\dfrac{z^2-1}{2iz})\dfrac{1}{iz}dz$
令 $f(z)=R(\dfrac{z^2+1}{2z},\dfrac{z^2-1}{2iz})\dfrac{1}{iz}$，则
$\displaystyle\int_{0}^{2π}R(\cosθ,\sinθ)dθ=\oint_{|z|=1}f(z)dz=2π i \sum_{k=1}^{n}\text{Res}(f,z_k)$
其中$z_0,z_1,\cdots,z_n$为在圆周$|z|=1$内的孤立奇点。

2. 形如 $\displaystyle\int_{-∞}^{+∞}R(x)dx$ 的积分
被积函数$R(x)$为有理函数，其分母的次数至少比分子的次数高二次，且在实轴上连续，设$R(z)=\dfrac{z^n+a_1z^{n-1}+\cdots+a_n}{z^m+b_1z^{m-1}+\cdots+b_m},\quad m-n⩾2$ 为一不可约分式。
![积分](https://img-blog.csdnimg.cn/20190730152938844.png)
由留数定理有 $\displaystyle\int_{-r}^{r}R(z)dz+\int_{C_r}R(z)dz=2π i \sum_{k=1}^{n}\text{Res}[R(z),z_k]$
其中$z_0,z_1,\cdots,z_n$为 $\text{Im }z>0$ 内所有的极点
令 $r\to ∞$，对上式两端取极限
$\displaystyle\int_{-∞}^{+∞}R(z)dz+\lim\limits_{r\to∞}\int_{C_r}R(z)dz=2π i \sum_{k=1}^{n}\text{Res}[R(z),z_k]$
由于$R(z)$分母的次数至少比分子的次数高二次，所以 $\lim\limits_{z\to ∞}zR(z)=0$
由引理 1 知 $\displaystyle\lim\limits_{r\to∞}\int_{C_r}R(z)dz=0$
所以 $\displaystyle\int_{-∞}^{+∞}R(z)dz=2π i \sum_{k=1}^{n}\text{Res}[R(z),z_k]$

3. 形如 $\displaystyle\int_{-∞}^{+∞}R(x)e^{iax}dx(a>0)$ 的积分
用上例的方法，根据若尔当引理可得
$\displaystyle\int_{-∞}^{+∞}R(z)e^{iax}dz=2π i \sum_{k=1}^{n}\text{Res}[R(z)e^{iax},z_k]$

- **实例**
(1) 积分  $\displaystyle\int_{0}^{+∞}\dfrac{\sin x}{x}dx=\dfrac{π}{2}$
(2) 积分 $\displaystyle\int_{0}^{+∞}\dfrac{dx}{(1+x)x^a}=\dfrac{π}{\sin πa}\quad(0<a<1)$


## 对数留数与辐角原理(Logarithmic Residue and Argument Principle)
  
<kbd>定理 1</kbd>：设闭曲线C是区域D的边界线，函数$f(z)$在D内除极点外每一点都解析，并且在C上解析，则$$\displaystyle\dfrac{1}{2π i }\oint_{C}\dfrac{f'(z)}{f(z)}dz=P-N$$这里P和N分别表示在D内零点[^2]及极点的总数， 而且每个k阶零点或极点分别算作k个零点或极点。
上式左端称为函数 $f(z)$关于围线C的==对数留数(Logarithmic Residue)==，实际上 $\dfrac{f'(z)}{f(z)}=\dfrac{\text{d}}{\text{d}z}[\text{Ln }f(z)]$。它提供了一种计算复变函数沿围线积分的方法。

<kbd>辐角原理</kbd>(Argument Principle)：设有闭曲线C及函数$f(z)$，满足定理 1 的条件，则$$\displaystyle P-N=\dfrac{1}{2π}Δ_{C}\arg f(z)$$ 这里$Δ_{C}\arg f(z)$表示z沿C的正向绕行一周时，函数 $f(z)$ 的辐角改变量。

<kbd>儒歇定理</kbd> (Rouché's theorem)：设C是一围线，若函数 $f(z)$与$ϕ(z)$均在C的内部及C上解析，且满足 $|ϕ(z)| < |f(z)| ,　z∈C$， 则 $f(z) +ϕ(z)$与 $f(z)$ 在C的内部的零点个数相同(一个k级零点算作k个零点)。

<kbd>代数基本定理</kbd>：任何复系数一元n次多项式方程 $f(z)=a_0z^n+a_1z^{n-1}+\cdots+a_n(a_0\neq 0)$ 有且只有 n 个零点(n 级零点就算作 n 个零点)。

# 共形映射(Conformal Mapping)


## 解析函数的映射性质

**导数的几何意义**
1. 设C 是一条有向光滑曲线，其方程为 $z=z(t),a⩽t⩽b$，它的正向为随t增大时z的移动方向，设$z_0=z(t_0),z=z(t_0+Δt)=z(t)$ 为曲线C上的点，则割线$\overline{zz_0}$的正向与复数 $\frac{z(t_0+Δt)-z(t_0)}{Δt}$ 表示的向量的方向一致，因此 $z'(t_0)=\lim\limits_{Δt\to 0}\frac{z(t_0+Δt)-z(t_0)}{Δt}$ 所表示的向量就是曲线C 处的切线向量，且与C的方向一致。
因此在处的切线与实轴的夹角可复数表示为 $α=\text{Arg }z'(t_0)$
![割线](https://img-blog.csdnimg.cn/20190801161313594.png)
2. 设$w=f(z)$将曲线C映射成曲线 $Γ:w=w(t)=f[z(t)]$， 则曲线 $Γ$在$w_0=f[z(t_0)]$处的切线与实轴的夹角为 $β=\text{Arg }w'(t_0)=\text{Arg }f'(z_0)z'(t_0)=\text{Arg }f'(z_0)+\text{Arg }z'(t_0)$
通过映射$w=f(z)$，曲线C在$z_0$处的切线逆时针方向旋转$\text{Arg }f'(z_0)$得到曲线$Γ$在$z_0$处的切线。
由此，称$\text{Arg }f'(z_0)$为映射$w=f(z)$在点 $z_0$ 处的==旋转角(angle of rotation)==。易知，旋转角只依赖于点$z_0$，而与曲线C 的形状和方向无关。称旋转角的这种性质为==旋转角不变性==。
![切线](https://img-blog.csdnimg.cn/20190801164048149.png)
3. 由旋转角不变性立即可获得一个重要性质：对于连续函数 $w=f(z),z∈D$， 若$f'(z_0)\neq 0$，则过点 $z_0$ 具有切线的任意两条有向连续曲线 $C,C_1$ 的夹角(二曲线在点$z_0$的切线所夹的角)与象曲线在点 $w_0 = f(z_0)$ 的夹角保持大小相等且方向相同(即由原象曲线 $C,C_1$ 的旋转方向与由象曲线$Γ,Γ_1$ 的旋转方向是一致的)，该性质称为==保角性==(Conformal)。
![保角性](https://img-blog.csdnimg.cn/20190802113716576.png)
4.  由导数定义，有$|f'(z_0)|=\lim\limits_{z\to z_0}\dfrac{|f(z)-f(z_0)|}{|z-z_0|}=r\quad (r\neq 0)$
上式表明，像点之间的距离$|f(z)-f(t_0)|$与原像点之间的距离$|z-z_0|$比值的极限为$|f'(z_0)|$，称这个极限为映射$w= f(z)$在点 $z_0$ 的==伸缩率(shrinkage)==。显然，这伸缩率只依赖于点 $z_0$ ，而与曲线C 的形状及方向无关，这种性质称为==伸缩率不变性==。


- **共形映射**(conformal mapping)
若函数 $w = f(z)$在 $z_0$ 的邻域内有定义，且在$z_0$具有保角性和伸缩率不变性，则称映射$w = f(z)$在 $z_0$ 是共形的，或称 $w = f(z)$在 $z_0$ 是==共形映射==。若映射 $w = f(z)$在区域G 内每一点都是共形的，则称该映射为区域G 内的==共形映射==。
<kbd>单叶函数 (univalent function)</kbd>：设函数$f(z)$在区域D内解析，且对D内任意不同两点$z_1$和$z_2$，均有$f(z_1)\neq f(z_2)$ ，则称$f(z)$为区域D内的单叶解析函数，简称单叶函数。
由单叶函数的性质知，单叶函数在定义域内为共形映射。
<kbd>定理 1</kbd>：设$f(z)$在区域D内单叶解析，则$f'(z)\neq 0,z\in D$
<kbd>保域性定理</kbd>：设函数$f(z)$在区域D内解析，并且不恒等于常数，则D的像$D'=f(D)$是一个区域，即$f(z)$确定从区域D到区域$D'$的一个满射。
<kbd>定理 2</kbd>：若函数$w = f(z)$在 $z_0$ 解析，且 $f'(z_0) ≠ 0$，则映射$w = f(z)$是共形的，而且 $\text{Arg }f'(z_0)$ 表示这个映射在 $z_0$ 的旋转角， $|f'(z_0)|$ 表示这个映射在 $z_0$ 的伸缩率。如果解析函数$w = f(z)$在G 内处处有 $f'(z) ≠ 0$，则映射$w = f(z)$是G 内的共形映射。
<kbd>定理 3</kbd>：若函数$w = f(z)$为区域G 内单叶函数，则反函数 $z = φ(w)$ 为 $G_1=f(G)$ 内单叶函数，并有 $φ'(w_0)=\dfrac{1}{f'(z_0)},z_0\in G,w_0=f(z_0)\in G_1$

## 分式线性映射(Fractional Linear Mapping)
- <kbd>分式线性映射</kbd>：设$a,b,c,d$为满足$ad-bc\neq 0$的复常数，称由分式线性函数$w=\dfrac{az+b}{cz+d}$构成的映射为==分式线性映射==。特别的，当$c=0$时，称为==线性映射==。
(1) 其中条件限制$ad-bc\neq 0$是为了映射的保角性，否则将有$\dfrac{dw}{dz}=\dfrac{ad-bc}{(cz+d)^2}=0$，此时$w≡$ 常数，将会把整个 z平面映射 w平面一个点。
(2) 逆映射 $z=\dfrac{-dw+b}{cw-a}$满足$(-a)(-d)-bc\neq 0$，仍为分式线性映射。
(3) 三个基本映射：一个一般的分式线性映射可以分解为几个简单的映射的复合。
当 $c=0$ 时，有 $w=\cfrac{az+b}{d}=\cfrac{a}{d}(z+\cfrac{b}{a})$
当 $c\neq0$ 时，有 $w=\cfrac{az+b}{cz+d}=(b-\cfrac{ad}{c})\cfrac{1}{cz+d}+\cfrac{a}{c}$
由此可见，分式线性映射可由 $w=z+b,w=αz,w=\frac{1}{z}$ 复合而成。

- **平移映射**(translation)：$w=z+b$
![平移映射](https://img-blog.csdnimg.cn/20190819135412871.png =130x)

- **旋转和相似映射**(rotation and similar)：$w=αz$
设 $α=re^{iθ_0},z=|z|e^{iθ}$，则$w=r|z|e^{i(θ_0+θ)}$ 
从而 $\text{Arg }w=\text{Arg }z+θ,|w|=r|z|$，即 z点先旋转角度 $θ_0$，$|z|$再伸缩 $r$ 倍。
![旋转映射](https://img-blog.csdnimg.cn/20190819135751334.png =150x) ![相似映射](https://img-blog.csdnimg.cn/20190819135823849.png =150x)
- **反演映射**(inverse)：$w=\dfrac{1}{z}$
设 $z=re^{iθ}$，则$w=\dfrac{1}{r}e^{i(-θ)}$ 
![反演映射](https://img-blog.csdnimg.cn/20190819141429316.png =130x)
反演映射通常分解为两个映射完成：
(1) $\xi=\dfrac{1}{\bar z}=\dfrac{1}{r}e^{iθ}$ ，$|\xi||z|=1$，即 $z$ 和 $\xi$关于单位圆周 $|z|=1$对称[^2]
(2) $w=\bar \xi=\dfrac{1}{r}e^{i(-θ)}$，$\xi$ 和 $w$关于实轴对称。

[^2]: <kbd>圆周对称定义</kbd>：设圆周$C$的半径为$R$，$A,B$两点位于从圆心$O$出发的射线上，且$OA\cdot OB=R^2$，则称点 $A$与点$B$是关于该圆周的对称点。
约定圆心的对称点为无穷远点 $∞$
![圆周对称](https://img-blog.csdnimg.cn/20190819142256646.png =180x)


- **分式线性映射的性质**
为便于研究分式线性变换在扩充复平面的性质，约定：
(1) 反演映射 $w=\dfrac{1}{z}$将 $z=0$映射成 $w=∞$， $z=∞$映射成 $w=0$
(2) 函数 $f(z)$在$z=∞$及其邻域内的性质可由函数 $f(\frac{1}{ξ}),ξ=\frac{1}{z}$在$z=0$及其邻域内的性质确定。
(3) 在扩充复平面上将直线视作一个过无穷远点的特殊圆周。
<kbd>**共形性**</kbd>(conformity)：分式线性映射在扩充复平面是单叶的，且是共形的。
(1) 线性映射 $w=az+b(a\neq 0)$是单叶的，且$w'(z)=a\neq 0$，显然在扩充复平面是共形的
(2) 反演映射 $w=\dfrac{1}{z}$是单叶的，且$w'(z)=-\dfrac{1}{z^2}$，根据约定计算，在扩充复平面是共形的
分式线性映射由线性映射和反演映射复合而成，显然是单叶共形的。
<kbd>**保圆性**</kbd> (circular)：分式线性映射将扩充复平面上的圆周映射为圆周。
(1) 线性映射 $w=az+b(a\neq 0)$ 将 z平移，旋转，伸缩，且有相同的旋转角 $\text{Arg }a$和伸缩因子 $|a|$，故将映射成圆。
(2) 反演映射 $w=\dfrac{1}{z}$，设$z=x+iy,w=u+iv$，可得$x=\dfrac{u}{u^2+v^2},y=-\dfrac{v}{u^2+v^2}$
对于z平面任意给定的圆 $A(x^2+y^2)+Bx+Cy+D=0$，其像曲线满足方程 $D(u^2+v^2)+Bu-Cv+A=0$，故仍然为圆。
<kbd>**保对称性**</kbd>(Symmetries)：设点$z_1,z_2$是关于圆周C的对称点， 则在分式线性映射$w=f(z)$下，他们的像点$w_1=f(z_1),w_2=f(z_2)$是关于C的像曲线 $Γ=f(C)$ 对称。
<kbd>定理 1</kbd>：在扩充复平面上的两点 $z_1,z_2$ 是关于圆周C 的对称点的充要条件是通过$z_1,z_2$ 的任何圆周与圆周C 正交。
<kbd>**对应点公式**</kbd>：若分式性性映射将扩充复平面( z 平面)上3个互异的点 $z_1,z_2,z_3$ 依次映射为扩充复平面(w平面)上的三点 $w_1,w_2,w_3$，则此分式线性映射就唯一确定，且可写成$\dfrac{w-w_1}{w-w_2}:\dfrac{w_3-w_1}{w_3-w_2}=\dfrac{z-z_1}{z-z_2}:\dfrac{z_3-z_1}{z_3-z_2}$
称 $\dfrac{z-z_1}{z-z_2}:\dfrac{z_3-z_1}{z_3-z_2}$ 为$z_1,z_2,z,z_3$的==交比==(cross ratio)，或称非调和比，记为 $(z_1,z_2,z,z_3)$
由上式可知，分式线性函数保持交比不变。



## 部分初等函数的映射性质

- **指数函数的映射**：$w=e^z=e^xe^{iy}$ ，以$2π i$为周期，在一个周期内为单叶函数。
指数函数将水平带状区域映射为角形区域。
![指数映射](https://img-blog.csdnimg.cn/20190819150136213.png)

- **对数函数的映射**：$w=\text{Ln }z=\ln z+2kπi$，主值分支 $\ln z=\ln|z|+i\arg z$
对数函数为指数函数反函数，在单值分支内为单叶函数。
取单值分支$f_k(z)=\ln|z|+i\arg z+2kπi$
设 z平面内角形区域 $z=re^{iθ} (0<θ<θ_0⩽2π)$，则 $f_k(z)=\ln|r|+i(θ+2kπ)$
即将 z平面角形区域映射成 w平面平行于实轴的带形区域.

- **幂函数的映射**：$w=z^n(n\in \Z^+)$
设$z=re^{iθ}$，则 $w=r^{n}e^{inθ}$ ，即 $|w|=r^n,\arg w=nθ$
即 z平面角形区域 $\arg z\in[0,θ_0]$ 映射为 w平面角形区域 $\arg w \in [0,nθ_0]$
![幂函数映射](https://img-blog.csdnimg.cn/20190819144123837.png)


## 共形映射的基本问题示例
共形映射的基本问题是：对任意给定的两个单连通区域G 与G′ ，是否存在一个单叶函数能将G 保形映射成G′ = f(G)？若存在，是否唯一。
<kbd>黎曼(Riemann)定理</kbd>：若G 为扩充复平面上的一个单连通区域，其边界点不止一点，则必存在单叶函数$w = f(z)$ 将G映射为单位圆D；若G内某一点满足条件$f(z_0)=0$且$f'(z_0)>0$，则映射 $w = f(z)$ 是唯一的。

<kbd>边界对应定理</kbd>(boundary correspondence)：设 C为单连通区域G的边界，若函数$w=f(z)$ 在闭区域$\bar G=G∪C$上解析，且把$C$双射成$C_1$，则函数$w=f(z)$ 在G内部单叶，且把G映射成$C_1$包围的区域$G_1$
边界对应定理，将区域问题变为考查察边界问题。

1. 将上半平面(半径为无穷大的圆) $\text{Im }z > 0$ 映射为单位圆盘 $|w| <1$ 的分式线性映射。
解：设 z上平面一点 $z=z_0(\text{Im }z_0 > 0)$映射到 w平面原点 $w=0$，有保对称性知，$z=\bar z_0$将映射成$w=∞$，故可设线性映射 $w=k\dfrac{z-z_0}{z-\bar z_0},k\in\R$
只须利用该映射将实轴上的点 z = x 映射为单位圆周 $|w| =1$上的点，即当z = x时，有 $|w|=|k\dfrac{x-z_0}{x-\bar z_0}|=|k||\dfrac{x-z_0}{x-\bar z_0}|=|k|=1$，即$k=e^{iθ},θ\in\R$
所求的映射为 $w=e^{iθ}\dfrac{z-z_0}{z-\bar z_0}\quad(θ\in\R,\text{Im }z_0 > 0)$
![线性映射1](https://img-blog.csdnimg.cn/20190805122657775.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNTE4Mjc3,size_16,color_FFFFFF,t_70)

2.  求把圆盘 $|z|<1$ 映射成 $|w|<1$ 的分式线性映射。
解：设 z上平面一点 $z=z_0(|z_0| < 1)$映射到 w平面原点 $w=0$，有保对称性知，$z=z_0$关于圆周 $|z|=1$ 的对称点$\frac{1}{\bar z_0}$ 将映射成$w=∞$，故可设线性映射 $w=k\cfrac{z-z_0}{z-\frac{1}{\bar z_0}}=k'\cfrac{z-z_0}{1-\bar z_0z},k'=k\bar z_0$
只须利用该映射将 $|z|=1$ 映射为 $|w| =1$上的点，即当z = 1时，有 $|w|=|k'\dfrac{1-z_0}{1-\bar z_0}|=|k'|=1$，即$k'=e^{iθ},θ\in\R$
所求的映射为 $w=e^{iθ}\dfrac{z-z_0}{1-\bar z_0z}\quad(θ\in\R,|z_0| < 1)$
![线性映射2](https://img-blog.csdnimg.cn/20190805122730470.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNTE4Mjc3,size_16,color_FFFFFF,t_70)

3. 将角形区域 $G:0<\arg z<π/6$映射为单位圆盘$|w|<1$的映射
$z_1=z^6$可将角形区域映射成半平面$G_1:\text{Im }z_1>0$
又根据上述例 1，取$z_0=i,θ=0$，通过$w=\dfrac{z_1-i}{z_1+i}$将 $G_1$映射成单位圆盘
复合可得 $w=\dfrac{z^6-i}{z^6+i}$
![映射3](https://img-blog.csdnimg.cn/20190805132510402.png)

4. 将半圆$G:|z|<1,\text{Im }z > 0$ 映射成上平面 $G':\text{Im }w > 0$的映射
$w=(\dfrac{z+1}{z-1})^2$
![半圆映射](https://img-blog.csdnimg.cn/20190805134128708.png)

5. 将上半平面(半径为无穷大的圆) $G:\text{Im }z > 0$ 映射为一般圆盘 $G':|w-w_0| <R$ 
首先 $G$ 经$z_1=e^{iθ}\dfrac{z-z_0}{z-\bar z_0}$映射为$G_1:|z_1|<1$
齐次 $G_1$经 $w=Rz_1+w_0$映射为$G':|w-w_0| <R$ 
复合可得$z_1=Re^{iθ}\dfrac{z-z_0}{z-\bar z_0}+w_0\quad(θ\in\R,\text{Im }z_0 > 0)$
![半平面映射](https://img-blog.csdnimg.cn/20190805134200303.png)

6. ==茹科夫斯基(Zhukovskii)映射==：$w=\frac{1}{2}(z+\frac{1}{z})$
(1) 将圆周 $|z| = r>1$映射为椭圆周
令$z=re^{iθ},w=u+iv$，则$\begin{cases}
u=\frac{1}{2}(r+\frac{1}{r})\cosθ \\
v=\frac{1}{2}(r-\frac{1}{r})\sinθ
\end{cases}$
像的坐标满足方程 $\frac{u^2}{a^2}+\frac{v^2}{b^2}=1$，其中$a=\frac{1}{2}(r+\frac{1}{r}),b=\frac{1}{2}(r-\frac{1}{r})$
即焦点为$(-1,0),(1,0)$的椭圆
(2) 把扩充 z平面的单位圆外部$|z|>1$映射成扩充 w平面去掉割线$[-1,1]$的平面
可将单位圆外部视为无穷个圆周$|z|=r>1$的集合，只须确
定这无穷个圆周的象即。
基于(1) 的讨论，知道这无穷个圆周的象是无穷个椭圆周，并且 $\lim\limits_{r\to 1}\frac{1}{2}(r+\frac{1}{r})=1,\lim\limits_{r\to 1}\frac{1}{2}(r-\frac{1}{r})=0$，即椭圆周的长半轴趋向1，而短半轴趋向0，因而相应的椭圆周便退化为w 平面上的线段$[-1,1]$
又$\lim\limits_{r\to +∞}\frac{1}{2}(r+\frac{1}{r})=+∞,\lim\limits_{r\to +∞}\frac{1}{2}(r-\frac{1}{r})=+∞$，故能扫过除$[-1,1]$外的整个 w平面。
![茹科夫斯基变换](https://img-blog.csdnimg.cn/20190805143823190.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNTE4Mjc3,size_16,color_FFFFFF,t_70)



