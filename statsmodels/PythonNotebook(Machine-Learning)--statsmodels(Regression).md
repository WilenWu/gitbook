---
ID: 171d41b5d411a25392c1a3cfe7ed7891
title: Python手册(Machine Learning)--statsmodels(Regression)
tags: [python,机器学习,statsmodels,回归]
mathjax: true
copyright: true
date: 2018-12-19 16:40:34
categories: [python,Machine Learning]
sticky: false
---
# [Linear Regression(线性回归)](https://www.statsmodels.org/stable/regression.html)


`import statsmodels.api as sm`
适用于自变量X和因变量Y为线性关系，具体来说，画出散点图可以用一条直线来近似拟合。一般线性模型要求观测值之间相互独立、残差(因变量)服从正态分布、残差(因变量)方差齐性
统计模型被假定为 $Y=Xβ+μ,  μ\sim N(0,Σ)$

<!-- more -->

**Model Classes**
[Model Classes][Model Classes]|模型类
:------|:------
OLS	|一个简单的普通最小二乘模型。
GLS|具有一般协方差结构的广义最小二乘模型
WLS|具有对角但非标识协方差结构的回归模型
GLSAR|具有AR（p）协方差结构的回归模型。
yule_walker|使用Yule-Walker方程从序列X估计AR（p）参数
QuantReg|分位数回归
RecursiveLS|递归最小二乘法

[Model Classes]: http://www.statsmodels.org/stable/regression.html#model-classes

Methods|desc
:---|:---
fit()|Full fit of the model
from_formula(_formula_, _data_)|Create a Model from a formula and dataframe
predict(_params_)|Return linear predicted values from a design matrix.
score(_params_)|Evaluate the score function at a given point


Attributes|desc
:---|:---
df_model|模型自由度，定义为回归矩阵的秩，如果包括常数则减1
df_resid|剩余自由度，定义为观察数减去回归矩阵的rank

**Results Classes**

**Results Classes**|结果类
:---|:---
RegressionResults|总结了线性回归模型的拟合
OLSResults|OLS模型的结果类
PredictionResults|	
QuantRegResults|QuantReg模型的结果实例

Methods|desc
:---|:---
aic(), bic(), bse()...|
cov_params()|返回方差/协方差矩阵
eigenvals()|返回按降序排序的特征值
fvalue(), pvalues(), f_pvalue(), tvalues()|
f_test(r_matrix), t_test()|F检验，t检验
get_prediction()|计算预测结果
save(fname), load(fname)|保存pickle，加载（类方法）

**Examples** 
```python
# Load modules and data
In [1]: import numpy as np
In [2]: import statsmodels.api as sm
In [3]: spector_data = sm.datasets.spector.load()
In [4]: spector_data.exog = sm.add_constant(spector_data.exog, prepend=False)

# Fit and summarize OLS model
In [5]: mod = sm.OLS(spector_data.endog, spector_data.exog)
In [6]: res = mod.fit()
In [7]: res.summary()
```

# [Generalized Linear(广义线性回归)](http://www.statsmodels.org/stable/glm.html#module-reference)


是为了克服线性回归模型的缺点出现的，是线性回归模型的推广。首先自变量可以是离散的，也可以是连续的。离散的可以是0-1变量，也可以是多种取值的变量。广义线性模型又取消了对残差(因变量)服从正态分布的要求。残差不一定要服从正态分布，可以服从二项、泊松、负二项、正态、伽马、逆高斯等分布，这些分布被统称为指数分布族。
与线性回归模型相比较，有以下推广：
- 随机误差项不一定服从正态分布，可以服从二项、泊松、负二项、正态、伽马、逆高斯等分布，这些分布被统称为指数分布族。
- 引入link函数$g(\cdot )$。因变量和自变量通过联接函数产生影响。根据不同的数据，可以自由选择不同的模型。大家比较熟悉的Logit模型就是使用Logit联接、随机误差项服从二项分布得到模型。

The statistical model for each observation  ii  is assumed to be
$Y_i ∼F_{EDM}(⋅|θ,ϕ,w_i)$ and  $μ_i=E[Y_i|x_i]=g^{-1}(x_i β)$

**Model Classes**
`GLM(endog, exog, family=None)`
> Parameters:	
endog (array-like)
exog (array-like)
family (family class instance) – The default is Gaussian

Methods|desc
:---|:---
fit()|Full fit of the model
from_formula(_formula_, _data_)|Create a Model from a formula and dataframe
predict(_params_)|Return linear predicted values from a design matrix.
score(_params_)|Evaluate the score function at a given point

**Results Classes**
**Results Classes**|结果类
:---|:---
GLMResults|包含GLM结果的类。
PredictionResults|	

