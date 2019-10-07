---
ID: c6ea01c9b1d2b08cda33cc8ffa59db38
title: Python手册(Machine Learning)--statsmodels(Contingency Tables and Multiple Imputation)
tags: [python,机器学习,statsmodels,列联表,多重插补]
mathjax: true
copyright: true
date: 2018-12-19 16:59:00
categories: [python,Machine Learning]
sticky: false
---
## [Contingency Tables(列联表)](http://www.statsmodels.org/stable/contingency_tables.html)

Statsmodels支持各种分析列联表的方法，包括评估独立性，对称性，同质性的方法，以及处理来自分层人群的表集合的方法。

这里描述的方法主要用于双向表。可以使用对数线性模型分析多路表。Statsmodels目前没有statsmodels.genmod.GLM用于对数线性建模的专用API，但Poisson回归可用于此目的。

`from statsmodels import stats`

<!-- more -->

类|说明
:------|:------
Table|双向应变表列联表
Table2x2|可以在2x2列联表上执行分析
SquareTable|分析方形列联表的方法
StratifiedTable|分析2×2列联表的集合
mcnemar|McNemar同质性测试
cochrans_q|Cochran对相同二项式比例的Q检验

statsmodels.stats.Table是使用列联表的最基本的类。我们可以Table直接从任何包含列联表单元格计数的矩形数组对象创建对象：
```python
In [1]: import numpy as np
In [2]: import pandas as pd
In [3]: import statsmodels.api as sm
In [4]: df = sm.datasets.get_rdataset("Arthritis", "vcd").data
In [5]: tab = pd.crosstab(df['Treatment'], df['Improved'])
In [6]: tab = tab.loc[:, ["None", "Some", "Marked"]]
In [7]: table = sm.stats.Table(tab)
```
或者，我们可以传递原始数据，让Table类为我们构建单元格数组：
```python
In [8]: table = sm.stats.Table.from_data(df[["Treatment", "Improved"]])
```

### Independence(独立性)
独立性(Independence)是行和列因子独立出现的属性。联合(Association)缺乏独立性。如果联合分布是独立的，则可以将其写为行和列边缘分布的外积

$P_ {ij} = \sum_k P_ {ij} \cdot \sum_k P_ {kj}$ 

- 我们可以为我们观察到的数据获得最佳拟合的独立分布，然后查看识别最强烈违反独立性的特定残差
```python
In [9]: print(table.table_orig)
Improved   Marked  None  Some
Treatment                    
Placebo         7    29     7
Treated        21    13     7

In [10]: print(table.fittedvalues)
Improved      Marked  None      Some
Treatment                           
Placebo    14.333333  21.5  7.166667
Treated    13.666667  20.5  6.833333

In [11]: print(table.resid_pearson)
Improved     Marked      None      Some
Treatment                              
Placebo   -1.936992  1.617492 -0.062257
Treated    1.983673 -1.656473  0.063758
```
- 如果表的行和列是无序的（即名义变量，nominal factors），那么正式评估独立性的最常用方法是使用Pearson的$\chi^2$统计。
```python
In [12]: rslt = table.test_nominal_association()

In [13]: print(rslt.pvalue)
0.0014626434089526352

In [14]: print(table.chi2_contribs)
Improved     Marked      None      Some
Treatment                              
Placebo    3.751938  2.616279  0.003876
Treated    3.934959  2.743902  0.004065
```
- 对于有序行和列因子(factors)的表，我们可以通过线性相关检验，以获得更多权重来对抗关于排序的替代假设。线性相关检验的统计量为
$\sum_k r_i c_j T_ {ij}$

$r_i ,c_j$是行和列分数。通常将这些分数设置为序列0,1，.... 
这给出了Cochran-Armitage趋势测试。
```python
In [15]: rslt = table.test_ordinal_association()
In [16]: print(rslt.pvalue)
0.023644578093923983
```
- 我们可以评估再 $r \times x$ 表中的关联，通过构建一系列$2 \times 2$表格，并计算它们的比值比(OR)。有两种方法可以做到这一点。从相邻行和列类别的本地优势比(**local odds ratios**)来构建$2 \times 2$表。
```python
In [17]: print(table.local_oddsratios)
Improved     Marked      None  Some
Treatment                          
Placebo    0.149425  2.230769   NaN
Treated         NaN       NaN   NaN

In [18]: taloc = sm.stats.Table2x2(np.asarray([[7, 29], [21, 13]]))
In [19]: print(taloc.oddsratio)
0.14942528735632185

In [20]: taloc = sm.stats.Table2x2(np.asarray([[29, 7], [13, 7]]))
In [21]: print(taloc.oddsratio)
2.230769230769231
```
- 也可以通过在每个可能的点上对行和列因子进行二分法的累积比值比(**cumulative odds ratios**)来构建$2 \times 2$表。
```python
In [22]: print(table.cumulative_oddsratios)
Improved     Marked      None  Some
Treatment                          
Placebo    0.185185  1.058824   NaN
Treated         NaN       NaN   NaN

In [23]: tab1 = np.asarray([[7, 29 + 7], [21, 13 + 7]])
In [24]: tacum = sm.stats.Table2x2(tab1)
In [25]: print(tacum.oddsratio)
0.18518518518518517

In [26]: tab1 = np.asarray([[7 + 29, 7], [21 + 13, 7]])
In [27]: tacum = sm.stats.Table2x2(tab1)
In [28]: print(tacum.oddsratio)
1.0588235294117647
```
- 马赛克图(mosaic plot)是一种非正式评估双向表中依赖性的图形方法。
```python
from statsmodels.graphics.mosaicplot import mosaic
mosaic(data)
```
### Symmetry and homogeneity(对称性和同质性)

