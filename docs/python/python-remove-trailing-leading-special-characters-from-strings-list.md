# Python |从字符串列表中删除尾随/前导特殊字符

> 原文:[https://www . geesforgeks . org/python-remove-trading-leader-special-characters-from-strings-list/](https://www.geeksforgeeks.org/python-remove-trailing-leading-special-characters-from-strings-list/)

有时，在处理字符串列表时，我们会遇到一个问题，即我们需要删除多余的字符，这些字符可以被称为不需要的，并且出现在每个字符串的末尾。让我们讨论一下执行这项任务的方法。

**方法:使用`map() + str.strip()`**
结合以上两个功能可以帮助我们完成这个特殊的任务。在这种情况下，我们使用 `strip()`，它能够从字符串列表中删除末尾和前面的特殊不需要的字符。`map()`用于将逻辑扩展到列表中的每个元素。

```
# Python3 code to demonstrate working of
# Remove trailing / leading special characters from strings list
# Using map() + str.strip()

# initializing list
test_list = ['\rgfg\t\n', 'is\n', '\t\tbest\r']

# printing list
print("The original list : " + str(test_list))

# Remove trailing / leading special characters from strings list
# Using map() + str.strip()
res = list(map(str.strip, test_list))

# Printing result
print("List after removal of special characters : " + str(res))
```

**Output :**

```

The original list : ['\rgfg\t\n', 'is\n', '\t\tbest\r']
List after removal of special characters : ['gfg', 'is', 'best']

```