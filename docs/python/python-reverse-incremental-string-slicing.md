# Python |反向增量字符串切片

> 原文:[https://www . geesforgeks . org/python-反向-增量-字符串-切片/](https://www.geeksforgeeks.org/python-reverse-incremental-string-slicing/)

有时，在处理 Pythonn 字符串时，我们可能会遇到一个问题，即我们需要以相反的顺序执行字符串的切片和打印。这可以在日常编程中应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是可以执行该任务的蛮力方式。在这种情况下，我们以相反的顺序迭代列表，并将增量字符串存储在列表中。

```
# Python3 code to demonstrate working of 
# Reverse Incremental String Slicing
# Using loop

# initializing string
test_str = "geeks"

# printing original string
print("The original string is : " + test_str)

# Reverse Incremental String Slicing
# Using loop
res = []
sub = ''
for chr in reversed(test_str):
    sub += chr
    res.append(sub)

# printing result 
print("The incremental reverse strings : " + str(res)) 
```

**Output :**

```
The original string is : geeks
The incremental reverse strings : ['s', 'sk', 'ske', 'skee', 'skeeg']

```