Symmetry(对称性) is the property
 that $P_{i,j}=P_{j,i}$  for every i and j。 
 Homogeneity(同质性)是行因子和列因子的边际分布相同的特性
meaning that  $\sum_j P_ {ij} = \sum_j P_ {ji}$ for all i
> 注意，P (and T)必须是正方形，行和列类别必须相同，并且必须以相同的顺序出现。

为了说明，我们加载数据集，创建列联表，并计算行和列边距(the row and column margins)。本`Table`类包含分析方法$r \times c$列联表。下面加载的数据集包含人们左眼和右眼视敏度的评估。我们首先加载数据并创建一个列联表。
```python
In [29]: df = sm.datasets.get_rdataset("VisualAcuity", "vcd").data
In [30]: df = df.loc[df.gender == "female", :]
In [31]: tab = df.set_index(['left', 'right'])
In [32]: del tab["gender"]
In [33]: tab = tab.unstack()
In [34]: tab.columns = tab.columns.get_level_values(1)
In [35]: print(tab)
right     1     2     3    4
left                        
1      1520   234   117   36
2       266  1512   362   82
3       124   432  1772  179
4        66    78   205  492

# 从列联表创建一个SquareTable对象
In [36]: sqtab = sm.stats.SquareTable(tab)
In [37]: row, col = sqtab.marginal_probabilities
In [38]: print(row)
right
1    0.255049
2    0.297178
3    0.335295
4    0.112478
dtype: float64

In [39]: print(col)
right
1    0.264277
2    0.301725
3    0.328474 
4    0.105524
dtype: float64

# 该summary方法打印对称性和均匀性检测结果
In [40]: print(sqtab.summary()) 
            Statistic P-value DF
--------------------------------
Symmetry       19.107   0.004  6
Homogeneity    11.957   0.008  3
--------------------------------
```

### A single 2x2 table(单个2x2表)
`sm.stats.Table2x2`类提供了几种处理单个2x2表的方法。summary方法显示表的行和列之间的若干关联度量。
```python
In [41]: table = np.asarray([[35, 21], [25, 58]])
In [42]: t22 = sm.stats.Table2x2(table)
In [43]: print(t22.summary())
               Estimate   SE   LCB   UCB  p-value
-------------------------------------------------
Odds ratio        3.867       1.890 7.912   0.000
Log odds ratio    1.352 0.365 0.636 2.068   0.000
Risk ratio        2.075       1.411 3.051   0.000
Log risk ratio    0.730 0.197 0.345 1.115   0.000
-------------------------------------------------

#请注意，风险比不是对称的，因此如果分析转置表，将获得不同的结果。
In [44]: table = np.asarray([[35, 21], [25, 58]])
In [45]: t22 = sm.stats.Table2x2(table.T)
In [46]: print(t22.summary())
               Estimate   SE   LCB   UCB  p-value
-------------------------------------------------
Odds ratio        3.867       1.890 7.912   0.000
Log odds ratio    1.352 0.365 0.636 2.068   0.000
Risk ratio        2.194       1.436 3.354   0.000
Log risk ratio    0.786 0.216 0.362 1.210   0.000
-------------------------------------------------
```

### Stratified 2x2 tables(分层2x2表)
当我们有一组由同样行和列因子定义的列联表时，就会发生分层。

