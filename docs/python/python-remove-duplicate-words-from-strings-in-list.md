# Python–从列表中的字符串中删除重复的单词

> 原文:[https://www . geesforgeks . org/python-从列表字符串中删除重复单词/](https://www.geeksforgeeks.org/python-remove-duplicate-words-from-strings-in-list/)

有时，在使用 Python 列表时，我们可能会遇到一个问题，需要从字符串列表中删除重复的单词。当我们在数据领域时，这可能会有应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用`set() + split()` +循环**
以上方法的组合可以用来执行此任务。在这种情况下，我们首先将每个列表拆分成组合单词，然后使用 set()来执行重复删除任务。

```
# Python3 code to demonstrate 
# Remove duplicate words from Strings in List
# using loop + set() + split()

# Initializing list
test_list = ['gfg, best, gfg', 'I, am, I', 'two, two, three' ]

# printing original list
print("The original list is : " + str(test_list))

# Remove duplicate words from Strings<code></code> in List
# using loop + set() + split()
res = []
for strs in test_list:
    res.append(set(strs.split(", ")))

# printing result 
print ("The list after duplicate words removal is : " + str(res))
```

**Output :**

```
The original list is : ['gfg, best, gfg', 'I, am, I', 'two, two, three']
The list after duplicate words removal is : [{'best', 'gfg'}, {'I', 'am'}, {'three', 'two'}]

```