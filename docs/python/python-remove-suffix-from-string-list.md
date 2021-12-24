# Python–从字符串列表中删除后缀

> 原文:[https://www . geesforgeks . org/python-从字符串列表中删除后缀/](https://www.geeksforgeeks.org/python-remove-suffix-from-string-list/)

有时，在处理数据时，我们可能会遇到一个问题，即我们需要以删除以特定后缀结尾的字符串的方式过滤字符串列表。让我们讨论执行这项任务的某些方法。

**方法#1:使用 loop + `remove() + endswith()`**
以上功能的组合可以解决这个问题。在这种情况下，我们移除以使用循环访问的特定后缀结尾的元素，并返回修改后的列表。

```py
# Python3 code to demonstrate working of
# Suffix removal from String list
# using loop + remove() + endswith()

# initialize list 
test_list = ['allx', 'lovex', 'gfg', 'xit', 'is', 'bestx']

# printing original list 
print("The original list : " + str(test_list))

# initialize suffix
suff = 'x'

# Suffix removal from String list
# using loop + remove() + endswith()
for word in test_list[:]:
    if word.endswith(suff):
        test_list.remove(word)

# printing result
print("List after removal of suffix elements : " + str(test_list))
```

**Output :**

```py
The original list : ['allx', 'lovex', 'gfg', 'xit', 'is', 'bestx']
List after removal of suffix elements : ['gfg', 'xit', 'is']

```