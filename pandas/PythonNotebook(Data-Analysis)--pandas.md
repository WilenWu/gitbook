---
ID: 92968d580ae6ece91f4e4cc2ab6fce43
title: Python手册(Data Analysis)--pandas
tags: [python,pandas,数据分析,dataframe]
mathjax: false
copyright: true
date: 2018-05-10 23:00:51
categories: 
  - python 
  - pandas
sticky: false
---
pandas兼具NumPy高性能的数组计算功能，提供高性能，易用的数据结构和数据分析工具。Pandas库有两个主要数据结构：Series和DataFrame。
```python
import pandas as pd
```



<!-- more -->

# Series: 由一维数组和对应的索引组成

## 创建Series

{% tabs Series %}
<!-- tab array like -->

{% code lang:python %}
s=pd.Series(data,index=None,dtype=None) 
{% endcode %}

> data：tuple,list,dict,ndarray 
> index：list对象赋值索引 

<!-- endtab -->

<!-- tab dict -->

{% code lang:python %}
pd.Series(dict)
{% endcode %}

> 赋值方法 ：index=dict.keys,  data=dict.values

<!-- endtab -->

{% endtabs %}

## 属性

算术运算(`+,-,...`)自动匹配索引标签(full  join)

| 属性  | 可赋值修改|
|:---|:---|
| s.dtype | 数据类型 |
| s.index | 返回index对象  |
| s.values| 返回ndarrary对象 |
| s.size| 元素个数|
| s.index.name | 索引名字 |


## 索引和切片

| 索引和切片  | 可赋值修改|
|:---|:---|
| `s[index]`| num  or str  |
|`s[[index]]`|获得数值|
| `s[start:stop:step]`  | slice|
| `s[index_list]`   | 花式索引|
| `s2[(s2>0)&(s2<12)]`  | 逻辑索引 |
|`s.str`|Series的str属性可访问字符串的方法，`data.str.contains('gmail')`|
> 切片格式：`start:stop:step`
> 当切片由数字组成时：左闭右开区间  s[:10]
> 当切片由数字组成时：左右都是闭区间  s['a':'n']

## Series部分方法

> DataFrame的方法，Series基本都能用，下表摘取了有别于DataFrame的部分方法

| 方法  |     |
|:---|:---|
| s.astype(dtype,copy=True)   | 数据类型转换 |
| s.append(to_append,ignore_index=False)|追加，to_append : Series or list/tuple of Series  |
| s.unique()  | 唯一值 |
|s.map(func)|func映射至每个元素|
|s.isin(values)|成员判断|


# DataFrame

## 创建DataFrame

{% tabs DataFrame %}
<!-- tab array like -->

{% code lang:python %}
df=pd.DataFrame(data,index,columns,dtype,copy=False)
{% endcode %}

> data：tuple,list,dict,ndarray,Series ,DataFrame
> index,  columns：list赋值

<!-- endtab -->

<!-- tab dict -->
{% code lang:python %}
pd.DataFrame(dict)
{% endcode %}

- `dict={key1:value1,...}` 单层字典创建(*columns.name=dict.keys,data=dict.values* )
- `dict={key1:{key:value},...}` 嵌套字典创建 (*外层字典的键作为列索引，内层键则作为行索引*)
<!-- endtab -->

{% endtabs %}

## 属性

默认情况下，DataFrame和Series之间的算术运算(`+,-,*,...`)会将Series的索引匹配到DataFrame的列，然后沿着行一直向下广播

|属性|可赋值修改|
|:---|:---|
| df.dtypes| 元素类型，极为精细|
| df.index | 返回index对象（不可变），允许包含重复标签  |
| df.columns   | 返回index对象，所有列名   |
| df.values| 返回values（二维ndarrary，统一化dtype）|
| df.index.name| 索引名字 |
| df.columns.name  | columns的name属性   |
| df.shape | 维度信息tupple  |
| df.ndim  | 维度数量 |
| df.size  | 元素总个数|
| df.T | 转置   |


