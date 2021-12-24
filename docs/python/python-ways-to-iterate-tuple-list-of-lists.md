# Python |列表元组列表的迭代方式

> 原文:[https://www . geesforgeks . org/python-迭代方式-元组-列表列表/](https://www.geeksforgeeks.org/python-ways-to-iterate-tuple-list-of-lists/)

[**List**](https://www.geeksforgeeks.org/python-list/) 是一个重要的容器，几乎用在日常编程和网络开发的每一个代码中，用得越多，就越需要掌握它，因此对它的操作的了解是必要的。
给定一个列表的元组列表，编写一个 Python 程序来遍历它并获取所有元素。
**方法#1:** 使用 ITER tools . zip long

## 蟒蛇 3

```py
# Python code to demonstrate ways to iterate
# tuples list of list into single list
# using itertools.ziplongest

# import library
from itertools import zip_longest

# initialising listoflist
test_list = [
         [('11'), ('12'), ('13')],
         [('21'), ('22'), ('23')],
         [('31'), ('32'), ('33')]
         ]

# printing initial list
print ("Initial List = ", test_list)

# iterate list tuples list of list into single list
res_list = [item for my_list in zip_longest(*test_list)
                           for item in my_list if item]

# print final List
print ("Resultant List = ", res_list)
```

**Output:** 

```py
Initial List =  [['11', '12', '13'], ['21', '22', '23'], ['31', '32', '33']]
Resultant List =  ['11', '21', '31', '12', '22', '32', '13', '23', '33']
```

**方法 2:** 使用 lambda+ITER tools . chain+zip _ long

## 蟒蛇 3

```py
# Python code to demonstrate
# ways to iterate tuples list of list into single list
# using itertools.ziplongest + lambda + chain

# import library
from itertools import zip_longest, chain

# initialising listoflist
test_list = [
         [('11'), ('12'), ('13')],
         [('21'), ('22'), ('23')],
         [('31'), ('32'), ('33')]
         ]

# printing initial list
print ("Initial List = ", test_list)

# iterate list tuples list of list into single list
# using lambda + chain + filter
res_list = list(filter(lambda x: x, chain(*zip_longest(*test_list))))

# print final List
print ("Resultant List = ", res_list)
```

**Output:** 

```py
Initial List =  [['11', '12', '13'], ['21', '22', '23'], ['31', '32', '33']]
Resultant List =  ['11', '21', '31', '12', '22', '32', '13', '23', '33']
```

**方法#3:** 使用列表理解
列表理解是 python 中定义和创建列表的优雅方式。我们可以创建列表，就像数学陈述一样，并且只在一行中。列表理解的语法更容易掌握。

## 蟒蛇 3

```py
# Python code to demonstrate ways to
# iterate tuples list of list into single
# list using list comprehension

# initialising listoflist
test_list = [
         [('11'), ('12'), ('13')],
         [('21'), ('22'), ('23')],
         [('31'), ('32'), ('33')]
         ]

# printing initial list
print ("Initial List = ", test_list)

# iterate list tuples list of list into single list
# using list comprehension
res_list = [item for list2 in test_list for item in list2]

# print final List
print ("Resultant List = ", res_list)
```

**Output:** 

```py
Initial List =  [['11', '12', '13'], ['21', '22', '23'], ['31', '32', '33']]
Resultant List =  ['11', '12', '13', '21', '22', '23', '31', '32', '33']
```