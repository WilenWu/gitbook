---
title: 概率论与数理统计(Probability & Statistics II)
tags: [R]
mathjax: false
copyright: true
date: 2019-06-01 20:57:44
categories: [R,Probability & Statistics II]
sticky: false
---

------

[概率论与数理统计(Probability & Statistics I)](https://blog.csdn.net/qq_41518277/article/details/90261253)
[概率论与数理统计(Probability & Statistics II)](https://blog.csdn.net/qq_41518277/article/details/90733362)

------

<!-- more -->
# 样本与抽样分布(Sample and Sampling Distribution)
## 数理统计(Statistics)
数理统计是以概率论为基础, 关于实验数据的收集、整理、分析与推断的一门科学与艺术。

==总体==(population)：研究对象的全体；
==个体==(individual)：总体中的每一个具体对象称为个体；
==总体的容量==(capacity)：总体中包含的个体数；
==有限总体==(finite population)：容量有限的总体；
==无限总体==(infinite population)：容量无限的总体。通常将容量非常大的有限总体也按无限总体处理。

为了采用数理统计方法进行分析，首先要收集数据，数据收集方法一般有两种。
（1）通过调查、记录收集数据。（2）通过实验收集数据。

实际中人们通常只关注总体的某个（或几个）指标。
- 总体的某个指标$X$, 对于不同的个体来说有不同的取值, 这些取值构成一个分布, 因此$X$可以看成一个随机变量。
- 有时候直接将$X$称为总体. 假设$X$的分布函数为$F(x)$, 也称$X$服从$F(x)$分布$X∼ F(x)$

如何推断总体分布的未知参数（或分布）？
需要从总体中抽取一部分个体, 根据这部分个体的数据，并利用概率论的知识等作出分析推断.被抽取的部分个体叫做总体的一个==样本==(sample)。

**简单随机样本**(simple random sample)：满足以下两个条件的随机样本 $(X_1,X_2,…,X_n)$ 称为容量是$n$的简单随机样本，简称样本。
(1) 代表性：每个$X_i$与$X$同分布；
(2) 独立性：$(X_1,X_2,…,X_n)$是相互独立的随机变量。

获得简单随机样本的抽样称为简单随机抽样。
- 对于有限总体，采用放回抽样.
- 但当总体容量很大的时候，放回抽样有时候很不方便， 因此在实际中当总体容量比较大时，通常将不放回抽样所得到的样本近似当作简单随机样本来处理.
- 对于无限总体， 一般采取不放回抽样.

对样本 $X_1,X_2,…,X_n$ 进行观测后，得到的数值：$x_1,x_2,…,x_n$ 称为==样本观测值==(observed value)
观测前：$X_1,X_2,…,X_n$ 是随机变量
观测后：$x_1,x_2,…,x_n$ 是具体的数据

**样本的联合分布**：设总体 $X∼ F(x)$，则样本 $X_1,X_2,…,X_n$ 的联合分布函数为：$F(x_1,x_2,…,x_n)=P\{X_1⩽ x_1,…,X_n⩽ x_n\}=\displaystyle\prod_{i=1}^{n}F(x_i)$
若总体 $X$ 的密度函数为 $f(x)$，则样本 $X_1,X_2,…,X_n$ 的联合密度函数为：$f(x_1,x_2,…,x_n)=\displaystyle\prod_{i=1}^{n}f(x_i)$
若总体 $X$ 的分布律为 $P\{X=a_k\}=p_k$，则样本 $X_1,X_2,…,X_n$ 的联合分布律为：$P\{X_1=x_1,…,X_n=x_n\}=\displaystyle\prod_{i=1}^{n}P\{X=x_i\}$


## 抽样分布(Sampling distribution)
从样本中提取有用的信息来研究总体的分布及各种特征数——构造统计量.
**统计量**(statistic)：设 $X_1,X_2,…,X_n$ 是来自总体$X∼ F(x)$ 的样本， $g(x_1,x_2,…,x_n)$ 是$n$元实值连续函数，若函数$g(x_1,x_2,…,x_n)$ 不含未知参数， 则称随机变量 $g(X_1,X_2,…,X_n)$ 为统计量。
常用统计量
(1) 样本均值：$\bar X=\dfrac{1}{n}\displaystyle\sum_{i=1}^{n}X_i$
(2) 样本方差：$S^2=\dfrac{1}{n-1}\displaystyle\sum_{i=1}^{n}(X_i-\bar X)^2$
样本标准差：$S=\sqrt{S^2}$
(3) 样本 k 阶原点矩：$A_k=\dfrac{1}{n}\displaystyle\sum_{i=1}^{n}X_i^k$
样本 k 阶中心矩：$B_k=\dfrac{1}{n}\displaystyle\sum_{i=1}^{n}(X_i-\bar X)^k$
(4) 将样本按由小到大的顺序排成 $X_{(1)}⩽ X_{(2)}⩽ …⩽ X_{(n)}$
顺序统计量(order statistic)： $X_{(1)}, X_{(2)}, …, X_{(n)}$
样本极小值(minimum)：$X_{(1)}=\min \{X_{(1)}, X_{(2)}, …, X_{(n)}\}$
样本极大值(maximum)：$X_{(n)}=\max \{X_{(1)}, X_{(2)}, …, X_{(n)}\}$
样本极差(range)：$R_n=X_{(n)}-X_{(1)}$

==样本均值与样本方差的数字特征==：设$X_1,X_2,…,X_n$ 是来总体 $X$ 的样本，且总体的均值与方差存在，记为$E(X)=μ,D(X)=σ^2$，则有
(1) $E(\bar X)=E(\dfrac{1}{n}\displaystyle\sum_{i=1}^{n}X_i)=\dfrac{1}{n}\displaystyle\sum_{i=1}^{n}E(X_i)=μ$
$D(\bar X)=D(\dfrac{1}{n}\displaystyle\sum_{i=1}^{n}X_i)=\dfrac{1}{n^2}\displaystyle\sum_{i=1}^{n}D(X_i)=σ^2/n$
(2) $E(S^2)=σ^2$
(3) 若 $X∼ N(μ,σ^2)$，则 $D(S^2)=\dfrac{2σ^4}{n-1}$

**抽样分布**(sampling distribution)：统计量的分布被称为抽样分布
当总体$X$服从一般分布（如指数分布、均匀分布等），要得出统计量的分布是很困难的。当总体$X$服从正态分布时，统计量 $\bar X,S^2$是可以计算的，本节主要介绍与标准正态总体相关的抽样分布。

==$χ^2$ 分布==(chi-square distribution)：设 $X_1,X_2,…,X_n$ 相互独立，且都服从标准正态分布 $N(0, 1)$ ，则称随机变量 $$χ^2=\displaystyle\sum_{i=1}^{n}X_i^2$$ 服从自由度为 $n$ 的 $χ^2$ 分布，记为 $χ^2∼ χ^2(n)$，自由度指包含的独立变量的个数。
$χ^2$ 分布的概率密度为：$$f_n(x)=\begin{cases}
\dfrac{1}{2Γ(n/2)}(\dfrac{x}{2})^{n/2-1}e^{-x/2},\quad x>0 \\
0,\quad x⩽0
\end{cases}$$ 其中 $Γ(x)=\displaystyle\int_{0}^{+∞}t^{x-1}e^{-t}\mathrm{d}t$
![卡方分布](https://img-blog.csdnimg.cn/20190604114737263.png)
性质：
(1) 设 $Y∼ χ^2(n)$，则 $E(Y)=n,D(Y)=2n$
(2) 分布的可加性：设 $Y_1∼ χ^2(n_1),Y_2∼ χ^2(n_2)$，且$Y_1,Y_2$相互独立，则 $Y_1+Y_2∼ χ^2(n_1+n_2)$
推广：设$Y_1,Y_2,\cdots,Y_m$相互独立，且 $Y_i∼ χ^2(n_i)$，则 $\displaystyle\sum_{i=1}^{m}Y_i∼ χ^2(\sum_{i=1}^{m}n_i)$

==t 分布==(t-distribution)：设 $X∼ N(0,1),Y∼ χ^2(n)$，且 X与 Y 相互独立，则称随机变量$$T=\dfrac{X}{\sqrt{Y/n}}$$服从自由度为 n 的 t 分布，记为 $T∼ t(n)$
$t(n)$分布的概率密度为：$$f_n(x)=\dfrac{Γ(\frac{n+1}{2})}{\sqrt{nπ}Γ(\frac{n}{2})}(1+\dfrac{x^2}{n})^{-\frac{n+1}{2}},\quad x\in\R$$
特别地，$n=1$ 的 t 分布就是柯西分布 $f(x)=\dfrac{1}{π(1+x^2)},x\in\R$
$\lim\limits_{n\to∞}f_n(x)=\dfrac{1}{\sqrt{2π}}e^{-x^2/2},x\in\R$
![t分布](https://img-blog.csdnimg.cn/20190604123728569.png)

==F 分布==(F-distribution)：设 $X∼ χ^2(n_1),Y∼ χ^2(n_2)$，且 X与 Y 相互独立，则称随机变量$$F=\dfrac{X/n_1}{Y/n_2}$$服从自由度为 $(n_1,n_2)$ 的 F 分布，记为 $F∼ F(n_1,n_2)$，其中 $n_1$称为第一自由度, $n_2$称为第二自由度。
$F(n_1,n_2)$分布的概率密度为：$$f(x)=\begin{cases}
\dfrac{(n_1/n_2)^{\frac{n_1}{2}}}{B(\frac{n_1}{2},\frac{n_2}{2})}x^{\frac{n_1}{2}-1}(1+\frac{n_1}{n_2}x)^{-\frac{n_1+n_2}{2}},x>0 \\
0,\quad x⩽ 0
\end{cases}$$其中 $B(a,b)=\displaystyle\int_0^1x^{a-1}(1-x)^{b-1}\mathrm{d}x=\dfrac{Γ(a)Γ(b)}{Γ(a+b)}$
![F分布](https://img-blog.csdnimg.cn/20190604131851601.png)
重要性质：若 $F∼ F(n_1,n_2)$，则$\dfrac{1}{F}∼ F(n_2,n_1)$


**正态总体的抽样分布**
设 $X_1,X_2,…,X_n$ 是来自正态总体 $N(μ,σ^2)$的样本，样本均值$\bar X=\dfrac{1}{n}\displaystyle\sum_{i=1}^{n}X_i$，样本方差$S^2=\dfrac{1}{n-1}\displaystyle\sum_{i=1}^{n}(X_i-\bar X)^2$，则
(1) $\bar X∼ N(μ,σ^2/n)$
(2) $\dfrac{(n-1)S^2}{σ^2}∼χ^2(n-1)$
(3) $\bar X$与 $S^2$相互独立
(4) $\dfrac{\bar X-μ}{S/\sqrt{n}}∼ t(n-1)$

设 $X_1,X_2,…,X_{n_1}$和$Y_1,Y_2,…,Y_{n_2}$ 分别来自正态总体 $N(μ_1,σ_1^2)$和$N(μ_2,σ_2^2)$的样本，均值分别为 $\bar X,\bar Y$，方差分别为$S_1^2,S_2^2$，则
(1) $\dfrac{S_1^2/S_2^2}{σ_1^2/σ_2^2}∼ F(n_1-1,n_2-1)$

(2) $\dfrac{(\bar X-\bar Y)-(μ_1-μ_2)}{\sqrt{\dfrac{σ_1^2}{n_1}+\dfrac{σ_2^2}{n_2}}}∼ N(0,1)$
(3) 当 $σ_1^2=σ_2^2=σ^2$时

 $\dfrac{(\bar X-\bar Y)-(μ_1-μ_2)}{S_w\sqrt{\dfrac{1}{n_1}+\dfrac{1}{n_2}}}∼ t(n_1+n_2-2)$
 其中 $S_w^2=\dfrac{(n_1-1)S_1^2+(n_2-1)S_2^2}{n_1+n_2-2},S_w=\sqrt{S_w^2}$

# 参数估计(Parameter Estimation)
参数通常是刻画总体某些概率特征的数量。例如正态分布 $N(μ,σ^2)$ 中的参数 $μ$ 就是该分布的均值，参数 σ2 是该分布的方差。当该参数未知时，从总体中抽取一个样本，用某种方法对该未知参数进行估计，这就是参数估计。
参数估计的形式：先从该总体中抽样得到样本，然后构造样本函数，求出未知参数的估计值或取值范围，这就是点估计和区间估计。

假设总体 $X ∼ F(x; θ_1, θ_2,…, θ_m)$，其中分布函数 $F$ 的表达式已知，但参数 $θ_1, θ_2,…, θ_m$ 未知，若记 $θ = (θ_1, θ_2,…, θ_m)$，则总体分布可记为 $X∼ F(x; θ)$，参数 $θ$ 的取值范围称为==参数空间==(parameter space)，记为 $Θ$

## 点估计(Point estimation)
$X_1,X_2,…,X_n$  是来自总体  $X ∼ F(x; θ_1, θ_2,…, θ_m)$的一个样本，$θ_1, θ_2,…, θ_m$ 是未知参数，构造 m 个统计量：
$随机变量\begin{cases}
\hat θ_1(X_1,X_2,…,X_n) \\
\hat θ_2(X_1,X_2,…,X_n) \\
\quad\vdots\\
\hat θ_m(X_1,X_2,…,X_n)
\end{cases}$
把样本观测值 $x_1,x_2,…,x_n$ 代入上统计量，就得到 m 个数值：
$数值\begin{cases}
\hat θ_1(x_1,x_2,…,x_n) \\
\hat θ_2(x_1,x_2,…,x_n) \\
\quad\vdots\\
\hat θ_m(x_1,x_2,…,x_n)
\end{cases}$
称 $\hat θ_k(X_1,X_2,…,X_n)$为 $θ_k$的==估计量==(estimate)，$\hat θ_1(x_1,x_2,…,x_n)$为$θ_k$的==估计值==(estimator)。

常用的估计方法：矩估计法，极大似然估计法，最小二乘估计法，贝叶斯方法

**矩估计法**(Moment Estimation)
矩估计思想：以样本矩估计总体矩，以样本矩的函数估计总体矩的函数。
由辛钦大数定律，有 $A_k=\dfrac{1}{n}\displaystyle\sum_{i=1}^{n}X_i^k\xrightarrow{P}μ_k(θ_1, θ_2,…, θ_m)\quad (n\to∞)$
因此当n较大时有 $A_k\approx μ_k(θ_1, θ_2,…, θ_m)$假设总体的前m阶矩存在，令$A_k=μ_k(θ_1, θ_2,…, θ_m),k=1,2,\cdots,m$得方程组，其解 $\hat θ_k(X_1,X_2,…,X_n)$ 称为 $θ_k$的矩估计量。

总体均值和方差的矩估计量表达式不因不同的总体分布而异，设总体$X$的均值 $μ$及方差$σ^2$都存在
$\hat μ=\bar X,\hatσ^2=\dfrac{1}{n}\displaystyle\sum_{i=1}^{n}(X_i-\bar X)^2 \triangleq \tilde S^2$
设总体$X∼ U(a,b)\implies\hat a=\bar X-\sqrt{3}\tilde S,\hat b=\bar X+\sqrt{3}\tilde S$


**极大似然估计法**(Maximum Likelihood Estimate,MLE)
Fisher的极大似然思想：
假设总体 $X$ 是离散型随机变量，其分布律为 $P\{X=x\}=p(x;θ),θ\in Θ$，θ未知，$X_1,X_2,…,X_n$为样本，其观察值为 $x_1,x_2,…,x_n$，则事件 $\{X_1=x_1,X_2=x_2,\cdots,X_n=x_n\}$发生的概率（联合分布律）为$$L(θ)=L(x_1,x_2,…,x_n;θ)=\displaystyle\prod_{i=1}^{n} p(x_i;θ),θ\in Θ$$这一概率随θ的取值而改变，我们自然的认为使概率取得最大值的θ值较为合理，$L(θ)$称为样本的==似然函数==(likelihood function)，方程$$L(\hat θ)=\displaystyle\max_{θ\in Θ} L(θ),\hat θ=\hat θ(x_1,x_2,…,x_n)$$的解 $\hat θ$称为极大似然估计值，统计量 $\hat θ=\hat θ(X_1,X_2,…,X_n)$为θ 的==极大似然估计量==(MLE)
连续型随机变量 $X$的概率密度函数为 $f(x;θ),θ\in Θ$，可取得似然函数为$$L(θ)=L(x_1,x_2,…,x_n;θ)=\displaystyle\prod_{i=1}^{n} f(x_i;θ),θ\in Θ$$

在许多情况下，$p(x;θ),f(x;θ)$关于θ可微，这时 $\hat θ$常可从方程 $\dfrac{\mathrm{d}}{\mathrm{d}θ}L(θ)=0$解得，又因 $L(θ)$和 $\ln L(θ)$在同一处取得极值，因此$\hat θ$也可从方程$$\dfrac{\mathrm{d}}{\mathrm{d}θ}\ln L(θ)=0$$求得，这一方程被称作==对数似然方程==。
极大似然估计法同样适用于分布中含多个参数 $θ_1, θ_2,…, θ_m$的情况，这时似然函数L是这些未知参数的函数，分别令 $\dfrac{∂}{∂θ_i}L=0,i=1,2,\cdots,m$或$$\dfrac{∂}{∂θ_i}\ln L=0,i=1,2,\cdots,m$$解上述由m个方程组成的方程组即可，上式称为==对数似然方程组==。
设总体$X∼ N(μ,σ^2)\implies\hat μ=\bar X,\hatσ^2=\dfrac{1}{n}\displaystyle\sum_{i=1}^{n}(X_i-\bar X)^2 \triangleq \tilde S^2$
设总体$X∼ U(a,b)\implies\hat a=\min\{X_1,X_2,\cdots,X_n\}=X_{(1)},\hat b=\max\{X_1,X_2,\cdots,X_n\}=X_{(n)}$

==极大似然估计的不变性==：设 $\hat θ$是$θ$的极大似然估计，θ 的函数 $u=u(θ)$且有单值反函数 $θ=θ(u)$，则 $u(\hat θ)$是 $u$ 的极大似然估计。

## 估计量的评判标准(Criteria for estimators)
对同一个参数，不同方法得到的估计量可能不同。用什么标准来评价一个估计量的好坏?
(1) ==无偏性==(unbiased)：设$X_1,X_2,…,X_n$为总体 $X∼ F(x;θ) \quad (θ\inΘ)$ 的样本，若参数 $θ$ 的估计量 $\hat θ=\hat θ(X_1,X_2,…,X_n)$满足 $E(\hat θ)=θ$，则$\hat θ$是 $θ$的一个无偏估计量。
若$E(\hat θ)\neq θ$，则 $|E(\hat θ)-θ|$称为估计量 $θ$ 的偏差。
若$\lim\limits_{n\to∞}E(\hat θ)= θ$，则称$\hat θ$是 $θ$的渐近无偏估计量

估计量$\hat θ(X_1,X_2,…,X_n)$是随机变量，而估计值会有波动性，无偏性的统计意义是指在大量重复试验下，保证了没有系统误差。

设$X_1,X_2,…,X_n$是总体 $X$ 的样本，总体的k阶矩为$μ_k$，期望和方差为$μ,σ^2$
$E(A_k)=μ_k$，样本 k阶矩都是总体k阶矩的无偏估计
特别的，$E(\bar X)=μ,E(S^2)=σ^2$
而 $E(\tilde S^2)=\dfrac{n-1}{n}E(S^2)=\dfrac{n-1}{n}σ^2$不是总体方差的无偏估计
$\lim\limits_{n\to∞}E(\tilde S^2)=σ^2$，$\tilde S^2$是方差的渐进无偏估计。

纠偏方法：若$\hat θ$是有偏估计，$E(\hat θ)=aθ+b\quad (a\neq 0,θ\inΘ)$，则$\dfrac{θ-b}{a}$是θ 的无偏估计，上面就是用了此方法。

(2) ==有效性==(effective)：设 $\hat θ_1,\hat θ_2$ 都是 θ 的无偏估计量，若有 $∀ θ\inΘ,D(\hat θ_1) ⩽ D(\hat θ_2)$，且不等号至少对某一 $θ\inΘ$ 成立，则 $\hat θ_1$比 $\hat θ_1$ 有效。

==均方误差准则==：定义$E(\hat θ-θ)^2$是估计量 $\hat θ$的均方误差(mean square error;MSE)，记作$Mse(\hat θ)$，若$\hat θ$是θ 的无偏估计量，则 $Mse(\hat θ)=D(\hat θ)$。
设设 $\hat θ_1,\hat θ_2$ 都是 θ的点估计，若有 $∀ θ\inΘ,Mse(\hat θ_1) ⩽ Mse(\hat θ_2)$，且不等号至少对某一 $θ\inΘ$ 成立，则在均方误差条件下 $\hat θ_1$优于 $\hat θ_1$ 。
在实际应用中,均方误差准则比无偏性准则更重要


(3) ==相合性==(consistence)：设$\hat θ(X_1,X_2,…,X_n)$是参数θ的估计量
若$∀ θ\inΘ,∀ϵ>0,\lim\limits_{n\to∞}P\{|\hat θ-θ|<ϵ\}=1$
即 $\hat θ_n\xrightarrow{P}θ\quad (n\to∞)$，称$\hat θ$为θ的相合估计量。

相合性的相关结论：
(1) 样本 k 阶矩$A_k$是总体 k 阶矩 $μ_k$ 的相合估计量；-----辛钦大数定律证明
(2) $S^2,\tilde S^2$是总体方差的相合估计量。-----切比雪夫不等式证明
(3) 矩估计量一般是相合估计量。

**应用**
(1) 设 $X∼ N(μ,σ^2)\implies Mse(S^2)=D(S^2)=\dfrac{2σ^4}{n-1},Mse(\tilde S^2)=\dfrac{2n-1}{n^2}σ^4$
当 $n>1$时，$Mse(S^2)>Mse(\tilde S^2)$因此在均方误差条件下$\tilde S^2$优于$S^2$

(2) 设$X_1,X_2,…,X_n$是总体指数分布$X∼ Exp(θ)$的样本
θ 的矩估计量$\bar X$和极大似然估计量 $nZ,Z=\min\{X_1,X_2,…,X_n\}$均是无偏估计；
但 $D(\bar X)=θ^2/n,D(nZ)=θ^2$，当 $n>1$时，$D(\bar X)<D(nZ)$，所以$\bar X$比 $nZ$有效；

## 区间估计(Interval estimation)
对于一个未知量，根据具体样本观测值，点估计提供一个明确的数值。还希望根据所给的样本确定一个随机区间， 使其包含参数真值的概率达到指定的要求。

**置信区间**(Confidence Intervals)：设总体 $X∼ F(x;θ),θ\inΘ$，若对
给定的$α(0<α<1)$，由来自 $X$的样本确定的两个统计量 $\hat θ_L=\hat θ_L(X_1,X_2,…,X_n),\hat θ_U=\hat θ_U(X_1,X_2,…,X_n)(\hatθ_L<\hatθ_U)$，对于$∀ θ\inΘ$，满足$$P\{\hatθ_L<θ<\hatθ_U\}⩾ 1-α$$则称随机区间$(\hatθ_L,\hatθ_U)$为θ的置信度为 $1-α$ 的==置信区间==(confidence interval)。$\hatθ_L,\hatθ_U$分别称为置信下限和置信上限， $1-α$称为==置信度==或==置信水平==(confidence level)。
说明：
(1) 参数θ虽然未知，但是确定的值。置信区间$(\hatθ_L,\hatθ_U)$是随机的，依赖于样本，样本不同，算出的区间也不同。对于有些样本观察值，区间覆盖θ，但对于另一些样本观察值，区间则不能覆盖。反复抽样多次(各次样本容量相同)，按伯努利大数定律，在这些区间中，包含真值的比例约为 $1-α$
(2) 相同的置信水平也可以得到不同的区间估计。称置信区间$(\hatθ_L,\hatθ_U)$的平均长度$E(\hatθ_U-\hatθ_L)$为区间的==精确度==(accuracy)（长度最短，精度最高），精确度的一半为==误差限==(error limit)。在给定的样本容量下，置信水平和精确度是相互制约的。
(3) Neyman原则：在置信水平达到$1-α$的置信区间中，选精确度尽可能高的置信区间。

**求解置信区间的一般方法**
(1) 构造样本的一个函数 $G=G(X_1,X_2,…,X_n;θ)$它含有待估参数θ，不含其它未知参数，其分布已知，且分布不依赖于待估参数（常由θ的点估计出发考虑），具有这种性质的函数称为==枢轴量==(pivot)。
(2) 对于给定的置信水平$1-α$，求出两个分位点$a,b$，使得 $P\{a<G<b\}⩾ 1-α$
(3) 由 $a<G<b$得到与之等价的θ不等式 $\hatθ_L<θ<\hatθ_U$，那么$(\hatθ_L,\hatθ_U)$就是置信度为 $1-α$ 的置信区间。
==分位点==(percentile point)：设连续型随机变量 $X$的概率密度函数为 $f(x)$，对给定的 $α (0<α<1)$，称满足条件 $P\{X>x_α\}=\displaystyle\int_{x_α}^{∞}f(x)\mathrm{d}x=α$ 的点 $x_α$为 α 分位点。
标准正态分布 $N(0,1)$的α 分位点记作 $z_α,z_α=-z_{1-α}$
$χ^2(n)$分布的α 分位点记作 $χ_α^2(n)$
$t(n)$分布的α 分位点记作 $t_α(n),t_α(n)=-t_{1-α}(n)$
$F(n_1,n_2)$分布的α 分位点记作 $F_α(n_1,n_2)$

**单侧置信区间**(one-sided confidence interval)
如果$P\{\hatθ_L<θ\}⩾ 1-α$则称随机变量$\hatθ_L$为θ的置信度为 $1-α$ 的==单侧置信下限==(one-side confidence lower limit)。
如果$P\{θ<\hatθ_U\}⩾ 1-α$则称随机变量$\hatθ_U$为θ的置信度为 $1-α$ 的==单侧置信上限==(two-side confidence lower limit)。


**正态总体参数的区间估计示例**
设总体 $X∼ N(μ,σ^2),X_1,X_2,…,X_n$为样本，$\bar X,S^2$分别为样本均值和样本方差，置信区间为 $1-α$
(1) $σ^2$已知时，$\bar X$是 μ 的极大似然估计，取枢轴量 $G=\dfrac{\bar X-μ}{σ/\sqrt{n}}∼ N(0,1)$
设常数 $a,b$满足： $P\{a<G<b\}⩾ 1-α$
等价于$P\{\bar X-\dfrac{σ}{\sqrt{n}}b<μ<\bar X-\dfrac{σ}{\sqrt{n}}a\}⩾ 1-α$
此时区间的长度为 $(b-a)σ/\sqrt{n}$
![置信区间](https://img-blog.csdnimg.cn/20190606130143310.png)
由正态分布的对称性知，$a=-b=-z_{α/2}$时，区间的长度达到最短 $L=z_{α/2}σ/\sqrt{n}$
n固定，置信水平提高，即$1-α$增大，则 $z_{α/2}$增大，所以 $L$ 变大，精确度降低；反之亦然.
所得 μ 双侧置信区间为 $(\bar X-\dfrac{σ}{\sqrt{n}}z_{α/2},\bar X+\dfrac{σ}{\sqrt{n}}z_{α/2})$
单侧置信下限为 $\bar X-\dfrac{σ}{\sqrt{n}}z_{α}$
单侧置信上限为 $\bar X+\dfrac{σ}{\sqrt{n}}z_{α}$
(2) $σ^2$已知时，以$S^2$估计$σ^2$，的枢轴量 $G=\dfrac{\bar X-μ}{S/\sqrt{n}}∼ t(n-1)$
所得 μ 双侧置信区间为$(\bar X-\dfrac{S}{\sqrt{n}}t_{α/2}(n-1),\bar X+\dfrac{S}{\sqrt{n}}t_{α/2}(n-1))$
单侧置信下限为 $\bar X-\dfrac{σ}{\sqrt{n}}t_{α}(n-1)$
单侧置信上限为 $\bar X+\dfrac{σ}{\sqrt{n}}t_{α}(n-1)$
(3) 其他总体均值的区间估计
当n足够大时（一般 n>30），由中心极限定理知，近似 $\dfrac{\bar X-μ}{σ/\sqrt{n}}∼ N(0,1)$

**正态总体的均值、方差的置信区间和单侧置信限（置信水平为 $1-α$）**

==一个正态总体==
待估参数|其他参数|枢轴量G的分布|置信区间|单侧置信上/下限
:---|:---|:---|:---|:---|
$μ$|$σ^2$已知|$\dfrac{\bar X-μ}{σ/\sqrt{n}}∼ N(0,1)$|$(\bar X±\dfrac{σ}{\sqrt{n}}z_{α/2})$|$\bar X±\dfrac{σ}{\sqrt{n}}z_{α/2}$
$μ$|$σ^2$未知|$\dfrac{\bar X-μ}{S/\sqrt{n}}∼ t(n-1)$|$\left(\bar X± \dfrac{S}{\sqrt{n}}t_{α/2}(n-1)\right)$| $\bar X±\dfrac{σ}{\sqrt{n}}t_{α}(n-1)$
$σ^2$|$μ$未知|$\dfrac{(n-1)S^2}{σ^2}∼χ^2(n-1)$|$\left(\dfrac{(n-1)S^2}{χ^2_{α/2}(n-1)},\dfrac{(n-1)S^2}{χ^2_{1-α/2}(n-1)}\right)$|$\dfrac{(n-1)S^2}{χ^2_{α/2}(n-1)}$<br>$\dfrac{(n-1)S^2}{χ^2_{1-α/2}(n-1)}$

==两个正态总体==
待估参数|其他参数|枢轴量G的分布|置信区间|单侧置信上/下限
:---|:---|:---|:---|:---|
$μ_1-μ_2$|$σ^2_1,σ^2_2$ 已知| $\dfrac{(\bar X-\bar Y)-(μ_1-μ_2)}{\sqrt{\dfrac{σ_1^2}{n_1}+\dfrac{σ_2^2}{n_2}}}∼ N(0,1)$|$\left((\bar X-\bar Y)± z_{α/2}\sqrt{\dfrac{σ_1^2}{n_1}+\dfrac{σ_2^2}{n_2}}\right)$|$(\bar X-\bar Y)± z_{α/2}\sqrt{\dfrac{σ_1^2}{n_1}+\dfrac{σ_2^2}{n_2}}$|
$μ_1-μ_2$|$σ^2_1=σ^2_2=σ^2$ 未知| $\dfrac{(\bar X-\bar Y)-(μ_1-μ_2)}{S_w\sqrt{\dfrac{1}{n_1}+\dfrac{1}{n_2}}}∼ t(n_1+n_2-2)$<br> $S_w^2=\dfrac{(n_1-1)S_1^2+(n_2-1)S_2^2}{n_1+n_2-2}$|$\left((\bar X-\bar Y)± t_{α/2}t(n_1+n_2-2)S_w\sqrt{\dfrac{1}{n_1}+\dfrac{1}{n_2}}\right)$|$(\bar X-\bar Y)± t_{α/2}t(n_1+n_2-2)S_w\sqrt{\dfrac{1}{n_1}+\dfrac{1}{n_2}}$
$σ^2_1/σ^2_1$|$μ$未知| $\dfrac{S_1^2/S_2^2}{σ_1^2/σ_2^2}∼ F(n_1-1,n_2-1)$|$\left(\dfrac{S_1^2/S_2^2}{F_{α/2}(n_1-1,n_2-1)},\dfrac{S_1^2/S_2^2}{F_{1-α/2}(n_1-1,n_2-1)}\right)$|$\dfrac{S_1^2/S_2^2}{F_{α}(n_1-1,n_2-1)},\dfrac{S_1^2/S_2^2}{F_{1-α}(n_1-1,n_2-1)}$


# 假设检验(Hypothesis Testing)

## 假设检验的基本思想(The basic idea of hypothesis testing)
假设检验是抽样推断中的一项重要内容。它是根据原资料作出一个总体指标是否等于某一个数值，某一随机变量是否服从某种概率分布的假设，然后利用样本资料采用一定的统计方法计算出有关检验的统计量，依据一定的概率原则，以较小的风险来判断估计数值与总体数值(或者估计分布与实际分布)是否存在显著差异，是否应当接受原假设选择的一种检验方法。

某工厂生产袋装葡萄糖，每袋糖的净重是个随机变量，服从正态分布，机器正常时，每袋糖净重 $μ_0$ ，标准差为 $σ$ 。为了检验机器是否正常，随机抽取 n 袋，称得净重：$x_1,x_2,\cdots,x_n$
由于长期实践表明方差比较稳定，设每袋糖的净重 $X∼ N(μ,σ^2)$，接下来我们将根据样本值来判断 $μ=μ_0$ 或 $μ\neqμ_0$。

(1) 为此我们提出两个完全对立的假设：$H_0: μ=μ_0,\quad H_1: μ\neqμ_0$
观察到样本均值 $\bar X$是 $μ$ 无偏估计，若假设 $H_0$为真，则偏差 $|\bar X-μ_0|$一般不应太大，考虑到 $Z=\dfrac{\bar X-μ_0}{σ/\sqrt{n}}∼ N(0,1)$，基于以上想法，我们选一正数 $k$，使得观察值满足 $\left|\dfrac{\bar X-μ_0}{σ/\sqrt{n}}\right|⩾ k$时，就拒绝原假设 $H_0$，反之接受原假设。
(2) 然而，由于样本的随机性，当实际上 $H_0$为真时，仍有可能拒绝原假设（这种可能性是无法消除的），犯这种错误的概率记为 $P_{μ\in H_0}\{拒绝H_0\}=P\{\rm type\ I\ error\}$。
为了确定常数 $k$，我们希望犯这类错误的最大概率为 $α\in(0,1)$，令$P\{\rm type\ I\ error\}=P\{\left|\dfrac{\bar X-μ_0}{σ/\sqrt{n}}\right|⩾ k\}=α$，由于 $H_0$为真时，$Z=\dfrac{\bar X-μ_0}{σ/\sqrt{n}}∼ N(0,1)$
由正态分布分位点的定义知，$k=z_{α/2}$，当$|z|⩾ z_{α/2}$时，拒绝原假设。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190611121318308.png)



**综述**
上例统计量  $Z=\dfrac{\bar X-μ_0}{σ/\sqrt{n}}$ 称为==检验统计量==(test statistic)，数 $α$ 称为==显著水平==(significance level)，一般$α$很小 $(α=0.01,α=0.05,α=0.1)$。当检验统计量取某个区域 C 中的值，我们拒绝原假设，则称区域 C 为==拒绝域==(rejection region)，他的补集称为接受域，拒绝域的边界点称为==临界点==(critical point)。
前面的检验问题叙述成：在显著性水平 $α$ 下，检验$$H_0: μ=μ_0,\quad H_1: μ\neqμ_0$$$H_0$称为==原假设(零假设 null hypothesis)== ，$H_1$称为==备择假设(对立假设 alternative hypothesis)== 。

原假设与备择假设是不对称的！决定谁是原假设，依赖于立场、惯例、方便性。
(1) 保护原假设。如果错误地拒绝假设A比错误地拒绝假设B带来更严重的后果——A选作原假设。例如：2013年禽流感期间，一旦出现高烧一般先假定为禽流感患者
(2) 原假设为维持现状。为解释某些现象或效果的存在性，原假设常取为“无效果”、“无改进”、“无差异”等，拒绝原假设表示有较强的理由支持备择假设。
(3) 原假设取简单假设。只有一个参数(或分布)的假设称为简单假设。如果只有一个假设是简单假设，将其取为原假设。
==参数假设的形式==：设θ是反映总体指标某方面特征的量， 一般参数θ的假设有三种情形：
$H_0: θ=θ_0,\quad H_1: θ<θ_0$ (左边检验)
$H_0: θ=θ_0,\quad H_1: θ>θ_0$ (右边检验)
$H_0: θ=θ_0,\quad H_1: θ\neq θ_0$ (双边检验)

任一检验规则在应用时，都有可能发生错误的判断——==两类错误==。
为此在确定检验法则时，应尽量避免犯两类错误的概率。而不考虑犯第Ⅱ类错误的检验称为==显著性检验==(significance test)。犯两类错误的概率记为
$P_{μ\in H_0}\{拒绝H_0\}=P\{\rm type\ I\ error\}$
$P_{μ\in H_1}\{接受H_0\}=P\{\rm type\ II\ error\}$
$\quad$|原假设为真|原假设不真
---|---|---
根据样本**拒绝**原假设|**type Ⅰ error**|正确
根据样本**接受**原假设|正确|**type Ⅱ error**
设总体服从 $X∼ N(μ,1)$，则$\bar X∼ N(μ,1/n)$，
$H_0: μ=μ_0,\quad H_1: μ=μ_1>μ_0$，拒绝域$\bar X⩾ C$
![拒绝域](https://img-blog.csdnimg.cn/20190610171640761.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNTE4Mjc3,size_16,color_FFFFFF,t_70)

## 正态总体下的假设检验(Hypothesis testing in a normal population)
**正态总体均值和方差的检验法**（显著性水平为 $α$）

假设检验|原假设$H_0$|检验统计量|备择假设$H_1$|拒绝域
:---|:---|:---|:---|:---
==Z 检验==<br> ($σ^2$已知)|$μ=μ_0 \\ μ⩽ μ_0 \\ μ⩾μ_0$|$Z=\dfrac{\bar X-μ_0}{σ/\sqrt{n}}$|$μ\neq μ_0 \\ μ> μ_0 \\ μ<μ_0$|$\vert z\vert ⩾ z_{α/2} \\  z ⩾ z_{α} \\ z ⩽ -z_{α}$
==t 检验==<br> ($σ^2$未知)|$μ=μ_0 \\ μ⩽ μ_0 \\ μ⩾μ_0$|$t=\dfrac{\bar X-μ_0}{S/\sqrt{n}}$|$μ\neq μ_0 \\ μ> μ_0 \\ μ<μ_0$|$\vert t\vert ⩾ t_{α/2}(n-1) \\  t ⩾ t_{α}(n-1) \\ t ⩽ -t_{α}(n-1)$
==Z 检验==<br> ($σ_1^2,σ_2^2$已知)|$μ_1-μ_2=δ \\ μ_1-μ_2⩽ δ \\ μ_1-μ_2⩾δ$| $Z=\dfrac{(\bar X-\bar Y)-δ}{\sqrt{\dfrac{σ_1^2}{n_1}+\dfrac{σ_2^2}{n_2}}}$|$μ_1-μ_2\neqδ \\ μ_1-μ_2> δ \\ μ_1-μ_2<δ$|$\vert z\vert ⩾ z_{α/2} \\  z ⩾ z_{α} \\ z ⩽ -z_{α}$
==t 检验==<br> ($σ_1^2=σ_2^2=σ^2$未知)|$μ_1-μ_2=δ \\ μ_1-μ_2⩽ δ \\ μ_1-μ_2⩾δ$| $t=\dfrac{(\bar X-\bar Y)-δ}{S_w\sqrt{\dfrac{1}{n_1}+\dfrac{1}{n_2}}}$<br> $S_w^2=\dfrac{(n_1-1)S_1^2+(n_2-1)S_2^2}{n_1+n_2-2}$|$μ_1-μ_2\neqδ \\ μ_1-μ_2> δ \\ μ_1-μ_2<δ$|$\vert t\vert ⩾ t_{α/2}(n_1+n_2-2) \\  t ⩾ t_{α}(n_1+n_2-2) \\ t ⩽ -t_{α}(n_1+n_2-2)$
==$χ^2$检验==<br> ($μ$未知)|$σ^2=σ_0^2 \\ σ^2⩽ σ^2_0 \\ σ^2⩾σ^2_0$|$χ^2=\dfrac{(n-1)S^2}{σ^2}$|$σ^2\neq σ^2_0 \\ σ^2> σ^2_0 \\ σ^2<σ^2_0$|$χ^2 ⩾ χ^2_{α/2}(n-1) 或\\ χ^2 ⩽ χ^2_{1-α/2}(n-1) \\  χ^2 ⩾ χ^2_{α}(n-1) \\ χ^2 ⩽ -χ^2_{α}(n-1)$
==F检验==<br> ($μ_1,μ_2$未知)|$σ^2=σ_0^2 \\ σ^2⩽ σ^2_0 \\ σ^2⩾σ^2_0$|$F=\dfrac{S_1^2}{S_2^2}$|$σ^2\neq σ^2_0 \\ σ^2> σ^2_0 \\ σ^2<σ^2_0$|$F ⩾ F_{α/2}(n_1-1,n_2-1) 或\\ F ⩽ F_{1-α/2}(n_1-1,n_2-1) \\  F ⩾ F_{α}(n_1-1,n_2-1) \\ F ⩽ -F_{α}(n_1-1,n_2-1)$
==t 检验==<br> (成对数据D=X-Y) |$μ_D=0 \\ μ_D⩽ 0 \\ μ_D⩾ 0$|$t=\dfrac{\bar D-0}{S_D/\sqrt{n}}$|$μ_D\neq 0 \\ μ_D> 0 \\ μ_D<0$|$\vert t\vert ⩾ t_{α/2}(n-1) \\  t ⩾ t_{α}(n-1) \\ t ⩽ -t_{α}(n-1)$

## 置信区间和假设检验的关系(The relationship between confidence intervals and hypothesis testing)
置信区间和假设检验之间有明显的关联，先考察置信区间和双边检验的关系
设总体 $X∼ F(x;θ),θ\inΘ$， $X_1,X_2,\cdots,X_n$是来自总体的样本， $x_1,x_2,\cdots,x_n$是样本值
(1) 设区间$(\hatθ_L,\hatθ_U)$为θ的置信水平为 $1-α$ 的置信区间。则对于$∀ θ\inΘ$，满足$$P\{\hatθ_L<θ<\hatθ_U\}⩾ 1-α \tag{1}$$其中 $\hat θ_L=\hat θ_L(X_1,X_2,…,X_n),\hat θ_U=\hat θ_U(X_1,X_2,…,X_n)(\hatθ_L<\hatθ_U)$
(2) 考虑显著性水平为 $α$ 的双边检验 $H_0: θ=θ_0,\quad H_1: θ\neq θ_0$，由(1)式得 $P\{θ_0⩽ \hatθ_L∪ θ_0⩾ \hatθ_U\}⩽ α$，则假设检验的拒绝域为 $θ_0⩽ \hatθ_L∪ θ_0⩾ \hatθ_U$，接受域为 $\hatθ_L<θ_0<\hatθ_U$
这就是说当我们做上述假设检验时，先求出θ的置信区间，若 $θ_0\in(\hatθ_L,\hatθ_U)$则接受原假设 $H_0$，若 $θ_0\not\in(\hatθ_L,\hatθ_U)$则拒绝原假设 $H_0$
反之，显著水平为 $α$ 的双边检验也是置信水平为 $1-α$ 的置信区间。

结论
(1) 置信水平为 $1-α$ 的置信区间 $(\hatθ_L,\hatθ_U)$ 与显著水平为 $α$ 的双边检验 $H_0: θ=θ_0,\quad H_1: θ\neq θ_0$ 有对应关系
(2) 置信水平为 $1-α$ 的单侧置信区间 $(-∞,\hatθ_U)$ 与显著水平为 $α$ 的左边检验 $H_0: θ⩾ θ_0,\quad H_1: θ< θ_0$ 有对应关系
(3) 置信水平为 $1-α$ 的单侧置信区间 $(\hatθ_L,+∞)$ 与显著水平为 $α$ 的右边检验 $H_0: θ⩽ θ_0,\quad H_1: θ> θ_0$ 有对应关系

## 非参数检验(Nonparametric tests)
前面介绍的各种检验都是在总体服从正态分布前提下，对参数进行假设检验的。但是，在数据分析过程中，由于种种原因，总体服从何种理论分布并不知道，此时参数检验的方法就不再适用了。
> 百度百科：https://baike.baidu.com/item/%E9%9D%9E%E5%8F%82%E6%95%B0%E6%A3%80%E9%AA%8C/6910745?fr=aladdin

==Pearson $χ^2$ 拟合优度检验==(Goodness of Fit Test)
拟合优度检验是用卡方统计量根据样本数据，推断总体分布与期望分布或某一理论分布是否存在显著差异，是一种吻合性检验，通常适于对有多项分类值的总体分布的分析。它的原假设是：样本来自的总体分布与期望分布或某一理论分布无差异。

设总体 $X∼ F(x), F(x)$未知，检验假设 $H_0:F(x)=F_0(x)\quad ∀ x\in\R$，其中 $F_0(x)$为已知分布函数。

拟合优度检验的基本原理和步骤：
(1) 在 $H_0$ 下，总体 $X$ 取值的全体分成 k 个两两不相交的子集 $A_1,\cdots,A_k$
(2) 以 $n_i(i=1,\cdots,k)$ 记样本观察值 $x_1,\cdots,x_n$ 中落在 $A_i$的个数（实际频数）
(3) 当 $H_0$ 为真且 $F_0(x)$ 完全已知时，计算事件 $A_i$发生的概率 $p_i=P\{X=a_i\}$
当$F_0(x)$含有 $r$ 个未知参数时，先利用极大似然法估计 $r$ 个未知参数，然后求得的 $p_i$ 估计$\hat p_i$
此时称 $np_i$(或 $n\hat p_i$ )为理论频数。
(4) 以 $F_0(x)$ 完全已知为例，由大数定理得 $\dfrac{n_i}{n}\to p_i\quad(n\to∞)$
$\implies |n_i-np_i|$ 应偏小
$\implies \displaystyle\sum^{k}_{i=1}C_i(n_i/n-p_i)^2$ 应偏小

其中 $C_i$为给定常数，Pearson证明，如果 $C_i=n/p_i$，则统计量 $χ^2=\displaystyle\sum^{k}_{i=1}\frac{n}{p_i}(\frac{n_i}{n}-p_i)^2=\displaystyle\sum^{k}_{i=1}(\frac{n_i^2}{np_i}-n)$ 具有以下定理中的性质

<kbd>定理</kbd>：不论总体服从什么分布，若 n充分大，当 $H_0$ 为真时
统计量 $χ^2=\displaystyle\sum^{k}_{i=1}(\frac{n_i^2}{np_i}-n)$近似服从 $χ^2(k-1)$，拒绝域为 $χ^2⩾ χ^2_{α}(k-1)$
统计量 $χ^2=\displaystyle\sum^{k}_{i=1}(\frac{n_i^2}{n\hat p_i}-n)$近似服从 $χ^2(k-r-1)$，拒绝域为 $χ^2⩾ χ^2_{α}(k-r-1)$
其中 k 为分类数，$r$ 为 $F_0(x)$ 中被估未知参数的个数，$α$为显著性水平。
注：根据实践，要求 $n⩾ 50,np_i(或n\hat p_i)⩾ 5$。否则应适当合并相邻的类，以满足要求。

==Pearson $χ^2$ 独立性检验==(test of independence)
考虑二维总体 $(X,Y)∼ F(x,y)$，且 $X∼ F_1(x),Y∼ F_2(y)$，$(X_1,Y_1),(X_2,Y_2),\cdots,(X_n,Y_n)$是来自总体的样本
检验假设 $H_0:X,Y独立\quad H_1:X,Y不独立$
即 $H_0:F(x,y)=F_1(x)F_2(y)\quad H_1:F(x,y)\neq F_1(x)F_2(y)$

(1) 将两个指标 $X , Y$ 分别划分成两两互不相交的子集 $A_1,A_2,\cdots,A_r$ 和 $B_1,B_2,\cdots,B_s$，样本值落入小区域的个数为

$\begin{array}{c|cccccc|c}
X/Y &B_1&B_2&\cdots&B_j&\cdots &B_s&\{X\in A_i\} \\
\hline
A_1 &n_{11}&n_{12}&\cdots&n_{1j}&\cdots &n_{1s}&n_{1 \bullet} \\
A_2 &n_{21}&n_{22}&\cdots&n_{2j}&\cdots &n_{2s}&n_{2 \bullet} \\
\vdots &\cdots&&\cdots&&\cdots&  &\vdots \\
A_i&n_{i1}&n_{i2}&\cdots&n_{ij}&\cdots &n_{is}&n_{i \bullet} \\
\vdots &\cdots&&\cdots&&\cdots &&\vdots \\
A_r&n_{r1}&n_{r2}&\cdots&n_{rj}&\cdots &n_{rs}&n_{r \bullet} \\
\hline
\{Y\in B_j\} &n_{\bullet 1}&n_{\bullet 2}&\cdots&p_{\bullet j}&\cdots &n_{\bullet s}&n
\end{array}$

(2) 记 $p_{ij}$ 为 $( X , Y )$ 落入小区域 $( i , j )$ 中概率
边缘分布
$p_{i\bullet}=\displaystyle\sum^{s}_{j=1}p_{ij},\quad p_{\bullet j}=\displaystyle\sum^{r}_{i=1}p_{ij}$
则检验转化为 $H_0:p_{ij}=p_{i\bullet}\cdot  p_{\bullet j}$
由于 $p_{i\bullet},  p_{\bullet j}$未知，用估计量代替 $\hat p_{\bullet j}=\dfrac{n_{i\bullet}}{n},\quad \hat p_{\bullet j}=\dfrac{n_{\bullet j}}{n}$
(3) 当 $H_0$为真时，$\dfrac{n_{ij}}{n}\approx \hat p_{i\bullet}\cdot  \hat p_{\bullet j}$
统计量 $χ^2=\displaystyle\sum^{r}_{i=1}\sum^{s}_{j=1}(\frac{n_i^2}{n\hat p_{i\bullet}\cdot  \hat p_{\bullet j}}-n)∼ χ^2((r-1)(s-1))$ 
拒绝域为 $χ^2⩾ χ^2_{α}((r-1)(s-1))$

==偏度、峰度检验==
Pearson $χ^2$ 检验方法适合于一般的总体分布，但若总体分布为正态分布，其犯第 $\mathrm{II}$ 类错误的概率往往比较高。为此统计学家们对检验正态总体的方法进行了比较，通过大量模拟运算的结果，认为检验正态分布以偏度和峰度检验法和[夏皮罗-威尔克检验(Shapiro–Wilk test)](https://blog.csdn.net/lvsehaiyang1993/article/details/80473265)最为有效。

随机变量 $X$ 的偏度和峰度为标准变化量 $Y=[X-E(X)]/\sqrt{D(X)}$ 的三阶矩和四阶矩。
$ν_1=E(Y^3)=\dfrac{B_3}{B_2^{3/2}},\quad ν_2=E(Y^4)=\dfrac{B_4}{B_2^2}$
其中 $B_k=E[(X-E(X))^k]$为 $X$的 k 阶中心距。当 $X∼ N(μ,σ^2)$ 时，$ν_1=0,ν_2=3$

(1) 设 $X_1,X_2,\cdots,X_n$是来自总体的样本，偏度和峰度 $ν_1,ν_2$ 的矩估计量分别是 $G_1,G_2$
当 $X∼ N(μ,σ^2)$ ，可证明 $n$ 充分大时， 近似有$G_1∼ N(0,σ_1^2)  , G_2∼ N(μ_2,σ_2^2)$
其中 $σ_1^2=\dfrac{6(n-2)}{(n+1)(n+3)},μ_2=3-\dfrac{6}{n+1},σ_2^2=\dfrac{24(n-2)(n-3)}{(n+1)^2(n+3)(n+5)}$

(2) 现在来检验假设 $H_0:X∼ N(μ,σ^2)$
将$G_1,G_2$标准化 $U_1=G_1/σ_1,U_2=(G_2-μ_2)/σ_2$
由大数定律得 
$G_1\xrightarrow{P}ν_1\quad (n\to∞)$
$G_2\xrightarrow{P}ν_2\quad (n\to∞)$
当 $H_0$ 为真， $n$ 充分大时（一般大于100为宜），有$U_1∼ N(0,1),U_2∼ N(0,1)$
$|U_1|,|U_2|$的观察值 $|u_1|,|u_2|$不应与$ν_1=0,ν_2=3$ 偏离过大，取显著性水平为 $α$，可求得拒绝域为 $|u_1|⩾ z_{α/4}或|u_2|⩾ z_{α/4}$

==K-S 检验==
单样本K-S检验方法能够利用样本数据推断样本来自的总体是否服从某一理论分布，是一种拟合优度的检验方法，适用于探索连续型随机变量的分布。原假设是：样本来自的总体与指定的理论分布无显著差异。
K-S检验不仅能够检验单个总体是否服从某一理论分布，还能够检验两总体分布是否存在显著差异。其原假设是：两组独立样本来自的两总体的分布无显著差异。
这里是以变量值的秩作为分析对象，而非变量值本身。

==秩和检验==(Rank Sum Test)
如果两个样本来自两个独立的但非正态或形态不清的两总体，要检验两样本之间的差异是否显著，不应运用参数检验中的T检验，而需采用秩和检验。
秩和检验方法最早是由维尔克松(Wilcoxon)提出，叫维尔克松两样本检验法。后来曼—惠特尼将其应用到两样本容量不等($n_1\ne n_2$)的情况，因而又称为Mann-Whitney U test。这种方法主要用于比较两个独立样本的差异。

(1) 设两个总体 $X_1∼ F_1(x),X_2∼ F_2(x)$ 均为未知分布。
检验假设 $H_0:F_1(x)=F_2(x),\quad H_1:F_1(x)\neq F_2(x)$

(2) ==秩的定义==：设从总体 $X$ 抽出容量为 $n$的样本，把样本观察值排列成$x_{(1)}<x_{(2)}<\cdots<x_{(n)}$，称 $x_{(i)}$的足标 $i(i=1,2,\cdots,n)$ 为秩。
现从两总体 $X_1,X_2$ 中分别抽出容量为 $n_1,n_2$的样本（这里总假定 $n_1⩽ n_2$），把 $n_1+n_2$ 个观察值混合排列求出每个观察值的秩。
计算  $X_1,X_2$ 的样本观察值的秩相加，其和为 $R_1,R_2$，称为秩和。显然$R_1,R_2$为离散型随机变量，且 $R_1+R_2=\dfrac{1}{2}(n_1+n_2)(n_1+n_2+1)$已知。

(3) 当 $H_0$ 为真时，两个样本其实来自同一整体，$X_1$ 的样本观察值的秩应随机分散的在自然数 $[1,n_1+n_2]$ 之间，不应过渡集中，即 $R_1\in [\dfrac{1}{2}n_1(n_1+1),\dfrac{1}{2}n_1(n_1+2n_2+1)]$且不应过度靠近区间两端。
据以上分析，对于双边检验，在显著性水平 $α$ 下，$H_0$ 的拒绝域为 $r_1⩽ C_U(α/2)或r_1⩾ C_L(α/2)$，其中 $r_1$为 $R_1$的观察值，临界点$C_U(α/2)$ 是满足 $P\{R_1⩽ C_U(α/2)\}⩽ α/2$ 的最大整数，$C_L(α/2)$ 是满足 $P\{R_1⩾ C_L(α/2)\}⩽ α/2$ 的最小整数，而犯第 $\mathrm{I}$ 类错误的概率为 $α$
如果知道 $R_1$的分布，临界点是不难求得的。

(4) 当 $H_0$ 为真时，可知$X_1$的样本秩的不同取法共有 $∁_{n_1+n_2}^{n_1}$种，且是等可能的。
可证明 $μ_{R_1}=E(R_1)=\dfrac{1}{2}n_1(n_1+n_2+1),σ^2_{R_1}=D(R_1)=\dfrac{1}{12}n_1n_2(n_1+n_2+1)$
而当 $n_1,n_2⩾ 10$，$H_0$ 为真时，近似有 $R_1∼ N(μ_{R_1},σ^2_{R_1})$，此时我们可以采用 $Z=(R_1-μ_{R_1})/σ^2_{R_1}$ 作为统计量
在显著性水平 $α$ 下的双边检验、右边检验、左边检验分别为
$|z|⩾ z_{α/2},\quad z⩾ z_{α},\quad z⩽ -z_{α}$
这里 $z$是 $Z$ 的观察值。


## 假设检验问题中的 p-value 检验法(The p-value test method in hypothesis testing problems)
以上讨论的问题都是临界值法，在假设检验中常见到P值(P-Value，Probability，Pr)，P值是进行检验决策的另一个依据。

为理解 p-value 从一个例子引入
设总体 $X∼ N(μ,σ^2),μ$未知，现有样本 $X_1,X_2,\cdots,X_n$，观察值为 $x_1,x_2,\cdots,x_n$
检验假设 $H_0:μ=μ_0,\quad  H_1:μ\neq μ_0$
采用 Z检验法，统计量为 $Z=\dfrac{\bar X-μ_0}{σ/\sqrt{n}}$，将样本数据代入得Z的观察值为 $z_0=\dfrac{\bar x-μ_0}{σ/\sqrt{n}}$
概率 $P\{Z⩾ |z_0|\}=1-Φ( |z_0|)$，此即为标准正态曲线下位于 $|z_0|$ 右端的尾部面积。
此概率称为 Z 检验法右边检验的 p-value，若显著性水平 $α⩾ p$，则对应的临界值 $z_α⩽ z_0$，因而拒绝原假设。

==p-value 的定义==：假设检验的 p-value 由检验统计量的样本观察值得出的原假设可被拒绝的最小显著性水平。
(1) 若 $p⩽ α$，则在显著性水平 α 下拒绝 $H_0$
(2) 若 $p> α$，则在显著性水平 α 下接受 $H_0$
如果 $p⩽ 0.01$，说明是较强的判定结果。
如果 $0.01<p⩽ 0.05$，说明较弱的判定结果。
如果 $0.05<p⩽ 0.1$，说明拒绝的理由较弱的，检验不显著。
如果 $p>0.1$，没有理由拒绝。

# 方差分析(Analysis of Variance, ANOVA)
==方差分析(ANOVA)==，是由英国统计学家费歇尔(Fisher)在20世纪20年代提出的，可用于推断两个或两个以上总体均值是否有差异的显著性检验。
在方差分析中， 通常把研究对象的特征值，即所考察的试验结果称为==试验指标==(Test Indicators)。
对试验指标产生影响的原因称为==因素==(factor)。因素中各个不同状态称为==水平==(level)。
如果在一项试验中，只有一个因素改变，称为==单因素试验==(Single-factor experiment)，如果有多个因素改变称为==多因素试验==(Multiple-factor experiment)。

## 单因素方差分析(One-factor analysis of variance)
设因素 $A$ 有 $r$ 个水平 $A_1,A_2,\cdots,A_r$，在水平 $A_i$下进行 $n_i(n_i⩾ 2)$次试验，得到如下结果，我们假定各个水平下的样本符合正态分布，且方差相等（均值和方差均未知），且不同水平下样本之间相互独立。
水平|观察结果|样本均值
:---|:---|:---|
$A_1: N(μ_1,σ^2)$| $X_{11},X_{12},\cdots,X_{1n_1}$| $\bar X_{1\bullet}$
$A_2: N(μ_2,σ^2)$| $X_{21},X_{22},\cdots,X_{2n_2}$| $\bar X_{2\bullet}$
$\cdots$| $\cdots$| $\cdots$
$A_r: N(μ_r,σ^2)$| $X_{r1},X_{r2},\cdots,X_{rn_r}$| $\bar X_{r\bullet}$

由于 $X_{ij}∼ N(μ_i,σ^2)$，即有 $X_{ij}-μ_i∼ N(0,σ^2)$，故 $ϵ_{ij}=X_{ij}-μ_i$可看做随机误差。各总体间相互独立.。因此， 有如下的数学模型
$\begin{cases}
X_{ij}=μ_i+ϵ_{ij} \\
 ϵ_{ij}∼  N(0,σ^2),\quad 各ϵ_{ij}独立  \\
i=1,2,\cdots,r \\
j=1,2,\cdots,n_i
\end{cases}$
记 $n=\displaystyle\sum_{i=1}^{r}n_i$

方差分析的任务是对上述模型：
 - 比较这 $r$ 个总体的均值差异，即检验假设 $H_0:μ_1=μ_2=\cdots=μ_r,\quad H_1:μ_1,μ_2,\cdots,μ_r$不全相等
 - 作出未知参数 $μ_1,μ_2,\cdots,μ_r,σ^2$ 的估计


(1) 为了便于讨论，我们引入加权平均值 $μ=\displaystyle\frac{1}{n}\sum_{i=1}^{r}n_iμ_i$，称为==总平均==(total mean)。
再引入 $δ_i=μ_i-μ$，称为水平 $A_i$ 的==效应==(effect)。此时 $\displaystyle\sum_{i=1}^{r}n_iδ_i=0$
于是上述模型可改写为
$\begin{cases}
X_{ij}=μ+δ_i+ϵ_{ij} \\
 ϵ_{ij}∼  N(0,σ^2),\quad 各ϵ_{ij}独立  \\
i=1,2,\cdots,r \\
j=1,2,\cdots,n_i \\
 \displaystyle\sum_{i=1}^{r}n_iδ_i=0 
\end{cases}$
假设等价于 $H_0:δ_1=δ_2=\cdots=δ_r=0,\quad H_1:δ_1,δ_2,\cdots,δ_r$不全为零
(2) 平方和分解
引入总偏差平方和$\displaystyle S_T=\sum_{i=1}^{r}\sum_{j=1}^{n_i}(X_{ij}-\bar X)^2$，能反应全部数据间的差异，称为==总离差平方和==(total sum of deviation square)。其中$\displaystyle\bar X=\frac{1}{n}\sum_{i=1}^{r}\sum_{j=1}^{n_i}X_{ij}$是数据的总平均。
$S_T$ 可分解为两部分 
一部分是有因素 $A$ 引起的差异，称为==效应平方和==(sum of squares of effects) $S_A=\displaystyle\sum_{i=1}^{r}(X_{i\bullet}-\bar X)^2$
另一部分则由随机误差所引起的差异，称为==误差平方和==(sum of squares of errors) $S_E=\displaystyle\sum_{i=1}^{r}\sum_{j=1}^{n_i}(X_{ij}-X_{i\bullet})^2$
其中水平 $A_i$ 下的样本均值 $\bar X_{i\bullet}=\displaystyle\frac{1}{n_i}\sum_{j=1}^{n_i}X_{ij}$
(3) 拒绝域
$S_T=S_A+S_E$
$S_E/σ^2∼ χ^2(n-r)$
$S_A$与$S_E$相互独立
当 $H_0$为真时，$S_A/σ^2∼ χ^2(r-1),\dfrac{S_A/(r-1)}{S_E/(n-r)}∼ F(r-1,n-r)$
==单因素试验方差分析表==
方差来源|平方和(SumSquare)|自由度(df)|均方(MS)|F
:---|:---|:---|:---|:---
因素A(组间)|$S_A$|$r-1$|$MS_A=S_A/(r-1)$|$MS_A/MS_E$
误差(组内)|$S_E$|$n-r$|$MS_E=S_E/(n-r)$|
总和|$S_T$|$n-1$||
当$F⩾ F_α(r-1,n-r)$时，拒绝原假设

(4) 未知参数估计
无论 $H_0$ 是否为真，$E(\dfrac{S_E}{n-r})=σ^2$，$σ^2$的无偏估计 $\hat σ^2=S_E/(n-r)=MS_E$
$μ_i$ 的无偏估计 $\hat μ_i=\bar X_{i\bullet}\ (i=1,2,\cdots,r)$

(5) 当拒绝 $H_0$时，只能说明均值不全相等。那么，它们中有没有部分是相等的？
比较 $N(μ_i,σ^2),N(μ_j,σ^2)\ (i\neq j)$ 差异的两个方法
a. 作 $μ_i-μ_j$ 的区间估计
由于 $E(\bar X_{i\bullet}-\bar X_{j\bullet})=μ_i-μ_j,\ D(\bar X_{i\bullet}-\bar X_{j\bullet})=σ^2(\dfrac{1}{n_i}+\dfrac{1}{n_j})$，且 $\bar X_{i\bullet}-\bar X_{j\bullet}$与$\hat σ^2=S_E/(n-r)=MS_E$相互独立
则 $\dfrac{(\bar X_{i\bullet}-\bar X_{j\bullet})-(μ_i-μ_j)}{\sqrt{MS_E(1/n_i+1/n_j)}}∼ t(n-r)$，由此得 $μ_i-μ_j$在 $1-α$置信水平下的置信区间为
$((\bar X_{i\bullet}-\bar X_{j\bullet})± t_{α/2}(n-r)\sqrt{MS_E(1/n_i+1/n_j)})$

b. 检验假设 $H_0:μ_i=μ_j,\quad H_1:μ_i\neqμ_j$
检验统计量 $t=\dfrac{\bar X_{i\bullet}-\bar X_{j\bullet}}{\sqrt{MS_E(1/n_i+1/n_j)}}$
当 $H_0$成立时，$t∼ t(n-r)$
拒绝域 $W=\{|t|⩾ t_{α/2}(n-r)\}$

==方差分析的前提==
(1) 独立性：数据是来自r 个独立总体的简单随机样本.
(2) 正态性： r 个独立总体均为正态总体.
(3) 方差齐性： r 个正态总体的方差是相同
方差分析和其它统计推断一样，样本的独立性对方差分析是非常重要的，在实际应用中会经常遇到非随机样本的情况，这时使用方差分析得出的结论不可靠。
在实际中，几乎没有一个总体真正服从正态分布，而方差分析却依赖于正态性假设，不过根据经验，方差分析F检验对正态性的假设并不是非常敏感，即实际所得到的数据，若没有异常值和偏性， 或者说， 数据显示的分布比较对称的话， 即使样本容量比较小(如每个水平下的样本容量仅为5左右)， 方差分析的结果仍是值得依赖的。
方差齐性对于方差分析是非常重要的， 方差齐性的检验可采用如下的经验准则：当最大样本标准差不超过最小样本标准差的两倍时， 方差分析F检验结果近似正确。

## 双因素方差分析(Two-factor analysis of variance)
**双因素等重复试验的方差分析**
设有两个因素作用于试验指标，因素 $A$ 有 $r$ 个水平 $A_1,A_2,\cdots,A_r$，因素 $B$ 有 $s$ 个水平 $B_1,B_2,\cdots,B_s$，在水平 $(A_i,B_j)$下都进行 $t(t ⩾ 2)$次试验，得到如下结果
因素A / 因素B|$B_1$|$B_2$|$\cdots$|$B_s$|
---|---|---|---|---|
$A_1$| $X_{111},X_{112},\cdots,X_{11t}$| $X_{121},X_{122},\cdots,X_{12t}$|$\cdots$|$X_{1s1},X_{1s2},\cdots,X_{1st}$
$A_2$| $X_{211},X_{212},\cdots,X_{21t}$| $X_{221},X_{222},\cdots,X_{22t}$|$\cdots$|$X_{2s1},X_{2s2},\cdots,X_{2st}$
$\vdots$| $\vdots$| $\vdots$| |$\vdots$
$A_r$| $X_{r11},X_{r12},\cdots,X_{r1t}$| $X_{r21},X_{r22},\cdots,X_{r2t}$|$\cdots$|$X_{rs1},X_{rs2},\cdots,X_{rst}$|$\cdots$

并设 $X_{ijk}∼ N(μ_{ij},σ^2)$，且方差相等（均值和方差均未知），且不同水平下样本之间相互独立。或写成如下的数学模型
$\begin{cases}
X_{ijk}=μ_{ij}+ϵ_{ijk} \\
 ϵ_{ijk}∼  N(0,σ^2),\quad 各ϵ_{ijk}独立  \\
i=1,2,\cdots,r ;\quad j=1,2,\cdots,s ;\quad k=1,2,\cdots,t \\
\end{cases}$
引入记号 
$\displaystyle μ=\frac{1}{rs}\sum_{i=1}^{r}\sum_{j=1}^{s}μ_{ij} \\
μ_{i\bullet}=\frac{1}{s}\sum_{j=1}^{s}μ_{ij} \quad(i=1,2,\cdots,r)\\
μ_{\bullet j}=\frac{1}{r}\sum_{i=1}^{r}μ_{ij} \quad(j=1,2,\cdots,s)\\
α_i=μ_{i\bullet}-μ \quad(i=1,2,\cdots,r)\\
β_j=μ_{\bullet j}-μ  \quad(j=1,2,\cdots,s)$
易见 $\displaystyle\sum_{i=1}^{r}α_i=0,\quad\sum_{j=1}^{s}β_j=0$
称 $μ$ 为==总平均==，$α_i$为水平 $A_i$ 的==效应==，$β_j$为水平 $B_j$ 的==效应==，这样可将 $μ_{ij}$ 表示为
$μ_{ij}=μ+α_i+β_j+γ_{ij}$
$γ_{ij}=μ_{ij}-μ_{i\bullet}-μ_{\bullet j}+μ$ 称为水平$A_i$和水平$β_j$的==交互效应==(interaction)。这是有两个因素联合起来搭配作用而引起的。
易见 $\displaystyle\sum_{i=1}^{r}γ_{ij}=0,\quad\sum_{j=1}^{s}γ_{ij}=0$
于是上述模型可改写为
$\begin{cases}
X_{ij}=μ+α_i+β_j+γ_{ij}+ϵ_{ijk} \\
 ϵ_{ij}∼  N(0,σ^2),\quad 各ϵ_{ij}独立  \\
i=1,2,\cdots,r ;\quad j=1,2,\cdots,s ;\quad k=1,2,\cdots,t \\
\displaystyle\sum_{i=1}^{r}α_i=0,\quad\sum_{j=1}^{s}β_j=0 ,\quad\sum_{i=1}^{r}γ_{ij}=0,\quad\sum_{j=1}^{s}γ_{ij}=0
\end{cases}$
其中 $μ,α_i,β_j,γ_{ij}$ 都是未知参数。
对于这个模型我们要检验三个假设：
$H_{01}:α_1=α_2=\cdots=α_r=0,\quad H_{11}:α_1,α_2,\cdots,α_r$不全为零
$H_{02}:β_1=β_2=\cdots=β_s=0,\quad H_{12}:β_1,β_2,\cdots,β_s$不全为零
$H_{03}:γ_{ij}=0,\quad H_{13}:γ_{ij}$不全为零

与单因素类似，这些问题也建立在平方和分解上，先引入
$\displaystyle \bar X=\frac{1}{rst}\sum_{i=1}^{r}\sum_{j=1}^{s}\sum_{k=1}^{t}X_{ijk} \\
\bar X_{ij\bullet}=\frac{1}{t}\sum_{k=1}^{t}X_{ijk} \quad(i=1,2,\cdots,r ;\quad j=1,2,\cdots,s)\\
\bar X_{i\bullet\bullet}=\frac{1}{st}\sum_{j=1}^{s}\sum_{k=1}^{t}X_{ijk}  \quad(i=1,2,\cdots,r)\\
\bar X_{\bullet j\bullet}=\frac{1}{rt}\sum_{i=1}^{r}\sum_{k=1}^{t}X_{ijk}  \quad(j=1,2,\cdots,s)$

==总偏差平方和==$\displaystyle S_T=\sum_{i=1}^{r}\sum_{j=1}^{s}\sum_{k=1}^{t}(X_{ijk}-\bar X)^2$
平方和的分解式 $S_T=S_E+S_A+S_B+S_{A× B}$
$\displaystyle S_E=\displaystyle\sum_{i=1}^{r}\sum_{j=1}^{s}\sum_{k=1}^{t}( X_{ijk}-\bar X_{ij\bullet})^2 \\
S_A=st\sum_{i=1}^{r}(\bar X_{i\bullet\bullet}-\bar X)^2 \\
S_B=rt\sum_{j=1}^{s}(\bar X_{\bullet j\bullet}-\bar X)^2 \\
S_{A× B}=t\sum_{i=1}^{r}\sum_{j=1}^{s}(\bar X_{ij\bullet}-\bar X_{i\bullet\bullet}-\bar X_{\bullet j\bullet}+\bar X)^2$
$S_E$称为==误差平方和==，$S_A,S_B$称为因素  $A,B$ 的==效应平方和==，$S_{A× B}$称为 $A,B$ ==交互效应平方和==。

且可以证明下列
$\displaystyle
E\left(\dfrac{S_E}{rs(t-1)}\right)=σ^2\\ 
E\left(\dfrac{S_A}{r-1}\right)=σ^2+\dfrac{st}{r-1}\sum_{i=1}^{r}α_i^2 \\
E\left(\dfrac{S_B}{s-1}\right)=σ^2+\dfrac{rt}{s-1}\sum_{j=1}^{s}β_j^2 \\
E\left(\dfrac{S_{A× B}}{(r-1)(s-1)}\right)=σ^2+\dfrac{t}{(r-1)(s-1)}\sum_{i=1}^{r}\sum_{j=1}^{s}γ_{ij}^2$

==双因素试验方差分析表==
方差来源|平方和 SumSquare|自由度 df|均方 MS|F
:---|:---|:---|:---|:---
因素A(组间)|$S_A$|$r-1$|$MS_A=\dfrac{S_A}{(r-1)}$|$F_A=MS_A/MS_E$
因素B(组间)|$S_B$|$s-1$|$MS_B=\dfrac{S_B}{(s-1)}$|$F_B=MS_B/MS_E$
交互作用|$S_{A× B}$|$(r-1)(s-1)$|$MS_{A× B}=\dfrac{S_A}{(r-1)(s-1)}$|$F_{A× B}=MS_{A× B}/MS_E$
误差 (组内)|$S_E$|$rs(t-1)$|$MS_E=\dfrac{S_E}{rs(t-1)}$|
总和|$S_T$|$rst-1$||

当 $H_{01}$为真时，可以证明
$F_A∼ F(r-1,rs(t-1)) \\
 F_B∼ F(s-1,rs(t-1)) \\
 F_{A× B}∼ F((r-1)(s-1),rs(t-1))$

假设 $H_{01}$的拒绝域为 $F_A ⩾ F_α(r-1,rs(t-1))$
假设 $H_{02}$的拒绝域为 $F_B ⩾ F_α(s-1,rs(t-1))$
假设 $H_{03}$的拒绝域为 $F_{A× B} ⩾ F_α((r-1)(s-1),rs(t-1))$

**双因素无重复试验的方差分析**
在以上的讨论中，我们考虑了双因素实验中两个因素的交互作用，为了检验交互作用的效应是否显著，对于两个因素的每个组合 $(A_i,B_j)$ 至少要做两次试验，如果在实际问题中已经知道不存在交互作用，或效应很小，此时可以不考虑交互作用。每组制作一次试验 $k=1$ 也能分析因素 $A,B$ 的效应，此时称为无重复实验的方差分析。


# 回归分析(Regression Analysis)
在客观世界中，普遍存在着变量之间的额关系。变量之间的关系一般可分为确定性关系和相关性关系。

**确定性关系**(deterministic)：
当自变量给定一个值时，就确定应变量的值与之对应。如：在自由落体中，物体下落的高度 $h$与下落时间$t$之间有函数关系：$h=\frac{1}{2}gt^2$

**相关性关系**(correlation)：
变量之间的关系并不确定，而是表现为具有随机性的一种“趋势”。即对自变量 $x$ 的同一值，在不同的观测中，因变量$Y$可以取不同的值，而且取值是随机的，但对应 $x$在一定范围的不同值，对$Y$进行观测时，可以观察到$Y$随$x$的变化而呈现有一定趋势的变化。回归分析是研究相关关系得一种数学工具。

## 一元线性回归(Simple Linear Regression)
设随机变量 $Y$(因变量)与普通变量 $x$(自变量)存在着相关关系，对于 $x$的确定值， $Y$有他的分布（图中$C_1,C_2$分别是 $x_1,x_2$处 $Y$ 的概率密度曲线），用 $F(y|x)$ 表示 $Y$的分布函数，然而此函数讨论过于复杂，我们转而讨论 $E(Y)=μ(x)$与$x$的关系，称为 $Y$ 关于 $x$ 的==回归函数==(regression function)。同时以回归函数作为 $Y$ 的近似，其均方误差 $E[Y-μ(x)]^2$ 最小。
![一元回归](https://img-blog.csdnimg.cn/20190624145653732.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNTE4Mjc3,size_16,color_FFFFFF,t_70)

对从整体 $(x,Y)$ 中抽取的一个样本 $(x_1,Y_1),(x_2,Y_2),\cdots,(x_n,Y_n)$，样本值为 $(x_1,y_1),(x_2,y_2),\cdots,(x_n,y_n)$，若 $μ(x)$ 为线性函数 $μ(x)=a+bx$，此时的问题称为一元线性回归问题。$Y∼ N(a+bx,σ^2)$，设 $ϵ=Y-(a+bx)$则$$Y=a+bx+ϵ,\quad ϵ∼ N(0,σ^2)$$其中 $a,b,σ^2$ 都是不依赖于 $x$ 的未知参数，因变量 $Y$ 由线性函数和随机误差 $ϵ$ 组成。
一元线性回归要解决的问题：
参数估计：$\begin{cases} 
a,b 的估计 \\ 
σ^2 的估计 
\end{cases}$
参数检验及模型应用：$\begin{cases} 
线性假设的显著性检验 \\ 
回归系数b的置信区间 \\
Y 的点预测
\end{cases}$


(1) $a,b$ 的估计：最小二乘法
由一元线性回归模型得 $Y_i=a+bx_i+ϵ,\quad ϵ_i∼ N(0,σ^2)$且相互独立，用最大似然法来估计未知参数。只需函数取$Q(a,b)=\displaystyle\sum_{i=1}^{n}(y_i-a-bx_i)^2$取最小值，若 $Y$ 不是正态分布，使 $Y$ 的观察值 $y_i$ 与 $a+bx_i$ 偏差的平方和为最小，这种方法叫==最小二乘法==(least square method)。
求估计值 $\hat a,\hat b$ ，使$\displaystyle Q(\hat a,\hat b)=\min_{a,b}Q(a,b)$
$\dfrac{∂ Q}{∂ a}=0,\dfrac{∂ Q}{∂ b}=0$得方程组$$\begin{cases} 
\displaystyle na+(\sum_{i=1}^{n}x_i)b=\sum_{i=1}^{n}y_i \\ 
\displaystyle (\sum_{i=1}^{n}x_i)a+(\sum_{i=1}^{n}x_i^2)b=\sum_{i=1}^{n}x_iy_i
\end{cases}$$称为==正规方程组==(normal system of equations)。由于 $x_i$不全相同，系数行列式不为零，故上述方程有唯一解。则估计值为 $$\begin{cases} 
\hat b=\dfrac{S_{xy}}{S_{xx}} \\
\hat a=\bar y-\hat b\bar x
\end{cases}$$其中 $\displaystyle
S_{xx}=\sum_{i=1}^{n}(x_i-\bar x)^2 \\
S_{yy}=\sum_{i=1}^{n}(y_i-\bar y)^2 \\
S_{xy}=\sum_{i=1}^{n}(x_i-\bar x)(y_i-\bar y) \\
\bar x=\dfrac{1}{n}\sum_{i=1}^{n}x_i,\quad\bar y=\dfrac{1}{n}\sum_{i=1}^{n}y_i$
由此得==经验回归方程==(Empirical regression equation) $\hat y=\hat a+\hat bx$

(2) $σ^2$ 的估计 
记 $e_i=y_i-\hat y$为==残差==(residual)，注意到 $σ^2=D(ϵ)+E(ϵ^2)=E(ϵ^2)$
用==残差平方和==(residual sum of squares) $\displaystyle Q_e=\sum_{i=1}^{n}(y_i-\hat y_i)^2$估计 $σ^2$
可以证明 $Q_e/σ^2∼ χ^2(n-2)$，于是 $E(Q_e)=(n-2)σ^2$
因此 $\hat σ^2=Q_e/(n-2)$ 是 $σ^2$的无偏估计。

(3) 线性假设的显著性检验
检验假设 $H_0:b=0,\quad H_1:b\neq0$

若原假设被拒绝，说明回归效果是显著的。否则，若接受原假设，说明 Y与x不是线性关系，回归方程无意义。回归效果不显著的原因可能有以下几种：
a. 影响Y取值的，除了x，还有其他不可忽略的因素；
b. E(Y)与x的关系不是线性关系，而是其他关系；
c. Y与x不存在关系。

我们用 t 检验法来检验，可证明 $\hat b∼ N(b,σ^2/S_{xx}) \implies (n-2)\hat σ^2/σ^2=Q_e/σ^2∼ χ^2(n-2)$且 $\hat b$与 $Q_e$独立。故可推得 $(\hat b-b)\sqrt{S_{xx}}/\hat σ∼ t(n-2)$
若 $H_0$ 为真， $t=\hat b\sqrt{S_{xx}}/\hat σ∼ t(n-2)$，且 $E(\hat b)=b=0$既得 $H_0$的拒绝域为 $|t|⩾ t_{α/2}(n-2)$

(4) 回归系数(coefficient) $b$ 的置信区间
由上面推论， $b$ 的置信水平为 $1-α$ 的置信区间为：$\hat b±  t_{α/2}(n-2)\hat σ/\sqrt{S_{xx}}$

(5) 回归函数 $Y=a+bx$ 的点估计和置信区间
考虑估计量 $\hat Y_0=\hat a+\hat bx_0$，可求得 $E(\hat Y_0)=a+bx_0$为无偏估计。
并且 $\dfrac{\hat Y_0-(a+bx_0)}{\hat σ\sqrt{1/n+(x_0-\bar x)^2/S_{xx}}}∼ t(n-2)$，于是得到 $a+bx_0$ 的置信区间为
$\left(\hat Y_0± t_{α/2}(n-2)\hat σ\sqrt{\dfrac{1}{n}+\dfrac{(x_0-\bar x)^2}{S_{xx}}}\right)$
这一置信区间的长度是 $x_0$的函数，他随 $|x_0-\bar x|$的增加而增加。

(6) $Y$ 的观察值 $Y_0$ 的点估计和置信区间
观察值$Y_0=a+bx_0+ϵ_0,\quad ϵ_0∼ N(0,σ^2)$
$\implies \hat Y_0=\bar Y+\hat b(x_0-\bar x)$
$\implies\dfrac{\hat Y_0-(a+bx_0)}{\hat σ\sqrt{1+1/n+(x_0-\bar x)^2/S_{xx}}}∼ t(n-2)$
于是得 $Y_0$ 的==预测区间==(prediction interval) $\left(\hat Y_0± t_{α/2}(n-2)\hat σ\sqrt{1+\dfrac{1}{n}+\dfrac{(x_0-\bar x)^2}{S_{xx}}}\right)$


==回归分析表==
||Coef.|Std. error|t Stat|P value|Lower 95%|Upper 95%
---|---|---|---|---|---|---|
$\rm Intercept$|$\hat a$
$\rm X$|$\hat b$

**可化为一元线性回归的例子**
方程|条件|转化
:---|:---|:---
$Y=ae^{bx}\cdot ϵ$|$\ln ϵ∼ N(0,σ^2)$|$\ln Y=\ln a+ \ln bx+\ln ϵ$
$Y=ax^{b}\cdot ϵ$|$\ln ϵ∼ N(0,σ^2)$ |$\ln Y=\ln a+ b\ln x+\ln ϵ$
$Y=a+bh(x)+ ϵ$|$ϵ∼ N(0,σ^2)$|$Y=a+bx'+ ϵ,\quad x'=h(x)$

如果回归函数 $μ(x;θ_1,θ_2,\cdots,θ_p)$ 是参数 $θ_1,θ_2,\cdots,θ_p$ 的线性函数（不必是 $x$ 的线性函数），则称==线性回归模型==(linear regressive model)，若为非线性函数则称==非线性回归模型==(non-linear regressive model)，但是他们都能转化为线性回归模型。
又如 $Y=θ_1e^{θ_1x}\cdot ϵ,\quad ϵ∼ N(0,σ^2)$，他不能转化为线性回归模型，称为==本质的非线性回归模型==。又如 
$Y=(θ_1+θ_2x+θ_3x^2)^{-1}+ϵ\quad(Holiday 模型)\\
Y=\dfrac{θ_1}{1+exp(θ_2+θ_3^x)}+ϵ\quad(Logistic 模型)$ 
都是本质的非线性回归模型。


## 多元线性回归(Multiple Linear Regression)
在实际问题中，随机变量 $Y$ 往往与多个变量 $x_1,x_2,\cdots,x_p(p>1)$ 有关，若 $Y$ 的数学期望存在，记为$μ(x_1,x_2,\cdots,x_p)$它就是 $Y$ 关于 $x$的回归函数为，再次，我们只讨论线性回归模型$$Y=b_0+b_1x_1+b_2x_2=\cdots+b_px_p+ϵ,\quad ϵ∼ N(0,σ^2)$$ 其中 $b_0,b_1,b_2,\cdots,b_p$ 都是与 $x_1,x_2,\cdots,x_p$ 无关的未知参数。
设  $(x_{11},x_{12},\cdots,x_{1p}),\cdots,(x_{n1},x_{n2},\cdots,x_{np})$ 是一个样本，我们用最小二乘法来估计未知参数，只需函数$$Q(b_0,b_1,b_2,\cdots,b_p)=\displaystyle\sum_{i=1}^{n}[y_i-(b_0+b_1x_1+b_2x_2=\cdots+b_px_p)]^2$$取最小值，即估计值满足$$
\displaystyle Q(\hat b_0,\hat b_1,\hat b_2,\cdots,\hat b_p)=\min Q(b_0,b_1,b_2,\cdots,b_p )$$求偏导数$\dfrac{∂ Q}{∂ b_0}=0,\dfrac{∂ Q}{∂ b_j}=0(j=1,2,\cdots,p)$得方程组$$\begin{cases} 
\displaystyle b_0n+b_1\sum_{i=1}^{n}x_{i1}+b_2\sum_{i=1}^{n}x_{i2}+\cdots+b_p\sum_{i=1}^{n}x_{ip}=\sum_{i=1}^{n}y_i \\ 
\displaystyle b_0\sum_{i=1}^{n}x_{i1}+b_1\sum_{i=1}^{n}x_{i1}^2+b_2\sum_{i=1}^{n}x_{i1}\sum_{i=1}^{n}x_{i2}+\cdots+b_p\sum_{i=1}^{n}x_{i1}\sum_{i=1}^{n}x_{ip}=\sum_{i=1}^{n}x_{i1}y_i \\
\cdots \\
\displaystyle b_0\sum_{i=1}^{n}x_{ip}+b_1\sum_{i=1}^{n}x_{i1}\sum_{i=1}^{n}x_{ip}+b_2\sum_{i=1}^{n}x_{ip}\sum_{i=1}^{n}x_{i2}+\cdots+b_p\sum_{i=1}^{n}x_{ip}^2=\sum_{i=1}^{n}x_{ip}y_i
\end{cases}$$称为==正规方程组==，引入矩阵 $$
\bf{X}=\begin{pmatrix}
1&x_{11}&x_{12}&\cdots&x_{1p} \\
1&x_{21}&x_{22}&\cdots&x_{2p} \\
\vdots&\vdots&\ddots&\vdots \\
1&x_{n1}&x_{n2}&\cdots&x_{np} \\
\end{pmatrix},
\bf{Y}=\begin{pmatrix}
y_1 \\
y_2 \\
\vdots \\
y_p \\
\end{pmatrix},
\bf{B}=\begin{pmatrix}
b_0 \\
b_1 \\
\vdots \\
b_p \\
\end{pmatrix},
$$因 $$
\bf{X^TX}=\begin{pmatrix}
n&\displaystyle \sum_{i=1}^{n}x_{i1}&\cdots&\displaystyle \sum_{i=1}^{n}x_{ip} \\
\displaystyle \sum_{i=1}^{n}x_{i1} &\displaystyle \sum_{i=1}^{n}x_{i1}^2&\cdots&\displaystyle \sum_{i=1}^{n}x_{i1}x_{ip} \\
\vdots&\vdots&\ddots&\vdots \\
\displaystyle \sum_{i=1}^{n}x_{ip} &\displaystyle \sum_{i=1}^{n}x_{i1}x_{ip}&\cdots&\displaystyle \sum_{i=1}^{n}x_{ip}^2 \\
\end{pmatrix},
\bf{X^TY}=\begin{pmatrix}
\displaystyle\sum_{i=1}^{n}y_i \\
\vdots \\
\displaystyle\sum_{i=1}^{n}x_{i1}y_i \\
\displaystyle\sum_{i=1}^{n}x_{ip}y_i
\end{pmatrix}
$$上式化为矩阵方程 $$\bf{X^TXB=X^TY}$$可求得其解为 $$
\bf{\hat B}=\begin{pmatrix}
\hat b_0 \\
\hat b_1 \\
\vdots \\
\hat b_p \\
\end{pmatrix}=\bf{(X^TX)^{-1}X^TY}
$$ 于是我们求得经验回归方程为 $\hat y=\hat b_0+\hat b_1x_1+\hat b_2x_2=\cdots+\hat b_px_p$








