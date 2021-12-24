# Python |按特定顺序对元组列表进行排序

> 原文:[https://www . geesforgeks . org/python-按特定顺序排序元组列表/](https://www.geeksforgeeks.org/python-sort-list-of-tuples-by-specific-ordering/)

元组的正常排序已经在前面讨论过了。本文旨在根据某个列表中提供的顺序，按第二个元素对给定的元组列表进行排序。

**方法#1:使用列表理解+ `filter()` + lambda**
以上三个函数可以组合起来执行列表理解执行迭代的特定任务，lambda 函数作为过滤的辅助函数，根据元组的第二个元素进行排序。

```py
# Python3 code to demonstrate
# sort list of tuples according to second
# using list comprehension + filter() + lambda

# initializing list of tuples
test_list = [('a', 2), ('c', 3), ('d', 4)]

# initializing sort order 
sort_order = [4, 2, 3]

# printing the original list
print ("The original list is : " + str(test_list))

# printing sort order list 
print ("The sort order list is : " + str(sort_order))

# using list comprehension + filter() + lambda
# sort list of tuples according to second
res = [i for j in sort_order 
      for i in filter(lambda k: k[1] == j, test_list)]

# printing result
print ("The list after appropriate sorting : " + str(res))
```

**Output:**

```py
The original list is : [('a', 2), ('c', 3), ('d', 4)]
The sort order list is : [4, 2, 3]
The list after appropriate sorting : [('d', 4), ('a', 2), ('c', 3)]

```

**方法二:使用`sorted() + index()`+λ**
排序功能可以按照指定的顺序进行排序。index 函数指定必须考虑元组的第二个元素，所有元素都在 lambda 的帮助下连接在一起。

```py
# Python3 code to demonstrate
# sort list of tuples according to second
# using sorted() + index() + lambda

# initializing list of tuples
test_list = [('a', 2), ('c', 3), ('d', 4)]

# initializing sort order 
sort_order = [4, 2, 3]

# printing the original list
print ("The original list is : " + str(test_list))

# printing sort order list 
print ("The sort order list is : " + str(sort_order))

# using sorted() + index() + lambda
# sort list of tuples according to second
res = list(sorted(test_list, 
      key = lambda i: sort_order.index(i[1])))

# printing result
print ("The list after appropriate sorting : " + str(res))
```

**Output:**

```py
The original list is : [('a', 2), ('c', 3), ('d', 4)]
The sort order list is : [4, 2, 3]
The list after appropriate sorting : [('d', 4), ('a', 2), ('c', 3)]

```