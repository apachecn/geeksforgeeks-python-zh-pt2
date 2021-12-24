# Python 程序对字符串进行排序

> 原文:[https://www . geesforgeks . org/python-程序对字符串进行排序/](https://www.geeksforgeeks.org/python-program-to-sort-a-string/)

排序一直是非常受欢迎的实用工具，在任何地方都有很多应用程序，选择了 Python 语言。Python 在其语言中提供了一个排序函数来执行这个任务。但是由于并非 Python 中的所有容器都是可变的，比如字符串，排序函数在试图排序时不起作用，不变性阻止了这一点。让我们讨论字符串排序的某些方法。

**方法#1 : `join() + sorted()`**
上述功能的结合有可能解决这个特殊问题。这个任务分两步执行，在第一步中，我们得到字符的排序列表，然后将结果连接起来，得到排序后的字符串。

```
# Python3 code to demonstrate
# Sorting a string 
# using join() + sorted()

# initializing string 
test_string = "geekforgeeks"

# printing original string 
print("The original string : " + str(test_string))

# using join() + sorted()
# Sorting a string 
res = ''.join(sorted(test_string))

# print result
print("String after sorting : " + str(res))
```

**Output :**

```
The original string : geekforgeeks
String after sorting : eeeefggkkors

```