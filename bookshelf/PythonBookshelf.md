---
ID: ec51f4c1169645f2cdf0ea94efa7e733
title: Python手册
date: 2018-04-30 11:42:18
categories: [bookshelf]
tags: [python,书架]
comments: true
copyright: false
---

本手册所列包来自[Awesome-Python](https://awesome-python.com/) ，结合[GitHub](https://github.com/) 和官方文档  
致谢，[ApacheCN 中文开源组织](http://www.apachecn.org/#)：致力于官方文档及AI书籍中文翻译。  
![pandas](images/pandas.png)  

# <font color="red">Python手册</font>

## <font color="green">IDE</font>

- :white_large_square:  [常用的Python IDE][ide]  
- :ballot_box_with_check:  [Jupyter Notebook][Jupyter]  

[ide]: /posts/python/PythonNotebook(Python-Basics)--common-editor.html
[Jupyter]: /posts/python/PythonNotebook(Python-Basics)--Jupyter-Notebook.html

## <font color="green">Python Basics</font>  

- :ballot_box_with_check:  [Python基础][Base]: [Python 3 官方中文文档](base_doc)  
- :heart:  [rpy2][rpy2]： Python 通过rpy2调用 R语言  

[Base]: /posts/python/PythonNotebook(Python-Basics)--Python-base.html
[base_doc]: https://docs.python.org/zh-cn/3/
[rpy2]: /posts/python/PythonNotebook(Python-Basics)--RPy2.html

## <font color="green">Standard Library</font>  

- :ballot_box_with_check:  [datetime+time+calendar][datetime]  
- :ballot_box_with_check:  [math+random][math]  
- :ballot_box_with_check:  [re][re]：正则表达式调用库
- :heart:  [tkinter][tk]：Python 的标准 GUI 库  
- :white_large_square:  [threading][threading] ：多线程  
- :white_large_square:  [multiprocessing][mul]： 多进程  
- :heart:  [os][os]: 文件和目录处理库([CSDN][csdn_os]参考链接)  
- :white_large_square:  [asyncio][asyncio]: 内置了对异步IO的支持   

[datetime]: /posts/python/PythonNotebook(Standard-Library)--datetime.html
[math]: /posts/python/PythonNotebook(Standard-Library)--math+random.html
[re]: /posts/python/PythonNotebook(Standard-Library)--re.html
[tk]: http://www.runoob.com/python/python-gui-tkinter.html
[threading]: http://www.runoob.com/python3/python3-multithreading.html
[mul]: http://python.jobbole.com/87760/
[os]: http://www.runoob.com/python/os-file-methods.html
[csdn_os]: https://blog.csdn.net/jinxiaonian11/article/details/78314192
[asyncio]: https://www.liaoxuefeng.com/wiki/0014316089557264a6b348958f449949df42a6d3a2e542c000/001432090954004980bd351f2cd4cc18c9e6c06d855c498000

## <font color="green">Scientific Computing</font>  

- :ballot_box_with_check:  [NumPy][NumPy]：使用 Python 进行科学计算的基础包。  
- :white_large_square:  PyDy：PyDy 是 Python Dynamics 的缩写，用来为动力学运动建模工作流程提供帮助， 基于NumPy, SciPy, IPython 和 matplotlib。  
- :heart:  [SciPy][SciPy]：由一些基于 Python ，用于数学，科学和工程的开源软件构成的生态系统。  
- :heart:  [SymPy][SymPy]：SymPy是一个符号计算的Python库  
- :white_large_square:  astropy：一个天文学 Python 库。  
- :heart:  [noise][noise]：柏林噪声(Python)  

[NumPy]: /posts/python/PythonNotebook(Scientific-Computing)--numpy.html
[SciPy]: /posts/python/PythonNotebook(Scientific-Computing)--scipy.html
[SymPy]: /posts/python/PythonNotebook(Scientific-Computing)--SymPy.html
[noise]: /posts/python/PerlinNoise(Python).html

## <font color="green">Data Analysis</font>  

- :ballot_box_with_check:  [pandas][pandas]：提供高性能，易用的数据结构和数据分析工具。  
- :ballot_box_with_check:  [pandas(Time Series)][time series]: 时间序列数据处理工具。  
- :heart:  blaze：NumPy 和 Pandas 的大数据接口。  
- :heart:  orange：通过可视化编程或 Python 脚本进行数据挖掘，数据可视化，分析和机器学习。  

[pandas]: /posts/python/PythonNotebook(Data-Analysis)--pandas.html
[Time Series]: /posts/python/PythonNotebook(Time-Series)--pandas(TimeSeries).html

## <font color="green">Web Crawling</font> 

*The Website is the API(Application Programming Interface,应用程序编程接口)...*  

- :ballot_box_with_check:  requests: 自动爬取HTML页面，自动网路请求提交。  
- :ballot_box_with_check:  BeautifulSoup ：解析HTML页面（[中文官网][bs4]）。  
- :heart:  Scrapy：专业的网络爬虫框架。  
- :white_large_square:  Selenium: 是一个用于Web应用程序测试的工具，能够模拟用户行为与浏览器交互。  

[bs4]: https://www.crummy.com/software/BeautifulSoup/bs4/doc.zh/

## <font color="green">Visualise</font>  

- :ballot_box_with_check:  [matplotlib][matplotlib]: 是一个 Python 的 2D绘图库。  
- :ballot_box_with_check:  [seaborn][seaborn]：基于matplotlib封装的数据可视化库。  
- :white_large_square:  bqplot： Jupyter Notebook的交互式绘图库  
- :white_large_square:  bokeh：用 Python 进行交互式 web 绘图。  
- :heart:  [ggplot][ggplot]：ggplot port for python  
- :white_large_square:  plotly：协同 Python 和 matplotlib 工作的 web 绘图库。  
- :white_large_square:  pyecharts：基于百度 Echarts 的数据可视化库。  
- :heart:  missingno：缺失数据图示。  

[matplotlib]: /posts/python/PythonNotebook(Visualise)--matplotlib.html
[seaborn]: /posts/python/PythonNotebook(Visualise)--seaborn.html
[ggplot]: http://yhat.github.io/ggpy/

## <font color="green">Machine Learning</font>  

- :ballot_box_with_check:  [sklearn][scikit-learn]：基于 SciPy 构建的机器学习 Python 模块。  
- :ballot_box_with_check:  [statsmodels][statsmodels]：统计建模和计量经济学。  
- :heart:  [xgboost][xgboost]： 一种可扩展，可移植且分布式的渐变增强库  

[scikit-learn]: /posts/python/PythonNotebook(Machine-Learning)--sklearn.html
[statsmodels]: /gitbook/statsmodels/
[xgboost]: http://xgboost.apachecn.org/#/

## <font color="green">Deep Learning</font>  

- :ballot_box_with_check:  [TensorFlow][TensorFlow]：Google开源的最受欢迎的深度学习框架。  
- :white_large_square:  [PyTorch][PyTorch]: Facebook 的 AI 研究团队发布了一个 Python 工具包，专门针对 GPU 加速的深度神经网络（DNN）编程。  
- :heart:  [Keras][Keras]: 以 tensorflow/theano/CNTK 为后端的深度学习封装库，快速上手神经网络。[莫烦PYTHON](https://morvanzhou.github.io/tutorials/machine-learning/theano/)  
- :white_large_square:  [Theano][Theano]:  基于TensorFlow，用于快速数值计算的库。  

[TensorFlow]: https://tensorflow.google.cn/tutorials/?hl=zh-cn
[PyTorch]: https://blog.csdn.net/u010510350/article/details/72526821
[Keras]: https://tensorflow.google.cn/guide/keras?hl=zh-cn
[Theano]: http://deeplearning.net/software/theano/#

## <font color="green">MapReduce</font>  

- :ballot_box_with_check:  PySpark : Apache Spark Python API  

## <font color="green">NLP(Natural Language Processing)</font>  

- :heart:  Jieba ： Chinese text segmentation  
- :white_large_square:  NLTK：Natural Language Toolkit  

## <font color="green">Documentation</font>  

- :white_large_square:  MkDocs ： Markdown友好的文档生成器。  
- :white_large_square:  Python-Markdown2：纯 Python 实现的 Markdown 解析器，比 Python-Markdown 更快，更准确，可扩展  
- :white_large_square:  PyYAML： implementations for Python.  
- :white_large_square:  python-docx: for creating and updating Microsoft Word (.docx) files.  
- :heart:  [openpyxl][op]: 全面，包括修改各种Excel格式，不能批量修改数据  
- :white_large_square:   [xlwings][xw]: 批量实时修改Excel数据，和pandas,matplotlib完美对接，只能修改个别格式  

[op]: https://openpyxl.readthedocs.io/en/stable/usage.html
[xw]: http://docs.xlwings.org/en/stable/quickstart.html

## <font color="green">Learning Python </font> 

- :ballot_box_with_check:  [Python基础中文教程](http://www.pythondoc.com/pythontutorial3/)  

------