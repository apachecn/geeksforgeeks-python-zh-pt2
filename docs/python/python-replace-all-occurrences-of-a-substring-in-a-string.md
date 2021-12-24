# Python–替换字符串中出现的所有子字符串

> 原文:[https://www . geesforgeks . org/python-替换字符串中出现的所有子字符串/](https://www.geeksforgeeks.org/python-replace-all-occurrences-of-a-substring-in-a-string/)

有时，在使用 Python 字符串时，我们可能会遇到一个问题，即我们需要用其他子字符串替换一个子字符串的所有出现。

> 输入:test_str =“geeks forgeeks”
> s1 =“geeks”
> s2 =“ABCD”
> 输出:test _ str =“abcdsforebcds”
> 说明:我们将 test _ str 中所有出现的 S1 替换为 S2。
> 
> 输入:test _ str = " geeksforgeeks "
> S1 = " for "
> S2 = " ABCD "
> 输出:test_str = "geeksabcdgeeks "

我们使用 [maketrans()和 translate()](https://www.geeksforgeeks.org/python-maketrans-translate-functions/) 。这是执行此任务的一种内置方式。该函数在内部维护表，并执行交换任务。

```py
# Python3 code to demonstrate working of 
# Swap Binary substring
# Using translate()

# initializing string
test_str = "geeksforgeeks"

# printing original string
print("The original string is : " + test_str)

# Swap Binary substring
# Using translate()
temp = str.maketrans("geek", "abcd")
test_str = test_str.translate(temp)

# printing result 
print("The string after swap : " + str(test_str)) 
```

**Output:**

```py
The original string is : geeksforgeeks
The string after swap : accdsforaccds

```