## 索引和切片

|索引和切片|建议用iloc,loc,ix方法赋值修改 |
|:---|:---|
| `df['index','columns']`| 筛选（str or num） |
| `df['columns']['index']`   |  |
| `df['column']` | 返回列Series  |
| `df.column`   | 返回列Series |
| `df.loc['index']`| 返回行Series |
| `df.iloc[index_num]`| 返回行Series |
| `df.loc['index','columns']`| 字符筛选 |
| `df.iloc[index_num,columns_num]`| 数字筛选，与bool类型不可混用 |
| `df.ix[]`  | 混合筛选 |
| `df.filter(items=None,like=None,regex=None, axis=None)` | 筛选方法，like: 字符列表 |
|`df.query(expr,inplace=False)`|逻辑筛选<br>`df.query('c1=="auto" & c2>=5')`|

![df](/images/df.png)

## 方法 

> axis参数：0 ( 'index') 代表行,  1 ('columns')  代表列

| **索引**  |  |
|:---|:---|
| df.reindex(index,column,method,fill_value) | 重命名轴索引<br>method:重新索引时缺失插补方式<br>fill_value:重新索引时填充值   |
| df.rename(index,columns,inplace=False) | 重命名<br>`data.rename(index=str.title, columns=str.upper)`<br>`data.rename(index={'oldname': 'newname'})` 字典赋值参数 |
|df.set_index(keys, drop=True, append=False, inplace=False)|将其一个或多个列转换为行索引|
|df.reset_index(level=None, drop=False, inplace=False, col_level=0, col_fill='')|层次化索引级别被转移到列里面|

| **数据预览** |  |
|:---|:---|
| df.info()| df 结构信息   |
| df.head(n=5) |  |
| df.tail(n=5) |  |

| **合并、插入和删除** |  |
|:---|:---|
| df.append(other,ignore_index=True) |other:DataFrame,Series,...(列表格式) |
| df.insert(loc, column, value, allow_duplicates=False)   | 插入列，loc(int)  |
| df.combine_first(other) | 合并重叠数据   |
| df.pop(column)   | 删除列，返回删除的列  |
| df.drop(labels,axis=0,inplace=False) | 删除行/列 |
| del df[column]  | del关键字删除列|

| **描述和汇总统计** |  |
|:---|:---|
| df.describe()| 针对0轴统计汇总 |
| df.mean(axis)| 平均值 |
| df.median(axis)  |  中位数 |
| df.count(axis)   |  计数 |
|df.nunique()|去重后计数|
| df.quantile(q=0.5, axis=0)|百分位数（默认中位数）|
| df.mad(axis)|平均绝对离差|
|df.var(axis)|方差|
|df.std(axis)|标准差|
|df.skew(axis)|偏度|
|df.kurt(axis)|峰度|
| df.cov(min_periods=None) | 协方差矩阵|
| df.corr(method='pearson', min_periods=1)| method : {'pearson', 'kendall',  'spearman'} |
|df.corrwith(other, axis=0, drop=False)|配对相关系数|
|df.diff(periods=1, axis=0)|一阶差分（对时间序列很有用）|
|df.pct_change(periods=1, fill_method='pad')|百分数变化|
| df.sum(axis) |  |
| df.idmax()/df.idmin()| 最大值/最小值的索引   |
| df.cumsum(axis)  | 累积求和 |
| df.cumprod(axis) | 累积求积 |
| df.cummax(axis)  | 累积最大值|
| df.cummin(axis)  | 累积最小值|
| df.rolling(window,axis).mean()   | 移动平均值|
| df.rolling(window,axis).min()| 移动最小值|

