# Python–最小长度字符串

> 原文:[https://www . geesforgeks . org/python-最小长度-字符串/](https://www.geeksforgeeks.org/python-smallest-length-string/)

有时，在处理大量数据时，我们会遇到一个问题，需要提取列表中所有字符串的最小值。这种问题在许多领域都有应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是我们执行这个任务的蛮力方法。在这种情况下，我们运行一个循环来保存最小字符串长度的内存，并返回列表中最小长度的字符串。

```py
# Python3 code to demonstrate working of 
# Smallest Length String
# using loop 

# initialize list 
test_list = ['gfg', 'is', 'best', 'for', 'geeks'] 

# printing original list 
print("The original list : " + str(test_list)) 

# Smallest Length String 
# using loop 
min_len = 99999
for ele in test_list: 
    if len(ele) < min_len: 
        min_len = len(ele) 
        res = ele 

# printing result 
print("Minimum length string is : " + res) 
```

**Output :**

```py
The original list : ['gfg', 'is', 'best', 'for', 'geeks']
Minimum length string is : is

```