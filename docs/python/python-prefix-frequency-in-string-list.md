# Python–字符串列表中的前缀频率

> 原文:[https://www . geesforgeks . org/python-prefix-in-frequency-in-string-list/](https://www.geeksforgeeks.org/python-prefix-frequency-in-string-list/)

有时，在使用 Python 列表时，我们可能会遇到一个问题，即我们需要获取以特定子字符串开头的字符串的计数。这可以在 web 开发和通用编程中得到应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用 loop + `startswith()`**
以上功能的组合可以用来执行这个任务。在本例中，我们对列表中的每个字符串运行一个循环，并使用 start with()来获取以特定前缀开头的字符串。

```py
# Python3 code to demonstrate 
# Prefix frequency in List
# using loop + startswith()

# Initializing list
test_list = ['gfgisbest', 'geeks', 'gfgfreak', 'gfgCS', 'Gcourses']

# printing original list
print("The original list is : " + str(test_list))

# Initializing substring
test_sub = 'gfg'

# Prefix frequency in List
# using loop + startswith()
res = 0
for ele in test_list:
    if ele.startswith(test_sub):
        res = res + 1

# printing result 
print ("Strings count with matching frequency : " + str(res))
```

**Output :**

> 原列表为:[' gfg gist '，' geeks '，' gfgfreak '，' gfgCS '，' Gcourses']
> 匹配频率为 3 的字符串计数