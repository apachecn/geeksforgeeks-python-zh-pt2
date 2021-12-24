# Python |将给定字符串分成相等的两半

> 原文:[https://www . geeksforgeeks . org/python-将给定字符串分成相等的两半/](https://www.geeksforgeeks.org/python-split-given-string-into-equal-halves/)

有时候，我们需要简单地把绳子分成相等的两半。这种类型的应用可以出现在从简单编程到 web 开发的各种领域。让我们讨论一下实现这一点的某些方法。

**方法#1:使用列表理解+字符串切片**
这是执行这个特定任务的幼稚方法。在这种情况下，我们只使用强力除法和切片来分离字符串的第一部分和最后一部分。

```
# Python3 code to demonstrate working of
# Splitting string into equal halves
# Using list comprehension + string slicing

# initializing string 
test_str = "GeeksforGeeks"

# printing original string 
print("The original string is : " + test_str)

# Using list comprehension + string slicing
# Splitting string into equal halves
res_first = test_str[0:len(test_str)//2]
res_second = test_str[len(test_str)//2 if len(test_str)%2 == 0
                                 else ((len(test_str)//2)+1):]

# printing result 
print("The first part of string : " + res_first)
print("The second part of string : " + res_second)
```

**Output :**

```
The original string is : GeeksforGeeks
The first part of string : Geeksf
The second part of string : rGeeks

```