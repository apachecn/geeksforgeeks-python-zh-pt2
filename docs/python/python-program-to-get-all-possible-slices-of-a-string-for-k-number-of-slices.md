# Python 程序获取一个字符串的所有可能切片为 K 个切片

> 原文:[https://www . geeksforgeeks . org/python-program-to-get-所有可能的切片-字符串-k-切片数/](https://www.geeksforgeeks.org/python-program-to-get-all-possible-slices-of-a-string-for-k-number-of-slices/)

给定一个字符串，任务是编写一个 Python 程序来获取 K 个切片的所有可能切片。

> **输入:** test_str = "Gfg4all "，K = 3
> 
> **输出:** [['G '，' f '，' g4all']，['G '，' fg '，' 4all']，['G '，' fg4 '，' all']，['G '，' fg4a '，' ll']，['G '，' fg4al '，' l']，['Gf '，' G '，' 4all']，['Gf '，' g4 '，' all']，['Gf '，' g4a '，' l']，[' Gfgg '，' 4 '，' all '，['
> 
> **说明:**返回所有可能的 3 个切片用于构造字符串。
> 
> **输入:** test_str = "Gfg4all "，K = 2
> 
> **输出:** [['G '，' fg4all']，['Gf '，' g4all']，['Gfg '，' 4all']，['Gfg4 '，' all']，['Gfg4a '，' ll']，['Gfg4al '，' l']
> 
> **说明:**返回所有可能的 2 个切片用于构造字符串。

**方法一:使用** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension/) **+** [**切片**](https://www.geeksforgeeks.org/string-slicing-in-python/) **+** [**循环**](https://www.geeksforgeeks.org/loops-in-python/)

在这种情况下，连续切片从大小 1 开始递增计算。在 acc 中，最后一个元素总是被一分为二。其他字符串。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# All possible slices for K length
# Using list comprehension + string slicing + loop

# initializing string
test_str = "Gfg4all"

# printing original string
print("The original string is : " + str(test_str))

# initializing number of slices
K = 3

res = [[test_str]]
for idx in range(K - 1):

    # slicing initial strings with difference sizes.
    res = [[*strt, end[:y], end[y:]] for *strt, end in res
           for y in range(1, len(end) - K + idx + 2)]

# printing result
print("All possible slices for K strings : " + str(res))
```

**输出:**

> 原始字符串是:Gfg4all
> 
> K 个字符串的所有可能切片:[['G '，' f '，' g4All']，['G '，' fg '，' 4all']，['G '，' fg4 '，' all']，['G '，' fg4a '，' ll']，['G '，' fg4al '，' l']，['Gf '，' G '，' 4all']，['Gf '，' g4a '，' ll']，['Gf '，' g4al '，' l']，[' Gfgg '，' 4 '，' all '，[' K '

**方法 2:使用** [**组合()**](https://www.geeksforgeeks.org/permutation-and-combination-in-python/)**+**[**zip()**](https://www.geeksforgeeks.org/zip-in-python/)**+**[**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension/)

在这种情况下，组合用于获取迭代期间使用切片计算的范围的所有可能的子字符串。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# All possible slices for K length
# Using combinations() + zip() + list comprehension
from itertools import combinations

# initializing string
test_str = "Gfg4all"

# printing original string
print("The original string is : " + str(test_str))

# initializing number of slices
K = 3

# combinations used to perform all possible slices
res = [[test_str[idx: j] for idx, j in zip([None, *sub], [*sub, None])]
       for sub in combinations(range(1, len(test_str)), K - 1)]

# printing result
print("All possible slices for K strings : " + str(res))
```

**输出:**

> 原始字符串是:Gfg4all
> 
> K 个字符串的所有可能切片:[['G '，' f '，' g4All']，['G '，' fg '，' 4all']，['G '，' fg4 '，' all']，['G '，' fg4a '，' ll']，['G '，' fg4al '，' l']，['Gf '，' G '，' 4all']，['Gf '，' g4a '，' ll']，['Gf '，' g4al '，' l']，[' Gfgg '，' 4 '，' all '，[' K '