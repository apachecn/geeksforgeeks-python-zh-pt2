# Python |特定字符前的前缀提取

> 原文:[https://www . geesforgeks . org/python-前缀-特定字符前提取/](https://www.geeksforgeeks.org/python-prefix-extraction-before-specific-character/)

有时，我们可能有一个用例，需要在字符串中找到前缀。但是有时，需求可能是动态的，比如特定的输入字符，而不是决定获取前缀的元素数量。
我们来讨论一下在某个字符之前找到字符串前缀的某些方法。

**方法#1:使用`rsplit()`**
这种方法最初执行的是从后端拆分琴弦的任务，而不是传统的从左到右的方式。不过，为了解决这个特殊问题，这可以限制为 1。

```
# Python3 code to demonstrate working of
# Prefix extraction before specific character
# Using rsplit()

# initializing string 
test_str = "GeeksforGeeks"

# initializing split character
spl_char = "r"

# printing original string 
print("The original string is : " + str(test_str))

# Using rsplit()
# Prefix extraction before specific character
res = test_str.rsplit(spl_char, 1)[0]

# printing result 
print("The prefix string is : " + str(res))
```

**Output :**

```
The original string is : GeeksforGeeks
The prefix string is : Geeksfo

```