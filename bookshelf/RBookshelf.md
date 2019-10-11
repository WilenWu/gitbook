---
ID: d14f78c294227c4381fa942cdbd695a4
title: R手册
date: 2018-04-30 16:46:55
categories: [bookshelf]
tags: [R]
comments: true
copyright: false
---

# <font color="red">R手册</font>

本手册所列包基本来自[AwesomeR][AwesomeR] ，结合[GitHub][GitHub]和`help(package="pk_name")`官方文档整理所得，有助于使用时下最实用的包对R进行深入的学习。  
致谢，[ApacheCN 中文开源组织](http://www.apachecn.org/## )：致力于官方文档及AI书籍中文翻译。  
![github](images/github.png)  

## <font color="green"> Common </font> 

- :ballot_box_with_check: [R语言入门][basic]: 包括Rstudio介绍，R的数据结构和基础语法等  
- :ballot_box_with_check: [R语言基础包][base]：base, stats等基础包函数  
- :ballot_box_with_check: [R6 and S4][R6]：面向对象  
- :ballot_box_with_check: [tidyverse+tibble][tidyverse]：Hadley包集合，核心包(ggplot2,tibble,tidyr,readr,purrr,dplyr)  
- :ballot_box_with_check: [data.table][data.table]：简短的代码实现快速操作数据  
- :heart:  devtools：使开发R包变得更简单(Hadley) (Update according to [cheat sheets][sheet])  
- :heart:  [rpy2][rpy2]：Python 通过rpy2调用 R语言  

[basic]: /posts/R/RNotebook(Common)--R-base.html
[base]: /posts/R/RNotebook(Common)--R-basic-packages.html
[tidyverse]: /posts/R/RNotebook(Common)--tidyverse+tibble.html
[data.table]: /posts/R/RNotebook(Common)--data.table.html
[R6]: /posts/R/RNotebook(Common)--Object-Oriented(R6-and-S4).html
[rpy2]: /posts/python/PythonNotebook(Python-Basics)--RPy2.html


## <font color="green"> Syntax </font> 

- :ballot_box_with_check: [purrr][purrr]：函数化编程(FP, functional programming) (Hadley)  
- :white_large_square:  lambda.r：R中的函数式编程和简单模式匹配  
- :ballot_box_with_check: [magrittr][magrittr]：Let’s pipe it  
- :heart:  pipeR：多范式管道编程  

[purrr]: /posts/R/RNotebook(Syntax)--purrr.html
[magrittr]: /posts/R/RNotebook(Syntax)--magrittr.html

## <font color="green"> Import</font>  

- :ballot_box_with_check: [readr][readr]：快速读取文本型数据(csv,tsv,and fwf).(Hadley)  
- :ballot_box_with_check: [readxl][readxl]：for excel files.(Hadley)  
- :ballot_box_with_check: [openxlsx][openxlsx]：丰富的excel处理工具  
- :heart:  [jsonlite][jsonlite]：JSON处理.(Hadley)  
- :white_large_square:  haven：for SPSS,SAS and Stata files.(Hadley)  
- :heart:  feather：for sharing with Python and other languages.(Hadley)  

[readr]: /posts/R/RNotebook(Import)--read-csv-xlsx-or-json.html#readr:-read-rectangular-text-data
[readxl]: /posts/R/RNotebook(Import)--read-csv-xlsx-or-json.html#readxl:-for-excel
[openxlsx]: /posts/R/RNotebook(Import)--read-csv-xlsx-or-json.html#openxlsx:-xlsx-reading,-writing-and-editing
[jsonlite]: /posts/R/RNotebook(Import)--read-csv-xlsx-or-json.html#jsonlite:-for-json

*DATABASE MANAGEMENT*  

- :heart:  [DBI][DBI]：数据库统一接口(Hadley)  
- :heart:  RHive：通过Apache Hive促进分布式计算的R扩展  

[DBI]: /posts/R/RNotebook(Import)--DBI.html

*WEB TECHNOLOGIES*  

- :heart:  RCurl：用于R的通用网络(HTTP/FTP/ ...)接口  
- :ballot_box_with_check: [httr][httr]：for web APIs (RCurl升级版) (Hadley) (Update according to GitHub)  
- :ballot_box_with_check: [rvest][rvest]：web scraping (Hadley)  (Update according to GitHub)  
- :ballot_box_with_check:  xml2：解析XML文件 (Hadley)  (Update according to GitHub)  

[httr]: https://httr.r-lib.org/
[rvest]: /posts/R/RNotebook(Import)--rvest.html

## <font color="green"> Tidy+Transform</font>  

*DATA MANIPULATION*  

- :ballot_box_with_check: [tidyr][tidyr]：清理数据，reshape2替代版(Hadley)  
- :ballot_box_with_check: [dplyr and plyr][dplyr]：数据操作(Hadley)  
- :white_large_square:  rlist：用于list(非规整)数据操作工具箱  
- :ballot_box_with_check: [stringr][stringr]：for strings.(Hadley)  
- :white_large_square:  utf8：处理和修复R中的多种文本编码问题   
- :ballot_box_with_check: [lubridate+hms][lubridate]：for date and times(Hadley)  
- :ballot_box_with_check: [forcats][forcats]：for factors(Hadley)  
- :white_large_square:  sjmisc：各种实用功能的集合，支持数据重编码，缺失值处理等，与dplyr包无缝协作。  
- :ballot_box_with_check: [naniar][naniar]：缺失数据概述和可视化  
- :ballot_box_with_check: [simputation][simputation]：缺失数据插补框架  

[tidyr]: /posts/R/RNotebook(Tidy+Transform)--tidyr.html
[dplyr]: /posts/R/RNotebook(Tidy+Transform)--dplyr-and-plyr.html
[stringr]: /posts/R/RNotebook(Tidy+Transform)--stringr.html
[lubridate]: /posts/R/RNotebook(Tidy+Transform)--lubridate+hms.html
[forcats]: /posts/R/RNotebook(Tidy+Transform)--forcats.html
[naniar]: /posts/R/RNotebook(Tidy+Transform)--for-missing-data(naniar-and-simputation).html
[simputation]: /posts/R/RNotebook(Tidy+Transform)--for-missing-data(naniar-and-simputation).html

*LARGE DATASETS*  

- :white_large_square:  ff：在内存外存储数据，处理起来和在内存一样  
- :white_large_square:  bigmemory：内存外存储，操作，big 系列包提供了其他工具，包括线性模型 (biglm) 和随机森林 (bigrf)。  

## <font color="green"> Visualise</font>  

*GRAPHIC DISPLAYS*  

- :ballot_box_with_check: [RColorBrewer and extrafont][extrafont]：调色板和字体  
- :ballot_box_with_check: [ggmap+baidumap][ggmap]：使用ggplot2在R中绘制静态地图  
- :ballot_box_with_check: ggpubr：ggplot2封装，用于绘制适合出版物要求的图形  
- :heart:  corrplot：相关矩阵或一般矩阵的图形显示  
- :white_large_square:  misc3d：处理3D图，等值面等  
- :ballot_box_with_check: [ggplot2][ggplot2]：强大的绘图系统，并实现了许多扩展(Hadley)  
- :ballot_box_with_check: [ggplot2 extensions][ggplot2 extensions]: ggplot2扩展，包括各种补充图形，坐标系统，主题等。  

[extrafont]: /posts/R/RNotebook(Visualise)--RColorBrewer-and-extrafont.html
[ggplot2]: /posts/R/RNotebook(Visualise)--ggplot2.html
[ggmap]: /posts/R/RNotebook(Visualise)--ggmap+baidumap.html
[ggplot2 extensions]: http://www.ggplot2-exts.org/ggiraph.html

*HTML WIDGETS*  

- :heart:  [leaflet+leafletCN][leaflet+leafletCN]：最流行的JavaScript库交互式地图之一，动态交互地图。  
- :ballot_box_with_check: [Remap][Remap]：简易动态交互地图(基于Echarts)。  
- :heart:  rCharts：来自R的交互式JS图表。  
- :white_large_square:  DiagrammeR：在R中创建JS图形和流程图。  
- :white_large_square:  rbokeh：R与Bokeh的接口。  
- :heart:  plotly：R的交互式图形库，基于ggplot2 和shiny。  

[leaflet+leafletCN]: /posts/R/RNotebook(Visualise)--leaflet+leafletCN.html
[Remap]: /posts/R/RNotebook(Visualise)--REmap.html

## <font color="green"> Parallel Computing</font> 

- :heart:  [foreach][foreach]：在循环(loop)中并行化运算  

[foreach]: /posts/R/RNotebook(Parallel-Computing)--foreach.html

## <font color="green"> MapReduce</font>  

- :heart:  SparkR：Spark的R前端  
- :heart:  sparklyr：来自RStudio的Apache Spark的R接口，提供dplyr后端  

## <font color="green"> Model Tools</font>  

- :ballot_box_with_check: [broom][broom]：用于将统计模型的结果整理成数据框形式(Hadley)  
- :ballot_box_with_check: [modelr][modelr]：管道建模辅助包(Hadley)  
- :heart:  caret：分类和回归问题的数据训练综合工具包（包括交叉验证，网格搜索等）  

[broom]: /posts/R/RNotebook(Model-Tools)--broom.html
[modelr]: /posts/R/RNotebook(Model-Tools)--modelr.html


## <font color="green"> Machine Learning</font>  

- :ballot_box_with_check: [mlr][mlr]：机器学习（分类，回归，生存分析，聚类等）的可扩展框架，提供了用于分析的整套工具，包括重抽样，缺失值插补，模型评估(cv,etc)，超参数调优(grid-search,etc)，特征选择，可视化(ROC,learnning-curve,etc)等  
- :white_large_square:  mlapi：提供模型的统一接口，以便机器学习流程化(借鉴python scikit-learn，尚未开发完整)  
- :ballot_box_with_check: xgboost：以其速度和性能而著称的eXtreme Gradient Boosting Tree模型  
- :ballot_box_with_check: arules：关联规则挖掘和频繁项集  
- :white_large_square:  survival：生存分析模型  
- :white_large_square:  nnet：神经网络  

[mlr]: /posts/R/RNotebook(Machine-Learning)--mlr.html

## <font color="green"> Deep Learning</font>  

- :heart:  tensorflow：Google开源的最受欢迎的深度学习框架  
- :heart:  h2o：深度学习框架 (Update according to [cheat sheets][sheet])  
- :heart:  keras：以 tensorflow/theano/CNTK 为后端的深度学习封装库   

## <font color="green"> NLP (Natural Language Processing)</font>  

- :ballot_box_with_check: [jiebaR][jiebaR]：中文分词包  
- :white_large_square:  Rwordseg：中文分词包，安装复杂  
- :ballot_box_with_check: [wordcloud2][wordcloud2]：词云  
- :white_large_square:  tm： 一个全面的文本挖掘框架  
- :heart:  quanteda：文本挖掘 (Update according to [cheat sheets][sheet])  
- :heart:  tidytex：简单文本挖掘，结合dplyr，ggplot2和其他简洁工具  
- :ballot_box_with_check: [text2vec][text2vec]：一个快速文本挖掘框架（jiebaR推荐包） (Update according to GitHub)  

[jiebaR]: /posts/R/RNotebook(NLP)--jiebaR.html
[wordcloud2]: /posts/R/RNotebook(NLP)--wordcloud2.html
[text2vec]: /posts/R/RNotebook(NLP)--text2vec.html

## <font color="green"> Time Series</font>  

- :ballot_box_with_check: [zoo][zoo]：定义了规则和不规则时间序列S3类  (Update according to GitHub)  
- :heart:  [xts][xts]：对时间序列数据(zoo)的一种扩展实现，统一时间序列的操作接口  (Update according to GitHub)  
- :ballot_box_with_check: [prophet][prophet]：线性或非线性模型高质量时间序列预测，它最适合日常数据  
- :ballot_box_with_check: [forecast][forecast]：时间序列建模和预测  
- :ballot_box_with_check: [forecastHybrid][forecastHybrid]：结合forcast包时间序列模型混合预测  
- :white_large_square:  CausalImpact：使用贝叶斯结构时间序列模型进行因果推理  

[zoo]: /posts/R/RNotebook(Time-Series)--zoo.html
[xts]: http://joshuaulrich.github.io/xts/
[prophet]: /posts/R/RNotebook(Time-Series)--forecast-and-prophet.html
[forecast]: /posts/R/RNotebook(Time-Series)--forecast-and-prophet.html
[forecastHybrid]: /posts/R/RNotebook(Time-Series)--forecast-and-prophet.html

## <font color="green"> Finance</font>  

- :white_large_square:  quantmod：定量金融建模与交易框架（股票）  
- :white_large_square:  PerformanceAnalytics：用于性能和风险分析的计量经济学工具  

## <font color="green"> Communicate</font>  

- :ballot_box_with_check: [R Markdown][rmarkdown]：用于创建可重复性报告和动态文档  
- :white_large_square:  rticles：提供了一套RMarkdown模板  
- :white_large_square:  flexdashboard：基于rmarkdown，可以轻松的创建仪表盘  
- :white_large_square:  slidify：从Rmarkdown生成可重现的html5幻灯片  
- :white_large_square:  knitr：用于在PDF和HTML文档中嵌入R代码块  
- :ballot_box_with_check: [shiny][shiny]：使用R语言开发交互式web应用程序的工具  

[rmarkdown]: /posts/R/RNotebook(Communicate)--R-Markdown.html
[shiny]: /posts/R/RNotebook(Communicate)--shiny.html

## <font color="green"> Learning R</font>  

- :ballot_box_with_check: [Advanced R][Advanced R]   
- :ballot_box_with_check: [R packages][R packages]   
- :ballot_box_with_check: [R for Data Science][DataScienceR]   
- :ballot_box_with_check: [AwesomeR][AwesomeR]：R包大全  
- :ballot_box_with_check: [RStudio Cheat Sheets][sheets]   
- :ballot_box_with_check: [TaskViews][task]：CRAN Task Views  
- :ballot_box_with_check: [Search][Search]：Google search engine  

[Advanced R]: http://adv-r.had.co.nz/
[R packages]: http://r-pkgs.had.co.nz/
[DataScienceR]: http://r4ds.had.co.nz/
[AwesomeR]: https://github.com/asxinyu/AwesomeResources
[sheets]: https://www.rstudio.com/resources/cheatsheets/
[task]: https://cran.r-project.org/web/views/
[Search]: https://cran.r-project.org/search.html
[GitHub]: https://github.com/

------
