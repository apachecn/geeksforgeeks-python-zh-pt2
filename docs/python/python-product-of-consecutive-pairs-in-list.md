# Python–列表中连续对的乘积

> 原文:[https://www . geesforgeks . org/python-连续成对产品列表/](https://www.geeksforgeeks.org/python-product-of-consecutive-pairs-in-list/)

有时，在使用 Python 列表时，可能会遇到一个问题，即需要以对的形式找到并执行列表的乘积。这对于 web 开发和日常编程中较大问题的子问题解决方案非常有用。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用循环**
这是执行这个特殊任务的蛮力方法。在这种情况下，我们只是以跳过的方式迭代列表直到最后一个元素，以迭代的方式获得其他列表中的所有对积。

```py
# Python3 code to demonstrate working of
# List consecutive pair Product
# Using loop

# initializing list
test_list = [5, 8, 3, 5, 9, 10]

# printing list
print("The original list : " + str(test_list))

# List consecutive pair Product
# Using loop
res = []
for ele in range(0, len(test_list), 2):
    res.append(test_list[ele] * test_list[ele + 1])

# Printing result
print("Pair product of list : " + str(res))
```

**Output :**

```py
The original list : [5, 8, 3, 5, 9, 10]
Pair product of list : [40, 15, 90]

```