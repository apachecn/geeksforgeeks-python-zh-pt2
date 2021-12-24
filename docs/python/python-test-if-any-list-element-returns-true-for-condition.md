# Python |测试是否有任何列表元素在条件

下返回真

> 原文:[https://www . geesforgeks . org/python-test-if-list-element-returns-true-for-condition/](https://www.geeksforgeeks.org/python-test-if-any-list-element-returns-true-for-condition/)

有时，在用 Python 编码时，我们会遇到一个问题，即我们需要根据任何元素满足的条件来过滤列表。这可以在 web 开发领域得到应用。让我们讨论一种可以执行这项任务的速记方法。

**方法:使用`any()` +列表理解**
解决这个问题最简单的方式和速记就是结合内置`any()`和列表理解的功能进行渲染条件逻辑和列表迭代。如果列表元素中有任何一个符合条件，则`any()`返回真。

```py
# Python3 code to demonstrate working of
# Test if any list element returns true for condition
# Using any() + list comprehension

# initializing list
test_list = [6, 4, 8, 9, 10]

# printing list
print("The original list : " + str(test_list))

# Test if any list element returns true for condition
# Using any() + list comprehension
res = any(x % 5 for x in test_list)

# Printing result
print("Does list contain any element divisible by 5? : " + str(res))
```

**Output :**

```py

The original list : [6, 4, 8, 9, 10]
Does list contain any element divisible by 5? : True

```