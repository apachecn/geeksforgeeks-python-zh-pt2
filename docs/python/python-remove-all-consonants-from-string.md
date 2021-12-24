# Python–移除字符串中的所有辅音

> 原文:[https://www . geesforgeks . org/python-从字符串中移除所有辅音/](https://www.geeksforgeeks.org/python-remove-all-consonants-from-string/)

有时候，在使用 Python 时，我们可能会遇到一个问题，我们希望从字符串中删除所有非元音。这是一个非常受欢迎的问题，它的解决方案在竞争性编程和日常编程中非常有用。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是执行该任务的方法之一。在这种情况下，我们遍历列表，然后检查元音和过滤器是否存在。

```
# Python3 code to demonstrate working of 
# Remove all consonents from string
# Using loop

# initializing string
test_str = "Gfg is best for geeks"

# printing original string
print("The original string is : " + test_str)

# Remove all consonents from string
# Using loop
res = []
for chr in test_str:
    if chr in "aeiouAEIOU":
        res.extend(chr)
res = "".join(res)

# printing result 
print("String after consonents removal : " + str(res)) 
```

**Output :**

```
The original string is : Gfg is best for geeks
String after consonents removal : ieoee

```