# Python |字符串中的多个索引替换

> 原文:[https://www . geesforgeks . org/python-多重索引-字符串替换/](https://www.geeksforgeeks.org/python-multiple-indices-replace-in-string/)

有时，在使用 Python Stings 时，我们可能会遇到一个问题，即我们需要基于 String 的几个索引来执行字符替换。这种问题在许多领域都有应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用`loop + join()`**
这是可以执行这个任务的蛮力方式。在这种情况下，我们对每个字符进行迭代，如果是替换字符，则替换为替换字符。

```
# Python3 code to demonstrate working of 
# Multiple indices Replace in String
# Using loop + join()

# initializing string
test_str = 'geeksforgeeks is best'

# printing original string
print("The original string is : " + test_str)

# initializing list 
test_list = [2, 4, 7, 10]

# initializing repl char
repl_char = '*'

# Multiple indices Replace in String
# Using loop + join()
temp = list(test_str)
for idx in test_list:
    temp[idx] = repl_char
res = ''.join(temp)

# printing result 
print("The String after performing replace : " + str(res)) 
```

**Output :**

```
The original string is : geeksforgeeks is best
The String after performing replace : ge*k*fo*ge*ks is best

```