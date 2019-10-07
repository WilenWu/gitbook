  
说明：本手册所列包基本来自[AwesomeR][AwesomeR] ，结合[GitHub][GitHub]和`help(package="pk_name")`官方文档整理所得，有助于使用时下最实用的包对R进行深入的学习。  
  
其中，标记 <input type="checkbox" checked='checked' />的是本人必学，❤为待选包。  
  
致谢，[ApacheCN 中文开源组织](http://www.apachecn.org/#)：致力于官方文档及AI书籍中文翻译。  
  
![github](images/github.png)  
  
---------------------------------------  
# Common  
  
  :white_check_mark: [R语言入门][basic]: 包括Rstudio介绍，R的数据结构和基础语法等  
  :white_check_mark: [R语言基础包][base]：base, stats等基础包函数  
  :white_check_mark: [R6 and S4][R6]：面向对象  
  :white_check_mark: [tidyverse+tibble][tidyverse]：Hadley包集合，核心包(ggplot2,tibble,tidyr,readr,purrr,dplyr)  
  :white_check_mark: [data.table][data.table]：简短的代码实现快速操作数据  
  :white_medium_square:  devtools：❤使开发R包变得更简单(Hadley) (Update according to [cheat sheets][sheet])  
  :white_medium_square:  [rpy2][rpy2]：❤Python 通过rpy2调用 R语言  
  
[basic]: https://wilenwu.github.io/posts/R/RNotebook(Common)--R-base.html  
[base]: https://wilenwu.github.io/posts/R/RNotebook(Common)--R-basic-packages.html  
[tidyverse]: https://wilenwu.github.io/posts/R/RNotebook(Common)--tidyverse+tibble.html  
[data.table]: https://wilenwu.github.io/posts/R/RNotebook(Common)--data.table.html  
[R6]: https://wilenwu.github.io/posts/R/RNotebook(Common)--Object-Oriented(R6-and-S4).html  
[rpy2]: https://wilenwu.github.io/posts/python/PythonNotebook(Python-Basics)--RPy2.html  
  
  
# Syntax  
  
  :white_check_mark: [purrr][purrr]：函数化编程(FP, functional programming) (Hadley)  
  :white_medium_square:  lambda.r：R中的函数式编程和简单模式匹配  
  :white_check_mark: [magrittr][magrittr]：Let’s pipe it  
  :white_medium_square:  pipeR：❤多范式管道编程  
  
[purrr]: https://wilenwu.github.io/posts/R/RNotebook(Syntax)--purrr.html  
[magrittr]: https://wilenwu.github.io/posts/R/RNotebook(Syntax)--magrittr.html  
  
# Import  
  
  :white_check_mark: [readr][readr]：快速读取文本型数据(csv,tsv,and fwf).(Hadley)  
  :white_check_mark: [readxl][readxl]：for excel files.(Hadley)  
  :white_check_mark: [openxlsx][openxlsx]：丰富的excel处理工具  
  :white_medium_square:  [jsonlite][jsonlite]：❤JSON处理.(Hadley)  
  :white_medium_square:  haven：for SPSS,SAS and Stata files.(Hadley)  
  :white_medium_square:  feather：❤for sharing with Python and other languages.(Hadley)  
  
[readr]: https://wilenwu.github.io/posts/R/RNotebook(Import)--read-csv-xlsx-or-json.html#readr:-read-rectangular-text-data  
[readxl]: https://wilenwu.github.io/posts/R/RNotebook(Import)--read-csv-xlsx-or-json.html#readxl:-for-excel  
[openxlsx]: https://wilenwu.github.io/posts/R/RNotebook(Import)--read-csv-xlsx-or-json.html#openxlsx:-xlsx-reading,-writing-and-editing  
[jsonlite]: https://wilenwu.github.io/posts/R/RNotebook(Import)--read-csv-xlsx-or-json.html#jsonlite:-for-json  
  
*DATABASE MANAGEMENT*  
  
  :white_medium_square:  [DBI][DBI]：❤数据库统一接口(Hadley)  
  :white_medium_square:  RHive：❤通过Apache Hive促进分布式计算的R扩展  
  
[DBI]: https://wilenwu.github.io/posts/R/RNotebook(Import)--DBI.html  
  
*WEB TECHNOLOGIES*  
  
  :white_medium_square:  RCurl：❤用于R的通用网络(HTTP/FTP/ ...)接口  
  :white_check_mark: [httr][httr]：for web APIs (RCurl升级版) (Hadley) (Update according to GitHub)  
  :white_check_mark: [rvest][rvest]：web scraping (Hadley)  (Update according to GitHub)  
  :white_check_mark:  xml2：解析XML文件 (Hadley)  (Update according to GitHub)  
  
[httr]: https://httr.r-lib.org/  
[rvest]: https://wilenwu.github.io/posts/R/RNotebook(Import)--rvest.html  
  
# Tidy+Transform  
  
*DATA MANIPULATION*  
  
  :white_check_mark: [tidyr][tidyr]：清理数据,reshape2替代版(Hadley)  
  :white_check_mark: [dplyr and plyr][dplyr]：数据操作(Hadley)  
  :white_medium_square:  rlist：用于list(非规整)数据操作工具箱  
  :white_check_mark: [stringr][stringr]：for strings.(Hadley)  
  :white_medium_square:  utf8：处理和修复R中的多种文本编码问题   
  :white_check_mark: [正则表达式][re]：Regular Expression  
  :white_check_mark: [lubridate+hms][lubridate]：for date and times(Hadley)  
  :white_check_mark: [forcats][forcats]：for factors(Hadley)  
  :white_medium_square:  sjmisc：各种实用功能的集合，支持数据重编码，缺失值处理等，与dplyr包无缝协作。  
  :white_check_mark: [naniar][naniar]：缺失数据概述和可视化  
  :white_check_mark: [simputation][simputation]：缺失数据插补框架  
  
[tidyr]: https://wilenwu.github.io/posts/R/RNotebook(Tidy+Transform)--tidyr.html  
[dplyr]: https://wilenwu.github.io/posts/R/RNotebook(Tidy+Transform)--dplyr-and-plyr.html  
[stringr]: https://wilenwu.github.io/posts/R/RNotebook(Tidy+Transform)--stringr.html  
[re]: https://wilenwu.github.io/posts/R/RNotebook(Tidy+Transform)--regular-expression.html  
[lubridate]: https://wilenwu.github.io/posts/R/RNotebook(Tidy+Transform)--lubridate+hms.html  
[forcats]: https://wilenwu.github.io/posts/R/RNotebook(Tidy+Transform)--forcats.html  
[naniar]: https://wilenwu.github.io/posts/R/RNotebook(Tidy+Transform)--for-missing-data(naniar-and-simputation).html  
[simputation]: https://wilenwu.github.io/posts/R/RNotebook(Tidy+Transform)--for-missing-data(naniar-and-simputation).html  
  
*LARGE DATASETS*  
  
  :white_medium_square:  ff：在内存外存储数据，处理起来和在内存一样  
  :white_medium_square:  bigmemory：内存外存储，操作，big 系列包提供了其他工具，包括线性模型 (biglm) 和随机森林 (bigrf)。  
  
# Visualise  
  
*GRAPHIC DISPLAYS*  
  
  :white_check_mark: [RColorBrewer and extrafont][extrafont]：调色板和字体  
  :white_check_mark: [ggmap+baidumap][ggmap]：使用ggplot2在R中绘制静态地图  
  :white_check_mark: ggpubr：ggplot2封装，用于绘制适合出版物要求的图形  
  :white_medium_square:  corrplot：❤相关矩阵或一般矩阵的图形显示  
  :white_medium_square:  misc3d：处理3D图，等值面等  
  :white_check_mark: [ggplot2][ggplot2]：强大的绘图系统，并实现了许多扩展(Hadley)  
  :white_check_mark: [ggplot2 extensions][ggplot2 extensions]: ggplot2扩展，包括各种补充图形，坐标系统，主题等。  
  
[extrafont]: https://wilenwu.github.io/posts/R/RNotebook(Visualise)--RColorBrewer-and-extrafont.html  
[ggplot2]: https://wilenwu.github.io/posts/R/RNotebook(Visualise)--ggplot2.html  
[ggmap]: https://wilenwu.github.io/posts/R/RNotebook(Visualise)--ggmap+baidumap.html  
[ggplot2 extensions]: http://www.ggplot2-exts.org/ggiraph.html  
  
*HTML WIDGETS*  
  
  :white_medium_square:  [leaflet+leafletCN][leaflet+leafletCN]：❤最流行的JavaScript库交互式地图之一，动态交互地图。  
  :white_check_mark: [Remap][Remap]：简易动态交互地图(基于Echarts)。  
  :white_medium_square:  rCharts：❤来自R的交互式JS图表。  
  :white_medium_square:  DiagrammeR：在R中创建JS图形和流程图。  
  :white_medium_square:  rbokeh：R与Bokeh的接口。  
  :white_medium_square:  plotly：❤R的交互式图形库，基于ggplot2 和shiny。  
  
[leaflet+leafletCN]: https://wilenwu.github.io/posts/R/RNotebook(Visualise)--leaflet+leafletCN.html  
[Remap]: https://wilenwu.github.io/posts/R/RNotebook(Visualise)--REmap.html  
  
# Parallel Computing  
  
  :white_medium_square:  [foreach][foreach]：❤在循环(loop)中并行化运算  
  
[foreach]: https://wilenwu.github.io/posts/R/RNotebook(Parallel-Computing)--foreach.html  
  
# MapReduce  
  
  :white_medium_square:  SparkR：❤Spark的R前端  
  :white_medium_square:  sparklyr：❤来自RStudio的Apache Spark的R接口，提供dplyr后端  
  
# Model Tools  
  
  :white_check_mark: [broom][broom]：用于将统计模型的结果整理成数据框形式(Hadley)  
  :white_check_mark: [modelr][modelr]：管道建模辅助包(Hadley)  
  :white_medium_square:  caret：❤分类和回归问题的数据训练综合工具包（包括交叉验证，网格搜索等）  
  
[broom]: https://wilenwu.github.io/posts/R/RNotebook(Model-Tools)--broom.html  
[modelr]: https://wilenwu.github.io/posts/R/RNotebook(Model-Tools)--modelr.html  
  
  
# Machine Learning  
  
  :white_check_mark: [mlr][mlr]：机器学习（分类，回归，生存分析，聚类等）的可扩展框架，提供了用于分析的整套工具，包括重抽样，缺失值插补，模型评估(cv,etc)，超参数调优(grid-search,etc)，特征选择，可视化(ROC,learnning-curve,etc)等  
  :white_medium_square:  mlapi：提供模型的统一接口，以便机器学习流程化(借鉴python scikit-learn，尚未开发完整)  
  :white_check_mark: xgboost：以其速度和性能而著称的eXtreme Gradient Boosting Tree模型  
  :white_check_mark: arules：关联规则挖掘和频繁项集  
  :white_medium_square:  survival：生存分析模型  
  :white_medium_square:  nnet：神经网络  
  
[mlr]: https://wilenwu.github.io/posts/R/RNotebook(Machine-Learning)--mlr.html  
  
# Deep Learning  
  
  :white_medium_square:  tensorflow：❤Google开源的最受欢迎的深度学习框架  
  :white_medium_square:  h2o：❤深度学习框架 (Update according to [cheat sheets][sheet])  
  :white_medium_square:  keras：❤以 tensorflow/theano/CNTK 为后端的深度学习封装库   
  
# NLP (Natural Language Processing)  
  
  :white_check_mark: [jiebaR][jiebaR]：中文分词包  
  :white_medium_square:  Rwordseg：中文分词包，安装复杂  
  :white_check_mark: [wordcloud2][wordcloud2]：词云  
  :white_medium_square:  tm： 一个全面的文本挖掘框架  
  :white_medium_square:  quanteda：❤文本挖掘 (Update according to [cheat sheets][sheet])  
  :white_medium_square:  tidytex：❤简单文本挖掘，结合dplyr，ggplot2和其他简洁工具  
  :white_check_mark: [text2vec][text2vec]：一个快速文本挖掘框架（jiebaR推荐包） (Update according to GitHub)  
  
[jiebaR]: https://wilenwu.github.io/posts/R/RNotebook(NLP)--jiebaR.html  
[wordcloud2]: https://wilenwu.github.io/posts/R/RNotebook(NLP)--wordcloud2.html  
[text2vec]: https://wilenwu.github.io/posts/R/RNotebook(NLP)--text2vec.html  
  
# Time Series  
  
  :white_check_mark: [zoo][zoo]：定义了规则和不规则时间序列S3类  (Update according to GitHub)  
  :white_medium_square:  [xts][xts]：❤对时间序列数据(zoo)的一种扩展实现，统一时间序列的操作接口  (Update according to GitHub)  
  :white_check_mark: [prophet][prophet]：线性或非线性模型高质量时间序列预测，它最适合日常数据  
  :white_check_mark: [forecast][forecast]：时间序列建模和预测  
  :white_check_mark: [forecastHybrid][forecastHybrid]：结合forcast包时间序列模型混合预测  
  :white_medium_square:  CausalImpact：使用贝叶斯结构时间序列模型进行因果推理  
  
[zoo]: https://wilenwu.github.io/posts/R/RNotebook(Time-Series)--zoo.html  
[xts]: http://joshuaulrich.github.io/xts/  
[prophet]: https://wilenwu.github.io/posts/R/RNotebook(Time-Series)--forecast-and-prophet.html  
[forecast]: https://wilenwu.github.io/posts/R/RNotebook(Time-Series)--forecast-and-prophet.html  
[forecastHybrid]: https://wilenwu.github.io/posts/R/RNotebook(Time-Series)--forecast-and-prophet.html  
  
# Finance  
  
  :white_medium_square:  quantmod：定量金融建模与交易框架（股票）  
  :white_medium_square:  PerformanceAnalytics：用于性能和风险分析的计量经济学工具  
  
# Communicate  
  
  :white_check_mark: [R Markdown][rmarkdown]：用于创建可重复性报告和动态文档  
  :white_medium_square:  rticles：提供了一套RMarkdown模板  
  :white_medium_square:  flexdashboard：基于rmarkdown，可以轻松的创建仪表盘  
  :white_medium_square:  slidify：从Rmarkdown生成可重现的html5幻灯片  
  :white_medium_square:  knitr：用于在PDF和HTML文档中嵌入R代码块  
  :white_check_mark: [shiny][shiny]：使用R语言开发交互式web应用程序的工具  
  
[rmarkdown]: https://wilenwu.github.io/posts/R/RNotebook(Communicate)--R-Markdown.html  
[shiny]: https://wilenwu.github.io/posts/R/RNotebook(Communicate)--shiny.html  
  
# Others  
  
  :white_check_mark: [Advanced R][Advanced R]   
  :white_check_mark: [R packages][R packages]   
  :white_check_mark: [R for Data Science][DataScienceR]   
  :white_check_mark: [AwesomeR][AwesomeR]：R包大全  
  :white_check_mark: [RStudio Cheat Sheets][sheets]   
  :white_check_mark: [TaskViews][task]：CRAN Task Views  
  :white_check_mark: [Search][Search]：Google search engine  
  
  
[Advanced R]: http://adv-r.had.co.nz/  
[R packages]: http://r-pkgs.had.co.nz/  
[DataScienceR]: http://r4ds.had.co.nz/  
[AwesomeR]: https://github.com/asxinyu/AwesomeResources  
[sheets]: https://www.rstudio.com/resources/cheatsheets/  
[task]: https://cran.r-project.org/web/views/  
[Search]: https://cran.r-project.org/search.html  
[GitHub]: https://github.com/  
  
----------  
  
  
