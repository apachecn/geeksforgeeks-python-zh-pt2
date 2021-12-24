# Python–从字符串列表中删除多个空格的方法

> 原文:[https://www . geesforgeks . org/python-从字符串列表中删除多个空格的方法/](https://www.geeksforgeeks.org/python-ways-to-remove-multiple-empty-spaces-from-string-list/)

有时，在使用 Python 字符串时，我们会遇到一个问题，即需要删除字符串中的空白。过滤单个空间的问题更容易。但有时我们不知道空间的数量。这在许多领域都有应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用 loop + `strip()`**
这是我们执行这个任务的一种方式。在这种情况下，我们使用 strip()来剥离字符串，它会减少到单个空格，然后可以测试它的空值。如果字符串是单个空格，则返回 True，因此有助于筛选。

```py
# Python3 code to demonstrate working of 
# Remove multiple empty spaces from string List
# Using loop + strip()

# initializing list
test_list = ['gfg', '   ', ' ', 'is', '            ', 'best']

# printing original list
print("The original list is : " + str(test_list))

# Remove multiple empty spaces from string List
# Using loop + strip()
res = []
for ele in test_list:
    if ele.strip():
        res.append(ele)

# printing result 
print("List after filtering non-empty strings : " + str(res)) 
```

**Output :**

```py
The original list is : ['gfg', '   ', ' ', 'is', '            ', 'best']
List after filtering non-empty strings : ['gfg', 'is', 'best']

```