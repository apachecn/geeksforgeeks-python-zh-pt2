# Python |字符串列表中的选择性合并

> 原文:[https://www . geesforgeks . org/python-选择性-字符串合并-列表/](https://www.geeksforgeeks.org/python-selective-merge-in-string-list/)

有时，在使用 Python 列表时，我们可能会遇到需要执行合并操作的问题。可以有各种修改来合并。其中之一就是替换除某个特定字符之外的所有字符。让我们看看执行这项任务的不同方式。

**方法#1:使用列表理解+ `join() + zip()`**
以上方法的组合可以用来执行这个任务。在本文中，我们使用 zip()组合相似的元素，并使用 join()执行合并操作。列表理解用于提供逻辑和迭代。

```
# Python3 code to demonstrate working of
# Selective Merge in String list
# using list comprehension + join() + zip()

# initialize lists
test_list1 = ["abc", "de", "efgh"]
test_list2 = ["gfg", "is", "good"]

# printing original lists
print("The original list 1 : " + str(test_list1))
print("The original list 2 : " + str(test_list2))

# initialize exempt char 
exm_chr = 'g'

# Selective Merge in String list
# using list comprehension + join() + zip()
res = [''.join(l if l == exm_chr else k for k, l in zip(i, j))
      for i, j in zip(test_list1, test_list2)]

# printing result
print("The resultant list after Selective Merge : " + str(res))
```

**Output :**

```
The original list 1 : ['abc', 'de', 'efgh']
The original list 2 : ['gfg', 'is', 'good']
The resultant list after Selective Merge : ['gbg', 'de', 'gfgh']

```