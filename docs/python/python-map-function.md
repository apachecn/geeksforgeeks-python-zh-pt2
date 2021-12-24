# Python 图()功能

> 原文:[https://www.geeksforgeeks.org/python-map-function/](https://www.geeksforgeeks.org/python-map-function/)

**map()** 函数将给定函数应用于给定可迭代表(列表、元组等)的每个项目后，返回结果的 map 对象(它是一个迭代器)。)

**语法:**

```
map(fun, iter)

```

**参数:**

> **乐趣:**这是一个函数，给定可迭代的每个元素都会传递到这个函数。
> **iter :** 这是一个待映射的 iter。

**注意:**您可以向 map()函数传递一个或多个可迭代项。

**返回:**

```
Returns a list of the results after applying the given function  
to each item of a given iterable (list, tuple etc.) 

```

**注意:**从 map()返回的值(map 对象)可以传递给 list()(创建列表)、set()(创建集合)等函数。

**代码 1**

```
# Python program to demonstrate working
# of map.

# Return double of n
def addition(n):
    return n + n

# We double all numbers using map()
numbers = (1, 2, 3, 4)
result = map(addition, numbers)
print(list(result))
```

输出:

```
[2, 4, 6, 8]

```

**CODE 2**
我们也可以用[λ表达式](https://www.geeksforgeeks.org/python-lambda-anonymous-functions-filter-map-reduce/)搭配地图来达到上面的效果。

```
# Double all numbers using map and lambda

numbers = (1, 2, 3, 4)
result = map(lambda x: x + x, numbers)
print(list(result))
```

输出:

```
[2, 4, 6, 8]

```

**代码 3**

```
# Add two lists using map and lambda

numbers1 = [1, 2, 3]
numbers2 = [4, 5, 6]

result = map(lambda x, y: x + y, numbers1, numbers2)
print(list(result))
```

输出:

```
[5, 7, 9]

```

**代码 4**

```
# List of strings
l = ['sat', 'bat', 'cat', 'mat']

# map() can listify the list of strings individually
test = list(map(list, l))
print(test)
```

输出:

```
[['s', 'a', 't'], ['b', 'a', 't'], ['c', 'a', 't'], ['m', 'a', 't']]
```