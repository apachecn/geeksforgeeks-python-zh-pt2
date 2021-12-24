# Python |用其出现替换字符

> 原文:[https://www . geesforgeks . org/python-用出现替换字符/](https://www.geeksforgeeks.org/python-substitute-character-with-its-occurrence/)

有时，在使用 Python 时，我们可能会遇到一个问题，需要用字符串中的字符替换它。这是一个特殊的问题，但可以应用于许多领域。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是蛮力解决问题的方法。在这种情况下，我们为字符串中的每个字符运行一个循环，并在每次增加计数器的同时执行替换。

```py
# Python3 code to demonstrate working of 
# Substitute character with its occurrence
# Using loop

# initializing string
test_str = "geeksforgeeks is best for geeks"

# printing original string
print("The original string is : " + test_str)

# initializing letter 
test_let = 'g'

# Substitute character with its occurrence
# Using loop
res = ''
count = 1
for chr in test_str:
    if chr == test_let:
        res += str(count)
        count += 1
    else:
        res += chr

# printing result 
print("The string after performing substitution : " + str(res)) 
```

**Output :**

```py
The original string is : geeksforgeeks is best for geeks
The string after performing substitution : 1eeksfor2eeks is best for 3eeks

```