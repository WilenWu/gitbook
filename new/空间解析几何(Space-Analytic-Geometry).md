---
title: 空间解析几何(Space Analytic Geometry)
tags: [R]
mathjax: false
copyright: true
date: 2019-05-03 11:22:02
categories: [R,Space Analytic Geometry]
sticky: false
---
<!-- more -->
# 向量代数(Vector Algebra)
## 空间直角坐标系(space rectangular coordinate system)
(1) 过空间中一定点，作三条互相垂直的数轴构成的坐标系称为
空间直角坐标系.
(2) 有序三元数组$(x,y,z)$称为点M的坐标(coordinate)，也记为$M(x,y,z)$
(3) 空间中的两点$M_1(x_1,y_1,z_1),M_1(x_1,y_1,z_1)$ 间距离(distance)公式
$|M_1M_2|=\sqrt{(x_1-x_2)^2+(y_1-y_2)^2+(z_1-z_2)^2}$
![坐标系](https://img-blog.csdnimg.cn/20190513144857921.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNTE4Mjc3,size_16,color_FFFFFF,t_70 =280x) ![点M](https://img-blog.csdnimg.cn/20190513144917314.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNTE4Mjc3,size_16,color_FFFFFF,t_70 =250x)
## 向量和线性运算 (vector and linear operation)
**向量的记法**：加粗(如 **a、b、u、v**)或者加小箭头（如 $\vec a,\vec b, \overrightarrow{AB}$）
**向量的大小**：叫做向量的模(modulus)，记作 **|a|** ,$|\vec b|, |\overrightarrow{AB}|$，模等于1的向量叫做单位向量(unit vector)记作 $\vec e$ 或**e**，模等于0的叫做零向量(zero vector)，记作 $\vec 0$ 或 **0**
**向量夹角**(vector angel)：$(\widehat{\mathbf a,\mathbf b})=\varphi,\varphi\in[0,\pi]$


向量运算|表达式(a,b为向量)
:---|:---
交换律|a+b=b+a
结合律|a+(b+c)=(a+b)+c
数乘|λ(μa)=μ(λa)=(λμ)a<br>(λ+μ)a=λa+μa<br>λ(a+b)=λa+λb
![加法](https://img-blog.csdnimg.cn/20190513150227321.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNTE4Mjc3,size_16,color_FFFFFF,t_70 =500x)



**坐标表示**：
(1) $\mathbf a\parallel \mathbf b\iff \exists!\lambda,使\mathbf b=\lambda \mathbf a$
(2) 点M，向量$\mathbf r$与三个有序实数对一一对应关系
$M\longleftrightarrow \mathbf r=\overrightarrow{OM}=x\mathbf i+y\mathbf j+z\mathbf k\longleftrightarrow (x,y,z)$
![向量](https://img-blog.csdnimg.cn/20190513150152252.png =250x)

坐标运算|$\mathbf a=(x_1,y_1,z_1),\mathbf b=(x_2,y_2,z_2),\mathbf c=(x_3,y_3,z_3)\\ \mathbf r=(x,y,z)$
:---|:---
向量的模(modulus)|$\mid \mathbf r\mid=\sqrt{x^2+y^2+z^2}$
方向角余弦(direction cosine)|$(\cosα,\cosβ,\cosγ)=\dfrac{1}{\mathbf r}(x,y,z)=\mathbf e_r \\ \cos^2α+\cos^2β+\cos^2γ=1$
向量在坐标轴上的投影(projection)|$(x_1,y_1,z_1)=(\mathrm{Prj}_x\mathbf a,\mathrm{Prj}_y\mathbf a,\mathrm{Prj}_z\mathbf a)或\\ (x_1,y_1,z_1)=(\ (\mathbf a)_x,(\mathbf a)_y,(\mathbf a)_z\ )$
加法(plus)|$\mathbf a+\mathbf b=(x_1+x_2,y_1+y_2,z_1+z_2)$
数乘(scalar-multiplication)|$λ \mathbf a=(λ x_1,λ y_1,λ z_1)$
数量积(dot product)|$\mathbf a\cdot\mathbf b=\mid \mathbf a\mid\mid \mathbf b\mid\cos(\widehat{\mathbf a,\mathbf b})=\mid \mathbf a\mid\mathrm{Prj}_a\mathbf b=x_1x_2+y_1y_2+z_1z_2$
向量积(cross product)|$\mathbf a\times\mathbf b=\begin{vmatrix} \mathbf i&\mathbf j&\mathbf k  \\ x_1 &y_1&z_1\\  x_2 &y_2&z_2\end{vmatrix}$
混合积(mixed product)|$[\mathbf a\mathbf b\mathbf c]=(\mathbf a\times\mathbf b)\cdot\mathbf c=\begin{vmatrix}x_1 &y_1&z_1  \\ x_2 &y_2&z_2\\  x_3&y_3&z_3\end{vmatrix}$<br>几何意义：平行六面体的体积
![方向角](https://img-blog.csdnimg.cn/20190502190928772.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNTE4Mjc3,size_16,color_FFFFFF,t_70 =150x)![混合积](https://img-blog.csdnimg.cn/20190503092211787.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNTE4Mjc3,size_16,color_FFFFFF,t_70 =150x)
**结论**
(1) $\mathbf a\cdot\mathbf b=0 \iff \mathbf a\bot\mathbf b$
(2) $\mathbf a \times\mathbf b=0 \iff \mathbf a\parallel\mathbf b$
(2) $[\mathbf a\mathbf b\mathbf c]=0 \iff \mathbf a,\mathbf b,\mathbf c\ 共面$
# 空间解析几何(Space Analytic Geometry)
## 平面及其方程(plane and its equation)
(1) 点法式方程：法向量(normal vector) $\mathbf n\cdot\overrightarrow{M_0M}=0$
$\implies A(x-x_0)+B(y-y_0)+C(z-z_0)=0$
(2) 平面一般方程：$Ax+By+Cz+D=0$
(3) 平面的截距方程(intercept form)：$\dfrac{x}{a}+\dfrac{y}{b}+\dfrac{z}{c}=0$
(4) 两平面的夹角(included angle)：两平面法线(normal line)的夹角 $\cos\theta=|\cos(\widehat{\mathbf n_1,\mathbf n_2})|$

## 空间直线及其方程(space line and its equation)
(1) 直线的一般方程$\begin{cases} A_1x+B_1y+C_1z+D_1=0\\ A_2x+B_2y+C_2z+D_2=0 \end{cases}$
(2) 直线的对称式方程(点向式方程)：方向向量(direction vector) $\mathbf s\times\overrightarrow{M_0M}=0$
$\implies \dfrac{x-x_0}{m}= \dfrac{y-y_0}{n}= \dfrac{z-z_0}{p}$
(3) 直线的参数方程：$\begin{cases}x=x_0+mt \\y=y_0+nt\\z=z_0+pt\end{cases}$
(4) 两直线的夹角：方向向量的夹角 $\cos\varphi=|\cos(\widehat{\mathbf s_1,\mathbf s_2})|$
(5) 直线与平面的夹角：直线与在平面上投影直线的夹角 $\sin\varphi=|\cos(\widehat{\mathbf s,\mathbf n})|$

## 曲面及其方程(surface and its equation)
曲面的一般方程 $F(x,y,z)=0$
曲面参数方程 $\begin{cases}x=x(s,t)\\ y=y(s,t)\\ z=z(s,t) \end{cases}$
- **旋转曲面**(surface of revolution)：旋转曲线和定制线依次叫做曲面的母线(generating line)和轴(axis)。
(1) 绕z轴的方程$f(\pm\sqrt{x^2+y^2},z)=0$，x轴、y轴同理
(2) 圆锥曲面(conic surface)：$z^2=a^2(x^2+y^2),a=\cot\alpha$
(3) 双曲面(hyperboloid)：$xOz$坐标面上的双曲线$\dfrac{x^2}{a^2}-\dfrac{z^2}{c^2}=1$
旋转单叶双曲面：（绕z轴旋转）$\dfrac{x^2+y^2}{a^2}-\dfrac{z^2}{c^2}=1$
旋转双叶双曲面：（绕x轴旋转）$\dfrac{x^2}{a^2}-\dfrac{y^2+z^2}{c^2}=1$
![圆锥曲面](https://img-blog.csdnimg.cn/20190503103358420.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNTE4Mjc3,size_16,color_FFFFFF,t_70 =150x)![双曲面](https://img-blog.csdnimg.cn/20190503103458106.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNTE4Mjc3,size_16,color_FFFFFF,t_70 =400x)

- **柱面**(cylinder)：直线L（母线）沿曲线C（准线）平行移动形成的轨迹
一般的只含$x,y$而缺$z$的方程$F(x,y)=0$表示母线平行于z轴的柱面，其准线是$xOy$平面上的曲线$C:F(x,y)=0$，x,y轴类似。

-  **二次曲面**(quadric surface)：与曲线类似，我们把三元二次方程形成的曲面叫做二次曲面，平面称为一次曲面。
(1) 椭圆锥面(elliptic cone) $\dfrac{x^2}{a^2}+\dfrac{y^2}{b^2}=z^2$
(2) 椭球面(ellipsoid) $\dfrac{x^2}{a^2}+\dfrac{y^2}{b^2}+\dfrac{z^2}{c^2}=1$
![托圆锥面](https://img-blog.csdnimg.cn/20190503105518870.png =150x)![椭球面](https://img-blog.csdnimg.cn/20190503105617304.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNTE4Mjc3,size_16,color_FFFFFF,t_70 =200x)
(3) 单叶双曲面(hyperboloid of one sheet) $\dfrac{x^2}{a^2}+\dfrac{y^2}{b^2}-\dfrac{z^2}{c^2}=1$
(4) 双叶双曲面(hyperboloid of two sheets) $\dfrac{x^2}{a^2}-\dfrac{y^2}{b^2}-\dfrac{z^2}{c^2}=1$
(5) 椭圆抛物面(elliptic paraboloid) $\dfrac{x^2}{a^2}+\dfrac{y^2}{b^2}=z$
(6) 双曲抛物面(hyperbolic paraboloid)（马鞍面） $\dfrac{x^2}{a^2}-\dfrac{y^2}{b^2}=z$
![椭圆抛物面](https://img-blog.csdnimg.cn/20190503105707600.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNTE4Mjc3,size_16,color_FFFFFF,t_70 =150x)![马鞍面](https://img-blog.csdnimg.cn/20190503105748794.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNTE4Mjc3,size_16,color_FFFFFF,t_70 =200x) 
(7) 椭圆柱面(elliptic cylinder) $\dfrac{x^2}{a^2}+\dfrac{y^2}{b^2}=1$
(8) 双曲柱面(hyperbolic cylinder) $\dfrac{x^2}{a^2}-\dfrac{y^2}{b^2}=1$
(9) 抛物柱面(parabolic cylinder) $x^2=ay$

## 空间曲线及其方程(space curve and its equation)
(1) 空间曲线的一般方程 $\begin{cases}F(x,y,z)=0\\ G(x,y,z)=0 \end{cases}$
(2) 曲线参数方程 $\begin{cases}x=x(t)\\ y=y(t)\\ z=z(t) \end{cases}$
==螺旋线==(helix) $\begin{cases}x=a\cos\omega t\\ y=a\sin\omega t\\ z=vt \end{cases}$ 或 $\begin{cases}x=a\cos\theta\\ y=a\sin\theta\\ z=b\theta\end{cases}$
![螺旋线](https://img-blog.csdnimg.cn/20190503133609228.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQxNTE4Mjc3,size_16,color_FFFFFF,t_70 =150x)
(3) 空间曲线在坐标面上的投影
曲线C一般方程消去z得到$H(x,y)=0$，由上节知道这是母线平行于z轴的柱面，曲线C的所有点满足方程，都在柱面上，此柱面叫做曲线C在坐标平面$xOy$上的投影柱面，投影曲线方程为$\begin{cases}H(x,y)=0\\ z=0 \end{cases}$，其余坐标面类似。



