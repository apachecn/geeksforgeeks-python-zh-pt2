# Python |类型铸造全列表和矩阵

> 原文:[https://www . geesforgeks . org/python-type-casting-整体列表和矩阵/](https://www.geeksforgeeks.org/python-type-casting-whole-list-and-matrix/)

有时，在使用 Python List 或 Matrix 时，我们通常会遇到一个问题，即我们需要获得一个通用函数，该函数可以一次执行整个容器的类型转换。总是需要一种机制代码，它可以完全转换容器中所有元素的数据类型的允许变化。让我们讨论一下执行这项任务的方法。

**方法:使用`map()` +列表理解**
这个任务可以使用地图()来执行。通过传递所需的数据类型，可以使用单个映射函数来执行普通列表的转换。但是当涉及到整个矩阵的变换时，我们同样需要列表理解的帮助。

```
# Python3 code to demonstrate working of
# Type casting whole List and Matrix
# using map() + list comprehension

# helper function to type cast list 
def cast_list(test_list, data_type):
    return list(map(data_type, test_list))

# helper function to type cast Matrix 
def cast_matrix(test_matrix, data_type):
    return list(map(lambda sub: list(map(data_type, sub)), test_matrix))

# initialize list 
test_list = [1, 4, 9, 10, 19]

# initialize Matrix
test_matrix = [[5, 6, 8], [8, 5, 3], [9, 10, 3]]

# printing original list
print("The original list is : " + str(test_list))

# printing original matrix
print("The original Matrix is : " + str(test_matrix))

# Type casting whole List and Matrix
# using map() + list comprehension
res_list = cast_list(test_list, str)
res_matrix = cast_matrix(test_matrix, str)

# printing result
print("The List after type casting is : " + str(res_list))
print("The Matrix after type casting is : " + str(res_matrix))
```

**Output :**

```
The original list is : [1, 4, 9, 10, 19]
The original Matrix is : [[5, 6, 8], [8, 5, 3], [9, 10, 3]]
The List after type casting is : ['1', '4', '9', '10', '19']
The Matrix after type casting is : [['5', '6', '8'], ['8', '5', '3'], ['9', '10', '3']]

```