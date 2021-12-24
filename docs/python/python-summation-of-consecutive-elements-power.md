# Python–连续元素功率之和

> 原文:[https://www . geeksforgeeks . org/python-连续元素求和-power/](https://www.geeksforgeeks.org/python-summation-of-consecutive-elements-power/)

给定一个列表，任务是编写一个 Python 程序来计算连续元素出现频率的幂的总和。

**示例:**

> **输入** : test_list = [2，2，2，3，3，3，4，4，5]
> **输出** : 110
> **解释** : 2^3 + 3^4 + 4^2 + 5 = 110
> 
> **输入** : test_list = [2，2，2，3，3，3，4，4]
> **输出** : 105
> **解释** : 2^3 + 3^4 + 4^2 = 105

**方法#1:使用循环**

在这种情况下，我们对每个元素进行迭代，并测试下一个元素，如果发现不同，则对连续元素的幂进行求和，否则添加计数器以获取频率来提高数字。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Summation of consecutive elements power
# Using loop

# initializing list
test_list = [2, 2, 2, 3, 3, 3, 3, 4, 4, 5]

# printing original lists
print("The original list is : " + str(test_list))

freq = 1
res = 0
for idx in range(0, len(test_list) - 1):

    # adding powers
    if test_list[idx] != test_list[idx + 1]:
        res = res + test_list[idx] ** freq
        freq = 1
    else:
        freq += 1

# catering for last element
res = res + test_list[len(test_list) - 1] ** freq

# printing result
print("Computed summation of powers : " + str(res))
```

**Output**

```py
The original list is : [2, 2, 2, 3, 3, 3, 3, 4, 4, 5]
Computed summation of powers : 110
```

**方法 2:使用**[**default dict()**](https://www.geeksforgeeks.org/defaultdict-in-python/)**+loop+**[**sum()**](https://www.geeksforgeeks.org/sum-function-python/)

在本文中，我们使用 defautldict 使用键值对捕获频率，并使用循环来迭代每个元素。接下来，使用 sum()执行求和。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Summation of consecutive elements power
# Using defaultdict() + loop + sum()
from collections import defaultdict

# initializing list
test_list = [2, 2, 2, 3, 3, 3, 3, 4, 4, 5]

# printing original lists
print("The original list is : " + str(test_list))

# getting frequency
temp = defaultdict(int)
for ele in test_list:
    temp[ele] += 1

temp = dict(temp)

# computing summation
res = sum([key ** temp[key] for key in temp])

# printing result
print("Computed summation of powers : " + str(res))
```

**Output**

```py
The original list is : [2, 2, 2, 3, 3, 3, 3, 4, 4, 5]
Computed summation of powers : 110
```