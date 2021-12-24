# Python |字符串长度求和

> 原文:[https://www . geesforgeks . org/python-strings-length-summary/](https://www.geeksforgeeks.org/python-strings-length-summation/)

有时，我们在容器中接收数据，我们需要对这些数据进行处理，以进一步处理这些数据，从而实现一些基本的实用功能。数据量的大小有时变得很重要，需要知道。本文讨论字符串列表的总长度。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`sum()` +列表理解**
这两个功能的组合可以用来执行这个特定的功能。sum 函数用于查找列表的每个字符串的总和，列表理解执行迭代任务。

```py
# Python3 code to demonstrate
# string lengths summation 
# using sum() + list comprehension

# initializing list of tuples
test_list = ['Geeks', 'for', 'Geeks']

# printing the original list
print ("The original list is : " + str(test_list))

# using sum() + list comprehension
# string lengths summation 
res = sum(len(i) for i in test_list)

# printing result
print ("The summation of strings is : " + str(res))
```

**Output:**

```py
The original list is : ['Geeks', 'for', 'Geeks']
The summation of strings is : 13

```

**方法 2:使用`join() + len()`**
python 的内置功能可以帮助执行这个特定的任务。join 函数可用于将所有字符串连接在一起，len 函数取它们的累积和。

```py
# Python3 code to demonstrate
# string lengths summation 
# using sum() + list comprehension

# initializing list of tuples
test_list = ['Geeks', 'for', 'Geeks']

# printing the original list
print ("The original list is : " + str(test_list))

# using sum() + list comprehension
# string lengths summation 
res = len(''.join(test_list))

# printing result
print ("The summation of strings is : " + str(res))
```

**Output:**

```py
The original list is : ['Geeks', 'for', 'Geeks']
The summation of strings is : 13

```