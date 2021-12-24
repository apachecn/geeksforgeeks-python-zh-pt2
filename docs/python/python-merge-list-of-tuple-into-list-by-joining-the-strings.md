# Python |通过连接字符串将元组列表合并到列表中

> 原文:[https://www . geesforgeks . org/python-通过连接字符串将元组列表合并到列表中/](https://www.geeksforgeeks.org/python-merge-list-of-tuple-into-list-by-joining-the-strings/)

有时，我们需要通过用一个特殊字符连接元组的两个元素来将元组列表转换成列表。这通常是字符到字符串转换的情况。这种类型的任务通常在开发领域中需要，以便将名称合并到一个元素中。让我们讨论一下实现这一点的某些方法。

让我们通过代码示例来更好地理解它。

**方法 1:** 使用列表理解和`join()`

```py
# Python code to convert list of tuple into list
# by joining elements of tuple

# Input list initialisation
Input = [('Hello', 'There'), ('Namastey', 'India'), ('Incredible', 'India')]

# using join and list comprehension
Output = ['_'.join(temp) for temp in Input]

# printing output
print(Output)
```

**Output:**

```py
['Hello_There', 'Namastey_India', 'Incredible_India']

```

**方法二:**使用地图和`join()`

```py
# Python code to convert list of tuple into list
# by joining elements of tuple

# Input list initialisation
Input = [('Hello', 'There'), ('Namastey', 'India'), ('Incredible', 'India')]

# using map and join
Output = list(map('_'.join, Input))

# printing output
print(Output)
```

**Output:**

```py
['Hello_There', 'Namastey_India', 'Incredible_India']

```