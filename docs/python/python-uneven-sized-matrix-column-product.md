# Python |不均匀尺寸矩阵柱产品

> 原文:[https://www . geesforgeks . org/python-大小不一-矩阵-列-产品/](https://www.geeksforgeeks.org/python-uneven-sized-matrix-column-product/)

与传统的 C 类型矩阵不同，通常的列表可以允许可变长度的嵌套列表，当我们需要其列的乘积时，不均匀的行长度可能会导致该元素中的某些元素缺失，如果处理不正确，可能会引发异常。让我们讨论以无错误的方式解决这个问题的某些方法。

**方法#1:使用循环+ `filter() + map()` +列表理解**
以上三个函数结合列表理解可以帮助我们执行这个特定的任务，外部 prod 函数帮助执行乘法，filter 允许我们检查当前元素，所有行都使用 map 函数进行组合。仅适用于 python 2。

```py
# Python code to demonstrate 
# Uneven Sized Matrix Column product
# using loop + filter() + map() + list comprehension

# getting Product 
def prod(val) : 
    res = 1 
    for ele in val: 
        res *= ele 
    return res 

# initializing list of lists
test_list = [[1, 5, 3], [4], [9, 8]]

# printing original list 
print ("The original list is : " + str(test_list))

# using loop + filter() + map() + list comprehension
# Uneven Sized Matrix Column product
res = [prod(filter(None, j)) for j in map(None, *test_list)]

# printing result
print ("The product of columns is : " + str(res))
```

**Output :**

```py
The original list is : [[1, 5, 3], [4], [9, 8]]
The product of columns is : [36, 40, 3]

```