**Families**
Families|desc
:---|:---
Family(link,variances)|单参数指数族的父类。
Binomial(link=None)|二项式指数族分布。
Gamma(link=None)|Gamma指数族分布。
Gaussian(link=None)|高斯指数族分布。
InverseGaussian(link=None)|InverseGaussian指数族。
NegativeBinomial(link=None,alpha=None)|负二项指数族。
Poisson(link=None)|泊松指数族。
Tweedie(link=None,var_power=None)|Tweedie。

**Link Functions**
```python
>>> sm.families.family.<familyname>.links
```
Link Functions|desc
:---|:---
Link|单参数指数族的通用链接函数。
CDFLink([DBN])|使用scipy.stats发行版的CDF
CLogLog|互补的log-log变换
Log|对数转换
Logit|logit变换
NegativeBinomial([α])|负二项式link函数
Power([power])|指数转换
cauchy()|Cauchy(标准Cauchy CDF)变换
cloglog|CLogLog转换link函数。
identity()|identity转换
inverse_power()|逆变换
inverse_squared()|逆平方变换
nbinom([α])|负二项式link函数。
probit([DBN])|probit(标准普通CDF)变换

**Examples** 
```python
In [1]: import statsmodels.api as sm
In [2]: data = sm.datasets.scotland.load()
In [3]: data.exog = sm.add_constant(data.exog)
# Instantiate a gamma family model with the default link function.
In [4]: gamma_model = sm.GLM(data.endog, data.exog, family=sm.families.Gamma())
In [5]: gamma_results = gamma_model.fit()
In [6]: print(gamma_results.summary())
In [7]: gamma_results = gamma_model.fit()
In [8]: gamma_results.params
```

# [Generalized Estimating Equations(广义估计方程)](http://www.statsmodels.org/stable/gee.html)

实际工作中一些资料由于部分观察值含有非独立或相关的信息，不能用传统的一般线性（或广义线性进行分析），故而发展出了广义估计方程。如纵向数据，重复测量数据，整群抽样设计资料，聚集性资料或是多次层次系统结构资料。
> 纵向数据(longitudinal data)：是按照时间顺序对个体某指标进行重复测量得到的数据，同一对象的多次测量成相关性（倾向），如儿童的生长检测资料



Model Classes|模型类
:------|:------
GEE|用广义估计方程（GEE）估计边际回归模型。
**Results Classes**|结果类
GEEResults|总结了使用GEE的边际回归模型的适合性。
GEEMargins|	与GEE匹配的回归模型的估计边际效应。
**Dependence Structures**|依赖结构
CovStruct|分组数据的相关性和协方差结构的基类。
Autoregressive|一阶自回归工作依赖结构。
Exchangeable|可交换的工作依赖结构。
GlobalOddsRatio|估算具有序数或名义数据的GEE的全局优势比。
Independence|独立工作依赖结构。
Nested|嵌套的工作相关结构。

```python
In [1]: import statsmodels.api as sm
In [2]: import statsmodels.formula.api as smf
In [3]: data = sm.datasets.get_rdataset('epil', package='MASS').data
In [4]: fam = sm.families.Poisson()
In [5]: ind = sm.cov_struct.Exchangeable()
In [6]: mod = smf.gee("y ~ age + trt + base", "subject", data,
   ...:               cov_struct=ind, family=fam)
In [7]: res = mod.fit()
In [8]: print(res.summary())
```

# [Robust Linear Models(稳健的线性模型)](http://www.statsmodels.org/stable/rlm.html)

稳健回归(robust regression)是将稳健估计方法用于回归模型，以拟合大部分数据存在的结构，同时可识别出潜在可能的离群点、强影响点或与模型假设相偏离的结构。当误差服从正态分布时，其估计几乎和最小二乘估计一样好，而最小二乘估计条件不满足时，其结果优于最小二乘估计。

Model Classes|模型类
:------|:------
RLM|稳健的线性模型
**Results Classes**|结果类
RLMResults|	包含RLM结果的类
**Norms**|
AndrewWave|安德鲁的M估计浪潮。
Hampe|Hampel函数用于M估计。
HuberT|胡伯的T为M估计。
LeastSquares|M估计的最小二乘ρ及其派生函数。
RamsayE|Ramsay的Ea用于M估计。
RobustNorm|用于稳健回归的规范的父类。
TrimmedMean|用于M估计的修正均值函数。
TukeyBiweight|Tukey的M估计的权重函数。
estimate_location|使用self.norm和当前的尺度估计量的位置M估计量。
**Scale**|
Huber|Huber提出的联合估计地点和规模的建议2。
HuberScale|Huber用于拟合鲁棒线性模型的缩放比例。
mad|沿数组给定轴的中值绝对偏差
hubers_scale|Huber用于拟合鲁棒线性模型的缩放比例。