| **缺失值处理**| NaN（np.nan, Not a Number）  |
|:---|:---|
| df.isnull()  | 缺失值bool数组|
| df.notnull() |  |
| df.dropna(axis=0, how='any', thresh=None, subset=None, inplace=False)  | how:{'any','all'}<br> thresh: int,非NaN的最小值|
| df.fillna(value, method, axis, inplace=False, limit) | value:填充的标量值或字典<br>method :  {'backfill', 'bfill', 'pad', 'ffill', None} <br>limit: 可以连续填充的最大数量 |
```python
df.dropna(thresh=4)
df.dropna(axis=1, how='all')

df.fillna(method='ffill')
df.fillna(value={'A':np.mean(df.A), 'B': 1, 'C': 2, 'D': 3}, limit=1)
```


|**替换**||
|:---|:---|
|df.replace(to_replace, value, inplace=False, limit=None, regex=False, method='pad', axis=None)||
```python
data.replace([-999, -1000], [np.nan, 0]`)
data.replace({-999: np.nan, -1000: 0})   #参数为字典
```

| **数据转换**|   |
|:---|:---|
| df.transform(func)   | 数据转换，返回的形状和df完全一样<br>`df.transform(lambda x: (x - x.mean()) / x.std())`|
| df.astype(dtype,copy=False)   | 数据类型转换|
| df['column'].str.title()  | 转换成首字母大写（字符的属性和方法对pandas适用） |
| df['datetime'].dt.day | 获取日期（datetime类的属性和方法对pandas适用） |

|**重复值**|默认判断全部列|
|:---|:---|
|df.duplicated(subset=None, keep='first',inplace=False)|返回重复值布尔型Series<br>keep : {'first', 'last', False}|
|df.drop_duplicates(subset=None, keep='first', inplace=False)||

| **排序**   |  |
|:---|:---|
| df.sort_index(axis=0,ascending=True)| 索引排序 |
| df.sort_values(by,axis=0,ascending=True)| 按列数值排序   |
| df.rank(axis=0,method='average',ascending=True)| 排名，method : {'average', 'min', 'max', 'first', 'dense'}  |

| **抽样**   |  |
|:---|:---|
| df.sample(n, frac, replace=False)| 随机抽样 |

| **轴向旋转** |  |
|:---|:---|
| df.stack(level=-1, dropna=True)   | 把最内层列转换成行   |
| df.unstack(level=-1, fill_value=None) | stack逆运算，把行转换成最内层列   |

|**融合和重构**||
|:---|:---|
|pd.melt(frame, id_vars, value_vars, var_name, value_name='value', col_level=None)|宽格式变长格式|
|df.pivot(index=None, columns=None, values=None)|reshape|
| df.apply(func,axis=0)| 单函数聚合|

|**分组和聚合**|(介绍分组时举例)|
|:---|:---|
|df.groupby()|分组|
| df.applymap(func)| 映射至每个元素  |
| df.agg(func,axis=0)  | 多函数聚合|

```python
import numpy as np
df=pd.DataFrame(np.random.rand(3,4))
df.applymap(lambda x:format(x,'.2%'))

Out[10]: 
        0       1       2       3
