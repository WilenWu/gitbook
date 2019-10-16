---
title: 微积分(Calculus III)
tags: [R]
mathjax: false
copyright: true
date: 2019-05-15 17:17:52
categories: [R,Calculus III]
sticky: false
---

------

[微积分(Calculus I)](https://blog.csdn.net/qq_41518277/article/details/89397964)
[微积分(Calculus II)](https://blog.csdn.net/qq_41518277/article/details/89761069)
[微积分(Calculus III)](https://blog.csdn.net/qq_41518277/article/details/90029881)

------

<!-- more -->
# 无穷级数(Infinite Series)
## 常数项级数的概念和性质
**定义**
(1) 数列$\{a_n\}=a_1,a_2,\cdots,a_n,\cdots$ 构成的表达式$\displaystyle\sum_{n=1}^{∞}a_n=a_1+a_2+\cdots+a_n+\cdots$ 叫做（常数项）无穷级数，简称（常数项）级数。其中第n项$a_n$叫做级数的==通项==(general term)。
(2) 级数的前n项==部分和==(partial sum) $S_n=a_1+a_2+\cdots+a_n$
(3) 对于级数$\{a_n\}$，若其部分和数列$\{S_n\}$有极限S，即$\lim\limits_{n\to∞}S_n=S$，则称级数==收敛==(convergence)，S 称为该级数的和，记为$\displaystyle\sum_{n=1}^{∞}a_n=S$，若部分和数列$\{S_n\}$没有极限，则称级数==发散==(divergence)。
(4) 当级数$\{a_n\}$收敛，其部分和$\{S_n\}$是级数和S的近似值，他们的差值 $r_n=S_n-S$叫做级数的==余项==(remainder)。

**收敛级数基本性质**
<kbd>性质 1</kbd>（级数收敛的必要条件）若级数$\displaystyle\sum_{n=1}^{∞}a_n$收敛，则有$\lim\limits_{n\to∞}a_n=0$
<kbd>性质 2</kbd> 设级数$\displaystyle\sum_{n=1}^{∞}a_n$和$\displaystyle\sum_{n=1}^{∞}b_n$分别收敛于$A和B$，则级数$\displaystyle\sum_{n=1}^{∞}(a_n± b_n)$也收敛，且其和为$A± B$
<kbd>性质 3</kbd> 若级数$\displaystyle\sum_{n=1}^{∞}a_n$收敛于$S$，则$\displaystyle\sum_{n=1}^{∞}ka_n$收敛于$kS$
<kbd>性质 4</kbd> 增加或减少级数中的有限项不改变原级数的收敛性，即级数的收敛性与前有限项无关
<kbd>性质 5</kbd> 设级数$\displaystyle\sum_{n=1}^{∞}a_n$收敛，则在不改变级数项前后位置的条件下，任意结合级数的有限项得到新级数$\displaystyle\sum_{n=1}^{∞}a'_n$，则新级数也收敛，且和不变．
<kbd>性质 6</kbd>又称柯西审敛原理 (Cauchy's convergence test)
 $级数\displaystyle\sum_{n=1}^{∞}a_n收敛\iff ∀ ϵ>0,∃ N\in\N^+,当n>N时,对于∀ p\in\N^+,都有|a_{n+1}+a_{n+1}+\cdots+a_{n+p}|<ϵ$


## 常数项级数的审敛法
**正项级数**(series of positive terms)：若$a_n>0$，则称级数$\displaystyle\sum_{n=1}^{∞}a_n$为正项级数。
**正项级数的审敛法**：设$\displaystyle\sum_{n=1}^{∞}a_n和\displaystyle\sum_{n=1}^{∞}b_n$为正项级数
<kbd>定理 1</kbd> $\displaystyle\sum_{n=1}^{∞}a_n收敛\iff 部分和数列\{S_n\}有界$
<kbd>定理 2</kbd> （比较判别法的不等式形式）若$a_n⩽ b_n (n=1,2,\cdots)$则
(1) 当级数$\displaystyle\sum_{n=1}^{∞}b_n$收敛时，级数$\displaystyle\sum_{n=1}^{∞}a_n$也收敛
(2) 当级数$\displaystyle\sum_{n=1}^{∞}a_n$发散时，级数$\displaystyle\sum_{n=1}^{∞}b_n$也发散
<kbd>定理 3</kbd> （比较判别法的极限形式）若$\lim\limits_{n\to∞}\dfrac{a_n}{b_n}=l(0⩽ l ⩽+∞)$，则
(1) 当$0<l<+∞$时，级数$\displaystyle\sum_{n=1}^{∞}a_n$和$\displaystyle\sum_{n=1}^{∞}b_n$有相同的敛散性
(2) 当$l=0$时，如果级数$\displaystyle\sum_{n=1}^{∞}b_n$收敛，那么$\displaystyle\sum_{n=1}^{∞}a_n$收敛
(3) 当$l=+∞$时，如果级数$\displaystyle\sum_{n=1}^{∞}b_n$发散，那么$\displaystyle\sum_{n=1}^{∞}a_n$发散.
<kbd>定理 4</kbd> （比值判别法，达朗贝尔判别法）若$\lim\limits_{n\to∞}\dfrac{a_{n+1}}{a_n}=q$，则
(1) 当$0⩽ q<1$时，级数$\displaystyle\sum_{n=1}^{∞}a_n$收敛
(2) 当$q>1$时，级数$\displaystyle\sum_{n=1}^{∞}a_n$发散
<kbd>定理 5</kbd> （根值判别法，柯西判别法）若$\lim\limits_{n\to∞}\sqrt[n]{a_n}=q$，则
(1) 当$0⩽ q<1$时，级数$\displaystyle\sum_{n=1}^{∞}a_n$收敛
(2) 当$q>1$时，级数$\displaystyle\sum_{n=1}^{∞}a_n$发散
<kbd>定理 6</kbd> 若正项级数$\displaystyle\sum_{n=1}^{∞}|a_n|$收敛，则级数$\displaystyle\sum_{n=1}^{∞}a_n$收敛，且$|\displaystyle\sum_{n=1}^{∞}a_n|⩽ \displaystyle\sum_{n=1}^{∞}|a_n|$

**交错级数**(alternating series)：正负项交错出现的级数
**交错级数的审敛法**
<kbd>定理 7</kbd> （莱布尼兹判别法）对于交错级数$\displaystyle\sum_{n=1}^{∞}(-1)^{n-1}a_n$，若满足
(1) $a_n⩾ a_{n+1}(n=1,2,\cdots)$
(2) $\lim\limits_{n\to∞}a_n=0$
则级数收敛，且其和$S⩽ a_1$，余项的绝对值$r_n⩽ a_{n+1}$

**绝对收敛和条件收敛**：若级数$\displaystyle\sum_{n=1}^{∞}|a_n|$收敛，则称级数$\displaystyle\sum_{n=1}^{∞}a_n$为绝对收敛(absolutely convergent)．若级数$\displaystyle\sum_{n=1}^{∞}a_n$收敛，而级数$\displaystyle\sum_{n=1}^{∞}|a_n|$发散，则称级数为条件收敛(conditionally convergent)．
<kbd>定理 8</kbd> 绝对收敛的级数一定收敛，反之则不然
<kbd>定理 9</kbd> 绝对收敛的级数经改变项的位置后构成的新级数也收敛，且与原级数有相同的和（即绝对收敛的级数具有可交换性）
<kbd>定理 10</kbd>（绝对收敛级数的乘积）设$\displaystyle\sum_{n=1}^{∞}a_n$与$\displaystyle\sum_{n=1}^{∞}b_n$为绝对收敛的级数，他们的和分别为$A和B$，则它们的柯西乘积$\displaystyle\sum_{n=1}^{∞}(a_nb_1+a_{n-1}b_2+\cdots+a_1b_n)$仍为绝对收敛，且其和为$A\cdot B$

## 函数项级数收敛与一致收敛
**函数项级数**(series of functions)
(1) 定义在区间D上的函数列$\{u_n(x)\}=u_1(x),u_2(x),\cdots,u_n(x),\cdots$构成的表达式$\displaystyle\sum_{n=1}^{∞}u_n(x)=u_1(x)+u_2(x)+\cdots+u_n(x)+\cdots$ 叫做（函数项）无穷级数，简称（函数项）级数。
(2) 对每一个确定的值$x_0\in D$ ,函数项级数$\displaystyle\sum_{n=1}^{∞}u_n(x)$成为常数项级数$\displaystyle\sum_{n=1}^{∞}u_n(x_0)$，若常数项级数收敛,则称点$x_0$为函数项级数的收敛点,收敛点的全体称为==收敛域==；若常数项级数发散，则称级数点$x_0$为函数项级数的发散点，发散点的全体称为==发散域==。
(3) 若$Ω$为函数项级数$\displaystyle\sum_{n=1}^{∞}u_n(x)$的收敛域，则对每个$x\inΩ$，存在惟一的$S(x)=\displaystyle\sum_{n=1}^{∞}u_n(x)$，$S(x)$称为函数项级数的==和函数==
(4) 函数项级数前项部分和记作$S_n(x), r_n(x)=S(x)-S_n(x)$为余项，则在收敛域上有$\lim\limits_{n\to∞}S_n(x)=S(x)或\lim\limits_{n\to∞}r_n(x)=0$

**一致收敛**(uniform convergence)
<kbd>定义1</kbd>设函数序列$\{u_n(x)\}$在收敛域D上逐点收敛于$u(x)$，如果对于任意$ϵ>0$ ，存在只依赖于$ϵ$ 的正整数N，使得当$n>N$时，恒有$|u_n(x)-u(x)|<ϵ,∀ x\in D$，则称函数序列$\{u_n(x)\}$在D上一致收敛于函数$u(x)$
<kbd>定义2</kbd>设函数项级数$\displaystyle\sum_{n=1}^{∞}u_n(x)在I$上的和函数为$S(x)$ ，若其部分和函数序列$\{S_n(x)\}在I$上一致收敛于$S(x)$，则称函数项级数$\displaystyle\sum_{n=1}^{∞}u_n(x)在I$ 上一致收敛于和函数$S(x)$.
![一致收敛](https://img-blog.csdnimg.cn/2019051517363731.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNTE4Mjc3,size_16,color_FFFFFF,t_70 =250x)
<kbd>定理</kbd>（魏尔斯特拉斯判别法）：如果函数项级数$\displaystyle\sum_{n=1}^{∞}u_n(x)在区间I$满足条件：
(1) $∀ x\in I,|u_n(x)|⩽ M_n(n=1,2,\cdots)$
(2)正项级数$\displaystyle\sum_{n=1}^{∞}M_n$收敛
则函数项级数$\displaystyle\sum_{n=1}^{∞}u_n(x)在区间I$上一致收敛

## 函数项级数的基本性质
设函数项级数$\displaystyle\sum_{n=1}^{∞}u_n(x)在I$ 上一致收敛于和函数$S(x)$
<kbd>定理 1</kbd> (连续) $\lim\limits_{x\to x_o}S(x)=S(x_0)\iff \lim\limits_{x\to x_o}\displaystyle\sum_{n=1}^{∞}u_n(x)=\displaystyle\sum_{n=1}^{∞}u_n(x_0)$
<kbd>定理 2</kbd> (积分)$\displaystyle\int_{x_0}^{x} S(x)dx=\displaystyle\sum_{n=1}^{∞}\int_{x_0}^{x}u_n(x)dx\iff \displaystyle\int_{x_0}^{x}\sum_{n=1}^{∞}u_n(x)dx=\displaystyle\sum_{n=1}^{∞}\int_{x_0}^{x}u_n(x)dx$
<kbd>定理 3</kbd> (导数)  $S'(x)=\displaystyle\sum_{n=1}^{∞}u'_n(x)$

## 幂级数的收敛域与和函数
**定义**：形如$\displaystyle\sum_{n=0}^{∞}a_n(x-x_0)^n=a_0+a_1(x-x_0)+\cdots+a_n(x-x_0)^n+\cdots$的级数称为幂级数(power series)，常数$a_0,a_1,\cdots,a_n,\cdots$称为幂级数的系数，特别令$x_0=0$有$\displaystyle\sum_{n=0}^{∞}a_nx^n$
<kbd>定理 1</kbd>（Abel 定理）
(1)若幂级数$\displaystyle\sum_{n=0}^{∞}a_nx^n$在点$x=x_0(x_0\neq0)$处收敛，则它对于满足不等式$|x|<|x_0|$ 的一切$x$ 都绝对收敛；
(2)若幂级数$\displaystyle\sum_{n=0}^{∞}a_nx^n$在点$x=x_0$处发散，则它对于满足不等式$|x|>|x_0|$ 的一切$x$ 都发散

**收敛半径**(radius of convergence)
<kbd>定理 2</kbd>如果幂级数$\displaystyle\sum_{n=0}^{∞}a_nx^n$既有不等于零的收敛点，又有发散点，则必存在唯一的正数$R\in\R^+$ ，使得当$|x|<R$ 时，该幂级数绝对收敛；当$|x|>R$ 时，该幂级数发散；当$|x|=R$ 时，该幂级数可能收敛也可能发散。
$R$通常叫做==收敛半径==；开区间$(-R,R)$ 叫做==收敛区间==，再加上收敛端点就构成收敛域了
两种特殊情形：
(1)幂级数只在$x=0$ 处收敛时,收敛半径$R=0$
(2)幂级数在整个数轴上收敛时，规定收敛半径$R=+∞$

**收敛半径的计算**
<kbd>定理 3</kbd> 对于幂级数$\displaystyle\sum_{n=0}^{∞}a_nx^n$，若$\lim\limits_{n\to∞}|\dfrac{a_{n+1}}{a_n}|=ρ或\lim\limits_{n\to∞}\sqrt[n]{|a_n|}=ρ$，其中$ρ⩾0$，则该幂级数的收敛半径为$R=\dfrac{1}{ρ}$
一般幂级数的收敛半径：对于一般幂级数$\displaystyle\sum_{n=0}^{∞}a_n(x-x_0)^n$，除收敛域为$\{x_0\}$或$(-∞,+∞)$两种情形，一定存在正数$R$的收敛半径。
![收敛半径](https://img-blog.csdnimg.cn/20190516091508122.png =500x)


**幂级数的四则运算**
设幂级数$\displaystyle\sum_{n=0}^{∞}a_nx^n$及$\displaystyle\sum_{n=0}^{∞}b_nx^n$的收敛半径分别为$R_1,R_2$，令$R=\min\{R_1,R_2\}$，则它们的和、差、乘积在公共收敛区间$(-R,R)$内都绝对收敛，且有
$\displaystyle\sum_{n=0}^{∞}a_nx^n± \displaystyle\sum_{n=0}^{∞}b_nx^n=\displaystyle\sum_{n=0}^{∞}(a_n± b_n)x^n,(-R<x<R)\\
(\displaystyle\sum_{n=0}^{∞}a_nx^n)(\displaystyle\sum_{n=0}^{∞}b_nx^n)=\displaystyle\sum_{n=0}^{∞}c_nx^n,(-R<x<R)$
其中$c_n=a_0b_n+a_1b_{n-1}+\cdots+a_{n-1}b_1+a_nb_0$

**幂级数和函数的基本性质**
<kbd>性质 1 </kbd> (幂级数和函数的连续性) 幂级数$\displaystyle\sum_{n=0}^{∞}a_nx^n$的和函数$S(x)$在其收敛域上连续
<kbd>性质 2 </kbd> (幂级数可逐项积分)幂级数$\displaystyle\sum_{n=0}^{∞}a_nx^n$的和函数$S(x)$在其收敛域$I$上可积，并有逐项积分公式
$\displaystyle\int_0^xS(x)dx=\displaystyle\int_0^x\sum_{n=0}^{∞}a_nx^ndx=\displaystyle\sum_{n=0}^{∞}\int_0^xa_nx^ndx=\displaystyle\sum_{n=0}^{∞}\frac{a_n}{n+1}x^{n+1}$
逐项积分后的得到的幂级数和原级数有相同的收敛半径
<kbd>性质 3 </kbd> 幂级数$\displaystyle\sum_{n=0}^{∞}a_nx^n$的和函数$S(x)$在其收敛区间$(-R,R)$上可导，并有逐项求导公式
$S'(x)=(\displaystyle\sum_{n=0}^{∞}a_nx^n)'=\displaystyle\sum_{n=0}^{∞}(a_nx^n)'=\displaystyle\sum_{n=1}^{∞}na_nx^{n-1}$
逐项求导后的得到的幂级数和原级数有相同的收敛半径
<kbd>推论 </kbd> 幂级数$\displaystyle\sum_{n=0}^{∞}a_nx^n$的和函数$S(x)$在其收敛区间$(-R,R)$上具有任意阶导数


## 函数的幂级数展开
$$\boxed{幂级数\displaystyle\sum_{n=0}^{∞}a_nx^n或\displaystyle\sum_{n=0}^{∞}a_n(x-x_0)^n}\xrightleftharpoons[expand]{sum}\boxed{和函数S(x)}$$
**泰勒级数**
(1) 假设函数$f(x)$在点$x_0$的某邻域内$U(x_0)$能展开成幂级数，即有
$f(x)=\displaystyle\sum_{n=0}^{∞}a_n(x-x_0)^n=a_0+a_1(x-x_0)+\cdots+a_n(x-x_0)^n+\cdots,x\in U(x_0)$
(2) 由幂级数和函数的性质可知，$f(x)$在$U(x_0)$内有任意阶导，且$f^{(n)}(x_0)=n!a_n$，于是$a_n=\dfrac{1}{n!}f^{(n)}(x_0),(n=0,1,2,\cdots)$
(3) 这就表明，若函数$f(x)$在$U(x_0)$有幂级数，则展开式为$$f(x)=\displaystyle\sum_{n=0}^{∞}\dfrac{1}{n!}f^{(n)}(x_0)(x-x_0)^n,x\in U(x_0)$$此幂级数叫做==泰勒级数==(Taylor series)，当$x_0=0$时，为==麦克劳林级数==(Maclaurin  series)。
<kbd>定理 </kbd> 函数$f(x)$在点$x_0$的某邻域$U(x_0)$内具有任意阶导数，则
$f(x)$在该邻域内能展开成泰勒级数的充要条件是$\lim\limits_{n\to ∞}R_n(x)=0,x\in U(x_0)$
其中$R_n(x)$为$f(x)$在$x=x_0$处的n阶泰勒公式的余项
推导：由于n阶泰勒多项式$p_n(x)=\displaystyle\sum_{k=0}^{n}\dfrac{1}{k!}f^{(k)}(x_0)(x-x_0)^k$就是泰勒级数的前n+1项部分和，余项$R_n(x)=f(x)-p_n(x)$,根据级数收敛的定义，有
$\displaystyle\sum_{n=0}^{∞}\dfrac{1}{n!}f^{(n)}(x_0)(x-x_0)^n=f(x) \\
\iff \lim\limits_{n\to ∞}p_n(x)=f(x)\\
\iff \lim\limits_{n\to ∞}[f(x)-p_n(x)]=f(x)\\
\iff \lim\limits_{n\to ∞}R_n(x)=0$
下面着重讨论$x=x_0$的情形，即麦克劳林展开
**用==公式法==将函数展为麦克劳林级数的步骤**
(1)检验函数$f(x)$在$x=0$处是否任意次可导，并求出$f^{(n)}(x),n=0,1,2,\cdots$；
(2)求出$f^{(n)}(0),n=0,1,2,\cdots$；
(3) 写出幂级数$\displaystyle\sum_{n=0}^{∞}\dfrac{1}{n!}f^{(n)}(0)x^n$，并求出收敛半径$R$
(4)利用余项的表达式$R_n(x)=\dfrac{1}{(n+1)!}f^{(n+1)}(θ x)x^{n+1} (0<θ<1)$，如果$\lim\limits_{n\to ∞}R_n(x)=0,x\in(-R,R)$，即可写出麦克劳林展开式
**==间接法==将函数展为麦克劳林级数**：通过幂级数的运算（如四则运算、逐项求导、逐项积分）以及变量代换等
$e^x=\displaystyle\sum_{n=0}^{∞}\dfrac{1}{n!}x^n,x\in(-∞,+∞)$
$\sin x=\displaystyle\sum_{n=0}^{∞}\dfrac{(-1)^n}{(2n+1)!}x^{2n+1},x\in(-∞,+∞)$
$\cos x=\displaystyle\sum_{n=0}^{∞}\dfrac{(-1)^n}{(2n)!}x^{2n},x\in(-∞,+∞)$
$\dfrac{1}{1+x}=\displaystyle\sum_{n=0}^{∞}(-x)^n,x\in(-1,1)$
$\ln (1+x)=\displaystyle\sum_{n=0}^{∞}\dfrac{(-1)^n}{n+1}x^{n+1},x\in(-1,1]$
![e](https://img-blog.csdnimg.cn/20190517131533151.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNTE4Mjc3,size_16,color_FFFFFF,t_70 =250x)
## 傅里叶级数(Fourier series)
**三角级数**(trigonometric series)：形如$\dfrac{a_0}{2}+\displaystyle\sum_{n=1}^{∞}(a_n\cos nx+b_n\sin nx),\boxed{T=2π}$ 的级数叫三角级数，其中$a_0,a_n,b_n(n=1,2,\cdots)$是三角级数的系数

**三角函数系**
$1,\cos x,\sin x,\cos2x,\sin2x,\cdots,\cos nx,\sin nx,\cdots$
<kbd>正交性 </kbd>(orthogonal) 对于三角函数系中任何不同的三角函数的乘积在$[-π,π]$上的积分为0，即
$\int_{-π}^{π}\sin nxdx=0,(n=1,2,3,\cdots)$
$\int_{-π}^{π}\cos nxdx=0,(n=1,2,3,\cdots)$
$\int_{-π}^{π}\sin kx\cos nxdx=0,(k,n=1,2,3,\cdots)$
$\int_{-π}^{π}\cos kx\cos nxdx=0,(k,n=1,2,3,\cdots,k\neq n)$
$\int_{-π}^{π}\sin kx\sin nxdx=0,(k,n=1,2,3,\cdots,k\neq n)$

**函数的傅里叶级数展开**
假设周期为$2π$的函数$f(x)$能展开成三角级数，即
$f(x)=\dfrac{a_0}{2}+\displaystyle\sum_{n=1}^{∞}(a_n\cos nx+b_n\sin nx)$
设右边三角级数在$[-π,π]$上可以逐项积分，利用三角级数的正交性可得
$\begin{cases} 
a_n=\dfrac{1}{π}\int_{-π}^{π}f(x)\cos nxdx ,(n=0,1,2,3,\cdots)\\ 
b_n=\dfrac{1}{π}\int_{-π}^{π}f(x)\sin nxdx ,(n=1,2,3,\cdots)
\end{cases}$
这时所确定的$a_0,a_1,b_1,\cdots$为函数$f(x)$的==傅里叶系数==(Fourier coefficient)．所得到的三角级数$\dfrac{a_0}{2}+\displaystyle\sum_{n=1}^{∞}(a_n\cos nx+b_n\sin nx)$称为函数$f(x)$的==傅里叶级数==(Fourier series)

<kbd>定理</kbd>(Dirichlet 收敛定理)设$f(x)$是周期为$2π$的周期函数,并满足狄利克莱(Dirichlet )条件：
(1)在一个周期区间内连续或只有有限个第一类间断点；
(2)在一个周期区间内只有有限个极值点，
则$f(x)$的傅里叶级数收敛，且有
$\dfrac{a_0}{2}+\displaystyle\sum_{n=1}^{∞}(a_n\cos nx+b_n\sin nx)=\begin{cases}
f(x) & x为连续点 \\
\dfrac{f(x^-)+f(x^+)}{2} & x为间断点
\end{cases}$
其中$a_n,b_n$为$f(x)$的傅里叶系数.

**正弦级数和余弦级数**
周期为$2π$的函数$f(x)$
若为奇函数，则傅里叶展开式为只含有正弦项的正弦级数$f(x)=\displaystyle\sum_{n=1}^{∞}a_n\sin nx$
若为偶函数，则傅里叶展开式为只含有余弦项的余弦级数$f(x)=\dfrac{a_0}{2}+\displaystyle\sum_{n=1}^{∞}a_n\cos nx$

**周期延拓** (periodic extension)
若函数$f(x)$只在$[-π,π]$上有定义，并满足收敛条件，我们可在定义区间外补充函数的定义，使其成为周期为$2π$的周期函数$F(x)$，再将$F(x)$展开成傅里叶级数，最后限制$x\in[-π,π]$，此时$f(x)\equiv F(x)$
用同样的方法也可为定义在$[0,π]$或$[-π,0]$的函数==奇（偶）延拓==

**吉布斯现象** (Gibbs phenomenon)
![吉布斯现象](https://img-blog.csdnimg.cn/20190517150917224.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNTE4Mjc3,size_16,color_FFFFFF,t_70 =500x)
在间断点附近部分和函数的图形出现大幅度波动，波动的区间随着项数的增加越来越小，但幅度似乎是一样的！
傅里叶级数在函数间断点处的上述现象称为==吉布斯现象==(Gibbs phenomenon)

## 一般周期函数的傅里叶级数
- **任意周期函数的傅里叶级数展开方法**
设函数 $f(x)$ 周期为 $2l$，令 $x=\frac{l}{π}t$
则函数 $F(t)=f(x)=f(\frac{l}{π}t)$ 周期为2π
求得 $F(t)$ 的傅里叶级数
再将 $t=\frac{π}{l}x$ 带入可得 $f(x)$ 的傅里叶级数
<kbd>定理</kbd> 设周期为$2l$的周期函数$f(x)$满足收敛定理条件，则傅里叶展开式为$f(x)=\dfrac{a_0}{2}+\displaystyle\sum_{n=1}^{∞}(a_n\cos \dfrac{nπ x}{l}+b_n\sin \dfrac{nπ x}{l}),x\in C$
其中
$\begin{cases} 
a_n=\dfrac{1}{l}\int_{-l}^{l}f(x)\cos \dfrac{nπ x}{l}dx ,(n=0,1,2,3,\cdots)\\ 
b_n=\dfrac{1}{l}\int_{-l}^{l}f(x)\sin \dfrac{nπ x}{l}dx ,(n=1,2,3,\cdots) 
\end{cases} \\
C=\{x|f(x)=\frac{1}{2}[f(x^-)+f(x^+)]\}$

- **定义在任何有限区间上的函数的傅里叶级数展开方法**
设 $f(x),x\in[a,b]$ ，令 $x=t+\frac{b+a}{2}$
则 $F(t)=f(x)=f(t+\frac{b+a}{2}),t\in[-\frac{b-a}{2},\frac{b-a}{2}]$
做周期延拓，将 $F(t)$ 在 $[-\frac{b-a}{2},\frac{b-a}{2}]$ 展开成傅里叶级数
将 $t=x-\frac{b+a}{2}$ 带入展开式
最后的到 $f(x)$ 在 $[a,b]$ 上的傅里叶展开

- **傅里叶级数的复数形式**
设周期为$2l$的函数$f(x)$的傅里叶级数为$\dfrac{a_0}{2}+\displaystyle\sum_{n=1}^{∞}(a_n\cos \dfrac{nπ x}{l}+b_n\sin \dfrac{nπ x}{l})$
利用欧拉公式 $\cos t=\frac{1}{2}(e^{it}+e^{-it}),\sin t=\frac{1}{2i}(e^{it}-e^{-it})$
可得傅里叶级数的复数形式
$f(x)=\displaystyle\sum_{n=-∞}^{+∞}c_ne^{i\frac{nπ x}{l}}$
其中 $c_n=\dfrac{1}{2l}\int_{-l}^{l}f(x)e^{-i\frac{nπ x}{l}}dx,(n=0,±1,±2,\cdots)$





