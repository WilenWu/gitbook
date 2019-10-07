---

title: R手册(Visualise)--gganimate(ggplot2 extensions)
tags: [R]
mathjax: false
copyright: true
date: 2018-05-28 16:45:17
categories: [R,Visualise]
sticky: false
---


**目录**


--------

[返回ggplot2扩展主目录](https://blog.csdn.net/qq_41518277/article/details/80516938)


<!-- more -->
## gganimate: Create easy animations with ggplot2

GitHub链接: https://github.com/dgrtwo/gganimate

 **ggplot对象**

  `gganimate(p=last_plot(),aes(frame),filename = NULL, interval=1,title_frame = TRUE )`

  > **参数：**
  >
  > aes(frame)：包括时间维度
  >  filename：输出文件
  >  interval：动画间隔
  >  title_frame：是否当前frame值附加到标题
  >
  > **aes()参数:**
  > cumulative = TRUE,：设置是否路径累积

  **geom图层**

geom必须设置aes(group)，group为frame的变量，用来指定时间维度

  ***for example:***

```r
  p <- ggplot(gapminder, aes(gdpPercap, lifeExp, size = pop, frame = year)) +
    geom_point() +geom_smooth(aes(group = year)) +
    facet_wrap(~continent, scales = "free") +
    scale_x_log10()
  gganimate(p, "output.swf", interval=.2)
```

  



