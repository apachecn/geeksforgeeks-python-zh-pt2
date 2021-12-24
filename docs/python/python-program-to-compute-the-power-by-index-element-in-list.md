# Python 程序通过列表

中的索引元素计算幂

> 原文:[https://www . geeksforgeeks . org/python-程序到计算-列表中的索引元素的幂/](https://www.geeksforgeeks.org/python-program-to-compute-the-power-by-index-element-in-list/)

给定一个列表，任务是编写一个 Python 程序，通过索引值计算每个元素的幂。

> **输入:** test_list = [6，9，1，8，4，7]
> 
> **输出:**【1，9，1，512，256，16807】
> 
> **说明:** 8 * 8 * 8 = 512，因为 8 在第 3 个指数。
> 
> **输入:** test_list = [6，9，1，8]
> 
> **输出:**【1，9，1，512】
> 
> **解释:** 9**1 = 9，因为 9 在第一个指数。

**方法一:使用** [****符**](https://www.geeksforgeeks.org/python-operators/) **+** [**循环**](https://www.geeksforgeeks.org/loops-in-python/) **+** [**枚举()**](https://www.geeksforgeeks.org/enumerate-in-python/)

在这种情况下，获取功率的任务是使用**运算符完成的，循环用于迭代元素。枚举()用于获取索引和值。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Index Power List
# Using ** operator + loop + enumerate()

# initializing list
test_list = [6, 9, 1, 8, 4, 7]

# printing original list
print("The original list is : " + str(test_list))

# ** does task of getting power
res = []
for idx, ele in enumerate(test_list):
  res.append(ele ** idx)

# printing result
print("Powered elements : " + str(res))
```

**输出:**

```py
The original list is : [6, 9, 1, 8, 4, 7]
Powered elements : [1, 9, 1, 512, 256, 16807]
```

**方法二:使用**[**pow()**](https://www.geeksforgeeks.org/pow-in-python/)**+**[**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/) **+** [**枚举()**](https://www.geeksforgeeks.org/enumerate-in-python/)

在本例中，我们使用 pow()执行获取功率的任务，enumerate()用于获取带有值的索引。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Index Power List
# Using pow() + list comprehension + enumerate()
from math import pow

# initializing list
test_list = [6, 9, 1, 8, 4, 7]

# printing original list
print("The original list is : " + str(test_list))

# pow() does task of getting power
# list comprehension for 1 liner alternative
res = [int(pow(ele, idx)) for idx, ele in enumerate(test_list)]

# printing result
print("Powered elements : " + str(res))
```

**输出:**

```py
The original list is : [6, 9, 1, 8, 4, 7]
Powered elements : [1, 9, 1, 512, 256, 16807]
```