0  89.19%  85.37%  60.62%  42.64%
1  89.50%  36.88%  27.67%  92.65%
2   2.88%  15.81%  56.87%  37.50%
```

**透视表**
`df.pivot_table(values=None, index=None, columns=None, aggfunc='mean', fill_value=None, margins=False, dropna=True, margins_name='All')` 
> margins: (boolean, default False) 分类汇总 


# Index对象

## 创建索引

{% tabs index %}
<!-- tab index -->

{% code lang:python %}
pd.Index(data=None, dtype=None, copy=False, name=None)
{% endcode %}

> dtype : NumPy dtype (default: object)

<!-- endtab -->

<!-- tab periods -->
{% code lang:python %}
pd.date_range(start, end, periods, freq='D', normalize=False, name=None)
pd.DatetimeIndex(data, freq, start, end, periods, copy=False, name)
{% endcode %}
<!-- endtab -->

{% endtabs %}


## Index方法

| 方法   |  |
|:---|:---|
|a.to_frame()|转化为DataFrame|
|a.to_series()|转化为series|
| a.append(b)  | 追加，生成副本  |
| a.difference(b)  | 差集，生成副本  |
| a.intersec(b)| 交集，生成副本  |
| a.union(b)   | 并集，生成副本  |
| a.isin(b)| 返回bool数组 |
| a.delete(loc)| 删除索引loc处元素，生成副本  |
| a.insert(loc,item)   | 在索引loc出插入元素iterm，生成副本|
|a.is_unique()|索引是否唯一|

## 层次化索引
层次化索引（hierarchical indexing）是pandas的一项重要功能，它使你能在一个轴上拥有多个（两个以上）索引级别。
|创建| |
|:---|:---|
pd.MultiIndex(levels=None, labels=None, sortorder=None, names=None, copy=False)|
pd.MultiIndex.from_arrays(arrays, sortorder=None, names=None) |由数组创建
pd.MultiIndex.from_product(iterables, sortorder=None, names=None) |生成笛卡儿积
pd.MultiIndex.from_tuples(tuples, sortorder=None, names=None)|


```python
columns = pd.MultiIndex.from_arrays([['US', 'US', 'US', 'JP', 'JP'],
                                    [1, 3, 5, 1, 3]],
                                     names=['cty', 'tenor'])
hier_df = pd.DataFrame(np.random.randn(4, 5), columns=columns)

df.swaplevel(i=-2, j=-1, axis=0) #交换层次化的索引级别

frame = pd.DataFrame(np.arange(12).reshape((4, 3)),
  index=[['a', 'a', 'b', 'b'], [1, 2, 1, 2]],
  columns=[['Ohio', 'Ohio', 'Colorado'],
  ['Green', 'Red', 'Green']])
frame.swaplevel('key1', 'key2').sort_index(level=0) # 重排与分级排序
frame.index.names = ['key1', 'key2']
frame.sum(level='key2') # 根据级别汇总统计
```

# 分组和聚合

> split-apply-combine（拆分－应用－合并）
> 本节`obj` 代表pandas对象(`Series or DataFrame`)

## 分组(groupby)

```python
obj.groupby(by=None, axis=0, level=None, as_index=True, 
    sort=True, group_keys=True, squeeze=False, **kwargs)
```

> **Return GroupBy object**
Parameters: 
**by** : (mapping, function, str, or iterable) 分组
**axis** :(int, default 0) 索引轴
**level** :(int, level name, or sequence of such) 根据层次化索引级别分组
**as_index** : (boolean, default True) 以行索引形式返回
**sort** : (boolean, default True) 索引排序
**group_keys** : (boolean, default True)
**squeeze** : (boolean, default False) 减少返回类型的维度


Examples:
```python
df = pd.DataFrame({'key1' : ['a', 'a', 'b', 'b', 'a'],
                   'key2' : ['one', 'two', 'one', 'two', 'one'],
                   'mapping': list('ABCDE'),
                   'data1' : np.random.randn(5),
                   'data2' : np.random.randn(5)})
# 列表或数组对象（其长度与待分组的轴一样）
states = np.array(['Ohio', 'California', 'California', 'Ohio', 'Ohio'])
years = np.array([2005, 2005, 2006, 2005, 2006])
df['data1'].groupby([states, years]).mean()
# 索引或列名列表
df.groupby(['key1', 'key2']).size()

# 通过字典或Series进行分组
mapping = {'A': 'red', 'B': 'red', 'C': 'blue','D': 'blue', 'E': 'red'}
df.groupby(mapping, axis=1)
map_series = pd.Series(mapping)
df.groupby(map_series, axis=1).count()
# 函数，用于处理轴索引或索引中的各个标签
df.index=['Joe','Steve','Wes','Jim','Travis']
df.groupby(df.dtypes, axis=1).size()
df.groupby(len).sum()
# 将函数跟数组、列表、字典、Series混合使用也不是问题，因为任何东西在内部都会被转换为数组
people.groupby([len, states]).min()
# 根据层次化索引级别分组
df2=df.set_index(['key1','key2'])
df2.groupby(level='key1').mean()
```

##  对分组进行迭代
GroupBy对象支持迭代，可以产生一组二元元组（由分组名和数据块组成），对于多重键的情况，元组的第一个元素将会是由键值组成的元组。

```python
for name, group in df.groupby('key1'):
     print(name)
     print(group)