**案例**
- 我们有一组2x2表，反映了中国几个地区吸烟和肺癌的联合分布。表格可能都具有共同的比值比，即使边际概率在各阶层之间变化也是如此。
- “Breslow-Day”程序测试数据是否与常见优势比一致。它在下面显示为常数OR的测试。
- Mantel-Haenszel程序测试这个常见优势比是否等于1。它在下面显示为OR = 1的测试。还可以估计共同的几率和风险比并获得它们的置信区间。
- summary方法显示所有这些结果。可以从类方法和属性中获得单个结果。
```python
In [47]: data = sm.datasets.china_smoking.load()
In [48]: mat = np.asarray(data.data)
In [49]: tables = [np.reshape(x.tolist()[1:], (2, 2)) for x in mat]
In [50]: st = sm.stats.StratifiedTable(tables)
In [51]: print(st.summary())
                   Estimate   LCB    UCB 
-----------------------------------------
Pooled odds           2.174   1.984 2.383
Pooled log odds       0.777   0.685 0.868
Pooled risk ratio     1.519              
                                         
                 Statistic P-value 
-----------------------------------
Test of OR=1       280.138   0.000 
Test constant OR     5.200   0.636 
                       
-----------------------
Number of tables    8  
Min n             213  
Max n            2900  
Avg n            1052  
Total n          8419  
-----------------------
```

## [Multiple Imputation(多重插补)](http://www.statsmodels.org/stable/imputation.html)


MICE模块允许大多数Statsmodels模型拟合独立和/或因变量上具有缺失值的数据集，并为拟合参数提供严格的标准误差。基本思想是将具有缺失值的每个变量视为回归中的因变量，其中一些或所有剩余变量作为其预测变量。MICE程序循环遍历这些模型，依次拟合每个模型，然后使用称为“预测平均匹配”（PMM）的过程从拟合模型确定的预测分布中生成随机抽取。这些随机抽取成为一个插补数据集的估算值。

默认情况下，每个具有缺失变量的变量都使用线性回归建模，拟合数据集中的所有其他变量。请注意，即使插补模型是线性的，PMM过程也会保留每个变量的域。因此，例如，如果给定变量的所有观测值都是正，则变量的所有估算值将始终为正。用户还可以选择指定使用哪个模型为每个变量生成插补值。

```python
from statsmodels.imputation import mice
```
类|说明
:------|:------
MICE(model_formula, model_class, data, n_skip=3, init_kwds=None, fit_kwds=None)|用链式方程多重插补
MICEData（data [，perturbation_method，k_pmm，...]）|包装数据集以允许MICE处理丢失数据


MICEData类方法|说明
---|---
get_fitting_data|返回进行插补所需的数据
get_split_data(vname)|返回endog和exog以获取给定变量的插补
impute(vname)|
impute_pmm(vname)|使用预测均值匹配来估算缺失值
next_sample()|返回插补过程中的下一个插补数据集
perturb_params(vname)|	
plot_bivariate(col1_name,col2_name [,...])|绘制两个变量的观察值和估算值
plot_fit_obs(col_name[, lowess_args, …])|绘制拟合估计值或观察值的散点图
plot_imputed_hist(col_name[, ax, …])|将一个变量的估算值显示为直方图
plot_missing_pattern([ax, row_order, …])|生成显示缺失数据模式的图像
set_imputer(endog_name[, formula, …])|指定单个变量的插补过程。
update(vname)|为单个变量计算缺失值。
update_all([n_iter])|执行指定数量的MICE迭代。

```python
>>> imp = mice.MICEData(data)
>>> fml = 'y ~ x1 + x2 + x3 + x4'
>>> mice = mice.MICE(fml, sm.OLS, imp)
>>> results = mice.fit(10, 10)
>>> print(results.summary())
                          Results: MICE
=================================================================
Method:                    MICE       Sample size:           1000
Model:                     OLS        Scale                  1.00
Dependent variable:        y          Num. imputations       10
-----------------------------------------------------------------
           Coef.  Std.Err.    t     P>|t|   [0.025  0.975]  FMI
-----------------------------------------------------------------
Intercept -0.0234   0.0318  -0.7345 0.4626 -0.0858  0.0390 0.0128
x1         1.0305   0.0578  17.8342 0.0000  0.9172  1.1437 0.0309
x2        -0.0134   0.0162  -0.8282 0.4076 -0.0451  0.0183 0.0236
x3        -1.0260   0.0328 -31.2706 0.0000 -1.0903 -0.9617 0.0169
x4        -0.0253   0.0336  -0.7520 0.4521 -0.0911  0.0406 0.0269
=================================================================

#获得一系列拟合分析模型，无需合并即可获得摘要：
>>> imp = mice.MICEData(data)
>>> fml = 'y ~ x1 + x2 + x3 + x4'
>>> mice = mice.MICE(fml, sm.OLS, imp)
>>> results = []
>>> for k in range(10):
>>>     x = mice.next_sample()
>>>     results.append(x)
```



