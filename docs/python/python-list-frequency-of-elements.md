# Python |元素列表频率

> 原文:[https://www . geesforgeks . org/python-list-元素频率/](https://www.geeksforgeeks.org/python-list-frequency-of-elements/)

有时我们有一个实用程序，我们需要找到列表中元素的频率，这个问题的解决方案已经讨论过很多次了。但有时我们会遇到这样的任务:我们需要找到特定元素出现的列表数量。让我们讨论一下可以做到这一点的某些人手不足的情况。

**方法一:使用 Counter() + set() +列表理解**
以上功能的组合可以用来执行任务。计数器函数进行分组，集合函数提取不同的元素作为字典的关键字，并对其列表出现进行列表理解检查。

## 蟒蛇 3

```
# Python3 code to demonstrate
# list frequency of elements
# using Counter() + set() + list comprehension
from collections import Counter

# initializing list
test_list = [[3, 5, 4],
             [6, 2, 4],
             [1, 3, 6]]

# printing original list
print("The original list : " + str(test_list))

# using Counter() + set() + list comprehension
# list frequency of elements
res = dict(Counter(i for sub in test_list for i in set(sub)))

# printing result
print("The list frequency of elements is : " + str(res))
```

**Output : **

```
The original list : [[3, 5, 4], [6, 2, 4], [1, 3, 6]]
The list frequency of elements is : {1: 1, 2: 1, 3: 2, 4: 2, 5: 1, 6: 2}
```