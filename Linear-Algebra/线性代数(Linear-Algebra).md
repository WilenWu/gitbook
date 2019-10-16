---
title: 线性代数(Linear Algebra)
tags: [R]
mathjax: false
copyright: true
date: 2019-05-23 15:39:34
categories: [R,Linear Algebra]
sticky: false
---
> 摘自MOOC东南大学和同济大学《线性代数》
> 友情链接：[高等代数-简书](https://www.jianshu.com/c/862d6b86a56d)

<!-- more -->
# 矩阵(Matrix)
> 理解矩阵：  https://blog.csdn.net/myan/article/details/647511

## 矩阵及其运算
**矩阵的概念**： $m× n$ 矩阵是指下列数表$$\begin{pmatrix}
a_{11}&a_{12}&\cdots&a_{1n} \\
a_{21}&a_{22}&\cdots&a_{2n} \\
\vdots&\vdots&\ddots&\vdots \\
a_{m1}&a_{m2}&\cdots&a_{mn} \\
\end{pmatrix}$$矩阵常用大写黑体字母表示，如$A$或$A_{m× n}$，有时也记 $(a_{ij})$或$(a_{ij})_{m× n}$ 。
其中$a_{ij}$叫做矩阵$A$中的$(i,j)$==元素==(entry)。
根据矩阵的元素所属的数域，可以将矩阵分为复矩阵和实矩阵。


**几种特殊的矩阵**
(1) 两个矩阵$A=(a_{ij})_{m× n},B=(a_{ij})_{s× t}$，若$m=s,n=t$，则$A$与$B$是==同型矩阵==(Homomorphic matrix)。
(2) 元全为零的矩阵称为==零矩阵==(zero matrix)，记作$O_{m× n}$或$O$
(3) 行矩阵和列矩阵：$1× n$型矩阵$(a_1,a_2,\cdots,a_n)$只有一行，称为行矩阵(row matrix)或行向量。$m× 1$型矩阵$\begin{pmatrix}a_1\\ a_2\\ \vdots \\ a_n\end{pmatrix}$只有一列，称为列矩阵(column matrix)或列向量。
(4) 行数和列数相等的矩阵为n阶==方阵==(n-order square matrix)或n阶矩阵。

**几种特殊的方阵**
(1) ==上三角矩阵==(upper triangular matrix)与==下三角矩阵==，未显示部分都为0。
$\begin{pmatrix}
a_{11}&a_{12}&\cdots&a_{1n} \\
&a_{22}&\cdots&a_{2n} \\
&&\ddots&\vdots \\
&&&a_{nn} \\
\end{pmatrix}\quad$与$\quad\begin{pmatrix}
a_{11}&&& \\
a_{21}&a_{22}&& \\
\vdots&\vdots&\ddots& \\
a_{n1}&a_{n2}&\cdots&a_{nn} \\
\end{pmatrix}$
(2) ==对角阵==(diagonal matrix)：记作 $\mathrm{diag}(a_{11},a_{22},\cdots,a_{nn})$，当$a_{11}=a_{22}=\cdots=a_{nn}$时，称为==数量矩阵==(scalar matrix)，未显示部分都为0。
$\begin{pmatrix}
a_{11} \\
&a_{22} \\
&&\ddots \\
&&&a_{nn} \\
\end{pmatrix}$
(3)  对角阵 $\mathrm{diag}(1,1,\cdots,1)$称为==单位阵==(identity matrix)，记作$E_n$或$I_n$
(4) ==对称阵==(symmetric matrix)与==反对称阵==(skew-symmetric matrix)：n阶方阵$A=(a_{ij})_{n× n}$，若$a_{ij}=a_{ji}$，称为n阶对称阵，若$a_{ij}=-a_{ji}$称为n阶反对称阵。

**矩阵的线性运算**(Matrix Algebra)
(1) 同型矩阵$A=(a_{ij})_{m× n}与B=(b_{ij})_{m× n}$，如果他们的元对应相等$a_{ij}=b_{ij}$，则称矩阵$A$与$B$相等，记作$A=B$
(2) 矩阵的加法： 同型矩阵$A=(a_{ij})_{m× n}与B=(b_{ij})_{m× n}$，$A+B=(a_{ij}+b_{ij})_{m× n}$
|$A+O=A$|
|:---|
|$A+B=B+A$|
|$(A+B)+C=A+(B+C)$|

(3) 矩阵的数乘：数$k$与矩阵$A=(a_{ij})_{m× n}$，$kA=(ka_{ij})_{m× n}$
$(k+l)A=kA+lA,\quad k(A+B)=kA+kB$|
|:---|
$(kl)A=k(lA)=l(kA)$|
$kA=O\iff k=0\ 或\ A=O$|

**矩阵的乘法**
(1)矩阵的乘法：设矩阵$A=(a_{ij})_{m× n}与B=(b_{ij})_{n× p}$，定义$AB=(c_{ij})_{m× p}$，其中$c_{ij}=\displaystyle\sum_{k=1}^{n}a_{ik}b_{kj},(i=1,2,\cdots,m;j=1,2,\cdots,p)$
$A(BC)=(AB)C$|
|:---|
$A(B+C)=AB+AC;\ (B+C)A=BA+CA$|
$k(AB)=(kA)B=A(kB)$|
$AE=A;\ EA=A$|
>  矩阵乘法不满足交换律和消去律
$AB\ \xcancel{=}\ BA$;
$AB=AC\xcancel{\Rarr} B=C$

(2) 方阵的幂：设A为n阶方阵，定义$A^1=A,\ A^2=AA,\cdots,A^{k+1}=A^kA$
$A^kA^l=A^{k+l}$|
|:---|
$(A^k)^l=A^{kl}$|
(3) 方阵的多项式：$f(A)=a_sA^s+a_{s-1}A^{s-1}+\cdots+a_1A+a_0E$

**矩阵的转置**(transpose)：设矩阵$A=(a_{ij})_{m× n},\ A^T=(a_{ji})_{n× m}$叫做矩阵 $A$的转置矩阵
$(A^T)^T=A$|$(A+B)^T=A^T+B^T$|
|:---|:---|
$(kA)^T=kA^T$|$(AB)^T=B^TA^T$|

**矩阵的行列式**：由n阶方阵A的元素所构成的行列式，称为A的行列式，记为$\det A$或$|A|$
$\det A^T=\det A$|
|:---|
$\det kA=k^n\det A$|
$\det AB=\det A\cdot\det B$ |

## 分块矩阵(Block matrix)
**矩阵的分块**：根据运算的需要，结合矩阵本身的特点，在矩阵的行间和列间，分别用横线和竖线将矩阵划分为若干个子矩阵(submatrix)，此方法称为矩阵的分块，并称这种以子块为元的矩阵为分块矩阵。
$\left(
\def\arraystretch{1.2} 
\begin{array}{cc:c} 
1&0 & 0 & 0 \\ 
0&1 & 0 &0 \\ 
\hdashline 
0&0 & 1 & 5
\end{array}
\right)=\begin{pmatrix}
   E & O \\
   A_1 & A_2
\end{pmatrix}$

==分块对角阵==(block diagonal matrix)：其中$A_1,A_2,\cdots,A_s$是方阵，未显示部分都为0。
$A=\begin{pmatrix}
A_1 \\
&A_2 \\
&&\ddots& \\
&&&A_s \\
\end{pmatrix}$

==按行和列分块==：$A=(A_1,A_2,\cdots,A_n);\quad A=\begin{pmatrix}α_1\\ α_2\\ \vdots \\ α_m\end{pmatrix}$
<kbd>证明</kbd>：$A=O\iff A^TA=O$

|分块矩阵的运算|条件
|:---|:---
$A_{m× n}± B_{m× n}=(A_{rs})_{p× q}± (B_{rs})_{p× q}=(A_{rs}+B_{rs})_{p× q}$|加减法：两个同型矩阵进行同样的分块
$kA_{m× n}=k(A_{rs})_{p× q}=(kA_{rs})_{p× q}$|数乘
$A_{m× s}B_{s× n}=(A_{ik})_{p× t}(B_{kj})_{t× q}=(C_{ij})_{p× q}$<br>其中$C_{ij}=\displaystyle\sum_{k=1}^{t}a_{ik}b_{kj}\\ (i=1,2,\cdots,p;j=1,2,\cdots,q)$|乘法：$B$的列分法和$A$的行分法一致
$A_{m× n}=(A_{rs})_{p× q}\Rarr A^T=(A^T_{rs})_{p× q}$|分块转置

## 矩阵的初等变换(Elementary transformation of matrix)
**初等变换**(elementary transformation)：行（列）初等变换
(1) 互换变换：$r_i\lrarr r_j或c_i\lrarr c_j$
(2) 倍乘变换：$r_i× k或c_i× k,其中k\neq0$
(3) 倍加变换：$r_i+kr_j或r_i+kr_j$
若$A$经有限次初等变换变为$B$，则$A$与$B$==等价==(equivalent)，记为$A \cong B$
任何矩阵A经有限次初等变换都可化为以下形式之一
$\begin{pmatrix}
E_r&O \\
O&O
\end{pmatrix}$、$(E_r,O)$、$\begin{pmatrix}
E_r \\
O 
\end{pmatrix}$
称为矩阵A的==等价标准型==(equivalent standard form)，其中$r$为矩阵$A$的秩。
**行阶梯型矩阵**(Row echelon matrix)：任何矩阵都可以通过初等变换化为行阶梯型
(1) 零行：元素全为0的行
(2) 非零行：元素不全为0的行
(3) 非零首元：非零行第一个不为0的元素
(4) 若有零行，则在最下方；非零首元的列随行的增加而严格递增
$\begin{pmatrix}
5&-3&6&8 \\
&1&-2&6 \\
&&&2 \\
&&& \\
\end{pmatrix}$
**行最简型矩阵**(Row simplest matrix)：任何矩阵都可以通过初等变换化为行最简型
(1) 行阶梯型矩阵
(2) 非零首元都是1
(3) 非零首元所在列的其他元素都是零
$\begin{pmatrix}
1&0&6&8 \\
&1&-2&6 \\
&&&2 
\end{pmatrix}$

**初等矩阵**(elementary matrix)：由单位矩阵$E$经一次初等变化得到的矩阵叫初等矩阵
三种初等变换对应着三种初等矩阵
初等变换|初等矩阵|逆变换|逆矩阵
:---|:---|:---|:---
$r_i\lrarr r_j$|$E(i,j)$|$r_i\lrarr r_j$|$E(i,j)^{-1}=E(i,j)$
$r_i× k$|$E(i(k))$|$r_i× \dfrac{1}{k}$|$E(i(k))^{-1}=E(i(\dfrac{1}{k}))$
$r_i+kr_j$|$E(ij(k))$|$r_i-kr_j$|$E(ij(k))^{-1}=E(ij(-k))$

<kbd>定理 </kbd>：对矩阵$A_{m× n}$进行一次行初等变换，相当于$m$阶初等矩阵左乘$A$；进行一次列初等变换，相当于$n$阶初等矩阵右乘$A$
<kbd>推论 </kbd>：设$A$与$B$为$m× n$矩阵
(1) 存在m阶初等矩阵$P_1,P_2,\cdots,P_s$，使得$P_1P_2\cdots P_sA$为行阶梯型（行最简形）。
(2) 存在m阶初等矩阵$P_1,P_2,\cdots,P_s$和n阶初等矩阵$Q_1,Q_2,\cdots,Q_t$，使得$P_1P_2\cdots P_sAQ_1,Q_2,\cdots,Q_t$为A的等价标准型。
(3) 若$A\cong B$
$\iff$存在可逆矩阵$P,Q$，使得$PA=AQ=B$
$\iff$存在可逆矩阵$P,Q$，使得$PAQ=B$

**利用初等变换解矩阵方程**：
(1) $AX=B\Rarr X=A^{-1}B$
利用行初等变换：$(A,B)\cong (E,A^{-1}B)$
(2) $YA=C\Rarr Y=CA^{-1}$
利用列初等变换：$\begin{pmatrix}A\\ B\end{pmatrix}\cong\begin{pmatrix}E\\ CA^{-1}\end{pmatrix}$
(3) 矩阵方程$AX=B$有解$\iff r(A)=r(A,B)$

## 逆矩阵(Inverses)
**概念**：对于n阶方阵$A$，如果存在n阶方阵$B$，使得$AB=BA=E$，则 $B$为$A$的逆矩阵，称$A$为==可逆矩阵==(invertible matrix)，记为$B=A^{-1}$

$(A^{-1})^{-1}=A$|$(A^T)^{-1}=(A^{-1})^T$|
|:---|:---|
$(AB)^{-1}=B^{-1}A^{-1}$|$(kA)^{-1}=\dfrac{1}{k}A^{-1},(k\neq0)$

<kbd>定理 1</kbd>
(1) 初等矩阵都可逆，且逆矩阵仍是同类型的初等矩阵
(2) A的逆矩阵$A^{-1}$是唯一的
(3) 对于矩阵$A$，存在可逆矩阵$P,Q$，使得$PAQ$为$A$的等价标准型
(4) 分块对角矩阵$A=\mathrm{diag}(A_1,A_2,\cdots,A_s)$可逆$\iff A_1,A_2,\cdots,A_s$均可逆

<kbd>定理  2</kbd>：==$n$ 阶矩阵$A$ 可逆==
$\iff A$可以写成有限个初等矩阵的乘积
$\iff A\cong E$（等价于单位矩阵）
$\iff \det A\neq0$（非奇异矩阵）
$\iff r(A)=n$（满秩矩阵）
$\iff A$的行（列）向量组线性无关
$\iff$齐次线性方程组$Ax=0$只有零解
$\iff ∀ b\in \R^n$，非齐次方程组$Ax=b$有唯一解
$\iff A$的特征值不全为零
$\iff A^TA$是正定矩阵
$\iff A$的行（列）向量组是 $\R^n$的一组基


**伴随矩阵**(adjoint matrix)：由行列式$|A|$的各个元素的代数余子式$A_{ij}$，所构成的矩阵$$A^*=\begin{pmatrix}
A_{11}&A_{21}&\cdots&A_{n1} \\
A_{12}&A_{22}&\cdots&A_{n2} \\
\vdots&\vdots&\ddots&\vdots \\
A_{1n}&A_{2n}&\cdots&A_{nn} \\
\end{pmatrix}$$叫做矩阵$A$的伴随矩阵。==$AA^*=A^*A=|A|E$==

**逆矩阵的计算**
(1) 利用初等行变换：$(A,E)\cong (E,A^{-1})$
(2) 利用初等列变换：$\begin{pmatrix}A\\ E\end{pmatrix}
\cong \begin{pmatrix} E\\ A^{-1} \end{pmatrix}$
(3) 利用伴随矩阵：$A^{-1}=\dfrac{1}{|A|}A^*$


## 矩阵的秩(Rank of matrix)
**概念**：设矩阵$A_{m× n}$
(1)  在矩阵$A$任取k行k列，位于这些行列交叉处的$k^2$个元素，不改变它们在$A$中所处的位置次序而得的k阶行列式，称为矩阵$A$的 ==k阶子式==(minor)。
(2) 若矩阵$A$中有一个不等于零的$r$阶子式$D$，且所有$r+1$阶子式(如果存在的话)全等于零，那么$D$称为矩阵$A$的最高阶非零子式，数$r$称为矩阵$A$的==秩==(rank)，记作$r(A)=r$。(规定零矩阵的秩等于零)
若$r(A_{n× n})=n$，则称$A$为==满秩矩阵==(full rank matrix)
若$|A_{n× n}|\neq 0$，则称$A$为==非奇异矩阵==(non-singular matrix)

**矩阵秩的性质**：
(1) 行阶梯形矩阵的秩就等于非零行的行数
(2) 初等变换不改变矩阵的秩
若$A\cong B$，则 $r(A)=r(B)$
若$P,Q$可逆，则$r(PAQ)=r(A)$
(3) 若$|A_{n× n}|=0$，则 $r(A)<n$
(4) $r(A^T)=r(A)$
(5)  矩阵秩的不等式：
 $0⩽ r(A_{m× n})⩽\min\{m,n\}$
$\max\{r(A),r(B)\}⩽ r(A,B)⩽ r(A)+r(B)$
$r(AB) ⩽  \min\{r(A),r(B)\}$
$r(A+B)⩽ r(A)+r(B)$

## 线性方程组(System of linear equations)
**概念**
(1) 设有n个未知数m个方程的线性方程组
$$
\begin{cases} 
a_{11}x_1+a_{12}x_2+\cdots+a_{1n}x_n=b_1 \\ 
a_{21}x_1+a_{22}x_2+\cdots+a_{2n}x_n=b_2 \\
\cdots \\
a_{m1}x_1+a_{m2}x_2+\cdots+a_{mn}x_n=b_m
\end{cases} 
$$当$b_1,b_2,\cdots,b_n$不全为零时称为==非齐次线性方程组==(system of non-homogeneous linear equations)，当$b_1=b_2=\cdots=b_m=0$时称为==齐次线性方程组==(system of homogeneous linear equations)
(2) 如果存在n个常数$\begin{cases} 
x_1=s_1 \\ 
x_2=s_2 \\
\cdots \\
x_n=s_n
\end{cases}$ 满足线性方程组的所有方程，则称为线性方程组的一个解。
(3) 记$A=\begin{pmatrix}
a_{11}&a_{12}&\cdots&a_{1n} \\
a_{21}&a_{22}&\cdots&a_{2n} \\
\vdots&\vdots&\ddots&\vdots \\
a_{m1}&a_{m2}&\cdots&a_{mn} \\
\end{pmatrix}$，$x=\begin{pmatrix}x_1\\ x_2\\ \vdots \\ x_n\end{pmatrix}$，$b=\begin{pmatrix}b_1\\ b_2\\ \vdots \\ b_m\end{pmatrix},\bar{A}=(A,b)$ 
其中$A,b$分别是系数矩阵和常数项矩阵，$\bar{A}$为==增广矩阵==(augmented matrix)，方程组可化为 ==$Ax=b$==

**线性方程组求解**：对增广矩阵作初等行变换变为行阶梯形矩阵（行最简形矩阵）
高斯消元法（Gaussian Elimination）
(1)两方程互换，解不变；
(2)一方程乘以非零数k，解不变；
(3)一方程乘以数k加上另一方程，解不变 。
由求解情况可知，解的情况完全由其系数 $a_{ij}$ 和常数项 $b_1,b_2,\cdots,b_n$ 决定。

<kbd>定理</kbd> $n$ 元线性方程组$Ax=b$
(1) 无解 $\iff r(A)<r(A,b)$
(2) 有惟一解 $\iff r(A)=r(A,b)=n$
(3) 有无限多解 $\iff r(A)=r(A,b)<n$

**解的性质和解的结构**
(1) $Ax=0$的任意两个解的线性组合仍是其解，一切解的集合构成向量空间，称为解空间
 当$r(A)=r<n$时，解空间的基础解系含有$n-r$个线性无关的解向量 $η_1,η_2,\cdots,η_{n-r}$，基础解系的一切线性组合$x=k_1η_1+k_2η_2+\cdots+k_{n-r}η_{n-r}$就是 $Ax=0$的通解
 当$r(A)=r=n$时，解空间为零空间，没有基础解系
(2) $Ax=b$的任意两个解之差，必为其导出组$Ax=0$的解
  一切解的集合不构成向量空间
 任一解 $η_0$与其导出组通解 $\bar{x}$ 之和 $x=η_0+\bar{x}$为其通解

**最小二乘解**(least squares solution)：
$x_0$为$Ax=b$的最小二乘解，即$\|b-Ax_0\|=\displaystyle\min_{x\in\R^n}\|b-Ax\| \iff x_0$满足$A^TAx_0=A^Tb$

# 行列式(Determinant)
>行列式的本质是什么？https://www.zhihu.com/question/36966326/answer/70687817

**行列式**(determinant)：行列式引自对线性方程组的求解
一阶行列式：$|a_{11}|=a_{11}$
二阶行列式：$\begin{vmatrix} 
a_{11} & a_{12} \\ 
a_{21} & a_{22} 
\end{vmatrix}=a_{11}a_{22}-a_{12}a_{21}$
三阶行列式：
$\begin{vmatrix} 
a_{11} & a_{12}& a_{13} \\ 
a_{21} & a_{22} & a_{23} \\
a_{31} & a_{32} & a_{33}
\end{vmatrix}
=a_{11}(-1)^{1+1}\begin{vmatrix} a_{22} & a_{23} \\ a_{32} & a_{33} \end{vmatrix}
+a_{12}(-1)^{1+2}\begin{vmatrix} a_{11} & a_{13} \\ a_{31} & a_{33} \end{vmatrix}
+a_{13}(-1)^{1+3}\begin{vmatrix} a_{21} & a_{22} \\ a_{31} & a_{32} \end{vmatrix}$
n阶行列式：
$$\begin{vmatrix}
a_{11}&a_{12}&\cdots&a_{1n} \\
a_{21}&a_{22}&\cdots&a_{2n} \\
\vdots&\vdots&\ddots&\vdots \\
a_{n1}&a_{n2}&\cdots&a_{nn} \\
\end{vmatrix}=\displaystyle\sum_{k=1}^{n}a_{1k}A_{1k}$$其中，划去元$a_{ij}$所在的第$i$行与第$j$列的元，剩下的元不改变原来的顺序所构成的$n-1$阶行列式称为元$a_{ij}$的==余子式==(cofactor)，记为$M_{ij}$，元$a_{ij}$的==代数余子式== (algebraic cofactor) $A_{ij}=(-1)^{i+j}M_{ij}$
> 二三阶行列式计算满足对角线法则，四阶及以上行列式不满足对角线法则。

**n阶行列式按行（列）展开**
$\displaystyle\sum_{k=1}^{n}a_{ik}A_{jk}=\begin{cases}D,(i=j)  \\
0,(i\neq j)\end{cases}\quad 
\displaystyle\sum_{k=1}^{n}a_{ki}A_{kj}=\begin{cases}D,(i=j)  \\
0,(i\neq j)\end{cases}$
其中$A_{ij}$是行列式D中$a_{ij}$的代数余子式。

**行列式的性质**
(1) 行列式与其转置行列式相等：$D=D^T$
(2) 互换行列式两行（列），行列式改变符号：
$A\xrightarrow[(c_i\lrarr c_j)]{r_i\lrarr r_j}B\Rarr | A|=-| B|$
(3) 用数$k$乘行列式等于行列式某一行（列）全部乘数$k$。
$A\xrightarrow[(kc_i)]{kr_i}B\Rarr k| A|=| B|$
由此可得
  a. 行列式某一行（列）的公因子可以提取到外面
  b. 行列式某一行（列）全为零，则行列式值为零
(4) 若行列式中两行（列）对应元素成比例，则行列式值为零
(5) 把行列式的某一行全部$k$倍加到另一行对应元素，行列式值不变
$A\xrightarrow[(c_i+kc_j)]{r_i+kr_j}B\Rarr | A|=| B|$
(6) 行列式的分拆定理，如
$\begin{vmatrix}
b_{11}+c_{11}&b_{12}+c_{12}&b_{13}+c_{13} \\
a_{21}&a_{22}&a_{23} \\
a_{31}&a_{32}&a_{33} \\
\end{vmatrix}=\begin{vmatrix}
b_{11}&b_{12}&b_{13} \\
a_{21}&a_{22}&a_{23} \\
a_{31}&a_{32}&a_{33} \\
\end{vmatrix}+\begin{vmatrix}
c_{11}&c_{12}&c_{13} \\
a_{21}&a_{22}&a_{23} \\
a_{31}&a_{32}&a_{33} \\
\end{vmatrix}$
(7) 上、下三角行列式及主对角行列式等于主对角元素的乘积
副对角线上、下三角行列式及副对角行列式等于副对角元素的乘积$× (-1)^{\frac{n(n-1)}{2}}$
(8) $| -A|=(-1)^n |A|$
(9) $\begin{vmatrix} 
A_{m× m} & C_{m× n} \\ 
O &B_{n× n}
\end{vmatrix}=|A|×| B|$
(10) $\begin{vmatrix} 
A_1 & &  & \\ 
  &A_2&  & \\
 & & \ddots& \\
  & &  & A_s
\end{vmatrix}=|A_1||A_2|\cdots|A_s|$，其中$A_1,A_2,\cdots,A_s$都是方阵
(11) $|AB|=|A|×| B|$，其中$A,B$为同阶方阵。

**高阶行列式的计算**
(1) 利用初等变换化为三角行列式
(2) 降价展开

**范德蒙行列式**(Vandermonde determinant)
$D_n=\begin{vmatrix} 
1 & 1& \cdots &1 \\ 
 a_1 &a_2&\cdots  &a_n \\
 a_1^2 &a_2^2&\cdots  &a_n^2  \\
\vdots &\vdots&\vdots  &\vdots \\
  a_1^{n-1} &a_2^{n-1}&\cdots  &a_n^{n-1} 
\end{vmatrix}=\displaystyle\prod_{1⩽ i<j⩽ n}(a_j-a_i)$

**克拉默法则**(Cramer rule)：如果n元线性方程组$$
\begin{cases} 
a_{11}x_1+a_{12}x_2+\cdots+a_{1n}x_n=b_1 \\ 
a_{21}x_1+a_{22}x_2+\cdots+a_{2n}x_n=b_2 \\
\cdots \\
a_{n1}x_1+a_{n2}x_2+\cdots+a_{nn}x_n=b_n
\end{cases} 
$$的系数行列式$D\neq0$，那么他有唯一解$$x_j=\frac{D_j}{D},(j=1,2,\cdots,n)$$其中$D_j$是把系数行列式$D$中的第$j$列换成常数项 $b_1,b_2,\cdots,b_n$ 所得的行列式

# n维向量(N-dimensional Vector)
## 向量的概念和运算
**n维向量**(N-dimensional vector)：n个有次序的数 $a_1,a_2,\cdots,a_n$ 所组成的数组称为n维向量。
行向量 $\mathbf a=(a_1,a_2,\cdots,a_n)$，列向量 $\mathbf{a}=\begin{pmatrix}a_1\\ a_2\\ \cdots \\ a_n\end{pmatrix}$
分量全为实数的向量称为实向量；分量全为复数的向量称为复向量；
每个分量都是零的向量称为零向量，记作 $\mathbf{0}$；
**向量的线性运算及性质**：向量的线性运算及性质同行（列）矩阵线性运算一致。
**向量组**：若干个同维数的列（行）向量所构成的集合叫做==向量组==(vector group)；含有限个向量的有序向量组与矩阵一一对应

## 向量组的线性表示与线性相关(Linear representations and linearly dependence)
**向量的线性组合与线性表示**：设向量组 $A: α_1,α_2,\cdots,α_r$ ，向量 $β=k_1α_1+k_2α_2+\cdots+k_nα_r$ 则$β$称为向量组的一个==线性组合==(linear combination)，或称$β$可由向量组$A$ ==线性表示==(linear representations)，$k_1,k_2,\cdots,k_r$称为组合系数(combination coefficient)。
线性表示：$β=k_1α_1+k_2α_2+\cdots+k_nα_r$ 
$\iff$线性方程组$Ax=β$ 有解 $x=(k_1,k_2,\cdots,k_r)^T$
$\iff r(A)=r(A,β)$
**向量组的线性表示与等价**：设两向量组$A: α_1,α_2,\cdots,α_r;\  B: β_1,β_2,\cdots,β_s$
若向量组 $B$中每一个向量皆可由向量组 $A$线性表示，即 $B=AK_{r× s}$ 则称向量组$B$可以由向量组 $A$ ==线性表示==。若向量组 $A$与向量组 $B$ 能相互线性表示，则称这两个向量组==等价==(equivalence)。
<kbd>定理</kbd>：向量组 $B$可以由向量组 $A$线性表示
$\iff$矩阵方程$AX=B$有解
$\iff r(A)=r(A,B)$
$\implies r(B)⩽ r(A)$
<kbd>推论</kbd>：向量组B与向量组 A等价
$\iff$矩阵方程$AX=B$与$BY=A$同时有解
$\iff r(A)=r(B)=r(A,B)$

**向量组线性相关与线性无关**：向量组 $A: α_1,α_2,\cdots,α_r$，如果存在不全为零的数$k_1,k_2,\cdots,k_r$，使得$k_1α_1+k_2α_2+\cdots+k_nα_r=0$则称向量组A ==线性相关==(linearly dependence)。否则向量组A ==线性无关==(Linear Independence)。

**向量组线性相关的判别**
<kbd>定理</kbd>：向量组 $A: α_1,α_2,\cdots,α_m$线性相关
$\iff m$元线性方程组 $Ax=0$ 有非零解 
$\iff r(A)<m$
(1) 向量组线性相关$\iff$向量组中至少存在一个向量可以由其余向量线性表示
 向量组线性无关$\iff$向量组中任意一个向量都不能由其余向量线性表示
(2) 若部分向量组线性相关，则整体向量组线性相关；若整体向量组线性无关，则它的任何部分组也线性无关
(3) 两个向量$α$与$β$线性相关（无关）$\iff α$与$β$的分量对应成比例（不成比例）
(4) 向量个数多余$n$的$n$维向量组必线性相关；含零向量的向量组必线性相关。
(5) 设$α_1,α_2,\cdots,α_m$线性无关，$α_1,α_2,\cdots,α_m,β$线性相关，则$β$可由$α_1,α_2,\cdots,α_m$线性表示
(6) 设$β$可由$α_1,α_2,\cdots,α_m$线性表示，则表示法唯一的充分必要条件是$α_1,α_2,\cdots,α_m$线性无关

## 向量组的秩(rank)
**定义**：设向量组 $A$，在$A$选取$r$个向量$α_1,α_2,\cdots,α_r$满足：
(1) 向量组$A_0: α_1,α_2,\cdots,α_r$线性无关
(2) 向量组$A$中任取$r+1$个向量（若存在）都线性相关
则称$A_0$为==最大（线性）无关组==(Maximum linearly independent group)，所含的向量数$r$叫做向量组$A$的==秩==，记为$r_A=r$
注：
(1) 一个向量组的最大无关组是向量组中所含向量个数最多的线性无关的子组之一.
(2)一个向量组的最大无关组不一定是惟一的．
(3) 一个向量组与它的最大无关组是等价的

<kbd>定理</kbd>：矩阵的秩等于它的列向量组的秩，也等于它的行向量组的秩.

## 向量空间的概念和性质(Vector spaces)
**向量空间**(Vector spaces)： 设 $V$ 为 $n$ 维向量的非空集合，$F$ 是一个数域，若 $V$ 对于向量的加法和数乘两种运算封闭，那么称集合 $V$ 为数域 $F$ 上的==向量空间==。所谓封闭是指
(1) $∀ \mathbf{α,β}\in V,\mathbf{α+β}\in V$
(2) $∀ \mathbf{α}\in V, λ\in F, λ\mathbf{α}\in V$

示例
(1) $n$维向量的全体$\R^n$为向量空间：$\R^n=\{(x_1,x_2,\cdots,x_n)^T|x_1,x_2,\cdots,x_n\in\R\}$
(2) 由向量组 $a_1,a_2,\cdots,a_m$ 所生成的向量空间为：$L=\{x=λ_1a_1+λ_2a_2+\cdots+λ_ma_m|λ_1,λ_2,\cdots,λ_m\in\R\}$
(3) n 元齐次线性方程组的解集$\{x=(x_1,x_2,\cdots,x_n)^T\in\R^n|Ax=0\}$是向量空间， 齐次线性方程组的解空间

等价的向量组生成相同的向量空间。


**子空间**(subspaces)： 设有线性空间$V_1,V_2$，若$V_1⊂e V_2$，对于 $V_1$ 中
所定义的加法及乘数两种运算是封闭的，则称$V_1$是$V_2$的==子空间==(subspace)。
任何由 $n$ 维向量组成的线性空间都是 $\R^n$的子空间。


**基和维数**(basis and dimension)： 设$V$ 为数域 $F$ 上的向量空间，向量$\mathbf{α_1,α_2,\cdots,α_r}$为 $V$ 中的 $r$ 个向量，并且满足
(1) $\mathbf{α_1,α_2,\cdots,α_r}$线性无关
(2) $V$ 中的每个向量都可由 $\mathbf{α_1,α_2,\cdots,α_r}$ 线性表示
则称向量组$\mathbf{α_1,α_2,\cdots,α_r}$为线性空间 $V$ 的一个==基==，而基中所含向量的个数 $r$，称为向量空间 $V$的==维数==，称$V$为$r$维向量空间，记为 $\dim V=r$

$n$维单位坐标向量组 $\mathbf{e_1},\mathbf{e_2},\cdots,\mathbf{e_n}$ 是$\R^n$的自然基，$\dim \R^n=n$
$\mathbf{e_1}=\begin{pmatrix}1\\0\\\vdots\\0\end{pmatrix},\mathbf{e_2}=\begin{pmatrix}0\\1\\\vdots\\0\end{pmatrix},\cdots,\mathbf{e_n}=\begin{pmatrix}0\\0\\\vdots\\1\end{pmatrix}$
$\R^n$中任意$n$个线性无关的 $n$维向量都是 $\R^n$的一组基。

向量组 $A: \mathbf{a_1},\mathbf{a_2},\cdots,\mathbf{a_m}$所生成的向量空间
$L=\{\mathbf{x}=λ_1\mathbf{a_1}+λ_2\mathbf{a_2}+\cdots+λ_m\mathbf{a_m}|λ_1,λ_2,\cdots,λ_m\in\R\}$
若$\mathbf{a_1},\mathbf{a_2},\cdots,\mathbf{a_m}$线性无关，则它是$L$的一个基；
若$\mathbf{a_1},\mathbf{a_2},\cdots,\mathbf{a_m}$线性相关，他的最大无关组 $A_0:\mathbf{a_1},\mathbf{a_2},\cdots,\mathbf{a_r}$为$L$的一个基，$\dim L=r$

**坐标**(coordinate)：如果在 向量空间$V$中选定一组基 $\mathbf{a_1},\mathbf{a_2},\cdots,\mathbf{a_r}$，那么空间中任意一向量可唯一表示为 $\mathbf{x}=λ_1\mathbf{a_1}+λ_2\mathbf{a_2}+\cdots+λ_r\mathbf{a_r}$，其中数组$λ_1,λ_2,\cdots,λ_r$称为向量$\mathbf{x}$在基$\mathbf{a_1},\mathbf{a_2},\cdots,\mathbf{a_r}$中的坐标。并记作 $\mathbf{x}=(λ_1,λ_2,\cdots,λ_r)^T$
## 基变换与坐标变换(Change of bases and coordinate transformation)
**基变换(change of bases)公式**：设$\mathbf{α_1,α_2,\cdots,α_n}$及$\mathbf{β_1,β_2,\cdots,β_n}$是$V_n$的两组基，他们之间的关系式$$(\mathbf{β_1,β_2,\cdots,β_n})=(\mathbf{α_1,α_2,\cdots,α_n})P$$称为由$\mathbf{α_1,α_2,\cdots,α_n}$到$\mathbf{β_1,β_2,\cdots,β_n}$的==基变换公式==，$n$维可逆矩阵 $P$ 为由基$\mathbf{α_1,α_2,\cdots,α_n}$到基$\mathbf{β_1,β_2,\cdots,β_n}$的==过渡矩阵==(transition matrix)，显然 $P^{-1}$ 为由基$\mathbf{β_1,β_2,\cdots,β_n}$到基$\mathbf{α_1,α_2,\cdots,α_n}$的==过渡矩阵==。
**坐标变换**(coordinate transformation)：设 $\mathbf{a}\in V_n$，它的基$\mathbf{α_1,α_2,\cdots,α_n}$与基$\mathbf{β_1,β_2,\cdots,β_n}$下的坐标分别为$(x_1,x_2,\cdots,x_n)^T$与$(x'_1,x'_2,\cdots,x'_n)^T$，则有==坐标变换公式==$$\begin{pmatrix} x_1  \\ x_2 \\ \vdots\\ x_n \end{pmatrix}
=P\begin{pmatrix} x'_1  \\ x'_2 \\ \vdots\\ x'_n \end{pmatrix}\ 或\ 
\begin{pmatrix} x'_1  \\ x'_2 \\ \vdots\\ x'_n \end{pmatrix}
=P^{-1}\begin{pmatrix} x_1  \\ x_2 \\ \vdots\\ x_n \end{pmatrix}$$


## 向量的内积、长度与正交性
**内积**(inner products)：设$n$维实向量 $\mathbf{x}=(x_1,x_2,\cdots,x_n),\mathbf{y}=(y_1,y_2,\cdots,y_n)$，定义内积为$$\mathbf{[x,y]}=x_1y_1+x_2y_2+\cdots+x_ny_n=\mathbf{xy}^T$$
性质|表达式
:---|:---
对称性|$\mathbf{[x,y]}=\mathbf{[y,x]}$
线性|$\mathbf{[x+y,z]=[x,z]+[y,z]} \\ [k\mathbf{x,y}]=k\mathbf{[x,y]}$
正定性|$\mathbf{[x,x]}⩾ 0$

**长度（模或范数）**：实数 $\|\mathbf{x}\|=\sqrt{\mathbf{[x,x]}}=\sqrt{x_1^2+x_2^2+\cdots+x_n^2}$
长度为1的向量称为单位向量。
性质|表达式
:---|:---
正定性|$\Vert\mathbf{x}\Vert ⩾ 0$
齐次性|$\Vert k\mathbf{x}\Vert=\vert k\vert \cdot\Vert \mathbf{x}\Vert$
三角不等式|$\Vert\mathbf{x+y}\Vert⩽ \Vert \mathbf{x}\Vert+\Vert \mathbf{y}\Vert$
柯西－施瓦兹不等式|$\mathbf{[x,y]}^2⩽ \mathbf{[x,x]}\mathbf{[y,y]}$

**向量之间的夹角**：$\mathbf{x}$与$\mathbf{y}$的夹角$θ=\arccos\dfrac{\mathbf{[x,y]}}{\|\mathbf{x}\|\|\mathbf{y}\|}, (0 ⩽θ ⩽π)$

**正交**(orthogonal)：若$\mathbf{[x,y]}=0$，则称向量$\mathbf{x,y}$正交
(1) 若向量组中的向量两两正交，且均为非零向量，则这个向量组称为==正交（向量）组==。正交向量组线性无关。
(2) 由单位向量组成的正交组称为==规范正交组==。如
$e_1=(1,0,0)^T,e_2=(0,1,0)^T,e_3=(0,0,1)^T$
(3) 若正交向量组为向量空间$V$上的一个基，则称为向量空间上的一个==正交基==(orthogonal basis)
(4) 若规范正交组为向量空间$V$上的一个基，则称为向量空间上的一个==规范正交基==(orthonormal basis)


## 向量组的正交化(orthogonalization)
 若$\mathbf{e_1},\mathbf{e_2},\cdots,\mathbf{e_r}$ 是向量空间$V$的一个规范正交基
 $∀\mathbf{x}\in V,\mathbf{x}=λ_1\mathbf{e_1}+λ_2\mathbf{e_2}+\cdots+λ_r\mathbf{e_r}\implies λ_i=\mathbf{e_i}^T\mathbf{x}=[\mathbf{x,e_i}]$
 这就是向量在规范正交基中的坐标的计算公式，利用这个公式能方便地求得向量的坐标.
 
**施密特正交化法**(Schimidt orthogonalization)
设$\mathbf{α_1,α_2,\cdots,α_r}$是向量空间$Ｖ$的一个基，寻找向量空间的一个规范正交基。也就是要找一组两两正交的单位向量 $ξ_1,ξ_2,\cdots,ξ_r$与$\mathbf{α_1,α_2,\cdots,α_r}$等价。
此问题称为把基 $\mathbf{α_1,α_2,\cdots,α_r}$ ==规范正交化==(orthonormalization)
(1) 正交化
令 $β_1=α_1,β_2=α_2-\dfrac{[β_1,α_2]}{[β_1,β_1]}β_1,β_3=α_3-\dfrac{[β_1,α_3]}{[β_1,β_1]}β_1-\dfrac{[β_2,α_3]}{[β_2,β_2]}β_2,$
$\cdots,β_r=α_r-\displaystyle\sum_{k=1}^{r-1}\dfrac{[β_k,α_r]}{[β_k,β_k]}β_k$
则 $\mathbf{β_1,β_2,\cdots,β_r}$ 正交，且与$\mathbf{α_1,α_2,\cdots,α_r}$等价
(2) 规范化
令$ξ_1=\dfrac{β_1}{\|β_1\|},ξ_2=\dfrac{β_2}{\|β_2\|},\cdots,ξ_r=\dfrac{β_r}{\|β_r\|}$
就得到$V$的一个规范正交基

## 正交矩阵与正交变换(Orthogonal matrix and orthogonal transformation)
**正交矩阵**(orthogonal matrix)：如果n阶矩阵A满足$A^TA=E$ (即$A^{-1}=A^T$)，那么称A为正交矩阵，简称正交阵。

**正交矩阵的性质**：$A$ 为正交阵
$\iff A$ 的行(列)向量组为规范正交向量组
$\iff A^T$为正交阵
$\iff A^{-1}$为正交阵
$\implies |A|^2=1$为正交阵
$A,B$ 为正交阵$\implies AB$ 为正交阵

**正交变换**(orthogonal transformation)：若为 $P$正交矩阵，则线性变换 $\mathbf{y}=P\mathbf{x}$称为正交变换。

$\|\mathbf{y}\|=\sqrt{[\mathbf{y,y}]}=\sqrt{\mathbf{y^Ty}} \\
=\sqrt{\mathbf{x^TP^TPx}} \\
=\sqrt{\mathbf{x^Tx}}=\sqrt{[\mathbf{x,x}]}=\|\mathbf{x}\|$
注：经正交变换后向量的长度保持不变，内积保持不变，从而夹角保持不变


# 相似矩阵(Similar Matrix)
## 矩阵的特征值和特征向量(Eigenvalues and eigenvectors)
**定义**
(1) 设$A$是$n$阶矩阵，如果数$λ$和$n$维非零向量$\mathbf{x}$满足$$A\mathbf{x}=λ \mathbf{x}$$,则这样的数$λ$称为矩阵$A$的==特征值==(eigenvalues)，向量$\mathbf{x}$称为$A$的对应于特征值$λ$的==特征向量==(eigenvectors)。
$A\mathbf{x}=λ \mathbf{x} \iff (A-λ E)\mathbf{x}=0$有非零解$\iff |A-λ E|=0$
(2) 以$λ$为未知数的一元n次方程$|A-λ E|=0$称为A的==特征方程==(characteristic equation)。矩阵A的特征值就是它的特征方程的根.
(3) $f(λ)=|A-λ E|$称为矩阵Ａ的==特征多项式==(characteristic polynomial)

**特征值与特征向量的性质**：
n 阶矩阵$A=(a_{ij})$ 在复数范围内有n个特征值，设特征值为$λ_1,λ_2,\cdots,λ_n$，则
$\begin{cases}λ_1+λ_2+\cdots+λ_n=\mathrm{A}=a_{11}+a_{22}+\cdots+a_{nn} \\
λ_1λ_2\cdotsλ_n=|A|
\end{cases}$

设 $λ$ 是方阵 $A$ 的特征值，则
$\implies$ $λ$ 是 $A^T$的特征值
$\implies$ 当 $A$可逆时，$λ^{-1}$是 $A^{-1}$ 的特征值.
$\implies$ $ϕ(λ)$是$ϕ(A)$的特征值
$\implies$ 属于不同特征值的特征向量是线性无关的
$\implies$ 对应于不同特征值的线性无关的特征向量组，合起来仍是线性无关的

**特征值与特征向量的求法**
步骤： (1) 写出A的特征多项式 $|A-λ E|$
(2). 解特征方程得n个特征值 $λ_1,λ_2,\cdots,λ_n$
(3). 对每个特征值 $λ_i$，求 $(A-λ_i E)\mathbf{x}=0$ 的基础解系，写出其全体非零线性组合，即得 $λ_i$ 的全体特征向量


## 相似矩阵(Similar matrix)
**定义**：设 $A, B$ 都是 $n$ 阶矩阵，若存在可逆阵 $P$ ,使得$P^{-1}AP=B$，则称A与B==相似==，记作$A∼ B$，对 A 进行运算 $P^{-1}AP$ 称为对 A进行==相似变换==(similarity transformation)。


**性质**：
(1) 相似关系为等价关系
反身性：$A∼ A$ 
对称性：$A∼ B\implies B∼ A$
传递性：$A∼ B,B∼ C\implies A∼ C$
(2) $A∼ B$
$\implies ϕ(A)∼ ϕ(B)$，其中$ϕ$是一个多项式
$\implies r(A)=r(B)且|A|=|B|$
$\implies |A-λ E|= |B-λ E|$，特征多项式相同
$\implies A$与 $B$ 的特征值相同
$\implies \mathrm{tr} A= \mathrm{tr} B$ 迹(trace)相等(主对角线上元素的和)

**矩阵的相似对角化**(Similar diagonalization)：若 $A_{n× n}∼Λ=\mathrm{diag}(λ_1,λ_2,\cdots,λ_n)=P^{-1}AP$ ，则称 $A$ 能==相似对角化==，对角线就是 $A$ 的 $n$ 个特征值。
假设已找到可逆阵 $P=(p_1,p_2,\cdots,p_n)$，
由 $P^{-1}AP=Λ \implies AP=PΛ\implies Ap_i=λ_ip_i(i=1,2,\cdots,n)$
可见 $λ_i$ 是$A$的特征值，而 $P$ 的列向量 $p_i$ 就是 $A$ 的对应于特征值 $λ_i$ 的特征向量。

<kbd>定理</kbd> 矩阵$A_{n× n}$能相似对角化
$\iff A$有n个线性无关的特征向量
$\iff$ 对于$A$的每个$n_i$重特征值$λ_i$，特征矩阵$λ_iE-A$的秩为$n-n_i$
$\impliedby A$有n个互不相同的特征值

## 对称矩阵的对角化(Diagonalization of symmetric matrix)
**对称矩阵特征值、特征向量的性质**：设 $A_{n× n}$ 为对称阵，特征值为$λ_1,λ_2,\cdots,λ_n$
(1) $λ_1,λ_2,\cdots,λ_n \in \R$
(2) 设 $λ_1,λ_2$ 是对称矩阵 $A$ 的两个特征值，$p_1,p_2$ 是对应的特征向量.，若 $λ_1\neq λ_2$ 则 $p_1,p_2$ 正交，即 $p_1^Tp_2=0$
(3) 任意对称阵$A$，必有正交阵 $P$，使 $P^{-1}AP=P^TAP=\mathrm{diag}(λ_1,λ_2,\cdots,λ_n)$

**对称矩阵的正交对角化步骤**：设 $A_{n× n}$ 为对称阵
(1) 求出 $A$ 的全部特征值，设为 $λ_1,λ_2,\cdots,λ_s$（两两不同），每个特征值分别有$l_1,l_2,\cdots,l_s$重（$l_1+l_2+\cdots+l_s=n$）
(2) 解 $(A-λ_iE)x=0$，求 $A$ 的 $l_i$ 个线性无关的  $λ_i$ 特征向量
(3) 各组内部正交化、单位化
(4) 将各组向量并排得正交阵 $P_{n× n}$，则$P^{-1}AP=P^TAP=Λ=\mathrm{diag}(λ_1,λ_2,\cdots,λ_n)$

# 二次型(Quadratic Form)

## 二次型及其标准型(Quadratic form and its standard form)
**概念**：n元二次齐次多项式 $f(x_1,x_2,\cdots,x_n)=\displaystyle\sum_{i=1}^{n}a_{ii}x_i^2+\displaystyle\sum_{1⩽ i<j⩽ n}2a_{ij}x_ix_j$
叫做==二次型==(quadratic form)，可表示为矩阵形式 $f=\mathbf{x}^TA\mathbf{x}$，其中 $\mathbf{x}=(x_1,x_2,\cdots,x_n)^T,A$为$n$阶对称矩阵；（二次型$f \lrarr$实对称矩阵）
只含有平方项的二次型称为二次型的==标准形==(standard form)；（标准型$\lrarr$对角矩阵）
系数全为"+1"或"-1"的标准型叫做（二次型）的==规范型==(gauge form)；
系数全为实数的二次型叫做==实二次型==。

二次型可通过满秩（或可逆）线性变换化为标准型


**用正交变换将二次型标准化**：具有保持几何形状不变的优点
<kbd>定理</kbd>：任意二次型 $f=\displaystyle\sum_{i,j=1}^{n}a_{ij}x_ix_j(a_{ij}=a_{ji})$，总有正交变换 $x=Py$ 化二次型为标准型 $f=λ_1y_1^2+λ_2y_2^2+\cdots+λ_ny_n^2$，其中$λ_1,λ_2,\cdots,λ_n$是$f$的矩阵$A=(a_{ij})$ 的特征值。
<kbd>推论</kbd>：任意$n$元二次型 $f=\mathbf{x}^TA\mathbf{x} (A^T=A)$，总有可逆变换 $x=Cz$，使 $f(Cz)$ 为规范型。
具体步骤如下：
(1) 将二次型表成矩阵形式 $f=\mathbf{x}^TA\mathbf{x}$，求出 $A$
(2) 求出 $A$的所有特征值$λ_1,λ_2,\cdots,λ_n$
(3) 求出对应于特征值的特征向量 $ξ_1,ξ_2,\cdots,ξ_n$
(4) 将特征向量$ξ_1,ξ_2,\cdots,ξ_n$正交化、单位化，得 $P=(p_1,p_2,\cdots,p_n)$
(5) 作正交变换 $x=Py$ 化二次型为标准型 $f=λ_1y_1^2+λ_2y_2^2+\cdots+λ_ny_n^2$

**拉格朗日配方法化二次型为标准型**
主要步骤如下：
(1) 设二次型含有$x_i$的平方项，则把含有$x_i$的项集中，然后按$x_i$配成平方项，对其他变量也做类似处理，知道都配成平方项为止。
(2) 若在二次型中没有平方项，但 $a_{ij}\neq 0(i\neq j)$ ，则做可逆线性变换 $x_i=y_i-y_j, x_j=y_i+y_j, x_k= y_k(k\neq i,j)$，化二次型为含平方项的二次型，再按(1) 中的方法配方。

## 矩阵的合同与惯性定理(Contract and inertia theorem of matrix )
**合同矩阵**(congruent matrices;cogradient matrices)：设 $A$ 和 $B$ 是 $n$ 阶矩阵，若有可逆矩阵 $C$ ，使 $B=C^TAC$，则称矩阵 $A$ 与 $B$ 合同，记为$A≃ B$
**合同矩阵的性质**
(1). 合同关系为等价关系
反身性：$A≃ A$ 
对称性：$A≃ B\implies B≃ A$
传递性：$A≃ B,B≃ C\implies A≃ C$
(2). 与对称矩阵合同的矩阵也是对称矩阵
(3). 合同矩阵具有相同的秩.

<kbd>惯性定理</kbd>：设二次型$f=\mathbf{x}^TA\mathbf{x}$的秩为$r$，有两个可逆变换 $x=Cy$及 $x=Pz$，
使 $f=k_1y_1^2+k_2y_2^2+\cdots+k_ry_r^2\quad(k_i\neq0)$
及 $f=λ_1z_1^2+λ_2z_2^2+\cdots+λ_rz_r^2\quad(λ_i\neq0)$
则 $k_1,k_2,\cdots,k_r$中正数得个数与$λ_1,λ_2,\cdots,λ_r$中正数得个数相等。

二次型的标准形中，
负系数的个数称为二次型的==负惯性指数==(Negative inertia index)
正系数的个数称为二次型的==正惯性指数==(Positive inertia index)
若二次型 $f$ 的正惯性指数为 $p$ ，秩为 $r$ ，
则 $f$ 的规范形便可确定为 $f=y_1^2+y_2^2+\cdots+y_p^2-y_{p+1}^2-\cdots-y_r^2$

## 正定二次型(Positive definite quadratic form)
**定义**：设二次型$f(\mathbf{x})=\mathbf{x}^TA\mathbf{x}$，如果对任何 $\mathbf{x}\neq\mathbf{0}$ 都有 $f(\mathbf{x})>0$（显然$f(\mathbf{0})=0$），则称 $f$ 为==正定二次型==(positive definite quadratic form)，并称对称阵 $A$ 是==正定矩阵==(positive definite matrix)。
非退化线性替换不改变二次型的正定性。

**正定矩阵的判别法**：二次型$f(\mathbf{x})=\mathbf{x}^TA\mathbf{x}$ 正定，其中$\mathbf{x}=(x_1,x_2,\cdots,x_n)^T$
$\iff ∀\mathbf{x}\neq\mathbf{0},\mathbf{x}^TA\mathbf{x}>0$
$\iff A$的特征值全大于零
$\iff f$的正惯性指数为 $n$
$\iff A$与单位矩阵合同
$\iff$存在可逆矩阵$C$，使得 $A=CC^T$
$\iff A$的各阶顺序主子式均大于零
$D_1=a_{11}>0,
D_2=\begin{vmatrix}
a_{11}&a_{12} \\
a_{21}&a_{22} 
\end{vmatrix}>0,\cdots,D_n=|A|>0$


# 线性变换(Linear Transformation)
## 线性空间的定义与性质
**线性空间**(linear space)： 设 $V$ 为 非空集合，$\R$ 为实数域，若 $V$ 对于向量的加法和数乘两种运算封闭，且满足八条运算规律，那么称集合 $V$ 为实数域 $\R$ 上的==线性空间==。封闭是指
(1) $∀ \mathbf{α,β}\in V,∃! \mathbf{γ=α+β}\in V$
(2) $∀ \mathbf{α}\in V, λ\in \R, ∃! \mathbf{δ}=λ\mathbf{α}\in V$
八条运算规律|$α,β,γ\in V,λ,μ\in\R$
:---|:---|
$(\mathbf{i})\ α+β=β+α$ |$(\mathbf{ii})\ (α+β)+γ=α+(β+γ)$ 
$(\mathbf{iii})\ ∃ Θ\in V,∀ α\in V,α+Θ=α$ (零元素)|$(\mathbf{iv})\ ∀ α\in V,∃ β\in V, α+β=Θ$ (负元素)
$(\mathbf{v})\ 1α=α$|$(\mathbf{vi})\ (λμ)α=λ(μα)$
$(\mathbf{vii})\ (λ+μ)α=λα+μα$|$(\mathbf{viii})\ λ(α+β)=λα+λβ$
说明：
(1) 满足八条运算规律的加法与数乘运算，就称为线性运算，
凡定义了线性运算的集合就称为线性空间，元 素就称为向量.
(2) 向量不一定是有序数组.
(3) 线性空间的运算不一定是有序数组的加法及数乘运算.

注意：
线性空间的概念是集合与运算二者的结合。同一个集合，若 定义两种不同的线性运算，就构成不同的线性空间； 若定义的运算不是线性运算，就不能构成线性空间。

**线性空间实例**
向量类：
(1).全体 n 维向量 $\R$ 在向量的加法与数乘下
(2).向量空间
(3).齐次线性方程组的解空间
 矩阵类：
(1).全体 $m× n$ 阵在矩阵加法和数乘下
(2).全体n阶方阵
(3).全体n阶对称阵
(4).全体n阶对角阵
多项式类：次数不超过 n 的实一元多项式的全体 
$P[x]_n=\{p=a_nx_n+\cdots+a_1x+a_0|a_n,\cdots,a_1,a_0\in\R\}$，
对于通常的多项式的加法和数乘多项式的乘法.
函数类：正弦函数的集合 
$S[x]=\{s=A\sin(x+B)|A,B\in\R\}$，
对于通常的函数加法和数乘函数的乘法.

**线性空间的基本性质**
(1) 零元素 $Θ$ 是惟一的
(2) 任一向量的负向量是惟一的，$α$ 的负向量记作 $-α$
(3) $0α=Θ,(-1)α=-α,λΘ=Θ$
(4) $λα=Θ\implies λ=0或α=Θ$

**子空间**(subspace)：设 $V$ 是一个线性空间，$L$ 是 $V$ 的一个非空子集，如果 $L$对于$V$ 中所定义的加法和数乘两种运算也构成一个线性空间，则称 $L$ 为$V$ 的子空间.
<kbd>定理</kbd> 线性空间$V$ 的非空子集$L$ 构成子空间$\iff  L$ 对于$V$ 中的线性运算封闭

**基、维数和坐标**：定义同向量空间

**同构**(isomorphism)：设U 与V 是两个线性空间，如 果它们的向量之间有一一对应关系，且 这个对应关系保持线性组合的对应，就说线性空间U 与V 同构，记作 $U\cong V$

设在n 维线性空间 $V_n$ 中取定一个基 $α_1,α_2,\cdots,α_n$ ，则$∀α,β\in V_n$
$α\lrarr (x_1,x_2,\cdots,x_n)^T,β\lrarr (y_1,y_2,\cdots,y_n)^T$
这个一一对应关系保持线性组合的对应：
(1) $α+β\lrarr (x_1,x_2,\cdots,x_n)^T+ (y_1,y_2,\cdots,y_n)^T$
(2) $λα\lrarr λ(x_1,x_2,\cdots,x_n)^T$
称 $V_n$与 $\R^n$ 同构，记作 $V_n\cong\R^n$

任何n 维线性空间都与$\R^n$ 同构，即维数相等的线性空间都同构。线性空间的结构完全被它的维数所决定。

**基变换与坐标变换**：同向量空间

==线性空间 $p[x]_3$实例==
(1) 取一个基$p_1=1,p_2=x,p_3=x^2,p_4=x^3$，求坐标
任一不超过3 次的多项式 $p=a_3x^3+a_2x^2+a_1x+a_0$ 
都可表示为 $p=a_0p_1+a_1p_2+a_2p_3+a_3p_4$
因此 $p$ 在这个基中的坐标为$(a_0,a_1,a_2,a_3)^T$
(2) 任取两个基，求坐标变换公式
$\begin{array}{c:c}
a_1=x^3+2x^2-x & b_1=2x^3+x^2+1 \\
a_2=x^3-x^2+x+1 & b_2=x^2+2x+2 \\
a_3=-x^3+2x^2+x+1 & b_3=-2x^3+x^2+x+2 \\
a_4=-x^3-x^2+1 & b_4=x^3+3x^2+x+2 \\
\end{array}$
将 $b_1,b_2,b_3,b_4$ 用 $a_1,a_2,a_3,a_4$ 表示
$(a_1,a_2,a_3,a_4)=(x^3,x^2,x,1)A ,\\
(b_1,b_2,b_3,b_4)=(x^3,x^2,x,1)B$，求得

$A=\begin{pmatrix}
1&1&-1&-1 \\
2&-1&2&-1 \\
-1&1&1&0 \\
0&1&1&1 \\
\end{pmatrix},\ 
B=\begin{pmatrix}
2&0&-2&1 \\
1&1&1&3 \\
0&2&1&1 \\
1&2&2&2 \\
\end{pmatrix}$

$(b_1,b_2,b_3,b_4)=(a_1,a_2,a_3,a_4)A^{-1}B$

故坐标变换公式为 $\begin{pmatrix}
x_1' \\
x_2' \\
x_3' \\
x_4' \\
\end{pmatrix}=B^{-1}A\begin{pmatrix}
x_1 \\
x_2 \\
x_3 \\
x_4 \\
\end{pmatrix}$

用矩阵的初等行变换求 $B^{-1}A$
$(B,A)∼(E,B^{-1}A)$

## 线性变换(Linear transformation)
**变换**(transformation)：设$A,B$是两个非空集合，如果对于$A$中任一元素$α$，按某法则总有$B$中唯一确定的元素$β$与之对应，则称这个对应法则为从集合$A$到集合$B$的变换（或映射），若记此法则为$T$，则上述变换可表示为：$β=T(α)$或$β=Tα$，并称$α$为源，$β$为像，$A$为源集，像的全体组成的集合称为像集。

**线性变换**(linear transformation)：设$V_n,U_m$分别为$n$维和$m$维线性空间，线性变换 $T: V_n\to U_m$满足
(1) $∀ α,β\in V_n,T(α+β)=T(α)+T(β)$
(2) $∀ α\in V_n,k\in\R,T(kα)=kT(α)$
特别的，从$V_n$到自身的线性变换叫做$V_n$中的线性变换。
==实例==：在线性空间 $p[x]_3$ 中
任取 $p=a_3x^3+a_2x^2+a_1x+a_0 \\
q=b_3x^3+b_2x^2+b_1x+b_0$
微分运算$D$ 是一个线性变换：$Dp=3a_3x^2+2a_2x+a_1;\ Dq=3b_3x^2+2b_2x+b_1$
$D(p+q)=Dp+Dq\\
D(λ p)=λ Dp$


**线性变换的基本性质**
(1) $T(Θ)=Θ, T(-α)=-T(α)$
(2) 若 $β=k_1α_1+k_2α_2+\cdots+k_mα_m$，则$T(β)=k_1T(α_1)+k_2T(α_2)+\cdots+k_mT(α_m)$
(4) 线性变换$T$ 的像集 $T(V_n)$ 是一个线性空间，称为线性变换 $T$ 的==像空间==(image space)
(5) 集合 $\{α|α\in V_n,T(α)=Θ\}$ 也是一个线性空间，称为线性变换 $T$ 的==核==(kernel)


**线性变换的矩阵表示**：设线性空间$V_n$的一组基为$\mathbf{α_1,α_2,\cdots,α_n}$，此基的像分别为
$T(α_1)=P_{11}α_1+P_{12}α_2+\cdots+P_{1n}α_n \\
T(α_2)=P_{21}α_1+P_{22}α_2+\cdots+P_{2n}α_n \\
\cdots \\
T(α_n)=P_{n1}α_1+P_{n2}α_2+\cdots+P_{nn}α_n$
即 $(T(α_1),T(α_2),\cdots,T(α_n))=(\mathbf{α_1,α_2,\cdots,α_n})P$
此处的$P=\begin{pmatrix}
P_{11}&P_{12}&\cdots&P_{1n} \\
P_{21}&P_{22}&\cdots&p_{2n} \\
\vdots&\vdots&\ddots&\vdots \\
p_{n1}&p_{n2}&\cdots&p_{nn} \\
\end{pmatrix}$
称为线性空间$V_n$中线性变换$T$在基$\mathbf{α_1,α_2,\cdots,α_n}$下的矩阵

**同一线性变换在不同基下的矩阵的关系**
<kbd>定理</kbd> ：设线性空间$V_n$取定两个基 $α_1,α_2,\cdots,α_n;β_1,β_2,\cdots,β_n$ ，且两个基有变换公式 $(β_1,β_2,\cdots,β_n)=(α_1,α_2,\cdots,α_n)P$，$V_n$ 中的线性变换 $T$ 在这两个基下的矩阵分别是 $A$ 与 $B$，则 $B=P^{-1}AP$

**秩的定义**：线性变换 $T$ 的像空间 $T(V_n)$ 的维数, 称为线性变换 $T$ 的==秩==(rank)
(1) 若  $A$ 是 $T$ 的矩阵, 则 $T$ 的秩就是  $r(A)$
(2) 若 $T$ 的秩为 $r$ , 则 $T$ 的核 $N_T$ 的维数为 $n-r$



