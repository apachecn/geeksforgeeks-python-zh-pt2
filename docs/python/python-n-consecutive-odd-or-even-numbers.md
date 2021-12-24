# Python | N 个连续的奇数或偶数

> 原文:[https://www . geesforgeks . org/python-n-连续奇数或偶数/](https://www.geeksforgeeks.org/python-n-consecutive-odd-or-even-numbers/)

本文关注的问题非常具体，在不同领域可能用处不大。但这种解决方式可能会为解决潜在的类似问题打开大门，因此值得一读。本文解决了测试一个列表是否包含一系列奇数或偶数元素的问题。让我们讨论一下解决这个问题的某些方法。

**方法一:使用`sum()` +列表理解+`zip() + any()`+T3】**

使用上述功能的组合可以解决这个问题。这种方法分两步解决问题。在第一步中，我们使用列表理解和 zip 函数计算所有可能的 N 对，在第二步中，我们使用 sum 和任何函数来测试 N 个可分的结果，如果我们找到其中的任何一个，我们返回正。

```py
# Python3 code to demonstrate
# N consecutive Odd or Even Numbers
# using sum() + zip() + any() + list comprehension

# initializing list
test_list = [1, 5, 6, 4, 8]

# printing original list
print("The original list : " + str(test_list))

# initializing N 
N = 3

# using sum() + zip() + any() + list comprehension
# N consecutive Odd or Even Numbers
temp = ( test_list[i : i + N] for i in range(len(test_list) - N + 1) )
res = any( sum(ele % 2 for ele in temps) % N == 0 for temps in temp )

# print result
print("Does list contain the desired consecution : " + str(res))
```

**Output :**

```py
The original list : [1, 5, 6, 4, 8]
Does list contain the desired consecution : True

```

**方法 2:使用`groupby() + any()`**

上述方法中执行第一步的整个逻辑可以使用 groupby 函数来管理，在该函数中我们执行分组，任何函数都可以在以后用于检查连续性。

```py
# Python3 code to demonstrate
# N consecutive Odd or Even Numbers
# using groupby() + any()
from itertools import groupby

# initializing list
test_list = [1, 5, 6, 4, 8]

# printing original list
print("The original list : " + str(test_list))

# initializing N 
N = 3

# using groupby() + any()
# N consecutive Odd or Even Numbers
res = any(len(list(sub)) == N for idx, sub in
     groupby([sub % 2 for sub in test_list]))

# print result
print("Does list contain the desired consecution : " + str(res))
```

**Output :**

```py
The original list : [1, 5, 6, 4, 8]
Does list contain the desired consecution : True

```