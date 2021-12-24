# Python |键值大于 K 的记录

> 原文:[https://www . geesforgeks . org/python-带键记录-值-大于-k/](https://www.geeksforgeeks.org/python-records-with-keys-value-greater-than-k/)

当一个人开始使用字典时，得到至少有一个相应键值的合适字典的问题是很常见的。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是可以执行该任务的蛮力方法。为此，我们只使用简单的检查，比较并附加特定关键字的值大于 k 的记录

```py
# Python3 code to demonstrate working of
# Records with Key's value greater than K
# Using loop

# Initialize list
test_list = [{'gfg' : 2, 'is' : 4, 'best' : 6}, 
            {'it' : 5, 'is' : 7, 'best' : 8},
            {'CS' : 10, 'is' : 8, 'best' : 10}]

# Printing original list
print("The original list is : " + str(test_list))

# Initialize K 
K = 6

# Using loop
# Records with Key's value greater than K
res = []
for sub in test_list:
    if sub['is'] >= K:
        res.append(sub)

# printing result 
print("The filtered dictionary records is : " + str(res))
```

**Output :**

```py
The original list is : [{'best': 6, 'gfg': 2, 'is': 4}, {'best': 8, 'it': 5, 'is': 7}, {'best': 10, 'CS': 10, 'is': 8}]
The filtered dictionary records is : [{'best': 8, 'it': 5, 'is': 7}, {'best': 10, 'CS': 10, 'is': 8}]

```