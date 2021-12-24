# Python |列表中最长的字符串

> 原文:[https://www . geesforgeks . org/python-列表中最长的字符串/](https://www.geeksforgeeks.org/python-longest-string-in-list/)

有时，在使用 Python 列表时，我们会遇到一个问题，即我们接收字符串作为元素，并希望计算最大长度的字符串。这种问题在许多领域都有应用。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用循环**
这是我们执行这个任务的蛮力方法。在这种情况下，我们运行一个循环来保存最长字符串长度的内存，并返回列表中最大长度的字符串。

```py
# Python3 code to demonstrate working of
# Longest String in list
# using loop

# initialize list 
test_list = ['gfg', 'is', 'best', 'for', 'geeks']

# printing original list 
print("The original list : " + str(test_list))

# Longest String in list
# using loop
max_len = -1
for ele in test_list:
    if len(ele) > max_len:
        max_len = len(ele)
        res = ele

# printing result
print("Maximum length string is : " + res)
```

**Output :**

```py
The original list : ['gfg', 'is', 'best', 'for', 'geeks']
Maximum length string is : geeks

```