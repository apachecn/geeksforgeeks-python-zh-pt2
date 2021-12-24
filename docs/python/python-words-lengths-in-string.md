# Python |字符串中的单词长度

> 原文:[https://www . geesforgeks . org/python-words-length-in-string/](https://www.geeksforgeeks.org/python-words-lengths-in-string/)

我们有时会遇到这样的情况，我们需要获取字符串中存在的所有单词长度，这可能是一项使用简单方法完成的乏味任务。因此，让人手不足的人来执行这项任务总是有用的。让我们讨论实现这一点的某些方法。

**方法#1:使用`split() + len()`**
使用分割功能，我们可以将字符串分割成一个单词列表，如果你想完成这个特定的任务，这是最通用和推荐的方法。但缺点是它在字符串中包含标点符号的情况下会失败。len()用于计算字符串长度。

```py
# Python3 code to demonstrate 
# Words lengths in String
# using split()

# initializing string 
test_string = "Geeksforgeeks is best Computer Science Portal"

# printing original string
print ("The original string is : " + test_string)

# using split()
# Words lengths in String
res = list(map(len, test_string.split()))

# printing result
print ("The list of words lengths is : " + str(res))
```

**Output :**

```py
The original string is : Geeksforgeeks is best Computer Science Portal
The list of words lengths is : [13, 2, 4, 8, 7, 6]

```