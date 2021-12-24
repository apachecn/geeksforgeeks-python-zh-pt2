# Python–从索引

开始的单词

> 原文:[https://www . geesforgeks . org/python-word-start-at-index/](https://www.geeksforgeeks.org/python-word-starting-at-index/)

有时，在使用 Python 时，我们可能会遇到一个问题，即我们需要提取从特定索引开始的单词。这在学校编程中有很多应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是可以执行该任务的蛮力方式。在这种情况下，我们在获取索引后对字符串进行迭代，直到第一个空格。

```
# Python3 code to demonstrate working of 
# Word starting at Index
# Using loop

# initializing string
test_str = "gfg is best for geeks"

# printing original string
print("The original string is : " + test_str)

# initializing K 
K = 7

# Word starting at Index
# Using loop
res = ''
for idx in range(K, len(test_str)):
    if test_str[idx] == ' ':
        break
    res += test_str[idx]

# printing result 
print("Word at index K : " + str(res)) 
```

**Output :**

```
The original string is : gfg is best for geeks
Word at index K : best

```