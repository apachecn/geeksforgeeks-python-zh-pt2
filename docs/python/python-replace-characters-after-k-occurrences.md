# Python |替换 K 次出现后的字符

> 原文:[https://www . geesforgeks . org/python-replace-characters-after-k-occurs/](https://www.geeksforgeeks.org/python-replace-characters-after-k-occurrences/)

有时，在使用 Python 字符串时，我们可能会遇到这样的问题，即在某些字符重复之后，我们需要执行字符替换。这可以应用于许多领域，包括日常和竞争性编程。

**方法#1:使用循环+字符串切片**
这是解决这个问题的蛮力方式。在这种情况下，我们在字符串上运行一个循环，跟踪出现次数，并在出现次数高于 K 时执行替换。

```
# Python3 code to demonstrate working of 
# Replace characters after K occurrences
# Using loop + string slices

# initializing string
test_str = "geeksforgeeks is best for geeks"

# printing original string
print("The original string is : " + test_str)

# initializing K 
K = 2

# initializing Repl char
repl_char = "*"

# Replace characters after K occurrences
# Using loop + string slices
for sub in set(test_str):
    for idx in [idx for idx in range(len(test_str)) if test_str[idx] == sub][K:]:
        test_str = test_str[:idx] + repl_char + test_str[idx + 1:]

# printing result 
print("The string after performing replace : " + test_str) 
```

**Output :**

```
The original string is : geeksforgeeks is best for geeks
The string after performing replace : geeksforg**ks i* b**t*for******

```