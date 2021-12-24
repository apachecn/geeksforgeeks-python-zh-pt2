# Python 程序查找列表中所有对的绝对差之和

> 原文:[https://www . geesforgeks . org/python-程序-查找列表中所有对的绝对差之和/](https://www.geeksforgeeks.org/python-program-to-find-sum-of-absolute-difference-between-all-pairs-in-a-list/)

给定一个不同元素的列表，编写一个 Python 程序来查找给定列表中所有对的绝对差之和。

**示例:**

```py
Input : [9, 2, 14] 
Output : 24 
Explanation: (abs(9-2) + abs(9-14) + abs(2-14))

Input : [1, 2, 3, 4]
Output : 10 
Explanation: (abs(1-2) + abs(1-3) + abs(1-4)
             + abs(2-3) + abs(2-4) + abs(3-4))

```

第一种方法是蛮力方法，之前已经讨论过。在这里，我们将讨论 pythonic 方法。

**方法#1 :** 使用`enumerate()`
`Enumerate()`方法将计数器添加到可迭代表中，并以枚举对象的形式返回它。在这个方法中，我们有一个包含绝对差异的“差异”列表。我们使用两个循环，每个循环有两个变量。一个用于迭代计数器，一个用于列表元素。在每次迭代中，我们检查元素是否相似。如果没有，找到绝对差异并将其附加到差异中。最后，求列表的和。由于每对将被计数两次，我们将最终总和除以 2 并返回。

```py
# Python3 program to find sum of 
# absolute differences in all pairs 

def sumPairs(lst): 

    diffs = []
    for i, x in enumerate(lst):
        for j, y in enumerate(lst):
            if i != j: 
                diffs.append(abs(x-y))

    return int(sum(diffs)/2)

# Driver program 
lst = [1, 2, 3, 4] 
print(sumPairs(lst))
```

**Output:**

```py
10

```

**方法 2 :** 使用*ITER tools*
Python ITER tools 由*置换()*方法组成。这个方法将一个列表作为输入，并返回一个包含列表形式的所有排列的元组的对象列表。这里，为了找到绝对差，我们本质上需要两个元素的排列。由于每对都要计算两次，所以我们把最后的总和除以 2。

```py
# Python3 program to find sum of 
# absolutre differences in all pairs 
import itertools

def sumPairs(lst): 

    diffs = [abs(e[1] - e[0]) for e in itertools.permutations(lst, 2)]
    return int(sum(diffs)/2)

# Driver program 
lst = [9, 8, 1, 16, 15] 
print(sumPairs(lst))
```

**Output:**

```py
74

```