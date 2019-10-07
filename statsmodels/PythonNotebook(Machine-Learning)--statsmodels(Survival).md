---
ID: 99bb4feb2dbfff3b153edf34328cf7ee
title: Python手册(Machine Learning)--statsmodels(Survival)
tags: [python,机器学习,statsmodels,生存分析]
mathjax: false
copyright: true
date: 2018-12-19 16:55:15
categories: [python,Machine Learning]
sticky: false
---
## [生存分析](http://www.statsmodels.org/stable/duration.html)

生存分析是用于分析直到一个或多个事件发生的预期持续时间的统计分支，例如生物有机体中的死亡和机械系统中的失败。本主题被称为可靠性理论和可靠性分析的工程，持续时间分析或持续时间建模在经济学和事件历史分析，在社会学。生存分析试图回答以下问题：在一定时间内存活的人口比例是多少？那些幸存下来的人会以什么样的速度死亡或失败？可以考虑多种死亡原因吗？具体情况或特征如何增加或减少生存的概率？[--*Wiki*](https://en.wikipedia.org/wiki/Survival_analysis)

<!-- more -->

理论链接：
[生存分析(survival analysis)](https://www.cnblogs.com/wwxbi/p/6136348.html)
[生存分析学习笔记](https://blog.csdn.net/jaen_tail/article/details/79081954)

`statsmodels.duration`实现了几种处理删失数据的标准方法。当数据由起始时间点和某些感兴趣事件发生的时间之间的持续时间组成时，最常使用这些方法。

目前只处理右侧审查。当我们知道在给定时间t之后发生事件时发生了右删失，但我们不知道确切的事件时间。

### 生存函数估计和推理

`statsmodels.api.SurvfuncRight`类可以被用来估计可以右删失数据的生存函数。 `SurvfuncRight`实现了几个推理程序，包括生存分布分位数的置信区间，生存函数的逐点和同时置信带以及绘图程序。`duration.survdiff`函数提供了比较生存分布的检验程序。

**Example**
在这里，我们SurvfuncRight使用flchain研究中的数据创建一个对象 ，该数据可通过R数据集存储库获得。我们只适合女性受试者的生存分布。
```python
import statsmodels.api as sm

data = sm.datasets.get_rdataset("flchain", "survival").data
df = data.loc[data.sex == "F", :]
sf = sm.SurvfuncRight(df["futime"], df["death"])

# 通过调用summary方法可以看出拟合生存分布的主要特征
sf.summary().head()

#我们可以获得生存分布的分位数的点估计和置信区间。
#由于在这项研究中只有约30％的受试者死亡，我们只能估计低于0.3概率点的分位数
sf.quantile(0.25)
sf.quantile_ci(0.25)
```
要绘制单个生存函数，请调用plot方法：
`sf.plot()`
由于这是一个包含大量删失的大型数据集，我们可能希望不绘制删失符号：
```python
fig = sf.plot()
ax = fig.get_axes()[0]
pt = ax.get_lines()[1]
pt.set_visible(False)

#我们还可以为情节添加95％的同时置信带。通常，这些波段仅针对分布的中心部分绘制。
fig = sf.plot()
lcb, ucb = sf.simultaneous_cb()
ax = fig.get_axes()[0]
ax.fill_between(sf.surv_times, lcb, ucb, color='lightgrey')
ax.set_xlim(365, 365*10)
ax.set_ylim(0.7, 1)
ax.set_ylabel("Proportion alive")
ax.set_xlabel("Days since enrollment")

#在这里，我们在同一轴上绘制两组（女性和男性）的生存函数：
gb = data.groupby("sex")
ax = plt.axes()
sexes = []
for g in gb:
    sexes.append(g[0])
    sf = sm.SurvfuncRight(g[1]["futime"], g[1]["death"])
    sf.plot(ax)
li = ax.get_lines()
li[1].set_visible(False)
li[3].set_visible(False)
plt.figlegend((li[0], li[2]), sexes, "center right")
plt.ylim(0.6, 1)
ax.set_ylabel("Proportion alive")
ax.set_xlabel("Days since enrollment")
```
我们可以正式比较两个生存分布`survdiff`，它实现了几个标准的非参数程序。默认程序是`logrank`检测：
```python
stat, pv = sm.duration.survdiff(data.futime, data.death, data.sex)

#以下是survdiff实施的一些其他测试程序
# Fleming-Harrington with p=1, i.e. weight by pooled survival time
stat, pv = sm.duration.survdiff(data.futime, data.death, data.sex, weight_type='fh', fh_p=1)
# Gehan-Breslow, weight by number at risk
stat, pv = sm.duration.survdiff(data.futime, data.death, data.sex, weight_type='gb')
# Tarone-Ware, weight by the square root of the number at risk
stat, pv = sm.duration.survdiff(data.futime, data.death, data.sex, weight_type='tw')
```

### 回归方法

比例风险回归模型（“Cox模型”）是用于删失数据的回归技术。它们允许以协变量的形式解释事件的时间变化，类似于线性或广义线性回归模型中所做的。这些模型以“风险比”表示协变量效应，这意味着危险（瞬时事件率）乘以给定因子，取决于协变量的值。

**Example**
```python
import statsmodels.api as sm
import statsmodels.formula.api as smf

data = sm.datasets.get_rdataset("flchain", "survival").data
del data["chapter"]
data = data.dropna()
data["lam"] = data["lambda"]
data["female"] = (data["sex"] == "F").astype(int)
data["year"] = data["sample.yr"] - min(data["sample.yr"])
status = data["death"].values

mod = smf.phreg("futime ~ 0 + age + female + creatinine + "
                "np.sqrt(kappa) + np.sqrt(lam) + year + mgus",
                data, status=status, ties="efron")
rslt = mod.fit()
print(rslt.summary())
```




