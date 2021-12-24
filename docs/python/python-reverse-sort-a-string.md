# Python–对字符串进行反向排序

> 原文:[https://www.geeksforgeeks.org/python-reverse-sort-a-string/](https://www.geeksforgeeks.org/python-reverse-sort-a-string/)

排序一直是非常受欢迎的工具，在 Python 语言选择的地方，到处都有很多应用程序。Python 在其语言中提供了一个排序函数来执行这项任务。但是由于并非 Python 中的所有容器都是可变的，比如字符串，排序函数在试图排序时不起作用，不变性阻止了这一点。让我们讨论字符串可以反向排序的某些方法。

**方法#1 : `join() + sorted() + reverse`键**
上述功能的组合可以潜在地解决这个特定的问题。这个任务分两步执行，在第一步中，我们得到字符的反向排序列表，然后我们连接结果以得到结果排序字符串。

```py
# Python3 code to demonstrate
# Reverse Sort a String
# using join() + sorted() + reverse

# initializing string 
test_string = "geekforgeeks"

# printing original string 
print("The original string : " + str(test_string))

# using join() + sorted() + reverse
# Sorting a string 
res = ''.join(sorted(test_string, reverse = True))

# print result
print("String after reverse sorting : " + str(res))
```

**Output :**

```py
The original string : geekforgeeks
String after reverse sorting : srokkggfeeee

```