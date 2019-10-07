---
ID: 46e946691a74dda4a3fadac7597d54b7
title: Python手册(Machine Learning)--statsmodels(ANOVA)
tags: [python,机器学习,statsmodels,方差分析]
mathjax: true
copyright: true
date: 2018-12-19 16:56:17
categories: [python,Machine Learning]
sticky: false
---
方差分析(Analysis of Variance，简称ANOVA)，又称“变异数分析”，为数据分析中常见的统计模型，主要为探讨连续型（Continuous）因变量（Dependent variable）与类别型自变量（Independent variable）的关系。当自变量的因子等于或超过三个类别时，检验各类别平均值是否相等，采用方差分析。
广义t检验中，方差相等（Equality of variance）的合并t检验（Pooled T-test）视为是方差分析的一种。t检验分析两组平均数是否相等，方差分析也采用相同的计算概念，实际上，当方差分析套用在合并t检验的分析上时，产生的F值则会等于t检验的平方项。

总偏差平方和 $SSt = SSb + SSw$

<!-- more -->

## [方差分析](http://www.statsmodels.org/stable/anova.html)

statsmodels包含anova_lm模型，用于使用线性OLSModel进行方差分析，和AnovaRM模型，用于重复测量方差分析（包含平衡数据方差分析）。

Module Reference|desc
:---|:---
`anova_lm(*args, **kwargs)` |Anova table for one or more fitted linear models
`AnovaRM(data, depvar, subject[, within, …])`|Repeated measures Anova using least squares regression

```python
In [1]: import statsmodels.api as sm
In [2]: from statsmodels.formula.api import ols
In [3]: moore = sm.datasets.get_rdataset("Moore", "car",
   ...:                                  cache=True) # load data
In [4]: data = moore.data
In [5]: data = data.rename(columns={"partner.status":
   ...:                             "partner_status"}) # make name pythonic
In [6]: moore_lm = ols('conformity ~ C(fcategory, Sum)*C(partner_status, Sum)',
   ...:                 data=data).fit()
In [7]: table = sm.stats.anova_lm(moore_lm, typ=2) # Type 2 ANOVA DataFrame
In [8]: print(table)
                                              sum_sq    df          F  \
C(fcategory, Sum)                          11.614700   2.0   0.276958   
C(partner_status, Sum)                    212.213778   1.0  10.120692   
C(fcategory, Sum):C(partner_status, Sum)  175.488928   2.0   4.184623   
Residual                                  817.763961  39.0        NaN   

                                            PR(>F)  
C(fcategory, Sum)                         0.759564  
C(partner_status, Sum)                    0.002874  
C(fcategory, Sum):C(partner_status, Sum)  0.022572  
Residual                                       NaN  
```



