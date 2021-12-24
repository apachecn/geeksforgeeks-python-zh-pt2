# Python |合并列表中的范围字符

> 原文:[https://www . geesforgeks . org/python-merge-range-列表中的字符/](https://www.geeksforgeeks.org/python-merge-range-characters-in-list/)

有时，我们需要将一些元素合并为列表中的单个元素。这通常是字符到字符串转换的情况。这种类型的任务通常在开发领域中需要，以便将名称合并到一个元素中。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`join()` +列表切片**
连接功能可以与列表切片耦合，列表切片可以执行连接列表切片功能选择的范围内的每个字符的任务。

```
# Python3 code to demonstrate 
# Merge Range Characters in List
# using join() + list slicing

# initializing list 
test_list = ['I', 'L', 'O', 'V', 'E', 'G', 'F', 'G']

# printing original list
print ("The original list is : " + str(test_list))

# initializing Range, i, j
i, j = 3, 7

# using join() + list slicing
# Merge Range Characters in List
test_list[i : j] = [''.join(test_list[i : j])]

# printing result 
print ("The list after merging elements : " + str(test_list))
```

**Output :**

```
The original list is : ['I', 'L', 'O', 'V', 'E', 'G', 'F', 'G']
The list after merging elements : ['I', 'L', 'O', 'VEGF', 'G']

```