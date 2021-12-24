# Python |列表元素对求和

> 原文:[https://www . geesforgeks . org/python-pair-summary-of-list-elements/](https://www.geeksforgeeks.org/python-pair-summation-of-list-elements/)

有时，在使用 Python 列表时，可能会遇到一个问题，即需要找到以对形式执行列表求和的方法。这对于 web 开发和日常编程中较大问题的子问题解决方案非常有用。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用循环**
这是执行这个特殊任务的蛮力方法。在这种情况下，我们只是以跳过的方式迭代列表直到最后一个元素，以迭代的方式获取其他列表中的所有对和。

```
# Python3 code to demonstrate working of
# Pair summation of list
# Using loop

# initializing list
test_list = [4, 5, 8, 9, 10, 17]

# printing list
print("The original list : " + str(test_list))

# Pair summation of list
# Using loop
res = []
for ele in range(0, len(test_list), 2):
    res.append(test_list[ele] + test_list[ele + 1])

# Printing result
print("Pair summation of list : " + str(res))
```

**Output :**

```

The original list : [4, 5, 8, 9, 10, 17]
Pair summation of list : [9, 17, 27]

```