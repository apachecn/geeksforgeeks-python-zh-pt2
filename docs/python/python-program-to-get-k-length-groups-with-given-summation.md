# Python 程序获取给定求和的 K 个长度组

> 原文:[https://www . geesforgeks . org/python-program-to-get-k-length-group-with-given-summary/](https://www.geeksforgeeks.org/python-program-to-get-k-length-groups-with-given-summation/)

给定一个列表，我们的任务是编写一个 Python 程序来提取所有的 K 长度子列表，并导致给定的求和。

> **输入:** test_list = [6，3，12，7，4，11]，N = 21，K = 4
> 
> **输出:** [(6，6，6，3)，(6，6，3，6)，(6，3，6，6)，(6，7，4，4)，(6，4，7，4)，(6，4，7)，(3，6，6，6)，(3，3，3，12)，(3，3，12，3)，(3，3，4，11)，(3，3，11，4)，(3，12，3，3)，(3，7，7，4)，(3，7，4)，(3，7，4，7，7，7) 3, 3, 3), (7, 6, 4, 4), (7, 3, 7, 4), (7, 3, 4, 7), (7, 7, 3, 4), (7, 7, 4, 3), (7, 4, 6, 4), (7, 4, 3, 7), (7, 4, 7, 3), (7, 4, 4, 6), (4, 6, 7, 4), (4, 6, 4, 7), (4, 3, 3, 11), (4, 3, 7, 7), (4, 3, 11, 3), (4, 7, 6, 4), (4, 7, 3, 7), (4, 7, 7, 3), (4, 7, 4, 6), (4, 4, 6, 7), (4, 4, 7, 6), (4, 11, 3, 3), (11, 3, 3, 4), (11, 3, 4, 3), (11, 4, 3, 3)]
> 
> **说明:**打印长度 4 和总和 21 的所有组。
> 
> **输入:** test_list = [6，3，12，7，4，11]，N = 210，K = 4
> 
> **输出:** []
> 
> **说明:**由于 4 号尺寸组和等于 210，因此不会打印任何组。

**法:用** [**求和()**](https://www.geeksforgeeks.org/sum-function-python/) **+积()+** [**循环**](https://www.geeksforgeeks.org/python-for-loops/)

在这种情况下，长度为 K 的所有可能的子列表都使用乘积()来计算，sum()用于比较子列表的和与所需的和。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# K length groups with given summation
# Using sum + product()
from itertools import product

# initializing list
test_list = [6, 3, 12, 7, 4, 11]

# printing original list
print("The original list is : " + str(test_list))

# initializing Summation 
N = 21

# initializing size 
K = 4

# Looping for each product and comparing with required summation
res = []
for sub in product(test_list, repeat = K):
  if sum(sub) == N:
    res.append(sub)

# printing result
print("The sublists with of given size and sum : " + str(res))
```

**输出:**

> 原来的名单是:[6，3，12，7，4，11]
> 
> 给定大小和总和的子列表:[(6，6，6，3)，(6，6，3，6)，(6，3，6，6)，(6，7，4，4)，(6，4，7，4)，(6，4，4，7)，(3，6，6，6)，(3，3，3，12)，(3，3，12，3)，(3，3，12，3)，(3，3，4，11)，(3，3，11，4)，(3，12，3，3)，(3，7，4)，(3，7，4)，(3，7，4) (3, 11, 4, 3), (12, 3, 3, 3), (7, 6, 4, 4), (7, 3, 7, 4), (7, 3, 4, 7), (7, 7, 3, 4), (7, 7, 4, 3), (7, 4, 6, 4), (7, 4, 3, 7), (7, 4, 7, 3), (7, 4, 4, 6), (4, 6, 7, 4), (4, 6, 4, 7), (4, 3, 3, 11), (4, 3, 7, 7), (4, 3, 11, 3), (4, 7, 6, 4), (4, 7, 3, 7), (4, 7, 7, 3), (4, 7, 4, 6), (4, 4, 6, 7), (4, 4, 7, 6), (4, 11, 3, 3), (11, 3, 3, 4), (11, 3, 4, 3), (11, 4, 3, 3)]