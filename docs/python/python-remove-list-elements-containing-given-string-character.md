# Python |移除包含给定字符串的列表元素

> 原文:[https://www . geesforgeks . org/python-remove-list-elements-containing-给定-string-character/](https://www.geeksforgeeks.org/python-remove-list-elements-containing-given-string-character/)

有时，在使用 Python 列表时，我们可能会遇到这样的问题，即我们需要执行删除列表中至少包含一个字符串字符的所有元素的任务。这可以在日常编程中应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是可以执行该任务的蛮力方式。在这种情况下，我们迭代所有列表元素，并使用循环检查任何字符的出现。

```
# Python3 code to demonstrate working of 
# Remove List elements containing String character
# Using loop

# initializing list
test_list = ['567', '840', '649', '7342']

# initializing string 
test_str = '1237'

# printing original list
print("The original list is : " + str(test_list))

# Remove List elements containing String character
# Using loop
res = []
for sub in test_list:
    flag = 0
    for ele in sub:
        if ele in test_str:
            flag = 1
    if not flag:
        res.append(sub)

# printing result 
print("The list after removal : " + str(res)) 
```

**Output :**

```
The original list is : ['567', '840', '649', '7342']
The list after removal : ['840', '649']

```