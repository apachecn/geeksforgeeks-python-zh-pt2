# Python |合并列表元素

> 原文:[https://www.geeksforgeeks.org/python-merge-list-elements/](https://www.geeksforgeeks.org/python-merge-list-elements/)

有时，我们需要将一些元素合并为列表中的单个元素。这通常是字符到字符串转换的情况。这种类型的任务通常在开发领域中需要，以便将名称合并到一个元素中。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`join() + List Slicing`**
连接功能可以与列表切片相结合，该列表切片可以执行连接列表切片功能选择的范围内的每个字符的任务。

```py
# Python3 code to demonstrate 
# merging list elements
# using join() + list slicing

# initializing list  
test_list = ['I', 'L', 'O', 'V', 'E', 'G', 'F', 'G']

# printing original list
print ("The original list is : " + str(test_list))

# using join() + list slicing
# merging list elements
test_list[5 : 8] = [''.join(test_list[5 : 8])]

# printing result 
print ("The list after merging elements : " +  str(test_list))
```

**Output:**

```py
The original list is : ['I', 'L', 'O', 'V', 'E', 'G', 'F', 'G']
The list after merging elements : ['I', 'L', 'O', 'V', 'E', 'GFG']

```

**方法#2:使用`reduce() + lambda + list slicing`**
通过 reduce 函数和 lambda 来执行在一个范围内连接每个元素的任务。reduce 函数为 lambda 函数定义的范围内的每个元素执行任务。它仅适用于 Python2】

```py
# Python code to demonstrate 
# merging list elements
# using reduce() + lambda + list slicing

# initializing list  
test_list = ['I', 'L', 'O', 'V', 'E', 'G', 'F', 'G']

# printing original list
print ("The original list is : " + str(test_list))

# using reduce() + lambda + list slicing
# merging list elements
test_list[5 : 8] = [reduce(lambda i, j: i + j, test_list[5 : 8])]

# printing result 
print ("The list after merging elements : " +  str(test_list))
```

**Output:**

```py
The original list is : ['I', 'L', 'O', 'V', 'E', 'G', 'F', 'G']
The list after merging elements : ['I', 'L', 'O', 'V', 'E', 'GFG']

```