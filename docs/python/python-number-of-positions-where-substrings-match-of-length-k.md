# Python–子串匹配长度为 K 的位置数

> 原文:[https://www . geesforgeks . org/python-位置数-where-substrings-长度匹配-k/](https://www.geeksforgeeks.org/python-number-of-positions-where-substrings-match-of-length-k/)

给定 2 个字符串，计算长度为 K 的子字符串匹配的位置。

> **输入** : test_str1 = 'geeksforgeeks '，test_str2 = 'peeksformeeks '，K = 4
> **输出** : 4
> **解释** : 4 个位置匹配 K 长度 Substings。
> 
> **输入** : test_str1 = 'geeksforgeeks '，test_str2 = 'peeksformeeks '，K = 5
> **输出** : 3
> **解释** : 3 个位置匹配 K 长度 Substings。

**方法一:使用列表理解+ min() +切片**

在这种情况下，我们迭代字符串，直到最小字符串的长度，比较是通过使用字符串切片切片来完成的。迭代是通过循环内部列表理解来完成的。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Number of positions where Substrings Match of Length K
# Using list comprehension + min() + slicing

# initializing strings
test_str1 = 'geeksforgeeks'
test_str2 = 'peeksformeeks'

# printing original strings
print("The original string 1 is : " + str(test_str1))
print("The original string 2 is : " + str(test_str2))

# initializing K 
K = 3 

# checking for substrings, 
# using len() to get total count
res = len([test_str1[idx : idx + K] for idx in range(min(len(test_str1), len(test_str2)) - K - 1)
        if test_str1[idx : idx + K] == test_str2[idx : idx + K]])

# printing result 
print("Number of positions of matching K length Substrings : " + str(res)) 
```

**Output**

```
The original string 1 is : geeksforgeeks
The original string 2 is : peeksformeeks
Number of positions of matching K length Substrings : 5

```

**方法二:使用地图()+列表理解**

在这种情况下，我们提取一个字符串的所有 K 长度子字符串，然后使用 In 运算符和 map，检查每个子字符串是否存在于其他字符串中，这忽略了问题的位置因素。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Number of positions where Substrings Match of Length K
# Using map() + list comprehension

# initializing strings
test_str1 = 'geeksforgeeks'
test_str2 = 'peeksformeeks'

# printing original strings
print("The original string 1 is : " + str(test_str1))
print("The original string 2 is : " + str(test_str2))

# initializing K 
K = 3 

# Extracting Substrings
subs_str = [test_str1[idx : idx + K] for idx in range(len(test_str1) - K - 1)]

# checking in other string
# using count() to get number
res = list(map(lambda ele: ele in test_str2, subs_str)).count(True)

# printing result 
print("Number of positions of matching K length Substrings : " + str(res)) 
```

**Output**

```
The original string 1 is : geeksforgeeks
The original string 2 is : peeksformeeks
Number of positions of matching K length Substrings : 5

```