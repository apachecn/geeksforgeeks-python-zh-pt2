# Python–通过第一个元素值的频率限制元组

> 原文:[https://www . geesforgeks . org/python-按第一个元素的频率限制元组-值/](https://www.geeksforgeeks.org/python-restrict-tuples-by-frequency-of-first-elements-value/)

给定一个元组列表，任务是编写一个 Python 程序，将元组值的第一个元素的频率限制为最多 k

**示例:**

> **输入:** test_list = [(2，3)，(3，3)，(1，4)，(2，4)，(2，5)，(3，4)，(1，4)，(3，4)，(4)，(4，7)]，K = 2
> 
> **输出:** [(2，3)，(3，3)，(1，4)，(2，4)，(3，4)，(1，4)，(4，7)]
> 
> **说明:** 2 在结果列表中出现 2 次，(2，5)，省略第 3 次出现。
> 
> **输入:** test_list = [(2，3)，(3，3)，(1，4)，(2，4)，(2，5)，(3，4)，(1，4)，(3，4)，(4)，(4，7)]，K = 3
> 
> **输出:** [(2，3)，(3，3)，(1，4)，(4，7)]
> 
> **解释:** 2、3、1、4 只限于第一次出现。

**方法一:使用循环+** [**键()**](https://www.geeksforgeeks.org/python-dictionary-keys-method/) **+条件语句**

在这种情况下，我们执行存储元组的第一位置的每个元素的计数的任务，并且如果其出现次数增加 k，则省略

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Restrict Tuples by frequency of first element's value
# Using loop + keys() + conditional statements

# initializing list
test_list = [(2, 3), (3, 3), (1, 4), (2, 4), (2, 5),
             (3, 4), (1, 4), (3, 4), (4, 7)]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 2

res = []
mem = dict()
for sub in test_list:

    # check in memory
    if sub[0] not in mem.keys():
        mem[sub[0]] = 1
    else:
        mem[sub[0]] += 1

    # add if less than K frequency
    if mem[sub[0]] <= K:
        res.append(sub)

# printing result
print("Filtered tuples : " + str(res))
```

**输出:**

> 原清单为:[(2、3)、(3、3)、(1、4)、(2、4)、(2、5)、(3、4)、(1、4)、(3、4)、(4、7)]
> 
> 过滤后的元组:[(2，3)，(3，3)，(1，4)，(2，4)，(3，4)，(1，4)，(4，7)]

**方法 2:使用**[**default dict()**](https://www.geeksforgeeks.org/defaultdict-in-python/)**+**[**滤镜()**](https://www.geeksforgeeks.org/filter-in-python/) **+ lambda**

在这种情况下，我们使用 defaultdict()执行记忆任务，filter()和 lambda 函数用于在满足条件时检查和添加结果的任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Restrict Tuples by frequency of first element's value
# Using defaultdict() + filter() + lambda
from collections import defaultdict

# initializing list
test_list = [(2, 3), (3, 3), (1, 4), (2, 4), (2, 5),
             (3, 4), (1, 4), (3, 4), (4, 7)]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 2

mem = defaultdict(list)

# filtering result using filter() and lambda function
res = list(filter(lambda sub: mem[sub[0]].append(
    sub[0]) or len(mem[sub[0]]) <= K, test_list))

# printing result
print("Filtered tuples : " + str(res))
```

**输出:**

> 原清单为:[(2、3)、(3、3)、(1、4)、(2、4)、(2、5)、(3、4)、(1、4)、(3、4)、(4、7)]
> 
> 过滤后的元组:[(2，3)，(3，3)，(1，4)，(2，4)，(3，4)，(1，4)，(4，7)]