for (k1, k2), group in df.groupby(['key1', 'key2']):
     print((k1, k2))
     print(group)
```


## 数据聚合(GroupBy对象)
不能被聚合的列，将会被剔除。
`grouped=df.groupby(key)`

| **聚合方法**| 说明（非NA值） |
|:---|:---|
|size|每组的大小（包括NA）|
|count, sum, prod, mean, median||
|std, var|无偏标准差和方差|
|min, max||
|first, last|第一个和最后一个|
```python
# SELECT count(distinct CLIENTCODE) FROM table GROUP BY YEARMONTH
table.groupby('YEARMONTH').CLIENTCODE.nunique()
```

**apply聚合方法**: 调用任意函数 split-apply-combine（拆分－应用－合并）
`grouped.apply(func, *args, **kwargs)`
```python
def top(df, n=5, column):
     return df.sort_values(by=column)[-n:]
df.groupby(['key1', 'key2']).apply(top, n=1, column='data1')
```

**agg聚合方法**

`grouped.agg(arg)`
> **Parameters: arg**(聚合函数)
> string function name
 > function, list of functions
 >  rename:  `[(name1,func1),(name2,func2),...] `
 >   dict of column names: `{'colname1':func1, 'colname2':func2,...}`

Examples:
```python
# 函数，函数名混合列表
grouped.agg(['mean', 'std', sum])
grouped['num'].agg(['mean', 'std', sum])
# (name,function)元组组成的列表，则各元组的第一个元素就会被用作DataFrame的列名
grouped.agg([('name1', 'mean'), ('name2', np.std)])

iris.groupby('Species')['Sepal.Length'].agg({'count':len,'sum':np.sum,'mean':np.mean}) 
```

## 桶(bucket)分析
pandas有一些能根据指定面元或样本分位数将数据拆分成多块的工具（比如cut和qcut），将这些函数跟groupby结合起来分析。
```python
In [82]: frame = pd.DataFrame({'data1': np.random.randn(1000),
   ....:                       'data2': np.random.randn(1000)})
In [85]: def get_stats(group):
   ....:     return {'min': group.min(), 'max': group.max(),
   ....:             'count': group.count(), 'mean': group.mean()}
In [86]: grouped = frame.data2.groupby(quartiles)
In [87]: grouped.apply(get_stats).unstack()
Out[87]: 
                 count       max      mean       min
data1                                               
(-2.956, -1.23]   95.0  1.670835 -0.039521 -3.399312
(-1.23, 0.489]   598.0  3.260383 -0.002051 -2.989741
(0.489, 2.208]   297.0  2.954439  0.081822 -3.745356
(2.208, 3.928]    10.0  1.765640  0.024750 -1.929776
```

## 示例
**用特定于分组的值填充缺失值**
```python
In [102]: fill_mean = lambda g: g.fillna(g.mean())
In [103]: data.groupby(group_key).apply(fill_mean)

In [104]: fill_values = {'A': 0.5, 'B': -1}
In [105]: fill_func = lambda g: g.fillna(fill_values[g.name])
In [106]: data.groupby(group_key).apply(fill_func)
```
**随机采样和排列**
```python
# Hearts, Spades, Clubs, Diamonds
In [103   ]: suits = ['H', 'S', 'C', 'D']
In [104]: card_val = (list(range(1, 11)) + [10] * 3) * 4
In [105]: base_names = ['A'] + list(range(2, 11)) + ['J', 'K', 'Q']
In [106]: cards = []
In [107]: for suit in ['H', 'S', 'C', 'D']:
   .....:    cards.extend(str(num) + suit for num in base_names)

