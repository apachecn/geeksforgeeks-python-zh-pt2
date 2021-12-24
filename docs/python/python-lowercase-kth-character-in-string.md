# Python–字符串中的小写 Kth 字符

> 原文:[https://www . geesforgeks . org/python-小写-kth-字符串中的字符/](https://www.geeksforgeeks.org/python-lowercase-kth-character-in-string/)

降低弦的问题很常见，已经讨论过很多次了。但是有时候，我们可能会遇到这样的问题，我们需要将字符串的第 n 个字符转换为小写。让我们讨论一下实现这一点的某些方法。

**方法#1:使用字符串切片+ `lower()`**
使用较低的方法可以轻松执行此任务，该方法降低了提供给它的字符的大小写，切片可用于在小写的第 N 个字符后添加剩余的字符串。

```
# Python3 code to demonstrate working of 
# Kth Character Lowercase
# Using lower() + string slicing 

# initializing string 
test_str = "GEEKSFORGEEKS"

# printing original string 
print("The original string is : " + str(test_str)) 

# initializing K
K = 4

# Using lower() + string slicing 
# Kth Character Lowercase
res = test_str[:K] + test_str[K].lower() + test_str[K + 1:] 

# printing result 
print("The string after lowercasing Kth character : " + str(res)) 
```

**Output :**

```
The original string is : GEEKSFORGEEKS
The string after lowercasing Kth character : GEEKsFORGEEKS

```