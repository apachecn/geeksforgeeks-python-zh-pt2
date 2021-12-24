# Python |从给定字符串中返回小写字符

> 原文:[https://www . geesforgeks . org/python-return-小写-characters-from-given-string/](https://www.geeksforgeeks.org/python-return-lowercase-characters-from-given-string/)

有时，在处理字符串时，我们担心字符串的区分大小写，可能需要在一个长字符串中只获取特定大小写的字符。让我们讨论从字符串中只提取小写字母的某些方法。

**方法#1:使用列表理解+ `islower()`**
列表理解和 islower 功能可以用来执行这个特定的任务。列表理解主要用于遍历列表，islower 函数检查小写字符。

```py
# Python3 code to demonstrate working of
# Return lowercase characters in string 
# Using list comprehension + islower()

# initializing string 
test_str = "GeeksForGeeKs"

# printing original string 
print("The original string is : " + str(test_str))

# Return lowercase characters in string 
# Using list comprehension + islower()
res = [char for char in test_str if char.islower()]

# printing result 
print("The lowercase characters in string are : " + str(res))
```

**Output :**

> 原字符串为:GeeksForGeeKs
> 字符串中的小写字符为:['e '，' e '，' k '，' s '，' o '，' r '，' e '，' e '，' s']