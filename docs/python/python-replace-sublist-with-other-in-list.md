# Python |用列表中的其他替换子列表

> 原文:[https://www . geesforgeks . org/python-replace-sublist-with-other-in-list/](https://www.geeksforgeeks.org/python-replace-sublist-with-other-in-list/)

有时候，在使用 Python 时，我们可能会遇到一个问题，我们需要以这样一种方式操作一个列表，以至于我们需要用其他列表替换一个子列表。这种问题在 web 开发领域很常见。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环(当给出子列表时)**
该方法用于我们知道要替换的子列表的情况。我们使用循环和列表切片来执行此任务，并划分逻辑以找到需要首先操作的索引，然后执行替换。

```py
# Python3 code to demonstrate working of
# Replace sublist with other in list
# Using loop (when sublist is given)

# helper function to find elements 
def find_sub_idx(test_list, repl_list, start = 0):
    length = len(repl_list)
    for idx in range(start, len(test_list)):
        if test_list[idx : idx + length] == repl_list:
            return idx, idx + length

# helper function to perform final task
def replace_sub(test_list, repl_list, new_list):
    length = len(new_list)
    idx = 0
    for start, end in iter(lambda: find_sub_idx(test_list, repl_list, idx), None):
        test_list[start : end] = new_list
        idx = start + length

# initializing list
test_list = [4, 5, 6, 7, 10, 2]

# printing original list
print("The original list is : " + str(test_list))

# Replace list 
repl_list = [5, 6, 7]
new_list = [11, 1]

# Replace sublist with other in list
# Using loop (when sublist is given)
replace_sub(test_list, repl_list, new_list)

# printing result 
print("List after replacing sublist : " + str(test_list))
```

**Output :**

```py
The original list is : [4, 5, 6, 7, 10, 2]
List after replacing sublist : [4, 11, 1, 10, 2]

```