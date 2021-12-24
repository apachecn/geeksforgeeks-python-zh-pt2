# Python |两串并集运算

> 原文:[https://www . geesforgeks . org/python-union-operation-in-two-strings/](https://www.geeksforgeeks.org/python-union-operation-in-two-strings/)

字符串操作之一可以是计算两个字符串的并集。这可能是可以处理的有用应用程序。本文通过不同的方式处理相同的计算。

**方法 1:朴素方法**
执行字符串并集的任务可以通过朴素方法来计算，方法是创建一个空字符串，检查字符串和非公共字符串共有的字符的新出现，并将其追加，从而计算新的并集字符串。这可以通过循环和 if/else 语句来实现。

```
# Python 3 code to demonstrate 
# Union Operation in two Strings
# using naive method 

# initializing strings
test_str1 = 'GeeksforGeeks'
test_str2 = 'Codefreaks'

# Printing initial strings
print ("The original string 1 is : " + test_str1)
print ("The original string 2 is : " + test_str2)

# using naive method to
# Union Operation in two Strings
res = ""
temp = test_str1
for i in test_str2:
    if i not in temp:
        test_str1 += i

# printing result
print ("The string union is : " + test_str1)
```

**Output :**

```
The original string 1 is : GeeksforGeeks
The original string 2 is : Codefreaks
The string union is : GeeksforGeeksCda

```