# Python–删除等长和等和元组副本

> 原文:[https://www . geesforgeks . org/python-remove-equilength-and-equisum-tuple-duplicates/](https://www.geeksforgeeks.org/python-remove-equilength-and-equisum-tuple-duplicates/)

有时，在使用 Python 元组时，我们可能会遇到一个问题，即需要在等长等和的基础上删除重复项。这种问题也可以打破，以适应任何一个所需的条件。这种问题可能发生在数据域和日常编程中。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [(1，2，0)，(3，0)，(2，1)]
> **输出** : [(1，2，0)，(3，0)]
> **输入** : test_list = [(1，2，0)，(3，0，0)，(0，2，1)]
> **输出** : [(1，2，0)]

**方法#1:使用嵌套循环**
这是执行该任务的方法之一。这是蛮力方法，其中我们对每个元组循环一个匹配的元组 w.r.t 大小和总和，并执行移除。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Remove Equilength and Equisum Tuple Duplicates
# Using nested loop

# initializing lists
test_list = [(4, 5, 6), (3, 0), (2, 1), (1, 2, 3), (5, 5, 5)]

# printing original list
print("The original list is : " + str(test_list))

# Remove Equilength and Equisum Tuple Duplicates
# Using nested loop
res = []
for sub in test_list:
    for sub1 in res:
        if len(sub) == len(sub1) and sum(sub) == sum(sub1):
            break
    else:
        res.append(sub)

# printing result
print("Tuples after filteration : " + str(res))
```

**Output : **

```py
The original list is : [(4, 5, 6), (3, 0), (2, 1), (1, 2, 3), (5, 5, 5)]
Tuples after filteration : [(4, 5, 6), (3, 0), (1, 2, 3)]
```

**方法 2:使用 dict() + values()**
上述函数的组合提供了解决这个问题的另一种方法。在这种情况下，我们只是利用字典具有唯一键的特性，用 len 和元组的和创建一个元组键。因此，避免了重复。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Remove Equilength and Equisum Tuple Duplicates
# Using dict() + values()

# initializing lists
test_list = [(4, 5, 6), (3, 0), (2, 1), (1, 2, 3), (5, 5, 5)]

# printing original list
print("The original list is : " + str(test_list))

# Remove Equilength and Equisum Tuple Duplicates
# Using dict() + values()
res = list({(len(sub), sum(sub)): sub for sub in test_list}.values())

# printing result
print("Tuples after filteration : " + str(res))
```

**Output : **

```py
The original list is : [(4, 5, 6), (3, 0), (2, 1), (1, 2, 3), (5, 5, 5)]
Tuples after filteration : [(4, 5, 6), (3, 0), (1, 2, 3)]
```