In [108]: deck = pd.Series(card_val, index=cards)

In [109]: def draw(deck, n=5):
   .....:     return deck.sample(n)
In [111]: get_suit = lambda card: card[-1] # last letter is suit
In [112]: deck.groupby(get_suit).apply(draw, n=2)
```
**分组加权平均数**
```python
In [114]: df = pd.DataFrame({'category': ['a', 'a', 'a', 'a',
   .....:                                 'b', 'b', 'b', 'b'],
   .....:                    'data': np.random.randn(8),
   .....:                    'weights': np.random.rand(8)})
In [116]: grouped = df.groupby('category')
In [117]: get_wavg = lambda g: np.average(g['data'], weights=g['weights'])
In [118]: grouped.apply(get_wavg)
```

**组级别的线性回归**
```python
import statsmodels.api as sm
def regress(data, yvar, xvars):
    Y = data[yvar]
    X = data[xvars]
    X['intercept'] = 1.
    result = sm.OLS(Y, X).fit()
    return result.params

In [129]: by_year.apply(regress, 'AAPL', ['SPX'])
```


# 分类数据

用整数表示字符数据的方法称为分类或字典编码表示法。表示分类的整数值称为分类编码或简单地称为编码。

## 创建分类变量(pandas.Categorical)

- **`df.take`方法**
`df.take(indices, axis=0, convert=True, is_copy=True, **kwargs)`
  > **Parameters：**
  > indices : (list / array of ints) 字符变量
  > axis : int, default 0
  > convert : translate neg to pos indices (default)
  > is_copy : 副本

```python
values = np.random.randint(2,size=100)
factor = pd.Series(['apple', 'orange'])
cat=factor.take(values)
```

- **`pd.Categorical`函数**
`pd.Categorical(values, categories=None, ordered=False, fastpath=False)`
`pd.Categorical.from_codes(codes, categories, ordered=False)`
  > **Parameters:**
  > values : (list-like) 字符变量
  > codes: (array-like, integers) 编码变量
  > categories : Index-like (unique, optional) 类别标签
  > ordered : boolean, (default False) 有序
  

```python
my_cats = pd.Categorical(['foo', 'bar', 'baz', 'foo', 'bar'])

categories = ['foo', 'bar', 'baz']
codes = [0, 1, 2, 0, 0, 1]
my_cats2 = pd.Categorical.from_codes(codes, categories)
```

- **astype方法**
`df['col'].astype('category')`

## pd.Categorical对象属性
`my_cat = pd.Categorical(values)`
`my_cat.values.categories` : (Index) 类别
`my_cat.values.codes` : (ndarray) 编码
`my_cat.values.ordered` : boolean


## 分类方法
`my_cat = pd.Categorical(values)`
`pd.Categorical` 对象的cat属性提供了分类方法的入口

|方法（`my_cat.cat` 属性）| 说明 |
|:---|:---|
|add_categories(new_categories, inplace=False)|添加新的分类
|as_ordered(inplace=False)|使分类有序
|as_unordered(inplace=False)|使分类无序
|remove_categories(removals, inplace=False)|移除分类
|remove_unused_categories(inplace=False)|移除任意不出现在数据中的分类
|rename_categories(new_categories, inplace=False)|重命名分类
|reorder_categories(new_categories, ordered=None, inplace=False)|重排序分类
|set_categories(new_categories, ordered=None, rename=False, inplace=False)|重新设置分类


## 为建模创建虚拟变量
**one-hot编码**：将分类变量转换为哑变量
`pd.get_dummies(data, prefix=None, prefix_sep='_', dummy_na=False, columns=None, sparse=False, drop_first=False)`
  > **Parameters:**
  > data : (array-like, Series, or DataFrame) 数据
  > prefix : (string, list of strings, or dict of strings) 列名
  > prefix_sep : (string) 列名分隔符
  > dummy_na : (bool) 是否删除NA
  > columns : (list-like) 选择列
  > sparse : bool, default False
  > drop_first : (bool) 去除第一个类别

```python
In : s = pd.Series(list('abca'))
In : pd.get_dummies(s)
Out : 
   a  b  c
