# Python–最大连续元素百分比变化

> 原文:[https://www . geesforgeks . org/python-最大-连续-元素-百分比-变化/](https://www.geeksforgeeks.org/python-maximum-consecutive-elements-percentage-change/)

有时，在使用 Python 列表时，我们可能会遇到一个问题，需要提取连续元素的最大变化。这类问题可以应用于数据科学等领域。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [4，6，7]
> **输出** : 50.0
> 
> **输入** : test_list = [7，7，7，7]
> **输出** : 0.0

**方法#1:使用 loop + zip()**
以上函数的组合可以用来解决这个问题。在本文中，我们使用 zip()将元素与其后续元素结合起来。循环用于以暴力方式执行计算。

```
# Python3 code to demonstrate working of 
# Maximum consecutive elements percentage change
# Using zip() + loop

# initializing list
test_list = [4, 6, 7, 4, 2, 6, 2, 8]

# printing original list
print("The original list is : " + str(test_list))

# Maximum consecutive elements percentage change
# Using zip() + loop
res = 0
for x, y in zip(test_list, test_list[1:]):
    res = max((abs(x - y) / x) * 100, res)

# printing result 
print("The maximum percentage change : " + str(res)) 
```

**Output :**

```
The original list is : [4, 6, 7, 4, 2, 6, 2, 8]
The maximum percentage change : 300.0

```

**方法 2:使用递归+ `max()`**
这是可以执行该任务的另一种方式。在这种情况下，我们不使用循环，而是使用递归来执行这个任务，跟踪每次调用的最大值。

```
# Python3 code to demonstrate working of 
# Maximum consecutive elements percentage change
# Using zip() + loop

# helpr_fnc
def get_max_diff(test_list, curr_max = None):
    pot_max = (abs(test_list[1] - test_list[0]) / test_list[0]) * 100
    if curr_max :
        pot_max = max(curr_max, pot_max)
    if len(test_list) == 2:
        return pot_max
    return get_max_diff(test_list[1:], pot_max)

# initializing list
test_list = [4, 6, 7, 4, 2, 6, 2, 8]

# printing original list
print("The original list is : " + str(test_list))

# Maximum consecutive elements percentage change
# Using zip() + loop
res = get_max_diff(test_list)

# printing result 
print("The maximum percentage change : " + str(res)) 
```

**Output :**

```
The original list is : [4, 6, 7, 4, 2, 6, 2, 8]
The maximum percentage change : 300.0

```