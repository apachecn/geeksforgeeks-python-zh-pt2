# Python |非零组求和

> 原文:[https://www . geesforgeks . org/python-非零组求和/](https://www.geeksforgeeks.org/python-summation-of-non-zero-groups/)

很多时候，我们需要得到的不是整个列表的总和，而是它的一部分，并且是定期的。这些间隔有时是在遍历之前静态决定的，但有时，约束是更动态的，因此我们需要以更复杂的方式处理它。这里讨论的标准是非零组的总和。让我们讨论一下完成这项任务的某些方法。

**方法#1:使用循环**

这个任务可以使用循环的强力方式来执行。我们只需遍历列表中的每个元素，测试它的后续元素是否为非零值，一旦找到下一个为零的值，就执行求和，并将其附加到结果列表中。

```
# Python3 code to demonstrate
# summation of non-zero groups
# Using loops

# initializing list
test_list = [4, 9, 0, 0, 3, 4, 5, 0, 0, 4, 0]

# printing original list
print("The original list : " + str(test_list))

# using loops
# summation of non-zero groups
res = []
val = 0
for ele in test_list:
    if ele == 0:
        if val != 0:
            res.append(val)
            val = 0
    else:
        val += ele

# print result
print("The non-zero group summation of list is : " + str(res))
```

**Output :**

```
The original list : [4, 9, 0, 0, 3, 4, 5, 0, 0, 4, 0]
The non-zero group summation of list is : [13, 12, 4]

```

**方法 2:使用`itertools.groupby() + sum()`**

也可以使用 groupby 函数对所有非零值进行分组，并使用 sum 函数对它们求和，从而执行该特定任务。

```
# Python3 code to demonstrate
# summation of non-zero groups
# Using itertools.groupby() + sum()
from itertools import groupby

# initializing list
test_list = [4, 9, 0, 0, 3, 4, 5, 0, 0, 4, 0]

# printing original list
print("The original list : " + str(test_list))

# using itertools.groupby() + sum()
# summation of non-zero groups
res = [sum(val) for keys, val in groupby(test_list,
              key = lambda x: x != 0) if keys != 0]

# print result
print("The non-zero group summation of list is : " + str(res))
```

**Output :**

```
The original list : [4, 9, 0, 0, 3, 4, 5, 0, 0, 4, 0]
The non-zero group summation of list is : [13, 12, 4]

```