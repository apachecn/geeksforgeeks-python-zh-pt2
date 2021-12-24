# python |嵌套列表交集矩阵积

> 原文:[https://www . geesforgeks . org/python-嵌套-列表-交集-矩阵-产品/](https://www.geeksforgeeks.org/python-nested-list-intersection-matrix-product/)

在 2 个列表的列表中找到公共元素的问题是一个相当常见的问题，可以很容易地处理，并且之前也讨论过很多次。但是有时，我们需要从 N 个列表中找到共同的元素并返回它们的产品。让我们讨论一下执行这个操作的某些方法。

**方法#1:使用`reduce() + lambda + set() + loop`**
结合上述功能，只需一行即可完成该特定任务。这个减少功能可以用来操作&的功能，对所有的列表进行操作。set 函数可用于将列表转换为集合，以消除重复。执行产品的任务是使用循环完成的。

```py
# Python code to demonstrate 
# Nested List Intersection Matrix Product
# using reduce() + lambda + set() + loop

# getting Product 
def prod(val) : 
    res = 1 
    for ele in val: 
        res *= ele 
    return res  

# initializing list of lists
test_list = [[2, 3, 5, 8], [2, 6, 7, 3], [10, 9, 2, 3]]

# printing original list
print ("The original list is : " + str(test_list))

# Nested List Intersection Matrix Product
# using reduce() + lambda + set() + loop
res = prod(list(reduce(lambda i, j: i & j, (set(x) for x in test_list))))

# printing result
print ("The common row elements product is : " + str(res))
```

**Output :**

```py
The original list is : [[2, 3, 5, 8], [2, 6, 7, 3], [10, 9, 2, 3]]
The common row elements product is : 6

```