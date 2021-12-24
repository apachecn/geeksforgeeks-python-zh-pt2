# 不考虑顺序移除重复元组的 Python 程序

> 原文:[https://www . geesforgeks . org/python-程序-删除-重复-元组-不考虑顺序/](https://www.geeksforgeeks.org/python-program-to-remove-duplicate-tuples-irrespective-of-order/)

给定一个二进制元组列表，任务是编写一个 Python 程序来移除所有重复的元组，而不管顺序如何，即如果包含相似的元素，则删除，而不管顺序如何。

> **输入:** test_list = [(4，6)，(1，2)，(9，2)，(2，1)，(5，7)，(6，4)，(9，2)]
> 
> **输出:** [(1，2)，(5，7)，(4，6)，(2，9)]
> 
> **说明:** (2，1)、(6，4)被删除，因为(1，2)、(4，6)已经包括在内。
> 
> **输入:** test_list = [(4，7)，(1，2)，(9，2)，(2，1)，(5，7)，(7，4)，(9，2)]
> 
> **输出:** [(1，2)，(5，7)，(4，7)，(2，9)]
> 
> **说明:** (2，1)、(7，4)被删除，因为(1，2)、(4，7)已经包括在内。

**方法一:** *利用* [*地图()*](https://www.geeksforgeeks.org/python-map-function/)*[*整理出()*](https://www.geeksforgeeks.org/sorted-function-python/)*[*集()*](https://www.geeksforgeeks.org/python-set-method/) *和* [*列表()*](https://www.geeksforgeeks.org/python-list/)**

**在本文中，我们使用 sorted()和 map()对元组的每个元素进行排序。然后将结果转换为 set 以删除重复项。最后，集合被转换为列表。**

****示例:****

## **蟒蛇 3**

```py
**# initializing list
test_list = [(4, 6), (1, 2), (9, 2), (2, 1), (5, 7), (6, 4), (9, 2)]

# printing original list
print("The original list is : " + str(test_list))

# using map() to get all sorted
# set removes duplicates
res = list({*map(tuple, map(sorted, test_list))})

# printing result
print("Tuples after removal : " + str(res))**
```

****输出:****

> **原清单为:[(4，6)，(1，2)，(9，2)，(2，1)，(5，7)，(6，4)，(9，2)]**
> 
> **移除后的元组:[(2，9)，(1，2)，(4，6)，(5，7)]**

****方法二:** *使用* [*列表理解，*](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/) [*排序()*](https://www.geeksforgeeks.org/sorted-function-python/) *和* [*集合()*](https://www.geeksforgeeks.org/python-set-method/)**

**对于所需的解决方案来说，这是一种幼稚的方法。在这种情况下，使用列表理解对列表的每个元素进行排序并排序()，然后使用 set()将结果转换回以移除重复项。**

****示例:****

## **蟒蛇 3**

```py
**# initializing list
test_list = [(4, 6), (1, 2), (9, 2), (2, 1), (5, 7), (6, 4), (9, 2)]

# printing original list
print("The original list is : " + str(test_list))

# sorting tuples
temp = [tuple(sorted(sub)) for sub in test_list]

# removing duplicates
res = list(set(temp))

# printing result
print("Tuples after removal : " + str(res))**
```

****输出:****

> **原清单为:[(4，6)，(1，2)，(9，2)，(2，1)，(5，7)，(6，4)，(9，2)]**
> 
> **移除后的元组:[(2，9)，(1，2)，(4，6)，(5，7)]**