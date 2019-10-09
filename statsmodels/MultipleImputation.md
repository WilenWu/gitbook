---
ID: 83cf473de1d10e4510e96726f7fee36c  
title: Python手册(Machine Learning)--statsmodels(Multiple Imputation)  
tags: [python,机器学习,statsmodels,多重插补]  
mathjax: true  
copyright: true  
date: 2018-12-19 16:59:01  
categories: [python,Machine Learning]  
sticky: false  
---
  
# [Multiple Imputation(多重插补)](http://www.statsmodels.org/stable/imputation.html)  
  
  
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
  
  
  
