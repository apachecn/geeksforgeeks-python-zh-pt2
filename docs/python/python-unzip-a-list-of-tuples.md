# Python |解压元组列表

> 原文:[https://www . geesforgeks . org/python-解压-元组列表/](https://www.geeksforgeeks.org/python-unzip-a-list-of-tuples/)

zipping 技术，即从两个不同的列表中分配键值或配对，已经在许多文章中介绍过，有时我们有特定的实用程序来执行相反的任务。这项任务可以通过各种方法来完成。

让我们讨论一些解压元组列表的方法。

**方法#1 :** 使用列表理解

使用列表理解是执行解压缩任务的最天真的方法，通常不用于执行此任务，但这是一个很好的方法。

```py
# Python3 code to demonstrate 
# Unzip a list of tuples
# using list comprehension

# initializing list of tuples
test_list = [('Akshat', 1), ('Bro', 2), ('is', 3), ('Placed', 4)]

# Printing original list
print ("Original list is : " + str(test_list))

# using list comprehension to
# perform Unzipping
res = [[ i for i, j in test_list ],
       [ j for i, j in test_list ]]

# Printing modified list 
print ("Modified list is : " + str(res))
```

**输出:**

```py
Original list is : [('Akshat', 1), ('Bro', 2), ('is', 3), ('Placed', 4)]
Modified list is : [['Akshat', 'Bro', 'is', 'Placed'], [1, 2, 3, 4]]

```

**方法 2 :** 使用`zip()`和*运算符

最常用的解压方法，也是最推荐的方法。这种方法一般被各地的程序员用来执行这个任务。*运算符将元组解压到独立的列表中。

```py
# Python3 code to demonstrate 
# Unzip a list of tuples
# using zip() and * operator

# initializing list of tuples
test_list = [('Akshat', 1), ('Bro', 2), ('is', 3), ('Placed', 4)]

# Printing original list
print ("Original list is : " + str(test_list))

# using zip() and * operator to
# perform Unzipping
res = list(zip(*test_list))

# Printing modified list 
print ("Modified list is : " + str(res))
```

**输出:**

```py
Original list is : [('Akshat', 1), ('Bro', 2), ('is', 3), ('Placed', 4)]
Modified list is : [('Akshat', 'Bro', 'is', 'Placed'), (1, 2, 3, 4)]

```

**方法#3 :** 使用`map()`
这是另一种可以用来执行解压任务的方法，这种方法不太为人所知，但确实是实现该任务的一种方法。这也使用*运算符来执行列表的基本解包。Python > = 3 个版本不推荐使用该功能。

```py
# Python code to demonstrate 
# Unzip a list of tuples
# using map()

# initializing list of tuples
test_list = [('Akshat', 1), ('Bro', 2), ('is', 3), ('Placed', 4)]

# Printing original list
print ("Original list is : " + str(test_list))

# using map() to
# perform Unzipping
res = map(None, *test_list)

# Printing modified list 
print ("Modified list is : " + str(res))
```

**输出:**

```py
Original list is : [('Akshat', 1), ('Bro', 2), ('is', 3), ('Placed', 4)]
Modified list is : [('Akshat', 'Bro', 'is', 'Placed'), (1, 2, 3, 4)]

```