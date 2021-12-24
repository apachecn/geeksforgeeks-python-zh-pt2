# Python |元素插入时返回新列表

> 原文:[https://www . geesforgeks . org/python-return-new-list-on-element-insertion/](https://www.geeksforgeeks.org/python-return-new-list-on-element-insertion/)

通常的[追加方法](https://www.geeksforgeeks.org/append-extend-python/)在原始序列中添加新元素，不返回值。但是有时我们需要在每次向列表中添加新元素时都有一个新列表。这种问题在 web 开发中很常见。让我们讨论执行这项任务的某些方法。

**方法#1:使用+运算符**
如果我们制作一个单元素列表，并将原始列表与这个新制作的单元素列表连接起来，就可以执行这个任务。

```
# Python3 code to demonstrate 
# returning new list on element insertion
# using + operator

# initializing list
test_list = [5, 6, 2, 3, 9]

# printing original list
print ("The original list is : " + str(test_list))

# element to add 
K = 10

# using + operator
# returning new list on element insertion
res = test_list + [K]

# printing result 
print ("The newly returned added list : " +  str(res))
```

**输出:**

```
The original list is : [5, 6, 2, 3, 9]
The newly returned added list : [5, 6, 2, 3, 9, 10]

```

**方法 2:使用*运算符**
类似的任务可以使用*运算符，其中我们使用*运算符来获取所有元素，并添加新元素以输出新列表。

```
# Python3 code to demonstrate 
# returning new list on element insertion
# using * operator

# initializing list
test_list = [5, 6, 2, 3, 9]

# printing original list
print ("The original list is : " + str(test_list))

# element to add 
K = 10

# using * operator
# returning new list on element insertion
res = [*test_list, K]

# printing result 
print ("The newly returned added list : " +  str(res))
```

**输出:**

```
The original list is : [5, 6, 2, 3, 9]
The newly returned added list : [5, 6, 2, 3, 9, 10]

```