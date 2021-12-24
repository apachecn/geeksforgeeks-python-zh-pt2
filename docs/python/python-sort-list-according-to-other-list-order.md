# Python |按照其他列表顺序排序列表

> 原文:[https://www . geesforgeks . org/python-sort-list-根据其他列表-order/](https://www.geeksforgeeks.org/python-sort-list-according-to-other-list-order/)

排序是大多数编程中使用的基本工具，无论是用于竞争性编程还是开发。传统的分类方法早就被处理过很多次了。这篇特别的文章讨论了相对于一些其他列表元素的排序。
我们来讨论一下按照其他列表顺序对列表进行排序的某些方法。
**方法一:**使用列表理解
列表理解可以用来完成这个特殊的任务。在这种情况下，我们只检查列表 2 中的每个元素是否与当前元组匹配，并以排序的方式进行相应的追加。

## 蟒蛇 3

```py
# Python3 code to demonstrate
# to sort according to other list
# using list comprehension

# initializing list of tuples
test_list = [ ('a', 1), ('b', 2), ('c', 3), ('d', 4)]

# initializing sort order
sort_order = ['d', 'c', 'a', 'b']

# printing original list
print ("The original list is : " + str(test_list))

# printing sort order list
print ("The sort order list is : " + str(sort_order))

# using list comprehension
# to sort according to other list
res = [tuple for x in sort_order for tuple in test_list if tuple[0] == x]

# printing result
print ("The sorted list is : " + str(res))
```

**Output:** 

```py
The original list is : [('a', 1), ('b', 2), ('c', 3), ('d', 4)]
The sort order list is : ['d', 'c', 'a', 'b']
The sorted list is : [('d', 4), ('c', 3), ('a', 1), ('b', 2)]
```

**方法#2 :** 使用 sort() + lambda + index()
执行这个特定操作的简写，sort 函数可以与 lambda with key 一起使用，为每对元组指定函数执行，其他列表的列表顺序使用 index 函数维护。

## 蟒蛇 3

```py
# Python code to demonstrate
# to sort according to other list
# using sort() + lambda + index()

# initializing list of tuples
test_list = [ ('a', 1), ('b', 2), ('c', 3), ('d', 4)]

# initializing sort order
sort_order = ['d', 'c', 'a', 'b']

# printing original list
print ("The original list is : " + str(test_list))

# printing sort order list
print ("The sort order list is : " + str(sort_order))

# using sort() + lambda + index()
# to sort according to other list
# test_list.sort(key = lambda(i, j): sort_order.index(i)) # works in python 2
test_list.sort(key = lambda i: sort_order.index(i[0])) # works in python 3

# printing result
print ("The sorted list is : " + str(test_list))
```

**Output:** 

```py
The original list is : [('a', 1), ('b', 2), ('c', 3), ('d', 4)]
The sort order list is : ['d', 'c', 'a', 'b']
The sorted list is : [('d', 4), ('c', 3), ('a', 1), ('b', 2)]
```