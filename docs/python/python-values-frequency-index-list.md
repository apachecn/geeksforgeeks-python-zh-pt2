# Python–值频率索引列表

> 原文:[https://www . geesforgeks . org/python-values-frequency-index-list/](https://www.geeksforgeeks.org/python-values-frequency-index-list/)

有时，在使用 Python 元组时，我们可能会遇到一个问题，即我们需要提取元组中每个值的频率。这个早就解决了。我们可以进行修改，我们需要创建一个列表，其中索引代表键，索引的值代表索引号的频率。这类问题可以在竞争编程领域中得到应用。让我们讨论一下解决这个问题的某些方法。

> **输入** : test_list = [('Gfg '，1)、(' is '，1)、(' best '，1)、(' for '，1)、(' geeks '，1)]
> **输出**:【0，5，0，0，0，0】
> 
> **输入** : test_list = [('Gfg '，5)、(' is '，5)]
> **输出** : [0，0，0，0，0，2]

**方法#1:使用循环**
这是一种蛮力方法，通过它可以执行该任务。在本文中，我们通过迭代和分配预初始化列表来执行分配频率的任务。

```
# Python3 code to demonstrate working of 
# Values Frequency Index List
# Using loop

# initializing list
test_list = [('Gfg', 3), ('is', 3), ('best', 1), ('for', 5), ('geeks', 1)]

# printing original list
print("The original list is : " + str(test_list))

# Values Frequency Index List
# Using loop
res = [0 for _ in range(6)]
for ele in test_list:
    res[ele[1]] = res[ele[1]] + 1

# printing result 
print("The Frequency list : " + str(res)) 
```

**Output :**

```
The original list is : [('Gfg', 3), ('is', 3), ('best', 1), ('for', 5), ('geeks', 1)]
The Frequency list : [0, 2, 0, 2, 0, 1]

```

**方法 2:使用`Counter()` +列表理解**
结合以上功能来解决这个问题。在本文中，我们使用 Counter()执行计算频率的任务，列表中的渲染是通过列表理解来完成的。

```
# Python3 code to demonstrate working of 
# Values Frequency Index List
# Using Counter() + list comprehension
from collections import Counter

# initializing list
test_list = [('Gfg', 3), ('is', 3), ('best', 1), ('for', 5), ('geeks', 1)]

# printing original list
print("The original list is : " + str(test_list))

# Values Frequency Index List
# Using Counter() + list comprehension
cntr = Counter(ele[1] for ele in test_list)
res = [cntr[idx] for idx in range(6)]

# printing result 
print("The Frequency list : " + str(res)) 
```

**Output :**

```
The original list is : [('Gfg', 3), ('is', 3), ('best', 1), ('for', 5), ('geeks', 1)]
The Frequency list : [0, 2, 0, 2, 0, 1]

```