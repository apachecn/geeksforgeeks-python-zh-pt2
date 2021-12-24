# Python |在列表末尾移动零

> 原文:[https://www . geesforgeks . org/python-shift-zero-at-end-list/](https://www.geeksforgeeks.org/python-shift-zeroes-at-end-of-list/)

涉及元素转移的传统问题在前面已经讨论过很多次了，但是有时我们有严格的约束来执行它们，任何可能的变化的知识都会有所帮助。本文讨论了一个在列表末尾移动 0 的问题，这里要注意的是，它只检查 0，不包括传统的“无”(假)值。让我们讨论一下实现这一点的某些方法。

**方法一:使用列表理解+ `isinstance()`**

在这种方法中，我们分两步执行换档操作。在第一步中，我们得到所有需要在前端和末端得到的值，我们只需将零推到末端。isinstance 方法用于过滤掉布尔假实体。

```py
# Python3 code to demonstrate
# Shift zeroes at end of list
# using list comprehension + isinstance()

# initializing list
test_list = [1, 4, None, "Manjeet", False, 0, False, 0, "Nikhil"]

# printing original list
print("The original list : " + str(test_list))

# using list comprehension + isinstance()
# Shift zeroes at end of list
temp = [ele for ele in test_list if ele or 
        ele is None or isinstance(ele, bool)]
res = temp + [0] * (len(test_list) - len(temp))

# print result
print("The list after shifting 0's to end : " + str(res))
```

**Output :**

> 原始列表:[1，4，无，'曼吉特'，假，0，假，0，'尼克尔']
> 将 0 '移至结尾后的列表:[1，4，无，'曼吉特'，假，假，'尼克尔'，0，0]

方法二:使用列表理解+ `isinstance()` +列表切片

这个方法类似于上面的方法，唯一的修改是为了减少步骤的数量，列表切片被用来附加 0 以在仅仅 1 个步骤中执行整个任务。

```py
# Python3 code to demonstrate
# Shift zeroes at end of list
# using list comprehension + isinstance() + list slicing

# initializing list
test_list = [1, 4, None, "Manjeet", False, 0, False, 0, "Nikhil"]

# printing original list
print("The original list : " + str(test_list))

# using list comprehension + isinstance() + list slicing
# Shift zeroes at end of list
res = ([ele for ele in test_list if not isinstance(ele, int)
        or ele or isinstance(ele, bool)]
        + [0] * len(test_list))[:len(test_list)]

# print result
print("The list after shifting 0's to end : " + str(res))
```

**Output :**

> 原始列表:[1，4，无，'曼吉特'，假，0，假，0，'尼克尔']
> 将 0 '移至结尾后的列表:[1，4，无，'曼吉特'，假，假，'尼克尔'，0，0]