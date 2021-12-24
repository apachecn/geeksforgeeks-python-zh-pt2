# Python–单值元组嵌套列表

> 原文:[https://www . geesforgeks . org/python-嵌套列表到单值元组/](https://www.geeksforgeeks.org/python-nested-list-to-single-value-tuple/)

有时，在处理 Python 数据时，我们可能会遇到需要将 Python 嵌套列表转换为单值元组的问题。这种问题可以应用于诸如 web 开发和竞争性编程等领域。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [[5，6]，[4，7，10，17]]
> **输出** : [(5)、(6)、(4)、(7)、(10)、(17)，]
> 
> **输入** : test_list = [[5，6，7，8]]
> **输出** : [(5)、(6)、(7)、(8、]

**方法#1:使用列表理解(对于单个嵌套)**
这是可以执行该任务的方式之一。我们迭代每个内部列表，并将每个元素转换为单独的元组。这只适合单一的筑巢。

```py
# Python3 code to demonstrate working of 
# Convert Nested List to 1 value Tuple
# Using list comprehension

# initializing list
test_list = [[5, 6], [4, 7, 10], [12], [9, 11]]

# printing original list
print("The original list is : " + str(test_list))

# Convert Nested List to 1 value Tuple
# Using list comprehension
res = [(ele, ) for sub in test_list for ele in sub]

# printing result 
print("The converted container : " + str(res)) 
```

**Output :**

```py
The original list is : [[5, 6], [4, 7, 10], [12], [9, 11]]
The converted container : [(5, ), (6, ), (4, ), (7, ), (10, ), (12, ), (9, ), (11, )]

```

**方法 2:使用`isinstance()` +递归**
以上函数的组合可以解决这个问题。在本文中，我们使用 isinstance()和递归来执行展平和转换任务，以适应随机嵌套的情况。

```py
# Python3 code to demonstrate working of 
# Convert Nested List to 1 value Tuple
# Using isinstance() + recursion

# helper_fnc
def hlper_fnc(test_list):
    res = []
    if isinstance(test_list, list):
        for ele in test_list:
            res.extend(hlper_fnc(ele))
    elif isinstance(test_list, int):
        res.append((test_list, ))
    return res

# initializing list
test_list = [[5, [6]], [4, 7, [10, 45]], [12], [9, 11]]

# printing original list
print("The original list is : " + str(test_list))

# Convert Nested List to 1 value Tuple
# Using isinstance() + recursion
res = hlper_fnc(test_list)

# printing result 
print("The converted container : " + str(res)) 
```

**Output :**

```py
The original list is : [[5, [6]], [4, 7, [10, 45]], [12], [9, 11]]
The converted container : [(5, ), (6, ), (4, ), (7, ), (10, ), (45, ), (12, ), (9, ), (11, )]

```