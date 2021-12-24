# Python |将 3D 列表转换为 2D 列表的方法

> 原文:[https://www . geesforgeks . org/python-将 3d 列表转换为 2d 列表的方法/](https://www.geeksforgeeks.org/python-ways-to-convert-a-3d-list-into-a-2d-list/)

列表是 Python 中常见的一种数据结构。虽然我们已经使用了列表和 2d 列表，但 3d 列表的使用日益增加，主要是在网络开发的情况下。
给定一个 3D 列表，任务是将其转换为 2D 列表。这些类型的问题是在从事项目工作或参与开源时遇到的。
下面是一些实现上述任务的方法。

```
Input:
[[[3], [4]], [[5], [6]], [[7], [8]]]
Output:
[[3], [4], [5], [6], [7], [8]]

```

**方法#1:** **使用简单迭代**将 3D 列表转换为 2D 列表。

```
# Python code to convert a 3D list into a 2D list

# Input list initialization
Input = [[[3], [4]], [[5], [6]], [[7], [8]]]

# Output list initialization
Output = []

# Using iteration
for temp in Input:
    for elem in temp:
        Output.append(elem)

# printing output
print("Initial 3d list is")
print(Input)
print("Converted 2d list is")
print(Output)
```

**输出:**

```
Initial 3d list is
[[[3], [4]], [[5], [6]], [[7], [8]]]
Converted 2d list is
[[3], [4], [5], [6], [7], [8]]

```

**方法 2:使用列表理解**将 3D 列表转换为 2D 列表

```
# Python code to convert a 3D list into a 2D list

# Input list initialization
Input = [[[1, 1], [2, 7]], [[3], [4]], [[6, 5], [6]]]

# Using list comprehension
Output = [elem for twod in Input for elem in twod]

# printing output
print("Initial 3d list is")
print(Input)
print("Converted 2d list is")
print(Output)
```

**输出:**

```
Initial 3d list is
[[[1, 1], [2, 7]], [[3], [4]], [[6, 5], [6]]]
Converted 2d list is
[[1, 1], [2, 7], [3], [4], [6, 5], [6]]

```