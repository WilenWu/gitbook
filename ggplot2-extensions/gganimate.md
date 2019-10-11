---
ID: c38ea0d1c332c29d4fb05349c08d9320
title: R手册(Visualise)--gganimate(ggplot2 extensions)
tags: [R,ggplot2]
mathjax: false
copyright: true
date: 2018-05-28 16:45:17
categories: [R,Visualise]
sticky: false
---

# gganimate: Create easy animations with ggplot2

[GitHub链接](https://github.com/dgrtwo/gganimate)

## ggplot对象

```R
gganimate(p=last_plot(),aes(frame),filename = NULL, interval=1,title_frame = TRUE )
```

**参数：**

- aes(frame)：包括时间维度
- filename：输出文件
- interval：动画间隔
- title_frame：是否当前frame值附加到标题

**aes参数:**
cumulative = TRUE：设置是否路径累积

## geom图层

geom必须设置aes(group)，group为frame的变量，用来指定时间维度

**for example:**

```R
  p <- ggplot(gapminder, aes(gdpPercap, lifeExp, size = pop, frame = year)) +
    geom_point() +geom_smooth(aes(group = year)) +
    facet_wrap(~continent, scales = "free") +
    scale_x_log10()
  gganimate(p, "output.swf", interval=.2)
```

  



