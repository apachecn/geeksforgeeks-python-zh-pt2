# Python–大写第 n 个字符

> 原文:[https://www . geesforgeks . org/python-大写-第 n 个字符/](https://www.geeksforgeeks.org/python-uppercase-nth-character/)

字符串大写的问题很常见，已经讨论过很多次了。但是有时候，我们可能会遇到这样的问题，我们需要将字符串的第 n 个字符转换为大写。让我们讨论一下实现这一点的某些方法。

**方法#1:使用字符串切片+ `upper()`**
这个任务可以很容易地使用大写方法来执行，该方法对提供给它的字符进行大写，切片可以用来在大写的第 N 个字符之后添加剩余的字符串。

```
# Python3 code to demonstrate working of
# Uppercase Nth character
# Using upper() + string slicing

# initializing string 
test_str = "GeeksforGeeks"

# printing original string 
print("The original string is : " + str(test_str))

# initializing N 
N = 4

# Using upper() + string slicing
# Uppercase Nth character
res = test_str[:N] + test_str[N].upper() + test_str[N + 1:]

# printing result 
print("The string after uppercasing Nth character : " + str(res))
```

**Output :**

```
The original string is : GeeksforGeeks
The string after uppercasing Nth character : GeekSforGeeks

```