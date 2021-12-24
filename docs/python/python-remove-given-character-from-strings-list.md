# Python |从字符串列表中删除给定字符

> 原文:[https://www . geesforgeks . org/python-从字符串列表中删除给定字符/](https://www.geeksforgeeks.org/python-remove-given-character-from-strings-list/)

有时，在使用 Python 列表时，我们会遇到一个问题，需要从列表中的每个字符串中删除一个特定的字符。这种应用可以出现在许多领域。让我们讨论解决这个问题的某些方法。

**方法#1:使用`replace() + enumerate()` +循环**
这是解决这个问题的蛮力方式。在这种情况下，我们遍历每个字符串并用空字符串替换指定的字符来执行删除。

```py
# Python3 code to demonstrate working of
# Remove character from Strings list
# using loop + replace() + enumerate()

# initialize list 
test_list = ['gfg', 'is', 'best', 'for', 'geeks']

# printing original list 
print("The original list : " + str(test_list))

# initialize character
char = 's'

# Remove character from Strings list
# using loop + replace() + enumerate()
for idx, ele in enumerate(test_list):
        test_list[idx] = ele.replace(char, '')

# printing result
print("The list after removal of character : " + str(test_list))
```

**Output :**

```py
The original list : ['gfg', 'is', 'best', 'for', 'geeks']
The list after removal of character : ['gfg', 'i', 'bet', 'for', 'geek']

```