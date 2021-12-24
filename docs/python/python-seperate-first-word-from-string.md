# Python–从字符串中分离第一个单词

> 原文:[https://www . geeksforgeeks . org/python-从字符串中分离第一个单词/](https://www.geeksforgeeks.org/python-seperate-first-word-from-string/)

有时，在使用 Python 字符串时，我们可能会遇到一个问题，需要将第一个单词从整个字符串中分离出来。这在许多领域都可能有应用，比如日常工作和网络开发。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是执行这个任务的蛮力方式。在这种情况下，我们迭代字符串并提取单词直到第一个单词，然后附加其他字符串作为列表的其他元素。

```
# Python3 code to demonstrate working of 
# Separate first word from String
# Using loop

# initializing string
test_str = "gfg is best"

# printing original string
print("The original string is : " + test_str)

# Separate first word from String
# Using loop
res = []
temp = ''
flag = 1
for ele in test_str:
    if ele == ' ' and flag:
        res.append(temp)
        temp = ''
        flag = 0
    else :
        temp += ele
res.append(temp)

# printing result 
print("Initial word separated list : " + str(res)) 
```

**Output :**

```
The original string is : gfg is best
Initial word separated list : ['gfg', 'is best']

```