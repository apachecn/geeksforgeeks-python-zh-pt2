# Python |从列表中删除前缀字符串

> 原文:[https://www . geesforgeks . org/python-remove-prefix-strings-from-list/](https://www.geeksforgeeks.org/python-remove-prefix-strings-from-list/)

有时，在处理数据时，我们可能会遇到一个问题，即我们需要以删除以特定前缀开头的字符串的方式过滤字符串列表。让我们讨论执行这项任务的某些方法。

**方法#1:使用 loop + `remove() + startswith()`**
以上功能的组合可以解决这个问题。在这种情况下，我们移除以使用循环访问的特定前缀开头的元素，并返回修改后的列表。

```py
# Python3 code to demonstrate working of
# Remove prefix strings from list
# using loop + remove() + startswith()

# initialize list 
test_list = ['xall', 'xlove', 'gfg', 'xit', 'is', 'best']

# printing original list 
print("The original list : " + str(test_list))

# initialize prefix 
pref = 'x'

# Remove prefix strings from list
# using loop + remove() + startswith()
for word in test_list[:]:
    if word.startswith(pref):
        test_list.remove(word)

# printing result
print("List after removal of Kth character of each string : " + str(test_list))
```

**Output :**

```py
The original list : ['xall', 'xlove', 'gfg', 'xit', 'is', 'best']
List after removal of Kth character of each string : ['gfg', 'is', 'best']

```