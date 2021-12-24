# Python–元组中相似键的最大值

> 原文:[https://www . geeksforgeeks . org/python-元组中最大相似键数/](https://www.geeksforgeeks.org/python-maximum-of-similar-keys-in-tuples/)

有时，在使用 Python 元组时，我们可能会遇到一个问题，即我们需要执行元组列表中所有相等键的最大值。这种应用程序在许多领域都很有用，例如 web 开发和日常编程。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [(4，8)，(4，2)，(4，2)，(4，6)]
> **输出** : [(4，18)]
> 
> **输入** : test_list = [(1，8)，(2，2)，(3，6)，(4，2)]
> **输出** : [(1，8)，(2，2)，(3，6)，(4，2)]

**方法一:使用 max()+group by()+lambda+loop**
以上函数的组合可以用来解决这个问题。在本例中，我们使用 groupby()执行分组任务，使用 max()提取最大值，并使用循环编译结果。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Maximum of Similar Keys in Tuples
# Using max() + groupby() + lambda + loop
from itertools import groupby

# initializing lists
test_list = [(4, 8), (3, 2), (2, 2), (4, 6), (3, 7), (4, 5)]

# printing original list
print("The original list is : " + str(test_list))

# Maximum of Similar Keys in Tuples
# Using max() + groupby() + lambda + loop
test_list.sort(key = lambda sub: sub[0])
temp = groupby(test_list, lambda ele: ele[0])
res = []
for key, val in temp:
    res.append((key, sum([ele[1] for ele in val])))

# printing result
print("Maximum grouped elements : " + str(res))
```

**Output : **

```py
The original list is : [(4, 8), (3, 2), (2, 2), (4, 6), (3, 7), (4, 5)]
Maximum grouped elements : [(2, 2), (3, 7), (4, 8)]
```

**方法 2:使用 max() + groupby() + itemgetter() +列表理解**
以上函数的组合可以用来解决这个问题。在这里，我们执行与上面类似的任务，使用 itemgetter 选择第二个元素，并使用列表理解来编译元素和提取结果。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Maximum of Similar Keys in Tuples
# Using max() + groupby() + itemgetter() + list comprehension
from itertools import groupby
from operator import itemgetter

# initializing lists
test_list = [(4, 8), (3, 2), (2, 2), (4, 6), (3, 7), (4, 5)]

# printing original list
print("The original list is : " + str(test_list))

# Maximum of Similar Keys in Tuples
# Using max() + groupby() + itemgetter() + list comprehension
temp = groupby(sorted(test_list, key = itemgetter(0)), key = itemgetter(0))
res = [(key, max(map(itemgetter(1), sub))) for key, sub in temp]

# printing result
print("Maximum grouped elements : " + str(res))
```

**Output : **

```py
The original list is : [(4, 8), (3, 2), (2, 2), (4, 6), (3, 7), (4, 5)]
Maximum grouped elements : [(2, 2), (3, 7), (4, 8)]
```