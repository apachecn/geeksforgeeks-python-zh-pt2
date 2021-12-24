# Python |前缀求和子数组直到假值

> 原文:[https://www . geesforgeks . org/python-prefix-sum-subarray-till-false-value/](https://www.geeksforgeeks.org/python-prefix-sum-subarray-till-false-value/)

前缀数组在编程实践中相当有名。本文将讨论这个方案的一个变体。这将处理累计列表总和，直到出现一个假值，并再次从出现真值开始累计。让我们讨论一下实现这一点的某些方法。

**方法#1:使用天真的方法**
在天真的方法中，我们只需构建包含前一个的总和的新列表。值，直到 0，并在遇到非零值时重新启动该过程。

```py
# Python3 code to demonstrate 
# Prefix Sum Subarray till False value 
# using naive method 

# initializing list of lists
test_list = [1, 3, 4, 0, 4, 5, 0, 7, 8]

# printing original list
print ("The original list is : " + str(test_list))

# Prefix Sum Subarray till False value 
# using naive method
for i in range(1, len(test_list)):
    if test_list[i]:  
        test_list[i] += test_list[i - 1]

# printing result
print ("The computed modified new list : " + str(test_list))
```

**Output:**

```py
The original list is : [1, 3, 4, 0, 4, 5, 0, 7, 8]
The computed modified new list : [1, 4, 8, 0, 4, 9, 0, 7, 15]

```

**方法 2:使用`from_iterable() + accumulate() + groupby()`**
以上三个功能组合在一起执行这个特定的任务。在这种情况下，累加函数执行元素相加的任务，groupby 函数将非零值分组，结果由`from_iterable` 函数组合。

```py
# Python3 code to demonstrate 
# Prefix Sum Subarray till False value 
# from_iterable() + accumulate() + groupby()
from itertools import groupby, accumulate, chain

# initializing list of lists
test_list = [1, 3, 4, 0, 4, 5, 0, 7, 8]

# printing original list
print ("The original list is : " + str(test_list))

# Prefix Sum Subarray till False value 
# from_iterable() + accumulate() + groupby()
res = list(chain.from_iterable(accumulate(j) 
            for i, j in groupby(test_list, bool)))

# printing result
print ("The computed modified new list : " + str(res))
```

**Output:**

```py
The original list is : [1, 3, 4, 0, 4, 5, 0, 7, 8]
The computed modified new list : [1, 4, 8, 0, 4, 9, 0, 7, 15]

```