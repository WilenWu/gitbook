
**说明**：本手册所列包来自[Awesome-Python](https://awesome-python.com/) ，结合[GitHub](https://github.com/) 和官方文档
致谢，[ApacheCN 中文开源组织](http://www.apachecn.org/#)：致力于官方文档及AI书籍中文翻译。

![pandas](images/pandas.png)

------


# IDE

  - [ ] [常用的Python IDE][ide]
  - [x] [Jupyter Notebook][Jupyter]

[ide]: https://wilenwu.github.io/posts/python/PythonNotebook(Python-Basics)--common-editor.html
[Jupyter]: https://wilenwu.github.io/posts/python/PythonNotebook(Python-Basics)--Jupyter-Notebook.html

# Python Basics

  - [x] [Python基础][Base]: [Python 3 官方中文文档](base_doc)
  - [ ] [rpy2][rpy2]：:yellow_heart: Python 通过rpy2调用 R语言

[Base]: https://wilenwu.github.io/posts/python/PythonNotebook(Python-Basics)--Python-base.html
[base_doc]: https://docs.python.org/zh-cn/3/
[rpy2]: https://wilenwu.github.io/posts/python/PythonNotebook(Python-Basics)--RPy2.html

# Standard Library

  - [x] [datetime+time+calendar][datetime]
  - [x] [math+random][math]
  - [x] [re+正则表达式][re]
  - [ ] [tkinter][tk]：:yellow_heart:Python 的标准 GUI 库
  - [ ] [threading][threading] ：多线程
  - [ ] [multiprocessing][mul]： 多进程
  - [ ] [os][os]: :yellow_heart:文件和目录处理库([CSDN][csdn_os]参考链接)
  - [ ] [asyncio][asyncio]: 内置了对异步IO的支持 

[datetime]: https://wilenwu.github.io/posts/python/PythonNotebook(Standard-Library)--datetime.html
[math]: https://wilenwu.github.io/posts/python/PythonNotebook(Standard-Library)--math+random.html
[re]: https://wilenwu.github.io/posts/python/PythonNotebook(Standard-Library)--re+regular-expression.html
[tk]: http://www.runoob.com/python/python-gui-tkinter.html
[threading]: http://www.runoob.com/python3/python3-multithreading.html
[mul]: http://python.jobbole.com/87760/
[os]: http://www.runoob.com/python/os-file-methods.html
[csdn_os]: https://blog.csdn.net/jinxiaonian11/article/details/78314192
[asyncio]: https://www.liaoxuefeng.com/wiki/0014316089557264a6b348958f449949df42a6d3a2e542c000/001432090954004980bd351f2cd4cc18c9e6c06d855c498000

# Scientific Computing

  - [x] [NumPy][NumPy]：使用 Python 进行科学计算的基础包。
  - [ ] PyDy：PyDy 是 Python Dynamics 的缩写，用来为动力学运动建模工作流程提供帮助， 基于NumPy, SciPy, IPython 和 matplotlib。
  - [ ] [SciPy][SciPy]：:yellow_heart:由一些基于 Python ，用于数学，科学和工程的开源软件构成的生态系统。
  - [ ] [SymPy][SymPy]：:yellow_heart:SymPy是一个符号计算的Python库
  - [ ] astropy：一个天文学 Python 库。
  - [ ] [noise][noise]：:yellow_heart:柏林噪声(Python)

[NumPy]: https://wilenwu.github.io/posts/python/PythonNotebook(Scientific-Computing)--numpy.html
[SciPy]: https://wilenwu.github.io/posts/python/PythonNotebook(Scientific-Computing)--scipy.html
[SymPy]: https://wilenwu.github.io/posts/python/PythonNotebook(Scientific-Computing)--SymPy.html
[noise]: https://wilenwu.github.io/posts/python/PerlinNoise(Python).html

# Data Analysis

  - [x] [pandas][pandas]：提供高性能，易用的数据结构和数据分析工具。
  - [x] [pandas(Time Series)][time series]: 时间序列数据处理工具。
  - [ ] blaze：:yellow_heart:NumPy 和 Pandas 的大数据接口。
  - [ ] orange：:yellow_heart:通过可视化编程或 Python 脚本进行数据挖掘，数据可视化，分析和机器学习。

[pandas]: https://wilenwu.github.io/posts/python/PythonNotebook(Data-Analysis)--pandas.html
[Time Series]: https://wilenwu.github.io/posts/python/PythonNotebook(Time-Series)--pandas(TimeSeries).html

# Web Crawling
*The Website is the API(Application Programming Interface,应用程序编程接口)...*

  - [x] requests: 自动爬取HTML页面，自动网路请求提交。
  - [x] BeautifulSoup ：解析HTML页面（[中文官网][bs4]）。
  - [ ] Scrapy：:yellow_heart:专业的网络爬虫框架。
  - [ ] Selenium: 是一个用于Web应用程序测试的工具，能够模拟用户行为与浏览器交互。

[bs4]: https://www.crummy.com/software/BeautifulSoup/bs4/doc.zh/

# Visualise

  - [x] [matplotlib][matplotlib]: 是一个 Python 的 2D绘图库。
  - [x] [seaborn][seaborn]：基于matplotlib封装的数据可视化库。
  - [ ] bqplot： Jupyter Notebook的交互式绘图库
  - [ ] bokeh：用 Python 进行交互式 web 绘图。
  - [ ] [ggplot][ggplot]：:yellow_heart:ggplot port for python
  - [ ] plotly：协同 Python 和 matplotlib 工作的 web 绘图库。
  - [ ] pyecharts：基于百度 Echarts 的数据可视化库。
  - [ ] missingno：:yellow_heart:缺失数据图示。

[matplotlib]: https://wilenwu.github.io/posts/python/PythonNotebook(Visualise)--matplotlib.html
[seaborn]: https://wilenwu.github.io/posts/python/PythonNotebook(Visualise)--seaborn.html
[ggplot]: http://yhat.github.io/ggpy/

# Machine Learning

  - [x] [sklearn][scikit-learn]：基于 SciPy 构建的机器学习 Python 模块。
  - [x] [statsmodels][statsmodels]：统计建模和计量经济学。
  - [ ] [xgboost][xgboost]： :yellow_heart:一种可扩展，可移植且分布式的渐变增强库

[scikit-learn]: https://wilenwu.github.io/posts/python/PythonNotebook(Machine-Learning)--sklearn.html
[statsmodels]: https://blog.csdn.net/qq_41518277/article/details/80275280
[xgboost]: http://xgboost.apachecn.org/#/

# Deep Learning

  - [x] [TensorFlow][TensorFlow]：Google开源的最受欢迎的深度学习框架。
  - [ ] [PyTorch][PyTorch]: Facebook 的 AI 研究团队发布了一个 Python 工具包，专门针对 GPU 加速的深度神经网络（DNN）编程。
  - [ ] [Keras][Keras]: :yellow_heart:以 tensorflow/theano/CNTK 为后端的深度学习封装库，快速上手神经网络。[莫烦PYTHON](https://morvanzhou.github.io/tutorials/machine-learning/theano/)
  - [ ] [Theano][Theano]:  基于TensorFlow，用于快速数值计算的库。

[TensorFlow]: https://tensorflow.google.cn/tutorials/?hl=zh-cn
[PyTorch]: https://blog.csdn.net/u010510350/article/details/72526821
[Keras]: https://tensorflow.google.cn/guide/keras?hl=zh-cn
[Theano]: http://deeplearning.net/software/theano/#

# MapReduce

  - [x] PySpark : Apache Spark Python API

# NLP(Natural Language Processing)

  - [ ] Jieba ： :yellow_heart:Chinese text segmentation
  - [ ] NLTK：Natural Language Toolkit

# Documentation

  - [ ] MkDocs ： Markdown友好的文档生成器。
  - [ ] Python-Markdown2：纯 Python 实现的 Markdown 解析器，比 Python-Markdown 更快，更准确，可扩展
  - [ ] PyYAML： implementations for Python.
  - [ ] python-docx: for creating and updating Microsoft Word (.docx) files.
  - [ ] [openpyxl][op]: :yellow_heart:全面，包括修改各种Excel格式，不能批量修改数据
  - [ ]  [xlwings][xw]: 批量实时修改Excel数据，和pandas,matplotlib完美对接，只能修改个别格式

[op]: https://openpyxl.readthedocs.io/en/stable/usage.html
[xw]: http://docs.xlwings.org/en/stable/quickstart.html

# Learning Python

  - [x] [Python基础中文教程](http://www.pythondoc.com/pythontutorial3/)

-------





