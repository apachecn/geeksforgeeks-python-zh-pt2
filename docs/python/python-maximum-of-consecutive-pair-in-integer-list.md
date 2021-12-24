# Python–整数列表中连续对的最大值

> 原文:[https://www . geesforgeks . org/python-整数列表中最大连续对数/](https://www.geeksforgeeks.org/python-maximum-of-consecutive-pair-in-integer-list/)

有时，在使用 Python 列表时，可能会遇到一个问题，即需要找到以对的形式执行列表的最大化。这对于 web 开发和日常编程中较大问题的子问题解决方案非常有用。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用 loop + max()**
这是执行这个特定任务的蛮力方法。在这种情况下，我们只是以跳过的方式迭代列表直到最后一个元素，以迭代的方式获取其他列表中的所有对最大值。

```py
# Python3 code to demonstrate working of
# Consecutive Pair Maximum
# Using loop + max()

# initializing list
test_list = [5, 8, 3, 5, 9, 10]

# printing list
print("The original list : " + str(test_list))

# Consecutive Pair Maximum
# Using loop + max()
res = []
for ele in range(0, len(test_list), 2):
    res.append(max(test_list[ele], test_list[ele + 1]))

# Printing result
print("Pair maximum of list : " + str(res))
```

**Output :**

```py
The original list : [5, 8, 3, 5, 9, 10]
Pair maximum of list : [8, 5, 10]

```