0  1  0  0
1  0  1  0
2  0  0  1
3  1  0  0
```

# 绘图和可视化

` import matplotlib.pyplot as plt`
`df.plot()`

参数|说明
:---|:---
label|图例标签
ax|matplotlib subplot对象（位置）
style|matploblib风格
alpha|图表的透明度
kind|{'line','bar','barh','kde'}
use_index|将对象的索引用作刻度标签
rot|旋转刻度标签（0：360）
xsticks/ysticks|x/y刻度
xlim/ylim|x/y界限
grid|显示网格线


| 可视化 |  |
|:---|---|
| s.hist(bins)| 直方图 |
|s.plot.kde()/s.plot.density()|Kernel Density Estimate，核密度估计）|
| df.plot.bar(stacked) | 条形图（参数stacked=True设置堆叠）  |
| df.plot.barh(stacked)| 水平条形图|
|  df.plot.line(x,y)|线图|
| df.plot.scatter(x,y,s=None,c=None) | 散点图，s(size)，c(color)  |
|df.plot.hexbin(x, y, C=None)|六角形分箱图
| df.plot.hist(bins)   | bins指定直方图宽度  |
| df.plot.box(by)| 箱线图 |
| df.plot.area(x,y)   |  |
| df.plot.pie(y)   |  |

|Plotting Tools函数|import pandas.plotting |
|:---|---|
|scatter_matrix()|散点图矩阵|
|andrews_curves()|Andrews Curves|
|Parallel Coordinates()|平行坐标|
|lag_plot()|滞积|
|autocorrelation_plot()|自相关图|
|bootstrap_plot()|Bootstrap|
|radviz()||





# Pandas函数 

NumPy的ufuncs（元素级数组函数）也可用于操作pandas对象（例如`np.abs(df)`）

## 导入导出

```python
pd.read_csv(filepath_or_buffer, sep=',',encoding,index_col)
df.to_csv(path_or_buf, sep=',columns=None, header=True, index=True) 
pd.read_excel(io,sheetname,header,skiprows,na_value)
df.to_excel(excel_writer, sheet_name='Sheet1', columns=None, header=True, index=True,startrow=0, startcol=0) 
read_table, read_json, read_html, read_pickle, read_sas,...   
```

```python
# 读取中文路径文件
f=open("中文路径.csv")
df=pd.read_csv(f)

#excel追加
writer = pd.ExcelWriter('output.xlsx')
df1.to_excel(writer, 'Sheet1')
df2.to_excel(writer, 'Sheet2')
writer.save()

with ExcelWriter('foo.xlsx') as writer:
    df.to_excel(writer, 'Data 0')
    df2.to_excel(writer, 'Data 1')
```

**MemoryError问题**：
[参考链接](https://blog.csdn.net/weixin_39750084/article/details/81501395)
pandas设计时应该是早就考虑到了这些可能存在的问题，所以在read功能中设计了块读取的功能，也就是不会一次性把所有的数据都放到内存中来，而是分块读到内存中，最后再将块合并到一起，形成一个完整的DataFrame。

```python
data = pd.read_csv(path, sep=',',engine = 'python',iterator=True)

def read_csv(data,chunkSize = 100000)
  loop = True  
  chunks = []
  index = 1
  while loop:
      try:
          print('reading')
          print(index+' chunk')
          chunk = data.get_chunk(chunkSize)
          chunks.append(chunk)
          index += 1
  
      except StopIteration:
          loop = False
          print("Iteration is stopped.")
  print('concat chunks ...')
  return pd.concat(chunks, ignore_index= True)

data = read_csv(data,chunkSize = 100000) 
```



## 合并和匹配

`pd.concat(objs, axis=0, join='outer',ignore_index=False,keys=None)` 
pandas合并,自动匹配
> keys:层次化索引
> join:{'inner','outer'}
> ignore_index：重新生成索引   |

`pd.merge(left,right,how='inner',on=None,indicator,suffixes=('_x', '_y'),left_index,right_index)` 
pandas匹配
> how:{'left','right','inner','outer'}
> indicator:{'left_only','right_only','both'}
> suffixes：列名前缀
> left_index,right_index：索引匹配

## 离散化和面元划分

```python
# 返回pandas.Categorical对象
pd.cut(x, bins, right=True, labels=None) # 按指定宽度或者数量分割面元<br>bins: 整数（面元数量） or 面元边界序列 or 区间索引|
pd.qcut(x, q, labels=None, duplicates='raise') # 分割的面元每组数量一致  <br>q : 整数(面元数量) or 分位数序列|
```

```python
>>> import numpy as np
>>> import pandas as pd
>>> ID=np.random.randint(100,500,1000)
>>> score=np.random.randn(1000)
>>> score=(score-score.min())/(score.max()-score.min())
>>> #均匀宽度分组cut或者均匀数量分组qcut
>>> cuts=pd.cut(score,bins=10,right=False)
>>> qcuts=pd.qcut(score,q=10,duplicates='drop') #删除重复分位数
>>> df.groupby(cuts).ID.nunique() #去重计数
[0.0, 0.1)        6
[0.1, 0.2)       21
[0.2, 0.3)       49
[0.3, 0.4)      109
[0.4, 0.5)      161
[0.5, 0.6)      177
[0.6, 0.7)      156
[0.7, 0.8)       96
[0.8, 0.9)       36
[0.9, 1.001)     10
Name: ID, dtype: int64
>>> df.groupby(qcuts).ID.nunique()
(-0.001, 0.32]    85
(0.32, 0.402]     95
(0.402, 0.457]    88
(0.457, 0.496]    85
(0.496, 0.535]    85
(0.535, 0.578]    87
(0.578, 0.618]    89
(0.618, 0.675]    88
(0.675, 0.736]    86
(0.736, 1.0]      86
Name: ID, dtype: int64
```

## 透视表(pivot table)

```python
pd.pivot_table(data, values=None, index=None, columns=None, aggfunc='mean', 
    fill_value=None, margins=False, dropna=True, margins_name='All')
```

> Parameters:
**data** : DataFrame
**values** : 要聚合的列（可选）
**index** : 分组的列名或其他分组键，透视表的行
**columns** : 分组的列名或其他分组键，透视表的列
**aggfunc** : 聚合函数或函数列表，可以是任何对groupby有效的函数
**fill_value** : 替换表中的缺失值
**margins** : boolean, 分类汇总
**dropna** : boolean, default True
**margins_name** : string, default 'All', 分类汇总名字

## 交叉表(cross-tabulation)

```python
pd.crosstab(index, columns, values=None, rownames=None, colnames=None, 
    aggfunc=None, margins=False, dropna=True, normalize=False)
```

> Parameters:
**index** : array-like, Series, or list of arrays/Series
**columns** : array-like, Series, or list of arrays/Series
**values** : array-like, optional
**aggfunc** : function, optional
**rownames** : sequence, default None
**colnames** : sequence, default None
**margins** : boolean, default False
**dropna** : boolean, default True
**normalize** : boolean, {'all', 'index', 'columns'}, or {0,1}, default False
    Normalize by dividing all values by the sum of values.

   - If passed 'all' or `True`, will normalize over all values.
   - If passed 'index' will normalize over each row.
   - If passed 'columns' will normalize over each column.
   - If margins is `True`, will also normalize margin values.


# 链式编程技术

```python
df.pipe(func, *args, **kwargs)   # df.pipe(f)等价于f(df)
```

```python
(df.pipe(h)
    .pipe(g, arg1=a)
    .pipe(f, arg2=b, arg3=c)
) # 加外括号便于换行
```





