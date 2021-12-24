# Python |解包嵌套元组

> 原文:[https://www . geesforgeks . org/python-解包-嵌套-元组/](https://www.geeksforgeeks.org/python-unpacking-nested-tuples/)

有时，在使用 Python 元组列表时，我们可能会遇到一个问题，即我们需要解包打包的元组。这在 web 开发中可能会有应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解**
这个任务可以使用列表理解来执行，在列表理解中，我们对元组进行迭代并构建期望的元组。这种技术在我们知道元组元素的确切数量和位置的情况下非常有用。

```py
# Python3 code to demonstrate working of
# Unpacking nested tuples
# using list comprehension

# initialize list
test_list = [(4, (5, 'Gfg')), (7, (8, 6))]

# printing original list
print("The original list is : " + str(test_list))

# Unpacking nested tuples
# using list comprehension
res = [(x, y, z) for x, (y, z) in test_list]

# printing result
print("The unpacked nested tuple list is : " + str(res))
```

**Output :**

```py
The original list is : [(4, (5, 'Gfg')), (7, (8, 6))]
The unpacked nested tuple list is : [(4, 5, 'Gfg'), (7, 8, 6)]

```