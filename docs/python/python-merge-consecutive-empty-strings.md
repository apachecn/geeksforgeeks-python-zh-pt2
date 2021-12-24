# Python–合并连续的空字符串

> 原文:[https://www . geesforgeks . org/python-merge-continuous-empty-strings/](https://www.geeksforgeeks.org/python-merge-consecutive-empty-strings/)

有时候，在使用 python 列表时，我们会遇到一个问题，那就是我们需要对列表字符串执行合并操作。这种合并是连续的，将多个空格转换为一个空格。让我们讨论一下实现这一点的特定方式。

**方法#1:使用循环**
这是一种可以执行该任务的暴力方式。在本文中，我们使用循环查找空字符串，并在创建新列表时忽略连续字符串。

```
# Python3 code to demonstrate 
# Merge consecutive empty Strings
# using loop

# Initializing list
test_list = ['Gfg', '', '', '', 'is', '', '', 'best', '']

# printing original list
print("The original list is : " + str(test_list))

# Merge consecutive empty Strings
# using loop
count = 0
res = []
for ele in test_list:
    if ele =='':
        count += 1
        if (count % 2)== 0:
            res.append('')
            count = 0
    else:
        res.append(ele)

# printing result 
print ("List after removal of consecutive empty strings : " + str(res))
```

**Output :**

```
The original list is : ['Gfg', '', '', '', 'is', '', '', 'best', '']
List after removal of consecutive empty strings : ['Gfg', '', 'is', '', 'best', '']

```