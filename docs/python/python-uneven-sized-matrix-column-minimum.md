# Python–不均匀大小的矩阵列最小值

> 原文:[https://www . geesforgeks . org/python-大小不均匀-矩阵-列-最小值/](https://www.geeksforgeeks.org/python-uneven-sized-matrix-column-minimum/)

与传统的 C 类型矩阵不同，通常的列表可以允许可变长度的嵌套列表，当我们要求其列的最小值时，不均匀的行长度可能会导致该元素中的某些元素缺失，如果处理不正确，可能会引发异常。让我们讨论以无错误的方式解决这个问题的某些方法。

**方法#1:使用`min() + filter() + map()` +列表理解**
以上三个函数结合列表理解可以帮助我们执行这个特定的任务，min 函数帮助执行最小值，filter 允许我们检查当前元素，所有行都使用 map 函数进行组合。仅适用于 python 2。

```
# Python code to demonstrate 
# Uneven Sized Matrix Column Minimum
# using min() + filter() + map() + list comprehension

# initializing list of lists
test_list = [[1, 5, 3], [4], [9, 8]]

# printing original list 
print ("The original list is : " + str(test_list))

# using min() + filter() + map() + list comprehension
# Uneven Sized Matrix Column Minimum
res = [min(filter(None, j)) for j in map(None, *test_list)]

# printing result
print ("The minimum of columns is : " + str(res))
```

**Output :**

```
The original list is : [[1, 5, 3], [4], [9, 8]]
The minimum of columns is : [1, 5, 3]

```