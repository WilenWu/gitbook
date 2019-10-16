---
title: 微积分(Calculus II)
tags: [R]
mathjax: false
copyright: true
date: 2019-05-03 20:31:28
categories: [R,Calculus II]
sticky: false
---


------

[微积分(Calculus I)](https://blog.csdn.net/qq_41518277/article/details/89397964)
[微积分(Calculus II)](https://blog.csdn.net/qq_41518277/article/details/89761069)
[微积分(Calculus III)](https://blog.csdn.net/qq_41518277/article/details/90029881)

------


<!-- more -->
# 多元函数微分法(Multi-element Function Infinitesimal Method)
## 多元函数(Multi-element Function)
- **平面点集**(planar point set)：
(1) 由平面解析几何知道，有序实数对$(x,y)$与平面点P视作等同。二元有序实数组$(x,y)$的全体，即$\R^2=\R×\R=\{(x,y)|x,y\in\R\}$就表示坐标平面。
(2) $P_0(x_0,y_0)是xOy平面的一个点, δ>0$
==邻域==(neighborhood)：$U(P_0,δ)=\{(x,y)|\sqrt{(x-x_0)^2+(y-y_0)^2}<δ\}$
==去心邻域==(punctured neighbourhood)：$\mathring{U}(P_0,δ)=\{(x,y)|0<\sqrt{(x-x_0)^2+(y-y_0)^2}<δ\}$
不需要强调半径$δ$时可记作$U(P_0), \mathring{U}(P_0)$
(3) 点与点集的关系：任意一点$P\in\R$与任意一点集$D⊂\R^2$之间必有以下关系之一
内点(interior point)：$∃ U(P),U(P)⊂ D$
外点(exterior point)：$∃ U(P),U(P)∩ D=\empty$
边界点(boundary point)：若点P的任一邻域$U(P)$中既含D的点也含不是D的点,则称
为D的边界==边界==，记作$∂ D$
聚点(point of accumulation)：$∀ δ>0,∃ A\in\mathring{U}(P,δ),A\in D$
![关系](https://img-blog.csdnimg.cn/20190513151351378.png =200x)
(4) 定义一些重要的平面点集
开集(open set)：$∀ P\in E$，P都是E的内点
闭集(closed set)：边界$∂ E⊂ E$
连通集(connected set)：点集E内任何两点都可以用折线连接起来，且该折线上的点都属于E
区域(region)：连通的开集
闭区域(closed region)：开区域连同它的边界一起构成的点集
有界集(bounded set)：$∃ r>0,E⊂ U(O,r),O$是坐标原点，点集E为有界集
无界集：不是有界集的点集
- **n维空间**(n-dimensional space)：n元有序实数组$(x_1,x_2,\cdots,x_n)$的全体构成的集合$\R^n=\{(x_1,x_2,\cdots,x_n)|x_i\in\R,i=1,2,\cdots,n\}$，称为n维空间

n维空间 $\R^n$|$x=(x_1,x_2,\cdots,x_n),y=(y_1,y_2,\cdots,y_n)\in\R^n$
:---|:---
线性运算|$x+y=(x_1+y_1,x_2+y_2,\cdots,x_n+y_n)\\ λx=(λx_1,λx_2,\cdots,λx_n),λ\in\R$
距离(distance)|$ρ(x,y)=\sqrt{(x_1-y_1)^2+(x_2-y_2)^2+\cdots+(x_n-y_n)^2}$
模(modulus)|$\|x\|=ρ(x,O)=\sqrt{x_1^2+x_2^2+\cdots+x_n^2}$
变元的极限|$x\to a\iff x_1\to a_1,x_2\to a_2,\cdots,x_n\to a_n$
定义邻域及其他|$a\in \R^n,δ>0\rightarrow U(a,δ)=\{x\mid x\in\R^n,ρ(x,a)<δ\}$

- **多元函数的概念**(function of several variables)
(1) 二元函数：映射$f：D\to \R,D⊂\R^2\Rightarrow z=f(x,y),(x,y)\in D$
(2) n元函数：映射$f：D\to \R,D⊂\R^n\Rightarrow u=f(x_1,x_2,\cdots,x_n),(x_1,x_2,\cdots,x_n)\in D$或简写为$u=f(x),x=(x_1,x_2,\cdots,x_n)\in D$
(3) 二元函数图和截痕法
![二元函数图](https://img-blog.csdnimg.cn/20190513152139108.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNTE4Mjc3,size_16,color_FFFFFF,t_70 =200x)  ![截痕法](https://img-blog.csdnimg.cn/20190513152151374.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNTE4Mjc3,size_16,color_FFFFFF,t_70 =200x)
- **多元函数的极限**
(1) ==二重极限==：$z=f(x,y),(x,y)\in D,P_0(x_0,y_0)$是D的聚点
$\lim\limits_{(x,y)\to(x_0,y_0)}f(x,y)=A或\lim\limits_{P\to P_0}f(P)=A \iff 
∃ A,∀ϵ>0,∃δ>0,使得P(x,y)\in D∪\mathring{U}(P_0,δ) 时,都有|f(P)-A|=|f(x,y)-A|< ϵ$
(2) 二元函数的极限概念可以相应的推广到n元

- **多元函数的连续性**：$z=f(x,y),(x,y)\in D,P_0(x_0,y_0)是D的聚点,且P_0\in D$
$\lim\limits_{(x,y)\to(x_0,y_0)}f(x,y)=f(x_0,y_0)\iff 函数在点P_0连续$

- **多元初等函数**：由常数及不同自变量的一元基本初等函数经过有限次四则运算和复合运算而得到的。
一切多元初等函数在定义区域内都是连续的。

- **多元函数的性质**
<kbd>有界性与最大值最小值定理</kbd>：在有界闭区域D上的多元连续函数，必定在D上有界，且能取得它的最大值最小值
<kbd>介值定理</kbd>:在有界闭区域D上的多元连续函数，必取得介于最大值最小值之间的任何值
<kbd>一致连续性定理</kbd>:在有界闭区域D上的多元连续函数，必定在D上一致连续(uniformly continuous)

## 偏导数(partial derivative)
 (1) $z=f(x,y)在点(x_0,y_0)$处对自变量x的偏导数定义为$$f_x(x_0,y_0)=\lim\limits_{Δ x\to0}\dfrac{f(x_0+Δ x,y_0)-f(x_0,y_0)}{Δ x}$$ 可记作$f_x(x_0,y_0), \dfrac{∂ z}{∂ x}|_{x=x_0 \atop y=y_0}, \dfrac{∂ f}{∂ x}|_{x=x_0 \atop y=y_0},z_x|_{x=x_0 \atop y=y_0}$，对自变量y的偏导数类似。
 (2) 同样的可以定义区间内任意自变量x的偏导函数，记作$f_x(x,y), \dfrac{∂ z}{∂ x}, \dfrac{∂ f}{∂ x},z_x$，偏导函数的概念还可推广到二元以上的函数。
 (3) 偏导数的记号是一个整体记号，不能看作微商，和一元函数不一样。
 (4) 偏导数的几何意义：$f_x(x_0,y_0)$就是平面$y=y_0$上的曲线$z=f(x,y_0)$在点$(x_0,y_0)$处的切线对x轴的斜率
 ![偏导数](https://img-blog.csdnimg.cn/20190513153308213.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNTE4Mjc3,size_16,color_FFFFFF,t_70 =200x)
 (5) 二阶偏导数$$\dfrac{∂}{∂ x}(\dfrac{∂ z}{∂ x})=\dfrac{∂^2 z}{∂ x^2}=f_{xx}(x,y),
 \dfrac{∂}{∂ y}(\dfrac{∂ z}{∂ x})=\dfrac{∂^2 z}{∂ x∂ y}=f_{xy}(x,y)\\
  \dfrac{∂}{∂ x}(\dfrac{∂ z}{∂ y})=\dfrac{∂^2 z}{∂ y∂ x}=f_{yx}(x,y),
  \dfrac{∂}{∂ y}(\dfrac{∂ z}{∂ y})=\dfrac{∂^2 y}{∂ y^2}=f_{yy}(x,y)
 $$ 其中二三两个称为混合偏导数，同样可求得三阶、四阶...以及n阶偏导数。
<kbd>定理</kbd>高阶混合偏导数在连续条件下与求导次序无关（即$\dfrac{∂^2 z}{∂ x∂ y}=\dfrac{∂^2 z}{∂ y∂ x}$）

## 全微分(total differential)
- **偏增量**(partial increment)：根据一元函数的关系可得$f(x+Δ x,y_0)-f(x,y)\approx f_x(x,y)Δ x$等式左边为对x的偏增量，右端对y的偏微分。
- **全增量**(total increment)：$Δ z=f(x+Δ x,y+Δ y)-f(x,y)$
- **全微分的定义**：若函数$z=f(x,y)$在点$(x,y)$的全增量$Δ z=f(x+Δ x,y+Δ y)-f(x,y)$可表示为$$Δ z=AΔ x+BΔ y+o(ρ)$$其中A和B不依赖于$Δ x和Δ y$而仅与x,y有关，$ρ=\sqrt{(Δ x)^2+(Δ y)^2}$，则称函数在点$(x,y)$==可微分==(differentiable)，$AΔ x+BΔ y$叫做==全微分==，记作$\mathrm{d}z$，即$$\mathrm{d}z=AΔ x+BΔ y$$
- **全微分与偏导数**
<kbd>必要条件</kbd>$函数z=f(x,y)在(x,y)可微分，那该函数在(x,y)偏导数 \dfrac{∂ z}{∂ x}， \dfrac{∂ z}{∂ y}必定存在$，全微分$$\mathrm{d}z=\dfrac{∂ z}{∂ x}Δ x+\dfrac{∂ z}{∂ y}Δ y$$
<kbd>充分条件</kbd>$函数z=f(x,y)的偏导数 \dfrac{∂ z}{∂ x}， \dfrac{∂ z}{∂ y}在(x,y)连续，那么函数在该点可微分$
<kbd>叠加原理</kbd>习惯上自变量的增量$Δ x,Δ y$常记作$\mathrm{d}x,\mathrm{d}y$ ，即全微分等于两个偏微分之和$$\mathrm{d}z=\dfrac{∂ z}{∂ x}\mathrm{d}x+\dfrac{∂ z}{∂ y}\mathrm{d}y$$叠加原理同样适用于二元以上函数

## 求导法则(derivation rules)
- **多元复合函数的求导法则**
(1) $u=ϕ(t),v=ψ(t),z=f(u,v)$,求全导数
$$\dfrac{\mathrm{d}z}{\mathrm{d}t}=\dfrac{∂ z}{∂ u}\dfrac{\mathrm{d}u}{\mathrm{d}t}+\dfrac{∂ z}{∂ v}\dfrac{\mathrm{d}v}{\mathrm{d}t}$$  (2) $u=ϕ(x,y),v=ψ(x,y),z=f(u,v)$
$$\dfrac{∂ z}{∂ x}=\dfrac{∂ z}{∂ u}\dfrac{∂ u}{∂ x}+\dfrac{∂ z}{∂ v}\dfrac{∂ v}{∂ x} ,\quad
\dfrac{∂ z}{∂ y}=\dfrac{∂ z}{∂ u}\dfrac{∂ u}{∂ y}+\dfrac{∂ z}{∂ v}\dfrac{∂ v}{∂ y}$$ (3) ==全微分形式不变性== ：$u=ϕ(x,y),v=ψ(x,y),z=f(u,v)$
$\mathrm{d}z=\dfrac{∂ z}{∂ x}\mathrm{d}x+\dfrac{∂ z}{∂ y}\mathrm{d}y=\dfrac{∂ z}{∂ u}\mathrm{d}u+\dfrac{∂ z}{∂ v}\mathrm{d}v$

- **隐函数的求导公式**
(1) $F(x,y)=0$，隐函数$y=f(x)$ $$\dfrac{\mathrm{d}y}{\mathrm{d}x}=-\dfrac{F_x}{F_y}$$
(2) $F(x,y,z)=0$，隐函数$z=f(x,y)$ $$\dfrac{∂ z}{∂ x}=-\dfrac{F_x}{F_z},\quad \dfrac{∂ z}{∂ y}=-\dfrac{F_y}{F_z}$$
(3) $\begin{cases} F(x,y,u,v)=0 \\ G(x,y,u,v)=0 \end{cases}$一般能确定两个二元函数$u=u(x,y),v=v(x,y)$ $$\dfrac{∂ u}{∂ x}=-\dfrac{1}{J}\dfrac{∂(F,G)}{∂(x,v)}, 
\dfrac{∂ u}{∂ y}=-\dfrac{1}{J}\dfrac{∂(F,G)}{∂(y,v)} \\ 
\dfrac{∂ v}{∂ x}=-\dfrac{1}{J}\dfrac{∂(F,G)}{∂(u,x)}, 
\dfrac{∂ v}{∂ y}=-\dfrac{1}{J}\dfrac{∂(F,G)}{∂(u,y)}
$$ 雅可比行列式(Jacobian) $J= \dfrac{∂(F,G)}{∂(u,v)}=\begin{vmatrix} \dfrac{∂ F}{∂ u} & \dfrac{∂ F}{∂ v} \\  \\ \dfrac{∂ G}{∂ u} & \dfrac{∂ G}{∂ v}\end{vmatrix}$

## 多元函数微分学的几何应用(applications in geometry)
- **一元向量值函数**(vector objective function)：
(1) 空间曲线$Γ$的参数方程$\begin{cases}x=x(t)\\ y=y(t)\\ z=z(t) \end{cases}$可以写成向量形式
$$\mathbf r=\mathbf f(t)=x(t)\mathbf i+y(t)\mathbf j+z(t)\mathbf k,\mathbf f(t)⊂\R^3$$  ==极限==$\lim\limits_{t\to t_0}\mathbf f(t)=\mathbf r_0$
==连续==$\mathbf f(t)在t_0连续\iff\lim\limits_{t\to t_0}\mathbf f(t)=\mathbf f(t_0)$
==导数==$\mathbf f'(t)=\lim\limits_{Δ t\to0}\dfrac{\mathbf f(t+Δ t)-\mathbf f (t)}{Δ t}$
$\mathbf f'(t)=x'(t)\mathbf i+y'(t)\mathbf j+z'(t)\mathbf k$
$(\mathbf u\cdot\mathbf v)'=\mathbf u'\cdot\mathbf v+\mathbf u\cdot\mathbf v'$ 
$(\mathbf u×\mathbf v)'=\mathbf u'×\mathbf v+\mathbf u×\mathbf v'$ 
$\dfrac{\mathrm{d}\mathbf u}{\mathrm{d}t}=\dfrac{\mathrm{d}\mathbf u}{\mathrm{d}\mathbf v}\dfrac{\mathrm{d}\mathbf v}{\mathrm{d}t}$
(2) 空间曲线$Γ$在点$M(x_0,y_0,z_0)$处的==切线方程==为$$\dfrac{x-x_0}{x'(t_0)}=\dfrac{y-y_0}{y'(t_0)}=\dfrac{z-z_0}{z'(t_0)}$$ 
(3) 通过点M且与切线垂直的==法平面方程==为$$x'(t_0)(x-x_0)+y'(t_0)(y-y_0)+z'(t_0)(z-z_0)=0$$ 
(4) 若曲线$Γ$方程为$\begin{cases}F(x,y,z)=0\\ G(x,y,z)=0 \end{cases}$，则法平面方程为 $$\begin{vmatrix}F_y&F_z \\ G_y&G_z\end{vmatrix}(x-x_0)+
\begin{vmatrix}F_z&F_x \\ G_z&G_x\end{vmatrix}(y-y_0)+
\begin{vmatrix}F_x&F_y \\ G_x&G_y\end{vmatrix}(z-z_0)=0$$

- **曲面** $Σ方程F(x,y,z)=0$，曲面上一点$M(x_0,y_0,z_0)$
(1) 过点M的切线形成的平面，==切平面==方程为$$F_x(x_0,y_0,z_0)(x-x_0)+F_y(x_0,y_0,z_0)(y-y_0)+F_z(x_0,y_0,z_0)(z-z_0)=0$$
(2) 过点M且垂直于切平面的==法线==方程$$\dfrac{x-x_0}{F_x(x_0,y_0,z_0)}=\dfrac{y-y_0}{F_y(x_0,y_0,z_0)}=\dfrac{z-z_0}{F_z(x_0,y_0,z_0)}$$

## 方向导数和梯度(directional derivative and gradient)
- **方向导数**(directional derivative)：函数$f(x,y)$在点$P_0(x_0,y_0)$沿任意 $l$ 方向的 方向导数 ：$$\dfrac{∂ f}{∂ l}\mid_{(x_0,y_0)}=f_x(x_0,y_0)\cosα+f_y(x_0,y_0)\cosβ$$ 其中$\cosα,\cosβ为l$的方向余弦，同样二元以上函数的方向导数类似。
由定义可知，方向导数就是函数在点$P_0$处沿$l$方向的变化率。
- **梯度**(gradient)：函数$f(x,y)$在点$P_0(x_0,y_0)$处的梯度：$$\mathrm{grad}f(x_0,y_0)=∇ f(x_0,y_0)=f_x(x_0,y_0)\mathbf i+f_y(x_0,y_0)\mathbf j$$ 其中$∇=\dfrac{∂}{∂ x}\mathbf i+\dfrac{∂}{∂ y}\mathbf j$ 称为微分算子[^0]，$∇ f=\dfrac{∂ f}{∂ x}\mathbf i+\dfrac{∂ f}{∂ y}\mathbf j$

[^0]: 哈密顿引进了一个矢性微分算子$∇=\dfrac{∂}{∂ x}\mathbf i+\dfrac{∂}{∂ y}\mathbf j+\dfrac{∂}{∂ z}\mathbf k$，称为哈密顿算子(Hamiltonian)或者nabla算子，读作 del ta或nabla 
梯度 $\mathrm{grad}A=∇ A$
散度 $\mathrm{div}\mathbf A=∇\cdot\mathbf A$
旋度 $\mathrm{curl}\mathbf A=∇×\mathbf A$
拉普拉斯算子 $Δ=∇\cdot∇=∇^2$
(1) $∇(cu)=c∇ u$ (c为常数)
(2) $∇(u± v)=∇ u+∇ v$
(3) $∇(uv)=u∇ v+v∇ u$
(4) $∇\dfrac{u}{v}=\dfrac{v∇ u-u∇ v}{v^2}$


- **方向导数与梯度**：$\mathbf e_l=(\cosα,\cosβ)$是与$l$同向的单位向量
$\dfrac{∂ f}{∂ l}\mid_{(x_0,y_0)}=\mathrm{grad}f(x_0,y_0)\cdot\mathbf e_l=|\mathrm{grad}f(x_0,y_0)|\cosθ$
其中$θ$为$\mathrm{grad}f(x_0,y_0)$与$\mathbf e_l$的夹角，由此表明
(1) 当$θ=0$时，函数$f(x,y)$增加最快
(2) 当$θ=π$时，函数$f(x,y)$减小最快
(3) 当$θ=\dfrac{π}{2}$时，函数$f(x,y)$变化率为0
- **等值线**(isoline)：曲面$z=f(x,y)$被平面$z=c$(c是常数)截得的曲线$L$的方程为$\begin{cases}z=f(x,y) \\z=c \end{cases}$，曲线在$xOy$平面上的投影是条平面曲线$L^*:f(x,y)=c$，$L^*$称为曲线$z=f(x,y)$的等值线
等值线$L^*$上任意一点的单位法向量$\mathbf n=\dfrac{∇ f(x_0,y_0)}{|∇ f(x_0,y_0)|}$，于是沿法线的方向导数$\dfrac{∂ f}{∂ n}$有$∇ f(x_0,y_0)=\dfrac{∂ f}{∂ n}\mathbf n$

![等值线](https://img-blog.csdnimg.cn/20190503200514437.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNTE4Mjc3,size_16,color_FFFFFF,t_70 =250x)
- **势场**[^6] (potential)：梯度场 $\mathrm{grad}\dfrac{m}{r}=-\dfrac{m}{r^2}\mathbf e_r$称为引力场，$\dfrac{m}{r}$称为引力势


## 多元函数的极值(extremum)
- **无条件极值**
==(定义)==：函数$z=f(x,y)$定义域为D，点$P_0(x_0,y_0)$是D的内点，$∀ (x,y)\in\mathring{U}(P_0),f(x,y)<f(x_0,y_0)或f(x,y)>f(x_0,y_0),称f(x_0,y_))是函数f(x,y)的一个极大值或极小值,极大值和极小值统称为极值,使函数取得极值的点称为极值点$
==(必要条件)==：$设f(x,y)在(x_0,y_0)处有偏导数,f(x_0,y_0)为极值\Rightarrow f_x(x_0,y_0)=0,f_y(x_0,y_0)=0$，点$(x_0,y_0)$称为驻点或稳定点。
==(充分条件)==：$设f(x,y)在(x_0,y_0)处连续,且f_x(x_0,y_0)=0,f_y(x_0,y_0)=0,令f_{xx}(x_0,y_0)=A,f_{xy}(x_0,y_0)=B,f_{yy}(x_0,y_0)=C,则\\
AC-B^2\begin{cases}<0,&有极值,A<0有极大值,A>0有极小值 \\ >0,&没有极值 \\=0,
&另做讨论
\end{cases}$

- [**拉格朗日乘子法**](https://baike.bai\mathrm{d}u.com/item/%E6%8B%89%E6%A0%BC%E6%9C%97%E6%97%A5%E4%B9%98%E5%AD%90%E6%B3%95/1946079) (Lagrange multiplier)
求函数$z=f(x,y)$在附加条件$ϕ(x,y)=0$下的条件极值(conditional extremum)
(1) 先做拉格朗日函数$L(x,y)=f(x,y)+λ ϕ(x,y)$
(2) 求偏导数然后与方程联立$\begin{cases}f_x(x,y)+λ ϕ_x(x,y)=0\\
f_y(x,y)+λ ϕ_y(x,y)=0\\
ϕ(x,y)=0\end{cases}$
求$x,y,λ$，点$(x,y)$就是在附加条件下的可能极值
拉格朗日乘子法也适用于大于二元的函数与多条件

- **最小二乘法**(least square method)
求样本想$(x_i,y_i)$的经验公式$f(x)=ax+b$
(1) 为使偏差$y_i-f(x_i)$取得最小值，即求$M(a,b)=\sum [y_i-(ax_i+b)]^2$的最小值，来确定常数a,b
(2) 根据本章的讨论得知，即求a,b的驻点$\begin{cases}M_a(a,b)=0\\ M_b(a,b)=0\end{cases}$，解方程组可得a,b

## 二元函数的泰勒公式(Taylor formula)
$设函数z=f(x,y)在点P_0(x_0,y_0)的某一邻域U(P_0)连续且有(n+1)阶连续偏导数,(x_0+h,y_0+k)\in U(P_0)$
$$\begin{aligned}
f(x_0+h,y_0+k)&=f(x_0,y_0)+(h\dfrac{∂}{∂ x}+k\dfrac{∂}{∂ y})f(x_0,y_0)+\dfrac{1}{2!}(h\dfrac{∂}{∂ x}+k\dfrac{∂}{∂ y})^2f(x_0,y_0)+\cdots+\dfrac{1}{n!}(h\dfrac{∂}{∂ x}+k\dfrac{∂}{∂ y})^nf(x_0,y_0)+R_n \\
&=\displaystyle\sum_{i=0}^{n}\dfrac{1}{i!}(h\dfrac{∂}{∂ x}+k\dfrac{∂}{∂ y})^i f(x_0,y_0)+R_n
\end{aligned}$$ 其中记号$$\begin{aligned} 
&(h\dfrac{∂}{∂ x}+k\dfrac{∂}{∂ y})f(x_0,y_0)表示 hf_x(x_0,y_0)+kf_y(x_0,y_0)\\ 
&(h\dfrac{∂}{∂ x}+k\dfrac{∂}{∂ y})^2f(x_0,y_0)表示 h^2f_{xx}(x_0,y_0)+2hkf_{xy}(x_0,y_0)+k^2f_{yy}(x_0,y_0)
\end{aligned}$$一般的，记号$$(h\dfrac{∂}{∂ x}+k\dfrac{∂}{∂ y})^mf(x_0,y_0)表示\displaystyle\sum_{p=0}^{m}∁_m^ph^pk^{m-p}\dfrac{∂ ^mf}{∂ x^p∂ y^{m-p}}\mid_{(x_0,y_0)}$$
$拉格朗日余项R_n=\dfrac{1}{(n+1)!}(h\dfrac{∂}{∂ x}+k\dfrac{∂}{∂ y})^{n+1}f(x_0+θ h,y_0+θ k) \quad(0<θ<1)$
当$n=0$时，即为二元函数的拉格朗日中值公式


# 重积分(Multiple Integral) 
## 二重积分(double integral)
- **引入意义**
曲顶$z=f(x,y)$柱体的体积$V=\lim\limits_{λ\to0}\displaystyle\sum_{k=1}^{n}f(ξ_k,η_k)Δ σ_k$
密度为$μ=μ(x,y)$平面薄片的质量 $m=\lim\limits_{λ\to0}\displaystyle\sum_{k=1}^{n}μ(ξ_k,η_k)Δ σ_k$
![曲顶柱体](https://img-blog.csdnimg.cn/20190513155429833.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNTE4Mjc3,size_16,color_FFFFFF,t_70 =200x) ![平面薄片](https://img-blog.csdnimg.cn/20190513155453760.png =200x) 

- **定义**：设$f(x,y)$ 是有界闭区域D上的有界函数
将闭区域$D$任意分成n个小闭区域 $$Δ σ_1,Δ σ_2,\cdots,Δ σ_n$$其中$Δ σ_i$第i个小闭区域，也表示它的面积，在每个$Δ σ_i$中任取一点$(ξ_,η_i)$，作乘积$f(ξ_,η_i)Δ σ_i(i=1,2,\cdots,n)$，并作出求和$$Ω=\displaystyle\sum_{i=1}^{n}f(ξ_,η_i)Δ σ_i$$  如果当各小闭区域直径中的最大值$λ\to0$时，和的极限总存在，且与闭区域D的分法及点$(ξ_,η_i)$的取法无关，则这个极限叫做函数$f(x,y)$ 在闭区域$D$的二重积分(double integral)，记  $$\iint_Df(x,y)\mathrm{d}σ=\lim\limits_{λ\to0}\displaystyle\sum_{i=1}^{n}f(ξ_,η_i)Δ σ_i$$ 其中D称为积分区域(domain of integration)，$\mathrm{d}σ$叫做面积元素，$f(x,y)$是被积函数
在直角坐标系中，有时把面积元素$\mathrm{d}σ$记作$\mathrm{d}x\mathrm{d}y$，把二重积分记作$\iint_Df(x,y)\mathrm{d}x\mathrm{d}y$

二重积分的主要性质|
:---|
$\iint_Dkf(x,y)\mathrm{d}σ=k\iint_Df(x,y)\mathrm{d}σ$|
$\iint_D [f(x,y)± g(x,y)]\mathrm{d}σ=\iint_D f(x,y)\mathrm{d}σ ± \iint_D g(x,y)\mathrm{d}σ$|
$\iint_{d} f(x,y)\mathrm{d}σ=\iint_{d_1} f(x,y)\mathrm{d}σ + \iint_{d_1} f(x,y)\mathrm{d}σ\quad (D=D_1+D_2)$|

- **二重积分中值定理**：$f(x,y)在闭区域D上连续,σ是D的面积\Rightarrow∃(ξ_,η_i)\in D$ $$\iint_Df(x,y)\mathrm{d}σ=f(ξ_,η_i)σ$$ 

## 二重积分的计算
- **利用直角坐标计算二重积分**
下面用几何观点来讨论二重积分$\iint_Df(x,y)\mathrm{d}σ$
(1) 假设积分区域D为X型区域，即可以用不等式 $y_1(x)⩽ y ⩽ y_2(x),a⩽ x⩽ b$表示
先计算截面面积$S(x_0)=\int_{y_1(x_0)}^{y_2(x_0)}f(x_0,y)\mathrm{d}y$，一般的$x\in[a,b]$时，方程都适用
再计算曲顶柱体体积$V=\int_a^bS(x)\mathrm{d}x=\int_a^b[\int_{y_1(x)}^{y_2(x)}f(x,y)\mathrm{d}y]\mathrm{d}x$
这个体积就是二重积分的值，这样先对y再对x积分的方法叫==二次积分==，二次积分也常记作$$\iint_Df(x,y)\mathrm{d}σ=\int_a^b \mathrm{d}x\int_{y_1(x)}^{y_2(x)}f(x,y)\mathrm{d}y$$
![X型区域](https://img-blog.csdnimg.cn/20190513160301106.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNTE4Mjc3,size_16,color_FFFFFF,t_70 =300x)  ![二重计算](https://img-blog.csdnimg.cn/20190513161603981.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNTE4Mjc3,size_16,color_FFFFFF,t_70 =300x)  
(2) 假设积分区域D为Y型区域，即可以用不等式 $x_1(y)⩽ x ⩽ x_2(y),a⩽ y⩽ b$表示 $$\iint_Df(x,y)\mathrm{d}σ=\int_a^b \mathrm{d}y\int_{x_1(y)}^{x_2(y)}f(x,y)\mathrm{d}x$$
![Y型区域](https://img-blog.csdnimg.cn/20190513161839919.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNTE4Mjc3,size_16,color_FFFFFF,t_70 =300x)
(3) 如果积分区域既不是X型区域，也不是Y型区域，这时可以把D分成几部分求和

- **利用极坐标计算二重积分**
(1) 按二重积分的定义来计算，小闭区域面积$Δσ_i=\dfrac{1}{2}(ρ_i+Δρ_i)^2\cdotΔθ_i=\bar{ρ_i}\cdotΔρ_i\cdotΔθ_i$，其中$\bar{ρ_i}$表示相邻两圆弧半径的平均值，由极坐标和直角坐标间的关系[^1]得$$\iint_Df(x,y)\mathrm{d}x\mathrm{d}y=\iint_Df(ρ\cosθ,ρ\sinθ)ρ \mathrm{d}ρ \mathrm{d}θ$$其中$ρ \mathrm{d}ρ \mathrm{d}θ$就是极坐标中的面积元素
(2) 极坐标的二重积分同样可以化为二次积分来求，设积分区域D可以用不等式$ρ_1(θ)⩽ ρ ⩽ ρ_2(θ),α⩽θ⩽ β$表示$$\iint_Df(ρ\cosθ,ρ\sinθ)ρ \mathrm{d}ρ \mathrm{d}θ
=\int_α^β \mathrm{d}θ\int_{ρ_1(θ)}^{ρ_2(θ)}f(ρ\cosθ,ρ\sinθ)ρ \mathrm{d}ρ$$
(特例) 设$f(x,y)=1$，小面积区域$\mathrm{d}σ=ρ \mathrm{d}ρ \mathrm{d}θ$，，可求得D的面积 $$σ=\iint_\mathrm{d}ρ \mathrm{d}ρ \mathrm{d}θ=\dfrac{1}{2}\int_α^β[ρ_2^2(θ)-ρ_1^2(θ)] \mathrm{d}θ$$
[^1]: 平面向量极坐标$(ρ,θ)$和直角坐标$(x,y)$换算：$\begin{cases}x=ρ\cosθ \\ y=ρ\sinθ\end{cases},ρ\in[0,+∞),θ\in[0,2π)$

![二重积分](https://img-blog.csdnimg.cn/20190513163017759.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNTE4Mjc3,size_16,color_FFFFFF,t_70 =200x)    ![二重积分](https://img-blog.csdnimg.cn/20190513163031234.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNTE4Mjc3,size_16,color_FFFFFF,t_70 =400x)
- **二重积分的换元法**
设$f(x,y)$在$xOy$平面上的闭区域$D$上连续，若变换$$T:x=x(u,v),y=y(u,v)$$将$uOv$平面上的闭区域$D'$变为$xOy$平面上的$D$，且满足
(1) $x(u,v),y(u,v)在D'$上具有一阶连续偏导数
(2) 在$D'$上雅可比行列式[^2]$\det J(u,v)=\det\dfrac{∂(x,y)}{∂(u,v)}\neq0$
(3) 变换$T:D'\to D$是一一对应的
则有$$\iint_Df(x,y)\mathrm{d}x\mathrm{d}y=\iint_{d'}f[x(u,v),y(u,v)]\ |J(u,v)|\ \mathrm{d}u\mathrm{d}v$$
[^2]: 雅可比矩阵(Jacobian matrix) $J(x_1,\cdots,x_n)=\dfrac{∂(y_1,\cdots,y_m)}{∂(x_1,\cdots,x_n)}=\begin{pmatrix}\dfrac{∂ y_1}{∂ x_1}\cdots\dfrac{∂ y_1}{∂ x_n} \\ \vdots \ddots \vdots \\ \dfrac{∂ y_m}{∂ x_1}\cdots\dfrac{∂ y_m}{∂ x_n} \end{pmatrix}$

## 三重积分(triple integral)
(1) 定积分和二重积分作为和的极限的概念自然推广到三重积分$$\iiint_{Ω}f(x,y,z)\mathrm{d}v=\lim\limits_{λ\to0}\displaystyle\sum_{i=1}^{n}f(ξ_,η_i,ζ_i)Δ v_i$$ 其中$f(x,y,z)$是被积函数，$Ω$称为积分区域(domain of integration)，$\mathrm{d}v$叫做体积元素
在直角坐标系中，有时把体积元素$\mathrm{d}v$记作$\mathrm{d}x\mathrm{d}y\mathrm{d}z$，把三重积分记作$\iiint_{Ω}f(x,y,z)\mathrm{d}x\mathrm{d}y\mathrm{d}z$
(2) 三重积分的性质与二重积分类似，这里就不在重复了

## 三重积分的计算
-  **利用直角坐标进行三重积分**
(1) 假设平行于$z$轴且穿过闭区域$Ω$的直线与闭区域的边界曲面$S$相交不多于两点，把闭区域$Ω$投影到$xOy$平面上，得一平面闭区域$D_{xy}$，如图，S的上下两部分方程为 $\begin{aligned}S_1:z=z_1(x,y)\\ S_2:z=z_2(x,y)\end{aligned}$，则积分区域可表示为 $Ω=\{(x,y,z)|z_1(x,y)⩽ z⩽ z_2(x,y),(x,y)\in D_{xy}\}$，假如$D_{xy}=\{(x,y)|y_1(x)⩽ y⩽ y_2(x),a⩽ x⩽ b\}$，三重积分可化为==三次积分==$$\iiint_{Ω}f(x,y,z)\mathrm{d}v=\int_a^b\mathrm{d}x\int_{y_1(x)}^{y_2(x)}\mathrm{d}y\int_{z_1(x,y)}^{z_2(x,y)}f(x,y,z)\mathrm{d}z$$
(2) 也可把闭区域投影到$xOz$或$yOz$平面上，三重积分解法类似
(3) 如果平行于坐标轴且穿过闭区域$Ω$的直线与闭区域的边界曲面$S$相交多于两点，可以把闭区域分成若干部分分别计算。
![三重积分](https://img-blog.csdnimg.cn/20190507132320779.png)
-  **利用柱面坐标进行三重积分**[^3]：体积元素$\mathrm{d}v=ρ \mathrm{d}ρ \mathrm{d}θ \mathrm{d}z$
$$\iiint_{Ω}f(x,y,z)\mathrm{d}x\mathrm{d}y\mathrm{d}z=\iiint_{Ω}f(ρ\cosθ,ρ\cosθ,z)ρ \mathrm{d}ρ \mathrm{d}θ \mathrm{d}z$$

-  **利用球面坐标进行三重积分**[^3]：体积元素$\mathrm{d}v=r^2\sinϕ \mathrm{d}r \mathrm{d}ϕ \mathrm{d}θ$
$$\iiint_{Ω}f(x,y,z)\mathrm{d}x\mathrm{d}y\mathrm{d}z=\iiint_{Ω}f(r\sinϕ\cosθ,r\sinϕ\sinθ,r\cosϕ)r^2\sinϕ \mathrm{d}r \mathrm{d}ϕ \mathrm{d}θ$$

[^3]: 柱面坐标$(ρ,θ,z)$和直角坐标$(x,y,z)$的换算$\begin{cases}x=ρ\cosθ \\ y=ρ\sinθ \\ z=z\end{cases},ρ\in[0,+∞),θ\in[0,2π),z\in[0,+∞)$，球面坐标$(r,ϕ,θ)$和直角坐标$(x,y,z)$的换算$\begin{cases}x=r\sinϕ\cosθ \\ y=r\sinϕ\sinθ \\z=r\cosϕ\end{cases},ρ\in[0,+∞),ϕ\in[0,π),θ\in[0,2π)$

![柱面坐标](https://img-blog.csdnimg.cn/20190507134836456.png =200x)![球坐标](https://img-blog.csdnimg.cn/20190507134859757.png =200x)

## 重积分的应用
- **曲面的面积**：
(1) 曲面方程$z=f(x,y)$
面积元素$\mathrm{d}A=\dfrac{\mathrm{d}σ}{\cosγ},\cosγ=\dfrac{1}{\sqrt{1+f_x^2(x,y)+f_y^2(x,y)}}$
由此面积公式$A=\iint_D\sqrt{1+f_x^2(x,y)+f_y^2(x,y)}\mathrm{d}x\mathrm{d}y$
(2) 曲面的参数方程$\begin{cases}x=x(u,v)\\y=y(u,v)\\z=z(u,v) \end{cases}\quad (u,v)\in D$，且[^2]$\det\dfrac{∂(x,y)}{∂(u,v)}\cdot\det\dfrac{∂(x,z)}{∂(u,v)}\cdot\det\dfrac{∂(y,z)}{∂(u,v)}\neq0$
面积公式$A=\iint_D\sqrt{EG-F^2}\mathrm{d}u\mathrm{d}v$，其中$E=x_u^2+y_u^2+z_u^2,F=x_ux_v+y_uy_v+z_uz_v,G=x_v^2+y_v^2+z_v^2$
![曲面面积](https://img-blog.csdnimg.cn/20190507143202256.png)
- **质心**[^4]：占有空间区域$Ω$，在$\mathbf r=(x,y,z)$处密度为$ρ(\mathbf r)=ρ(x,y,z)$的物体的质心坐标
$\displaystyle (\bar x,\bar y,\bar z)=\dfrac{1}{M}\iiint_{Ω}\mathbf rρ(\mathbf r)\mathrm{d}v,M=\iiint_{Ω}ρ(\mathbf r)\mathrm{d}v$
[^4]: 力学上质心坐标的计算公式$\mathbf r=\dfrac{\sum m_i\mathbf r_i}{M}, M=\sum m_i$

## 含参变量的积分
设函数$f(x,y)$是矩形$R=[a,b]×[c,d]$上的连续函数，函数$ϕ(x)=\int_c^df(x,y)\mathrm{d}y\quad(0⩽ x⩽ b)$则
(1) $\int_a^b\mathrm{d}x\int_c^df(x,y)\mathrm{d}y=\int_c^\mathrm{d}\mathrm{d}y\int_a^bf(x,y)\mathrm{d}x$
(2) $ϕ'(x)=\int_c^df_x(x,y)\mathrm{d}y$

# 曲线积分与曲面积分(Curvilinear Integral and Surface Integral)

## 对弧长的曲线积分(第一类曲线积分)
- **引入意义**
线密度$μ=μ(x,y,z)$构件在曲线$L$的质量$m=\lim\limits_{λ\to0}\displaystyle\sum_{k=1}^{n}μ(ξ_k,η_k,ζ_k)Δ s_k$
![曲线积分](https://img-blog.csdnimg.cn/20190513164848444.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNTE4Mjc3,size_16,color_FFFFFF,t_70 =250x)
- **概念**：设L为$xOy$平面的一条光滑曲线弧，定义$$\int_Lf(x,y)\mathrm{d}s=\lim\limits_{λ\to0}\displaystyle\sum_{i=1}^{n}f(ξ_,η_i)Δ s_i$$其中$f(x,y)$叫被积函数，$L$叫做积分弧段
(1) 上述定义可以推广至$f(x,y,z)$在空间弧段$Γ$上的曲线积分$\int_{Γ}f(x,y)\mathrm{d}s=\lim\limits_{λ\to0}\displaystyle\sum_{i=1}^{n}f(ξ_,η_i,ζ_i)Δ s_i$
(2) 如果$L$是闭曲线，曲线积分记作$\oint_Lf(x,y)\mathrm{d}s$


对弧长曲线积分的部分性质|
:---|
$\int_Lkf(x,y)\mathrm{d}s=k\int_Lf(x,y)\mathrm{d}s$|
$\int_L [f(x,y)± g(x,y)]\mathrm{d}s=\int_L f(x,y)\mathrm{d}s ± \int_L g(x,y)\mathrm{d}s$|
$\int_{L_1+L_2}f(x,y)\mathrm{d}s=\int_{L_1}f(x,y)\mathrm{d}s+\int_{L_2}f(x,y)\mathrm{d}s$|

- **对弧长曲线积分的计算方法**
设被积函数$f(x,y)$，积分弧段L的参数方程为$\begin{cases}x=ϕ(t)\\y=ψ(t)\end{cases}\quad t\in[α,β]$，且$ϕ^{'2}(t)+ψ^{'2}(t)\neq0$，则曲线积分$$\int_Lf(x,y)\mathrm{d}s=\int_{α}^{β}f[ϕ(t),ψ(t)]\sqrt{ϕ^{'2}(t)+ψ^{'2}(t)}\mathrm{d}t,\  α<β$$

## 对坐标的曲线积分(第二类曲线积分)
- **引入意义**：变力$\mathbf F=P(x,y,z)\mathbf i+Q(x,y,z)\mathbf j +R(x,y,z)\mathbf k$沿曲线$L$所做的功
$Δ W_k=\mathbf F(ξ_k,η_k,ζ_k)\cdot \overrightarrow{P_{k-1}P_k}=P(ξ_k,η_k,ζ_k)Δ x_k+Q(ξ_k,η_k,ζ_k)Δ y_k+R(ξ_k,η_k,ζ_k)Δ z_k$
$W=\displaystyle\sum_{k=1}^{n}Δ W_k=\lim\limits_{λ\to0}\displaystyle\sum_{k=1}^{n}[P(ξ_k,η_k,ζ_k)Δ x_k+Q(ξ_k,η_k,ζ_k)Δ y_k+R(ξ_k,η_k,ζ_k)Δ z_k]$
![曲线积分](https://img-blog.csdnimg.cn/20190513165517209.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNTE4Mjc3,size_16,color_FFFFFF,t_70 =250x)

- **概念**：设L为$xOy$平面上从点A到点B的一条有向光滑曲线弧，定义$$\int_LP(x,y)\mathrm{d}x=\lim\limits_{λ\to0}\displaystyle\sum_{i=1}^{n}f(ξ_,η_i)Δ x_i \\ 
\int_LQ(x,y)\mathrm{d}y=\lim\limits_{λ\to0}\displaystyle\sum_{i=1}^{n}f(ξ_,η_i)Δ y_i $$其中$P(x,y),Q(x,y)$叫被积函数，$L$叫做积分弧段
(1) 上述定义可以推广至$f(x,y,z)$在空间弧段$Γ$上的第二类曲线积分
(2) 应用上经常出现的是$\int_LP(x,y)\mathrm{d}x+\int_LQ(x,y)\mathrm{d}y$，简写为$$\int_LP(x,y)\mathrm{d}x+Q(x,y)\mathrm{d}y$$，也可以写成==向量形式==$$\int_L\mathbf F(x,y)\cdot \mathrm{d}\mathbf r$$，其中$\mathbf F(x,y)=P(x,y)\mathbf i+Q(x,y)\mathbf j,\mathbf r=\mathrm{d}x\mathbf i+\mathrm{d}y\mathbf j$


对坐标曲线积分的部分性质|
:---|
$\int_Lk\mathbf F(x,y)\cdot \mathrm{d}\mathbf r=k\int_L\mathbf F(x,y)\cdot \mathrm{d}\mathbf r$|
$\int_L [\mathbf F_1(x,y)± \mathbf F_2(x,y)]\cdot \mathrm{d}\mathbf r=\int_L \mathbf F_1(x,y)\cdot \mathrm{d}\mathbf r ± \int_L \mathbf F_2(x,y)\cdot \mathrm{d}\mathbf r$|
$\int_{L_1+L_2}\mathbf F(x,y)\cdot \mathrm{d}\mathbf r=\int_{L_1}\mathbf F(x,y)\cdot \mathrm{d}\mathbf r+\int_{L_2}\mathbf F(x,y)\cdot \mathrm{d}\mathbf r$|
$\int_{L^-}\mathbf F(x,y)\cdot \mathrm{d}\mathbf r=-\int_L\mathbf F(x,y)\cdot \mathrm{d}\mathbf r$ ($L^-$与$L$反向)|

- **对坐标曲线积分的计算方法**
设被积函数$P(x,y),Q(x,y)$，积分弧段L的参数方程为$\begin{cases}x=ϕ(t)\\y=ψ(t)\end{cases}$，当t单调的由$α$到$β$时，曲线上的点$M(x,y)$沿L从起点A到B，且$ϕ^{'2}(t)+ψ^{'2}(t)\neq0$，则曲线积分$$\int_LP(x,y)\mathrm{d}x+Q(x,y)\mathrm{d}y=\int_{α}^{β}\{P[ϕ(t),ψ(t)]ϕ'(t)+Q[ϕ(t),ψ(t)]ψ'(t)\}\mathrm{d}t$$
 
- **两类曲线积分之间的联系**
空间有向曲线弧$Γ$两类曲线积分的关系$$\int_{Γ}P\mathrm{d}x+Q\mathrm{d}y+R\mathrm{d}z=\int_{Γ}(P\cosα+Q\cosβ+R\cosγ) \mathrm{d}s$$其中$α(x,y,z),β(x,y,z),γ(x,y,z)$为有向曲线弧$Γ$在点$(x,y,z)$处的切向量的方向角，也可以用向量的形式表述$$\int_{Γ}\mathbf A\cdot \mathrm{d}\mathbf r=\int_{Γ}\mathbf A\cdot \mathbfτ \mathrm{d}s$$其中$\mathbf A=(P,Q,R),\mathbfτ=(\cosα,\cosβ,\cosγ)$，$\mathrm{d}\mathbf r=\mathbfτ \mathrm{d}s=(\mathrm{d}x,\mathrm{d}y,\mathrm{d}z)$称为有向曲线元



## 格林公式(Green formula)

**平面闭区域D的一些概念**
(1) 若D内任一闭曲线所围成的区域都属于D，则D为单连通区域，否则为复连通区域。
(2) 边界曲线的正向，如图复连通区域，$L$的正向为逆时针方向，$l$的正向为顺时针方向
![闭区域](https://img-blog.csdnimg.cn/20190513171632942.png)

<kbd>**格林公式**</kbd>(Green formula) 设闭区域D由分段光滑曲线L围成$$\iint_D(\dfrac{∂ Q}{∂ x}-\dfrac{∂ P}{∂ y})\mathrm{d}x\mathrm{d}y=\oint_LP\mathrm{d}x+Q\mathrm{d}y$$其中L是D取正向的边界曲线，其中复连通区域L应取全部边界曲线

**平面上曲线积分与积分路径无关的条件**
设区域D为单连通区域，若函数$P(x,y),Q(x,y)$在G内具有一阶==连续偏导数==，L为G内任意闭曲线，则下面的四种说法等价
(1) 在区域D内存在可微函数$u(x,y),使\mathrm{d}u=P\mathrm{d}x+Q\mathrm{d}y,(x,y)\in D$
(2) 在区域内成立$\dfrac{∂ Q}{∂ x}=\dfrac{∂ P}{∂ y}$
(3) 对于区域内的任何光滑曲线$L,均有\oint_LP\mathrm{d}x+Q\mathrm{d}y=0$ (如图$L_1+L_2^-$积分为(4) 对于区域内的任何两点A, B，积分$\int_{L_AB}P\mathrm{d}x+Q\mathrm{d}y$的值只与A, B两点的位置有关，而与$L_{AB}$在区域D内的路径无关
要求的所有条件都要满足，若区域G内含有==奇点==（破坏函数$P,Q,\dfrac{∂ Q}{∂ x},\dfrac{∂ P}{∂ y}$连续性的点），则定理不成立
![保守场](https://img-blog.csdnimg.cn/20190513171853456.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNTE4Mjc3,size_16,color_FFFFFF,t_70 =200x)


<kbd>**曲线积分的基本定理**</kbd>：设$\mathbf F(x,y)=P(x,y)\mathbf i+Q(x,y)\mathbf j$是平面区域G内的一个向量场，若$P,Q$都在G内连续，且存在一个数量函数$f(x,y)$，使得$\mathbf F=∇ f$ (保守场[^6])，则曲线积分$\int_L\mathbf F\cdot \mathrm{d}\mathbf r$在G内与路径无关，且$$\int_L\mathbf F\cdot \mathrm{d}\mathbf r=f(B)-f(A)$$其中L是G内起点为A，终点为B的任意一条分段光滑曲线

## 对面积的曲面积分(第一类曲面积分)
- **引入意义**
面密度为$μ=μ(x,y,z)$的曲面的质量$m=\lim\limits_{λ\to0}\displaystyle\sum_{i=1}^{n}μ(ξ_,η_i,ζ_i)Δ S_i$
![曲面积分](https://img-blog.csdnimg.cn/2019050816314880.png)
- **概念**：设曲面 $Σ$ 是光滑的，函数$f(x,y,z)在Σ$ 上有界，定义$$\iint_{Σ}f(x,y,z)\mathrm{d}s=\lim\limits_{λ\to0}\displaystyle\sum_{i=1}^{n}f(ξ_,η_i,ζ_i)Δ S_i$$ 其中$f(x,y,z)$是被积函数，$Σ$称为积分曲面

- **对面积的曲面积分的计算法**：设积分曲面$Σ$由方程$z=z(x,y)$给出，$Σ在xOy$平面上的投影区域为$D_{xy}$
$$\iint_{Σ}f(x,y,z)\mathrm{d}s=\iint_{d_{xy}}f(x,y,z(x,y))\sqrt{1+z_x^2(x,y)+z_y^2(x,y)} \mathrm{d}x\mathrm{d}y$$如果$Σ由方程x=x(y,z)或y=y(x,z)$给出，也可类似的把曲面积分化成对应的二重积分。
$(\star)$符号 ==$\oiint$== 表示在闭曲面上积分

## 对坐标的曲面积分(第二类曲面积分)
- **有向曲面$Σ$的一些概念**：通常我们遇到的曲面都是双侧的，有上侧和下侧，闭合曲面有外侧和内侧之分，我们取==曲面法向量的方向确定曲面的方向==，若曲面的法向量$\mathbf n$朝上，我们就认为取定曲面的上侧，法向量朝外，我们就认为取定曲面的外侧。

- **引入意义**
设稳定流动(流速与时间无关)不可压缩流体(假定密度为1)的速度场为$\mathbf v(x,y,z)=P(x,y,z)\mathbf i+Q(x,y,z)\mathbf j+R(x,y,z)\mathbf k$，求单位时间流过有向曲面 $Σ$ 指定侧的质量，即流量 $Φ$
![流量](https://img-blog.csdnimg.cn/20190514093143515.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNTE4Mjc3,size_16,color_FFFFFF,t_70 =280x)  ![流量](https://img-blog.csdnimg.cn/20190514093206581.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNTE4Mjc3,size_16,color_FFFFFF,t_70 =250x)
(1) 取$Σ$ 的一小块$Δ S_i$，单位法向量$\mathbf n_i=\cosα_i\mathbf i+\cosβ_i\mathbf j+\cosγ_i\mathbf j$，流量(流体质量)$ΔΦ_i=\mathbf v_i\cdot\mathbf n_iΔ S_i$
(2) 于是$Φ=\displaystyle\sum_{i=1}^{n}Δ Φ_i=\lim\limits_{λ\to0}\displaystyle\sum_{i=1}^{n}[P(ξ_i,η_i,ζ_i)\cosα_i+Q(ξ_i,η_i,ζ_i)\cosβ_i+R(ξ_i,η_i,ζ_i)\cosγ_i]Δ S_i$
(3) $又Δ S_i 在 yOz面的投影(Δ S_i)_{yz}\approx\cosα_iΔ S_i$，其余面的投影类似，所以
$Φ=\lim\limits_{λ\to0}\displaystyle\sum_{i=1}^{n}[P(ξ_i,η_i,ζ_i)(Δ S_i)_{yz}+Q(ξ_i,η_i,ζ_i)(Δ S_i)_{xz}+R(ξ_i,η_i,ζ_i)(Δ S_i)_{xy}]$

- **概念**：设$Σ$为光滑有向曲面，函数$R(x,y,z)在Σ$上有界，定义函数对坐标x,y的区面积积分$$\iint_{Σ}R(x,y,z)\mathrm{d}x\mathrm{d}y=\lim\limits_{λ\to0}\displaystyle\sum_{i=1}^{n}f(ξ_,η_i,ζ_i)(Δ S_i)_{xy} $$其中$R(x,y,z)$叫被积函数，$Σ$叫做积分曲面
(1) 类似还可定义其他坐标轴的曲面积分$$\iint_{Σ}P(x,y,z)\mathrm{d}y\mathrm{d}z=\lim\limits_{λ\to0}\displaystyle\sum_{i=1}^{n}f(ξ_,η_i,ζ_i)(Δ S_i)_{yz} \\ 
\iint_{Σ}Q(x,y,z)\mathrm{d}x\mathrm{d}z=\lim\limits_{λ\to0}\displaystyle\sum_{i=1}^{n}f(ξ_,η_i,ζ_i)(Δ S_i)_{xz}$$以上三个曲面积分也成第二类曲面积分。
(2) 上述流量 $Φ$ 可写为$\iint_{Σ}P(x,y,z)\mathrm{d}y\mathrm{d}z+\iint_{Σ}Q(x,y,z)\mathrm{d}x\mathrm{d}z+\iint_{Σ}R(x,y,z)\mathrm{d}x\mathrm{d}y$，简写为$$\iint_{Σ}P(x,y,z)\mathrm{d}y\mathrm{d}z+Q(x,y,z)\mathrm{d}x\mathrm{d}z+R(x,y,z)\mathrm{d}x\mathrm{d}y$$
也可以写成==向量形式==$$\iint_{Σ}\mathbf v(x,y,z)\cdot \mathrm{d}\mathbf S$$其中$\mathbf v(x,y,z)=P(x,y,z)\mathbf i+Q(x,y,z)\mathbf j+R(x,y,z)\mathbf k$ ，$\mathrm{d}\mathbf S=\mathrm{d}y\mathrm{d}z\mathbf i+\mathrm{d}x\mathrm{d}z\mathbf j+\mathrm{d}x\mathrm{d}y\mathbf k$ 称为有向曲面元。


对坐标曲面积分的部分性质|
:---|
$\iint_{Σ}k\mathbf v\cdot \mathrm{d}\mathbf S=k\iint_{Σ}\mathbf v\cdot \mathrm{d}\mathbf S$|
$\iint_{Σ} (\mathbf v_1± \mathbf v_2)\cdot \mathrm{d}\mathbf S=\iint_{Σ} \mathbf v_1\cdot \mathrm{d}\mathbf S ± \iint_{Σ} \mathbf v_2\cdot \mathrm{d}\mathbf S$|
$\iint_{Σ_1+Σ_2}\mathbf v\cdot \mathrm{d}\mathbf S=\iint_{Σ_1}\mathbf v\cdot \mathrm{d}\mathbf S+\iint_{Σ_2}\mathbf v\cdot \mathrm{d}\mathbf S$  ($Σ_1$与$Σ_2$无公共点)|
$\iint_{Σ^-}\mathbf v\cdot \mathrm{d}\mathbf S=-\iint_{Σ}\mathbf v\cdot \mathrm{d}\mathbf S$ ($Σ^-$与${Σ}$反向)|

- **对坐标曲面积分的计算方法**：设光滑曲面$Σ:z=f(x,y),(x,y)\in D_{xy}, D_{xy}为Σ在xOy$平面上的投影区域，$R(x,y,z)为Σ$上的连续函数，按对坐标曲面积分的定义有
$$\iint_{Σ}R(x,y,z)\mathrm{d}x\mathrm{d}y=±\iint_{d_{xy}}R[x,y,z(x,y)]\mathrm{d}x\mathrm{d}y$$ 等式右端的符号由法向量$\mathbf n与z$轴的夹角$γ$决定，==锐正钝负==，同样可得
$$\iint_{Σ}P(x,y,z)\mathrm{d}y\mathrm{d}z=±\iint_{d_{yz}}R[x(y,z),y,z]\mathrm{d}y\mathrm{d}z \\
\iint_{Σ}Q(x,y,z)\mathrm{d}x\mathrm{d}y=±\iint_{d_{xz}}R[x,y(y,z),z]\mathrm{d}y\mathrm{d}z$$   ![曲面积分](https://img-blog.csdnimg.cn/20190514095219560.png =150x)
- **两类曲面积分之间的联系**
空间有向曲面$Σ$两类曲面积分的关系$$\iint_{Σ}P(x,y,z)\mathrm{d}y\mathrm{d}z=\iint_{Σ}P(x,y,z)\cosα \mathrm{d}s \\
\iint_{Σ}Q(x,y,z)\mathrm{d}x\mathrm{d}y=\iint_{Σ}Q(x,y,z)\cosβ \mathrm{d}s \\
\iint_{Σ}R(x,y,z)\mathrm{d}x\mathrm{d}y=\iint_{Σ}R(x,y,z)\cosγ \mathrm{d}s$$其中$α(x,y,z),β(x,y,z),γ(x,y,z)$为有向曲面$Σ$在点$(x,y,z)$处的切向量的方向角，合并上面的方程得$$\iint_{Σ}P\mathrm{d}y\mathrm{d}z+Q\mathrm{d}x\mathrm{d}z+R\mathrm{d}x\mathrm{d}y=\iint_{Σ}(P\cosα+Q\cosβ+R\cosγ) \mathrm{d}s$$也可以用向量的形式表述$$\iint_{Σ}\mathbf A\cdot \mathrm{d}\mathbf S=\iint_{Σ}\mathbf A\cdot \mathbf n \mathrm{d}s$$其中$\mathbf A=(P,Q,R),\mathbf n=(\cosα,\cosβ,\cosγ)$为有向曲面在点$(x,y,z)$处的单位法向量，$\mathrm{d}\mathbf S=\mathbf n\mathrm{d}s=\mathrm{d}y\mathrm{d}z\mathbf i+\mathrm{d}x\mathrm{d}z\mathbf j+\mathrm{d}x\mathrm{d}y\mathbf k$ 称为有向曲面元。


## 高斯公式(Gauss formula)  
<kbd>高斯公式</kbd>设空间闭区域$Ω$由分片光滑的闭曲面$Σ$所围成，函数$P(x,y,z), Q(x,y,z), R(x,y,z)在Ω$上有连续的一阶偏导数，则有$$\begin{aligned} 
\iiint_{Ω}(\dfrac{∂ P}{∂ x}+\dfrac{∂ Q}{∂ y}+\dfrac{∂ R}{∂ z})\mathrm{d}v&=\oiint_{Σ}P\mathrm{d}y\mathrm{d}z+Q\mathrm{d}x\mathrm{d}z+R\mathrm{d}x\mathrm{d}y \\
&=\oiint_{Σ}(P\cosα+Q\cosβ+R\cosγ) \mathrm{d}s
\end{aligned} $$  $Σ$的方向取外侧，$\cosα,\cosβ,\cosγ$为曲面$Σ$在点$(x,y,z)$处的方向余弦
向量形式为$$\iiint_{Ω}∇\cdot \mathbf A\mathrm{d}v=\oiint_{Σ}\mathbf A\cdot \mathrm{d}\mathbf S=\oiint_{Σ}\mathbf A\cdot \mathbf n \mathrm{d}s$$其中$\mathbf A=(P,Q,R),\mathbf n=(\cosα,\cosβ,\cosγ),\mathrm{d}\mathbf S=\mathbf n\mathrm{d}s=\mathrm{d}y\mathrm{d}z\mathbf i+\mathrm{d}x\mathrm{d}z\mathbf j+\mathrm{d}x\mathrm{d}y\mathbf k$

<kbd>*格林第一公式 + 格林第二公式*</kbd> 设函数$u(x,y,z), v(x,y,z)$在空间闭区域$Ω$上有一阶二阶连续偏导数，则$$
\iiint_{Ω}uΔ v \mathrm{d}x\mathrm{d}y\mathrm{d}z=
\oiint_{Σ}u\dfrac{∂ v}{∂ n}\mathrm{d}s-
\iiint_{Ω}(\dfrac{∂ u}{∂ x}\dfrac{∂ v}{∂ x}+\dfrac{∂ u}{∂ y}\dfrac{∂ v}{∂ y}+\dfrac{∂ u}{∂ z}\dfrac{∂ v}{∂ z})\mathrm{d}x\mathrm{d}y\mathrm{d}z\\
\iiint_{Ω}(uΔ v-vΔ u)\mathrm{d}x\mathrm{d}y\mathrm{d}z=
\oiint_{Σ}(u\dfrac{∂ v}{∂ n}-v\dfrac{∂ u}{∂ n})\mathrm{d}s
$$ 其中$Σ是Ω$的所有边界曲面，$\dfrac{∂ u}{∂ n},\dfrac{∂ v}{∂ n}为u(x,y,z),v(x,y,z)沿Σ$的外法线方向的方向导数，符号$Δ=\dfrac{∂^2}{∂ x^2}+\dfrac{∂^2}{∂ y^2}+\dfrac{∂^2}{∂ z^2}$为拉普拉斯算子[^7]


[^7]: 拉普拉斯算子（Laplace Operator）是n维欧几里德空间中的一个二阶微分算子，定义为梯度($∇ f$)的散度($∇\cdot f$)。拉普拉斯算子也可以推广为定义在黎曼流形上的椭圆型算子，称为拉普拉斯-贝尔特拉米算子。$Δ=∇⋅∇=∇^2$


- **沿任意闭曲面的曲面积分为零的条件**：若空间区域$Ω$内任一闭曲面所围成的区域全属于$Ω$,则称$Ω$为空间==二维单连通域==
<kbd>定理</kbd>：若空间闭区域$Ω$为二维单连通域，函数在闭区域上有一阶连续偏导数，则$Ω$沿任意闭曲面的曲面积分为零的充要条件是$$\dfrac{∂ P}{∂ x}+\dfrac{∂ Q}{∂ y}+\dfrac{∂ R}{∂ z}=0, (x,y,z)\inΩ$$
![单连通区域](https://img-blog.csdnimg.cn/20190514114022197.png) ![曲面积分](https://img-blog.csdnimg.cn/20190514114444749.png =150x)

- **高斯公式的物理意义**[^8]：高斯公式
$$\iiint_{Ω}(\dfrac{∂ P}{∂ x}+\dfrac{∂ Q}{∂ y}+\dfrac{∂ R}{∂ z})\mathrm{d}v=\oiint_{Σ}P\mathrm{d}y\mathrm{d}z+Q\mathrm{d}x\mathrm{d}z+R\mathrm{d}x\mathrm{d}y$$
设在闭区域$Ω$有稳定流动(流速与时间无关)不可压缩流体(假定密度为1)，速度场为$\mathbf v(x,y,z)=P(x,y,z)\mathbf i+Q(x,y,z)\mathbf j+R(x,y,z)\mathbf k$， $Σ$ 是闭区域的边界曲面的外侧，$\mathbf n是Σ在点(x,y,z)$处的单位法向量
(1) 高斯公式右端可解释为单位时间内流向$Σ$指定侧的总==流量==(discharge)或==通量==(flux)
$Φ=\oiint_{Σ}\mathbf v\cdot\mathbf n\mathrm{d}s=\oiint_{Σ}P\mathrm{d}y\mathrm{d}z+Q\mathrm{d}x\mathrm{d}z+R\mathrm{d}x\mathrm{d}y$
当$Φ>0$ 时, 说明流入$Σ$的流体体积少于流出的, 表明$Σ$内有源;
当$Φ>0$ 时, 说明流入$Σ$的流体体积多于流出的, 表明$Σ$内有汇 ;
当$Φ>0$ 时, 说明流入与流出$Σ$的流体体积相等
(2) 由于我们假定流体是不可压缩且稳定的，高斯公式左端可解释为分布在$Ω$内的源头在单位时间内产生或吸收的流体的总质量
(3) 设$Ω$的体积为$V$，令$Ω$缩向一点$M(x,y,z)$，求极限
$(\dfrac{∂ P}{∂ x}+\dfrac{∂ Q}{∂ y}+\dfrac{∂ R}{∂ z})|_M=\lim\limits_{Ω\to M}\dfrac{Φ}{V}$
称$\mathrm{div}\ \mathbf{v}(M)=\dfrac{∂ P}{∂ x}+\dfrac{∂ Q}{∂ y}+\dfrac{∂ R}{∂ z}$为向量场在点M处的通量密度或==散度==(divergence)，在此处为流体在M处的源头强度。
说明: 散度是通量对体积的变化率, 且
$\mathrm{div}\ \mathbf{v}>0$，表明该点处有正源； 
$\mathrm{div}\ \mathbf{v}<0$，表明该点处有负源； 
$\mathrm{div}\ \mathbf{v}=0$，表明该点处无源.
散度绝对值的大小反映了源的强度.
(3) 高斯公式可简写为$\iiint_{Ω}\mathrm{div}\ \mathbf{v} \ \mathrm{d}x\mathrm{d}y\mathrm{d}z=\oiint_{Σ}\mathbf v\cdot\mathbf n\mathrm{d}s$
![流量](https://img-blog.csdnimg.cn/20190514125550365.png =200x)



## 斯托克斯公式(Stokes formula) 
<kbd>斯托克斯公式</kbd>(Stokes formula) 设光滑曲面$Σ$的边界$Γ$是分段光滑曲线,$Σ$的侧与$Γ$的正向符合右手法则,函数$P(x,y,z), Q(x,y,z), R(x,y,z)在Σ$上具有连续一阶偏导数，则有$$
\iint_{Σ}(\dfrac{∂ R}{∂ y}-\dfrac{∂ Q}{∂ z})\mathrm{d}y\mathrm{d}z+
(\dfrac{∂ P}{∂ z}-\dfrac{∂ R}{∂ x})\mathrm{d}x\mathrm{d}z
+(\dfrac{∂ Q}{∂ x}-\dfrac{∂ P}{∂ y})\mathrm{d}x\mathrm{d}y
=\oint_{Γ}P\mathrm{d}x+Q\mathrm{d}y+R\mathrm{d}z$$![右手法则](https://img-blog.csdnimg.cn/20190514142031211.png =150x)  ![斯托克斯公式](https://img-blog.csdnimg.cn/20190514143156414.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNTE4Mjc3,size_16,color_FFFFFF,t_70 =250x)
斯托克斯公式的其他格式为$$
\iint_{Σ}
\begin{vmatrix} 
\mathrm{d}y\mathrm{d}z & \mathrm{d}z\mathrm{d}x &\mathrm{d}x\mathrm{d}y \\ 
\dfrac{∂}{∂ x} & \dfrac{∂}{∂ y} &\dfrac{∂}{∂ z} \\
P & Q &R
\end{vmatrix}=\oint_{Γ}P\mathrm{d}x+Q\mathrm{d}y+R\mathrm{d}z$$ 或 (利用两类曲面积分的关系)$$
\iint_{Σ}
\begin{vmatrix} 
\cosα & \cosβ &\cosγ \\ 
\dfrac{∂}{∂ x} & \dfrac{∂}{∂ y} &\dfrac{∂}{∂ z} \\
P & Q &R
\end{vmatrix}=\oint_{Γ}P\mathrm{d}x+Q\mathrm{d}y+R\mathrm{d}z$$


- **空间曲线积分和路径无关的条件**
设G是空间一维单连通域,函数$P(x,y,z), Q(x,y,z), R(x,y,z)$在G内具有连续一阶偏导数,则下列四个说法等价:
(1) 对G内任意分段光滑闭曲线$Γ$，有$\oint_{Γ}P\mathrm{d}x+Q\mathrm{d}y+R\mathrm{d}z=0$
(2) 对G内任意分段光滑闭曲线$Γ$，有$\oint_{Γ}P\mathrm{d}x+Q\mathrm{d}y+R\mathrm{d}z$与路径无关
(3) 在G内存在某一函数$u(x,y,z),\mathrm{d}u=P\mathrm{d}x+Q\mathrm{d}y+R\mathrm{d}z$，这时可求得$u=\int_{(x_0,y_0,z_0)}^{(x,y,z)}P\mathrm{d}x+Q\mathrm{d}y+R\mathrm{d}z$ 如下图
![原函数](https://img-blog.csdnimg.cn/2019051414551530.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNTE4Mjc3,size_16,color_FFFFFF,t_70 =200x)
(4) 在G内处处有$\dfrac{∂ P}{∂ y}=\dfrac{∂ Q}{∂ x},\dfrac{∂ Q}{∂ z}=\dfrac{∂ R}{∂ y},\dfrac{∂ R}{∂ x}=\dfrac{∂ P}{∂ z}$

- **环流量与旋度[^9]的力学意义**
(1) 由环流量和旋度的定义，斯托克斯公式可简写为$\iint_{Σ}\mathrm{curl}\ \mathbf{A}\cdot\mathbf n\mathrm{d}s=\oint_{Γ}\mathbf A\cdot\mathbfτ \mathrm{d}s$
(2) 向量场$\mathbf A(x,y,z)=P(x,y,z)\mathbf i+Q(x,y,z)\mathbf j+R(x,y,z)\mathbf k$沿闭曲线$Γ$的环流量为$I=\oint_{Γ}\mathbf A\cdot\mathbfτ \mathrm{d}s=\oint_{Γ}\mathbf A\cdot  \mathrm{d}\mathbf r=\oint_{Γ}P\mathrm{d}x+Q\mathrm{d}y+R\mathrm{d}z$
(3) 点M处向量场$\mathbf A$的环流量密度为
$\lim\limits_{r\to0}\dfrac{\oint_{L_r}\mathbf A\cdot  \mathrm{d}\mathbf r}{π r^2}=\lim\limits_{r\to0}\dfrac{\iint_{Σ_r}\mathrm{curl}\ \mathbf{A}\cdot\mathbf n\mathrm{d}s}{π r^2}=\mathrm{curl}\ \mathbf{A}|_M$
(4) 旋度的力学意义：设某刚体绕定轴z转动,角速度为$\mathbfω$, M为刚体上任一点，建立坐标系如图，则$\mathbfω=ω\mathbf k,\mathbf r=(x,y,z)$，点M的线速度为$$\mathbfω=\mathbf v×\mathbf r=\begin{vmatrix}
\mathbf i &\mathbf j &\mathbf k \\
0&0&ω \\
x&y&z
\end{vmatrix}=(-ω y,ω x,0)$$而$$\mathrm{curl}\ \mathbf{v}=∇×\mathbf v=\begin{vmatrix} \mathbf i & \mathbf j &\mathbf k \\ \dfrac{∂}{∂ x} & \dfrac{∂}{∂ y} &\dfrac{∂}{∂ z} \\-ω y & ω x &0\end{vmatrix}=2\mathbfω$$

![旋度](https://img-blog.csdnimg.cn/20190514173946906.png =200x)  ![旋转](https://img-blog.csdnimg.cn/20190514173906412.png =200x)

## 向量场的微积分基本定理总结

定积分基本公式|$$\int_a^bF'(x)\mathrm{d}x=F(b)-F(a)$$
:---|:---
曲线积分的基本公式|$$\int_{L_{AB}}∇ f\cdot \mathrm{d}\mathbf r=f(B)-f(A)$$
格林公式(Green formula)|$$\iint_\mathrm{d}\mathrm{div}\mathbf A\mathrm{d}x\mathrm{d}y=\oint_L\mathbf A\cdot\mathbf n\mathrm{d}s$$
高斯公式(Gauss formula)|$$\iiint_{Ω}\mathrm{div}\mathbf A\mathrm{d}v=\oiint_{Σ}\mathbf A\cdot \mathrm{d}\mathbf S$$
斯托克斯公式(Stokes formula)|$$\iint_{Σ}\mathrm{curl}\ \mathbf{A}\cdot \mathrm{d}\mathbf S=\oint_{Γ}\mathbf A\cdot \mathrm{d}\mathbf r$$

![格林公式](https://img-blog.csdnimg.cn/2019051418320777.png)  ![高斯公式](https://img-blog.csdnimg.cn/20190514183226800.png)  ![斯托克斯公式](https://img-blog.csdnimg.cn/20190514183239529.png)

[^6]:场的定义：对于空间区域G
(1) 任意点M都有一个对应的数量$f(M)$，称为==数量场==(scalar field)
(2) 任意点M都有一个对应的向量$\mathbf F(M)=P(x,y,z)\mathbf i+Q(x,y,z)\mathbf j+R(x,y,z)\mathbf k$，称为==向量场==(vector field)，其中$P,Q,R$为数量场
(3) 若存在数量场$f(M)$和向量场$\mathbf F(M)=∇ f$，则称$\mathbf F$为==势场==(potential field)，$f$为势函数
(4) 若向量场曲线积分$\int_L\mathbf F\cdot \mathrm{d}\mathbf r$在G内与路径无关，则称为==保守场==(conservative field)
(5) 若向量场的散度$\mathrm{div}\ \mathbf{A}$处处为零，则称为==无源场==(field without sources)
(6) 若向量场的旋度$\mathrm{curl}\ \mathbf{A}$处处为零，则称为==无旋场==(irrotational field)
(7) 一个无源且无旋的向量场称为==调和场==(harmonic field)

[^8]: 设有向量场$\mathbf A=P(x,y,z)\mathbf i+Q(x,y,z)\mathbf j+R(x,y,z)\mathbf k,Σ$是向量场内的一片有向曲面，$\mathbf n是Σ在点(x,y,z)$处的单位法向量
(1) 则定义积分$Φ=\iint_{Σ}\mathbf A\cdot\mathbf n\mathrm{d}s=\oiint_{Σ}P\mathrm{d}y\mathrm{d}z+Q\mathrm{d}x\mathrm{d}z+R\mathrm{d}x\mathrm{d}y$ 称为向量场通过有向曲面的==通量==(flux)或==流量==(discharge)
(2) 定义$\mathrm{div}\ \mathbf{A}=\dfrac{∂ P}{∂ x}+\dfrac{∂ Q}{∂ y}+\dfrac{∂ R}{∂ z}=∇\cdot\mathbf A$为向量场A的==散度==(divergence)

[^9]: 设有向量场$\mathbf A=P(x,y,z)\mathbf i+Q(x,y,z)\mathbf j+R(x,y,z)\mathbf k,Γ$是向量场内的一条分段光滑的有向闭合曲线，$\mathbfτ是Γ在点(x,y,z)$处的单位切向量
(1) 则定义积分$I=\oint_{Γ}\mathbf A\cdot\mathbfτ \mathrm{d}s=\oint_{Γ}\mathbf A\cdot  \mathrm{d}\mathbf r=\oint_{Γ}P\mathrm{d}x+Q\mathrm{d}y+R\mathrm{d}z$ 称为向量场沿闭曲线的==环流量==(circulation)
(2) 定义$\mathrm{curl}\ \mathbf{A}=(\dfrac{∂ R}{∂ y}-\dfrac{∂ Q}{∂ z})\mathbf i+(\dfrac{∂ P}{∂ z}-\dfrac{∂ R}{∂ x})\mathbf j+(\dfrac{∂ Q}{∂ x}-\dfrac{∂ P}{∂ y})\mathbf k$为向量场A的==旋度==(rotation;curl)
其他形式为$\mathrm{curl}\ \mathbf{A}=∇×\mathbf A=\begin{vmatrix} \mathbf i & \mathbf j &\mathbf k \\ \dfrac{∂}{∂ x} & \dfrac{∂}{∂ y} &\dfrac{∂}{∂ z} \\P & Q &R\end{vmatrix}$