```python
# Load modules and data
In [1]: import statsmodels.api as sm
In [2]: data = sm.datasets.stackloss.load()
In [3]: data.exog = sm.add_constant(data.exog)

# Fit model and print summary
In [4]: rlm_model = sm.RLM(data.endog, data.exog,M=sm.robust.norms.HuberT())
In [5]: rlm_results = rlm_model.fit()
In [6]: print(rlm_results.params)
[-41.0265   0.8294   0.9261  -0.1278]
```
# [Linear Mixed Effects Models(线性混合效应模型)](http://www.statsmodels.org/stable/mixed_linear.html)

参考链接：https://blog.csdn.net/sinat_26917383/article/details/51636011

在线性模型中加入随机效应项，消了观测值之间相互独立和残差(因变量)方差齐性的要求。


Model Classes|模型类
:------|:------
MixedLM|
**Results Classes**|结果类
MixedLMResults|

```python
In [1]: import statsmodels.api as sm
In [2]: import statsmodels.formula.api as smf
In [3]: data = sm.datasets.get_rdataset("dietox", "geepack").data
In [4]: md = smf.mixedlm("Weight ~ Time", data, groups=data["Pig"])
In [5]: mdf = md.fit()
In [6]: print(mdf.summary())
```


# [Regression with Discrete Dependent Variable(具有离散因变量的回归)](http://www.statsmodels.org/stable/discretemod.html)


Model Classes|desc
:---|:---
Logit(endog,exog,**kwargs)|二元logit模型
Probit(endog,exog,**kwargs)|二元Probit模型
MNLogit(endog,exog,**kwargs)|多项logit模型
Poisson(endog, exog[, offset, exposure, missing])|计数数据的泊松模型
NegativeBinomial(endog,exog [,...])|计数数据的负二项模型
NegativeBinomialP(endog,exog [,p,offset,...])|计数数据的广义负二项(NB-P)模型
GeneralizedPoisson(endog,exog [,p,offset,...])|计数数据的广义Poisson模型
ZeroInflatedPoisson(endog,exog [,...])|用于计数数据的泊松零膨胀模型
ZeroInflatedNegativeBinomialP(endog,exog [,...])|计数数据的零膨胀广义负二项模型
ZeroInflatedGeneralizedPoisson(endog,exog)|计数数据的零膨胀广义Poisson模型
**Results Classes**|结果类
LogitResults（model，mlefit [，cov_type，...]）	|Logit Model的结果类
ProbitResults（model，mlefit [，cov_type，...]）	|Probit模型的结果类
CountResults（model，mlefit [，cov_type，...]）	|计数数据的结果类
MultinomialResults（model，mlefit [，...]）	|多项数据的结果类
NegativeBinomialResults（model，mlefit [，...]）	|NegativeBinomial 1和2的结果类
GeneralizedPoissonResults（model，mlefit [，...]）	|广义泊松分析的结果类
ZeroInflatedPoissonResults（model，mlefit [，...]）	|零膨胀泊松的结果类
ZeroInflatedNegativeBinomialResults	|零膨胀一般化负二项式的结果类
ZeroInflatedGeneralizedPoissonResults|	零膨胀广义泊松的结果类

DiscreteModel是所有离散回归模型的超类。估算结果作为其中一个子类的实例返回 DiscreteResults。模型的每个类别（二进制，计数和多项）都有其自己的中级模型和结果类。这个中间类主要是为了方便实现由DiscreteModel和 定义的方法和属性DiscreteResults。

DiscreteModel（endog，exog，** kwargs）	|抽象类用于离散选择模型。
:------|:------
DiscreteResults（model，mlefit [，cov_type，...]）	|离散因变量模型的结果类。
BinaryModel（endog，exog，** kwargs）	|
BinaryResults（model，mlefit [，cov_type，...]）	|二进制数据的结果类
CountModel（endog，exog [，offset，exposure，...]）	|
MultinomialModel（endog，exog，** kwargs）	|
GenericZeroInflated（endog，exog [，...]）	|Generiz Zero计数数据的充气模型

**Examples**
```python
# Load the data from Spector and Mazzeo (1980)
In [1]: spector_data = sm.datasets.spector.load()
In [2]: spector_data.exog = sm.add_constant(spector_data.exog)
# Logit Model
In [3]: logit_mod = sm.Logit(spector_data.endog, spector_data.exog)
In [4]: logit_res = logit_mod.fit()
Optimization terminated successfully.
 Current function value: 0.402801
 Iterations 7
In [5]: print(logit_res.summary())
```

# [Generalized Linear Mixed Effects Models(广义线性混合效应模型)](http://www.statsmodels.org/stable/mixed_glm.html)

广义线性混合效应模型是混合效应模型的推广

Model Classes|模型类
:------|:------
BinomialBayesMixedGLM|用贝叶斯方法拟合广义线性混合模型。
PoissonBayesMixedGLM|用贝叶斯方法拟合广义线性混合模型。
**Results Classes**|结果类
BayesMixedGLMResults|



