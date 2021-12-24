# Python |对列表中每个元素的操作

> 原文:[https://www . geesforgeks . org/python-操作到列表中的每个元素/](https://www.geeksforgeeks.org/python-operation-to-each-element-in-list/)

给定一个列表，我们总是会遇到这样的情况:我们需要对列表中的每个元素应用特定的函数。这可以通过应用循环并对每个元素执行操作来轻松完成。但是用人手不足来解决这个问题总是有好处的，并且有助于更好地关注问题的重要方面。让我们讨论列表中每个元素的操作方式。

**方法#1:使用列表理解**
该方法在后台执行与循环构造相同的任务。这种特殊方法提供的优势是这是一个单一的线性，也提高了代码的可读性。

```py
# Python3 code to demonstrate 
# operations on each list element
# using list comprehension

# initializing list 
test_list = ["geeks", "for", "geeks", "is", "best"]

# printing original list
print ("The original list is : " + str(test_list))

# operations on each list element
# using list comprehension
# uppercasing each element
res = [i.upper() for i in test_list]

# printing result
print ("The uppercased list is : " + str(res))
```

**Output:**

```py
The original list is : ['geeks', 'for', 'geeks', 'is', 'best']
The uppercased list is : ['GEEKS', 'FOR', 'GEEKS', 'IS', 'BEST']

```

**方法 2:使用`map()`**
使用地图功能，可以很容易地将一个元素与想要执行的操作相关联。这是执行或解决这类问题最优雅的方式。

```py
# Python3 code to demonstrate 
# operations on each list element
# using map()

# initializing list 
test_list = ["Geeks", "foR", "gEEks", "IS", "bEST"]

# printing original list
print ("The original list is : " + str(test_list))

# operations on each list element
# using map()
# lowercasing each element
res = list(map(str.lower, test_list))

# printing result
print ("The lowercased list is : " + str(res))
```

**Output:**

```py
The original list is : ['Geeks', 'foR', 'gEEks', 'IS', 'bEST']
The uppercased list is : ['geeks', 'for', 'geeks', 'is', 'best']

```