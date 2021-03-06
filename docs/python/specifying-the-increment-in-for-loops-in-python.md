# 在 Python 中指定 for 循环的增量

> 原文:[https://www . geesforgeks . org/指定 python 中的循环增量/](https://www.geeksforgeeks.org/specifying-the-increment-in-for-loops-in-python/)

让我们看看如何在 Python 中控制 for 循环的增量。我们可以通过使用**[**range()**](https://www.geeksforgeeks.org/python-range-method/)**功能来做到这一点。****

## ******范围()功能******

****range()允许用户在给定范围内生成一系列数字。根据用户传递给函数的参数数量，用户可以决定该系列数字的开始和结束位置，以及一个数字和下一个数字之间的差异有多大。****

> ******语法:**范围(开始、停止、步进)****
> 
>  ******参数:**
> 
> *   **开始:**整数，从该整数开始返回整数序列
> *   **停止:**整数，在此之前将返回整数序列
> *   **步骤:**确定序列中每个整数之间增量的整数值
> 
> **返回:**列表****

******示例 1:** 将迭代器递增 1。****

## ****蟒蛇 3****

```py
**for i in range(5):
  print(i)**
```

******输出:******

```py
**0
1
2
3
4** 
```

******示例 2:** 将迭代器增加一个整数值 n****

## ****蟒蛇 3****

```py
**# increment value
n = 3

for i in range(0, 10, n):
  print(i)**
```

******输出:******

```py
**0
3
6
9** 
```

******示例 3:** 将迭代器递减一个整数值-n****

## ****蟒蛇 3****

```py
**# decrement value
n = -3

for i in range(10, 0, n):
  print(i)**
```

******输出:******

```py
**10
7
4
1** 
```

******示例 4:** 用 n 的指数值递增迭代器。我们将使用列表理解。****

## ****蟒蛇 3****

```py
**# exponential value
n = 2

for i in ([n**x for x in range(5)]):
  print(i)**
```

******输出:******

```py
**1
2
4
8
16** 
```