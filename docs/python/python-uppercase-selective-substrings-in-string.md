# Python–字符串中的大写选择性子字符串

> 原文:[https://www . geesforgeks . org/python-大写-选择性-字符串中的子字符串/](https://www.geeksforgeeks.org/python-uppercase-selective-substrings-in-string/)

给定一个字符串，执行列表中特定子字符串的大写。

> **输入** : test_str = 'geeksforgeeks 最适合 cs '，子列表=[“BEST”，“GEEKSFORGEEKS”]
> **输出** : GEEKSFORGEEKS 最适合 cs
> **解释** : geeksforgeeks 和 best uppercased。
> 
> **输入**:test _ str = ' GEEKSFORGEEKS best for BEST '，sub _ list =[“BEST”，“GEEKSFORGEEKS”]
> **输出**:GEEKSFORGEEKS BEST for BEST
> **解释** : geeksforgeeks 和 BEST 这两个事件都增加了。

**方法#1:使用 split() + join() +循环**

在这种情况下，我们重复地按子串分割字符串，然后在用子串的高级版本连接字符串后执行连接操作。只有在字符串中出现 1 个子字符串的情况下，这才是成功的。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Uppercase Selective Substrings in String
# Using split() + join() + loop

# initializing strings
test_str = 'geeksforgeeks is best for cs'

# printing original string
print("The original string is : " + str(test_str))

# initializing substrings
sub_list = ["best", "cs", "geeksforgeeks"]

for sub in sub_list:

    # splitting string
    temp = test_str.split(sub, -1)

    # joining after uppercase
    test_str = sub.upper().join(temp)

# printing result 
print("The String after uppercasing : " + str(test_str)) 
```

**Output**

```
The original string is : geeksforgeeks is best for cs
The String after uppercasing : GEEKSFORGEEKS is BEST for CS

```

**方法 2:使用 re.sub() + upper()**

这使用正则表达式来解决这个问题。在这种情况下，我们使用适当的正则表达式，并对找到的字符串执行大写。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Uppercase Selective Substrings in String
# Using re.sub() + upper()
import re

# initializing strings
test_str = 'geeksforgeeks is best for cs'

# printing original string
print("The original string is : " + str(test_str))

# initializing substrings
sub_list = ["best", "cs", "geeksforgeeks"]

# constructing regex
reg = '|'.join(sub_list)
res = re.sub(reg, lambda ele: ele.group(0).upper(), test_str)

# printing result 
print("The String after uppercasing : " + str(res)) 
```

**Output**

```
The original string is : geeksforgeeks is best for cs
The String after uppercasing : GEEKSFORGEEKS is BEST for CS

```