# Python |反向拆分字符串

> 原文:[https://www . geesforgeks . org/python-reversed-split-strings/](https://www.geeksforgeeks.org/python-reversed-split-strings/)

拆分的功能在许多应用程序和用途中非常流行。随之而来的是许多类型的变化范围。本文讨论其中的一种变体，在这种变体中，人们希望同时获得元素字符串顺序的拆分和反转。让我们讨论解决这个特殊问题的某些方法。

**方法#1:使用`join() + reversed() + split()`**

在这个特定的方法中，我们首先使用 split 函数获取元素单词，使用 reversed 函数执行它们的逆序，然后执行 join 将元素绑定在一起。

```py
# Python3 code to demonstrate
# Reverse string split
# using join() + reversed() + split()

# initializing string
test_string = "Gfg is best"

# printing original string 
print("The original string : " + str(test_string))

# using join() + reversed() + split()
# Reverse string split
res =  ", ".join(reversed(test_string.split(" ")))

# print result
print("The string after reverse split : " + str(res))
```

**Output :**

```py
The original string : Gfg is best
The string after reverse split : best, is, Gfg

```

**方法 2:使用`join() + split()` +列表切片**

这个方法类似于上面我们执行拆分和连接的方法，但是这个方法唯一的区别是我们使用列表切片来执行反转。

```py
# Python3 code to demonstrate
# Reverse string split
# using join() + split() + list slicing

# initializing string
test_string = "Gfg is best"

# printing original string 
print("The original string : " + str(test_string))

# using join() + split() + list slicing
# Reverse string split
res =  ', '.join(test_string.split()[::-1])

# print result
print("The string after reverse split : " + str(res))
```

**Output :**

```py
The original string : Gfg is best
The string after reverse split : best, is, Gfg

```