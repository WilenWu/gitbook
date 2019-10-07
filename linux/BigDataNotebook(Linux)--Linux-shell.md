---
title: 大数据手册(Linux)--Linux shell教程
tags: [linux,大数据]
mathjax: false
copyright: true
date: 2018-06-22 13:38:14
categories: [Big Data]
sticky: false
---

<!--Hexo不能正常编译"{#"-->

------

[大数据手册(Linux)--Linux基础知识](https://wilenwu.github.io/big-data/BigDataNotebook(Linux)--Linux-base.html.html)
[大数据手册(Linux)--Linux Shell教程](https://wilenwu.github.io/big-data/BigDataNotebook(Linux)--Linux-shell.html)

------


# Shell简介

Shell 是一个用 C 语言编写的程序，它是用户使用 Linux 的桥梁。Shell 既是一种命令语言，又是一种程序设计语言。
Shell 注释以"#"开头的行就是注释，会被解释器忽略。sh里没有多行注释，只能每一行加一个#号。

<!-- more -->

# Shell 变量

- 定义变量时，变量名和等号之间**不能有空格**
- 还可以用控制/循环语句给变量赋值
- 使用变量，只要在变量名前面加美元符号`$`即可
- 变量名外面加`{}`，可以识别边界
-  `readonly` 命令可以将变量定义为只读变量
- `unset` 命令可以删除变量

**example**
```bash
your_name="runoob.com"  #赋值定义
for skill in Ada Coffe Action Java; do
    echo "I am good at ${skill}Script"
done

readonly your_name  #只读
echo $your_name  #引用变量
unset your_name  #删除变量
```

# Shell 字符串

字符串可以用单引号，也可以用双引号，也可以不用引号。

- 单引号里的任何字符都会**原样输出**
- 单引号字符串中的**变量是无效的**
- 双引号里可以有**变量**
- 双引号里可以出现**转义字符**
- 获取字符串长度 ${<b></b>#string}
- 字符串切片(length可以省略)`${string:start:length}`

```sh
str='string'
greeting="hello, ${str} !\n"
echo ${#str} # 输出6
echo ${str:1:4} # 输出 trin
echo ${str:4} #输出 ng
```

字符串切割的几种方法

- 利用shell 中 变量 的字符串替换   
`${parameter//pattern/string} `用string来替换parameter变量中所有匹配的pattern
- 设置分隔符，通过 IFS 变量
由于只是对单个字符进行的替换，则可以用  `echo args | tr "oldSpilt" "newSpilt"`  的方式实现
- 利用tr 指令实现字符替换  （！只能针对单个分隔符）

```bash
string="hello,shell,split,test"  
array=(${string//,/ })

partitions=(`hive -e "show partitions employee;"`)
for partition in partitions
  do
    part=(${partition////,})
    echo ${part:2}
  done
```


# Shell 数组

```bash
array_name=(value0 value1 ... valuen) #空格或换行定义数组
array_name[n]=valuen  #单独定义数组分量
```

- `${array_name[n]}`引用数组元素
-  `${array_name[@]}`引用整个数组
- \${\#array_name[@]} or \${\#array_name[*]} 获取数组长度
- \${\#array_name[n]} 获取数组元素的长度



# Shell 传递参数

[参考链接](http://www.runoob.com/linux/linux-shell-passing-arguments.html)

我们可以在**命令行**执行 **Shell 脚本**时，向脚本传递参数，**脚本内**获取参数的格式为：\$n。n 代表一个数字，0为脚本名，1为传递的第一个参数，2 为传递第二个参数，以此类推……

- 新建脚本test.sh脚本，内容如下：
```bash
#!/bin/bash
echo "执行的文件名：$0";
echo "第一个参数为：$1";
echo "第二个参数为：$2";
echo "第三个参数为：$3";
```

- shell终端执行脚本test.sh
```bash
chmod +x test.sh 
./test.sh a b c  #传递参数a,b,c 给脚本

# 输出内容如下：
执行的文件名：./test.sh
第一个参数为：a
第二个参数为：b
第三个参数为：c
```

# Shell 基本运算符

- 原生bash不支持简单的数学运算，但是可以通过其他命令来实现，例如 awk 和 expr，expr 最常用。
- 完整的表达式要被 \` 包含
- 表达式和运算符之间要有**空格**，例如 2+2 是不对的，必须写成 2 + 2，这与我们熟悉的大多数编程语言不一样。

```bash
#!/bin/bash
val=`expr 2 + 2`
echo "两数之和为 : $val"
let b=val*2
echo $b
```

算术运算符|说明|举例
:-|--|--
+   |加法|    `expr $a + $b` 
\-   |减法 |`expr $a - $b` 
\*  |乘法|    `expr $a * $b` 
/   |除法 |`expr $b / $a` 
%   |取余 |`expr $b % $a` 
=   |赋值 |`a=$b` 
==|相等|  `[ 10 == 20 ]` 返回false
!=|不相等| `[ 10 != 20 ]` 返回true

关系运算符|数字|字符串
--|--|--
相等|`[a -eq b] or [a == b]`| `[str1 = str2]`
不等|`[a -ne b] or [a != b]`|`[str1 != str2]`
大于|`[a -gt b]`
小于|`[a -lt b]`
大于等于|`[a -ge b]`
小于等于|`[a -le b]`
字符串长度为0||`[ -z str ]`
字符串长度不为0||`[ -n str ]`
字符串为空||`[str $a ] `

布尔运算符|说明|举例
--|--|--
！|非运算|`[ ! true ]` 返回false
-o|或运算|`[ 10 -lt 20 -o 20 -gt 100 ]` 返回 true
-a|与运算|`[ 10 -lt 20 -a 20 -gt 100 ]` 返回 false

```bash
a=10
b=20
if [ $a -lt 100 -a $b -gt 15 ]
then
   echo "$a 小于 100 且 $b 大于 15 : 返回 true"
else
   echo "$a 小于 100 且 $b 大于 15 : 返回 false"
fi
```

逻辑运算符|说明|举例
--|--|--
`&&`|逻辑的 AND|`[[ 10 -lt 100 && 20 -gt 100 ]]` 返回 false
`||`|逻辑的 OR|`[[ 10 -lt 100 \|\| 20 -gt 100 ]]` 返回 true

```bash
a=10
b=20

if [[ $a -lt 100 && $b -gt 100 ]]
then
   echo "返回 true"
else
   echo "返回 false"
fi
```

文件测试运算符|说明
--|--
`[ -d file ]`|检测文件是否是目录
`[ -f file ]`   |检测文件是否是普通文件（既不是目录，也不是设备文件）
`[ -r file ]`   |检测文件是否可读
`[ -w file ]`   |检测文件是否可写
`[ -x file ]`   |检测文件是否可执行
`[ -s file ]`   |检测文件是否为空（文件大小是否大于0）
`[ -e file ]`   |检测文件（包括目录）是否存在

# Shell 流程控制

##  if 语句

```bash
if condition1
then
    command1
elif condition2 
then 
    command2
else
    commandN
fi

# 单行if语句
if condition; then command; fi 
```

## for 循环

```bash
for var in item1 item2 ... itemN
do
    command1
    command2
    ...
    commandN
done

for var in item1 item2 ... itemN; do command1; command2… done; 

# ------------------------类C语法
for((i=1;i<=10;i++))
do
echo $i
done
# -----------------------数字序列
for i in $(seq 1 10)  
do   
echo $(expr $i \* 3 + 1);  
done   
# --------------------整数序列  
for i in {1..10}  
do  
echo $(expr $i \* 3 + 1);  
done 
# -------------------遍历目录
for i in `ls`;  
do   
echo $i is file name\! ;  
done 
```

```bash
# 备份一个hive表
empl=(`hive -e "show partitions employee;"`)
emp2=(`hive -e "show partitions employee_backup;"`)
for((i=1;i<${#empl[@]};i++))
  do
    update=${#empl[@]}
    tmp=(`echo ${emp2[@]} | grep ${update}`)

    if [ -z ${tmp} ]
    then
      hive "
      insert overwrite table tmp2 partition(${update})
      select `(y|m|d)?+.+` from  employee where ${update}
      ;" 
      printf "%-20s\n" ${update} > info 
    fi 
  done 
```

> 参考链接： [Linux下Shell的for循环语句](https://www.cnblogs.com/EasonJim/p/8315939.html)

## while 语句

```bash
while condition
do
    command
done
```

## until 循环

until 循环执行一系列命令直至条件为 true 时停止。

```bash
until condition
do
    command
done
```

## case语句

Shell case语句为多选择语句。可以用case语句匹配一个值与一个模式，如果匹配成功，执行相匹配的命令。

```bash
case values in
val1)
    command1
    command2
    ...
    commandN
    ;;
val2）
    command1
    command2
    ...
    commandN
    ;;
esac
```

## 跳出循环

```bash
break #跳出所有循环
continue #跳出当前循环
```

# Shell 函数

```bash
function funname ()
{
    action;
    return int;
}
```

说明：

- linux shell 可以用户定义函数，然后在shell脚本中可以随便调用。
- 可以不带关键字`function` 
- 参数的传递方法和使用脚本一样，`$1,$2`等
- 参数可以隐式加载
- `return`可以省略（将以最后一条命令运行结果）


