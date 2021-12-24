# Python |一次替换多个字符

> 原文:[https://www . geesforgeks . org/python-一次替换多个字符/](https://www.geeksforgeeks.org/python-replace-multiple-characters-at-once/)

用一个字符替换另一个字符是每个 python 程序员过去都会遇到的常见问题。但是有时候，我们需要一个简单的单线解决方案来完成这个特殊的任务。让我们讨论执行这项任务的某些方法。

**方法#1:使用嵌套的`replace()`**
这个问题可以使用嵌套的替换方法来解决，该方法会在内部创建一个 temp。变量来保持中间替换状态。

```
# Python3 code to demonstrate working of
# Replace multiple characters at once
# Using nested replace()

# initializing string 
test_str = "abbabba"

# printing original string 
print("The original string is : " + str(test_str))

# Using nested replace()
# Replace multiple characters at once
res = test_str.replace('a', '%temp%').replace('b', 'a').replace('%temp%', 'b')

# printing result 
print("The string after replacement of positions : " + res)
```

**Output :**

```
The original string is : abbabba
The string after replacement of positions : baabaab

```