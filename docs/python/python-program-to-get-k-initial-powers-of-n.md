# Python 程序获取 N 的 K 个初始幂

> 原文:[https://www . geesforgeks . org/python-program-to-get-k-initial-power-of-n/](https://www.geeksforgeeks.org/python-program-to-get-k-initial-powers-of-n/)

给定大小 K 和值 N，任务是编写一个 Python 程序来计算 N 的幂直到 K 的列表

```py
Input : N = 4, K = 6
Output : [1, 4, 16, 64, 256, 1024]
Explanation : 4^i is output till i = K. 

Input : N = 3, K = 6
Output : [1, 3, 9, 27, 81, 243]
Explanation : 3^i is output till i = K. 
```

**方法一:使用** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension/) **+ **操作符**

在这种情况下，使用列表理解将值递增到 K，并使用**获得所需的数字幂。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Get K initial powers of N
# Using list comprehension + ** operator

# initializing N
N = 4

# printing original list
print("The original N is : " + str(N))

# initializing K 
K = 6

# list comprehension provides shorthand for problem
res = [N ** idx for idx in range(0, K)]

# printing result
print("Square values of N till K : " + str(res))
```

**输出:**

```py
The original N is : 4
Square values of N till K : [1, 4, 16, 64, 256, 1024]
```

**方法 2:使用**[**pow()**](https://www.geeksforgeeks.org/pow-in-python/)**+**[**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)

在这种情况下，我们使用 pow()执行计算能力的任务，其余的所有功能都使用列表理解来执行。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Get K initial powers of N
# Using pow() + list comprehension 
from math import pow

# initializing N
N = 4

# printing original list
print("The original N is : " + str(N))

# initializing K 
K = 6

# list comprehension provides shorthand for problem
# squaring using pow()
res = [int(pow(N, idx)) for idx in range(0, K)]

# printing result
print("Square values of N till K : " + str(res))
```

**输出:**

```py
The original N is : 4
Square values of N till K : [1, 4, 16, 64, 256, 1024]
```