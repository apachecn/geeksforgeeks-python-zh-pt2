# 间隔打印数字的 Python 程序

> 原文:[https://www . geesforgeks . org/python-程序到打印-间隔中的数字/](https://www.geeksforgeeks.org/python-program-to-print-numbers-in-an-interval/)

给定一个数字范围，找出它们之间的所有数字。

> 输入:l = 2，u = 5
> 输出:2 3 4 5
> 
> 输入:l = 10，u = 20
> 输出:10 11 12 13 14 15 16 17 18 19 20

想法是用 Python 中的[范围函数](https://www.geeksforgeeks.org/python-range-method/)。

```py
# Python program to print all the numbers within an interval
l = 10
u = 20

for num in range(l, u + 1):
    print(num)
```

**Output:**

```py
10
11
12
13
14
15
16
17
18
19
20

```

我们也可以打印替代数字或给定步骤的数字。

```py
# Python program to print all EVEN numbers within an interval
l = 10
u = 20
if l%2==0:
    for num in range(l, u + 1, 2):
        print(num)
else:
    for num in range(l+1, u + 1, 2):
        print(num)
```

**Output:**

```py
10
12
14
16
18
20

```