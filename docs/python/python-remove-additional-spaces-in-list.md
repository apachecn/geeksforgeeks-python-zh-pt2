# Python |删除列表中的额外空格

> 原文:[https://www . geesforgeks . org/python-remove-additional-in-list/](https://www.geeksforgeeks.org/python-remove-additional-spaces-in-list/)

有时，我们有一个包含字符串和空格的列表。我们希望有一致性，这样以后如果我们决定了它们，我们在列表之间就只有一个空格。因此，有时有必要删除列表中单词之间多余的空格。

让我们讨论一下实现这一点的某些方法。

**方法#1:使用列表理解+ `enumerate()`**
在这个方法中，我们创建一个全新的列表，而不是修改原来的列表，并检查元素及其前面的元素是否有空格，并添加只添加一次出现的空格，其余的不添加。

```
# Python3 code to demonstrate 
# removing multiple spaces
# using list comprehension + enumerate()

# initializing list of lists
test_list = ["GfG", "", "", "", "", "is", "", "", "best"]

# printing original list 
print("The original list : " +  str(test_list))

# using list comprehension + enumerate()
# removing multiple spaces
res = [val for idx, val in enumerate(test_list)
       if val or (not val and test_list[idx - 1])]

# printing result 
print("The list after removing additional spaces :  " + str(res))
```

**Output :**

```
The original list : ['GfG', '', '', '', '', 'is', '', '', 'best']
The list after removing additional spaces :  ['GfG', '', 'is', '', 'best']

```

**方法 2:使用列表理解+ `zip()` +列表切片**
在这个方法中，我们一次取一对，检查它的两个元素是否都是空的，如果是，我们就丢弃它。如果有人是空的或者两者都不是空的，我们会把它保留在列表中。

```
# Python3 code to demonstrate 
# removing multiple spaces
# using list comprehension + zip() + list slicing

# initializing list of lists
test_list = ["GfG", "", "", "", "", "is", "", "", "best"]

# printing original list 
print("The original list : " +  str(test_list))

# using list comprehension + zip() + list slicing
# removing multiple spaces
res = test_list[ : 1] + [j for i, j in
      zip(test_list, test_list[1 : ]) if i or j]

# printing result 
print("The list after removing additional spaces :  " + str(res))
```

**Output :**

```
The original list : ['GfG', '', '', '', '', 'is', '', '', 'best']
The list after removing additional spaces :  ['GfG', '', 'is', '', 'best']

```