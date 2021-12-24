# 在 Python 中转置二元数组列表

> 原文:[https://www . geesforgeks . org/转置-双元组-python 中的列表/](https://www.geeksforgeeks.org/transpose-dual-tuple-list-in-python/)

有时，在使用 Python 元组时，我们会遇到一个问题，即我们需要执行元素的元组转置，即二元元组的每个列元素变成一行，一个 2*N 元组变成 N * 2 元组列表。这种问题可能会在诸如 web 开发和日常编程等领域得到应用。让我们讨论执行这项任务的某些方法。

```
Input : test_list = [(2, 'Gfg'), (3, 'is'), (94, 'Best')]
Output : ([2, 3, 94], ['Gfg', 'is', 'Best'])
Input : test_list = [(8, 1)]
Output : ([8, 1])
```

### 方法 1:使用循环

这是解决这个问题的方法之一。在这种情况下，我们采用蛮力策略来执行转置，通过构建 2 个列表并将其组合来获得转置结果。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Transpose Tuple List
# Using loop

# hlper_fnc function
def hlper_fnc(test_list):
    # declare empty list
    sub1 = []
    sub2 = []

    res = (sub1, sub2)
    for sub in test_list:
        # add element in the last of the list
        sub1.append(sub[0])
        sub2.append(sub[1])

    return res

# initializing list
test_list = [(5, 1), (3, 4), (9, 7), (10, 6)]

# printing original list
print("The original list is : " + str(test_list))

# Transpose Tuple List
# Using loop
res = hlper_fnc(test_list)

# printing result
print("The transposed tuple list : " + str(res))
```

**输出:**

```
The original list is : [(5, 1), (3, 4), (9, 7), (10, 6)]
The transposed tuple list : ([5, 3, 9, 10], [1, 4, 7, 6])
```

### 方法 2:使用循环+ zip() +元组()

上述功能的组合也可以用来解决这个问题。在本文中，我们使用 zip()执行形成转置和提取柱状元素的任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Transpose Tuple List
# Using zip() + tuple()

# hlper_fnc function
def hlper_fnc(test_list):
    return tuple(zip(*test_list))

# initializing list
test_list = [(5, 1), (3, 4), (9, 7), (10, 6)]

# printing original list
print("The original list is : " + str(test_list))

# Transpose Tuple List
# Using zip() + tuple()
sub1, sub2 = hlper_fnc(test_list)
res = (list(sub1), list(sub2))

# printing result
print("The transposed tuple list : " + str(res))
```

**输出:**

```
The original list is : [(5, 1), (3, 4), (9, 7), (10, 6)]
The transposed tuple list : ([5, 3, 9, 10], [1, 4, 7, 6])
```