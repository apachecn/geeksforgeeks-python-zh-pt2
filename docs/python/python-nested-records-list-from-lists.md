# Python–列表中的嵌套记录列表

> 原文:[https://www . geesforgeks . org/python-嵌套-记录-列表-来自列表/](https://www.geeksforgeeks.org/python-nested-records-list-from-lists/)

有时，在使用 Python 数据时，我们会遇到数据以不同格式传入的问题。在这种情况下，我们可以在单独的字典中以键和值的形式接收数据，并且我们需要用新的键将值作为记录列表。让我们讨论执行这项任务的某些方法。

**方法#1:使用`zip()` +循环**
以上功能的组合可以用来解决这个问题。在这种情况下，我们使用 zip 执行配对，手动添加密钥是以暴力的方式完成的。

```py
# Python3 code to demonstrate working of 
# Nested Records List from Lists
# Using zip() + loop

# initializing lists
test_list1 = ['gfg', 'best']
test_list2 = [[1, 2], [3, 4]]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# initializing add_key 
add_key = 'id'

# Nested Records List from Lists
# Using zip() + loop
res = dict()
for key, val in zip(test_list1, test_list2):
    res[key]=[{add_key : idx} for idx in val]

# printing result 
print("The constructed dictionary is : " + str(res)) 
```

**Output :**

> 原始列表 1 为:['gfg '，' best']
> 原始列表 2 为:[[1，2]，[3，4]]
> 构造的字典为:{'gfg': [{'id': 1}，{'id': 2}]，' best': [{'id': 3}，{'id': 4}]}