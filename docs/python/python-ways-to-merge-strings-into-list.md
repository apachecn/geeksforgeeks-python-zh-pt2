# Python |将字符串合并到列表中的方法

> 原文:[https://www . geesforgeks . org/python-将字符串合并到列表中的方法/](https://www.geeksforgeeks.org/python-ways-to-merge-strings-into-list/)

给定 n 个字符串，任务是将所有字符串合并到一个列表中。

在开发一个应用程序时，会有很多场景需要我们对字符串进行操作，并将其转换为一些可变的数据结构，比如 *list* 。有多种方法可以根据需求将字符串转换为列表。让我们借助例子更好地理解它。

 **方法#1:使用***ast***T6】**

```py
# Python code to merge all strings into a single list.

# Importing
import ast

# Initialization of strings
str1 ="'Geeks', 'for', 'Geeks'"
str2 ="'paras.j', 'jain.l'"
str3 ="'india'"

# Initialization of list
list = []

# Extending into single list
for x in (str1, str2, str3):
    list.extend(ast.literal_eval(x))

# printing output
print(list)
```

**Output:**

```py
['Geeks', 'for', 'Geeks', 'paras.j', 'jain.l', 'i', 'n', 'd', 'i', 'a']

```

 **方法 2:使用 ***eval*****

```py
# Python code to merge all strings into a single list.

# Initialization of strings
str1 ="['Geeks', 'for', 'Geeks']"
str2 ="['paras.j', 'jain.l']"
str3 ="['india']"

out = [str1, str2, str3]

out = eval('+'.join(out))

# printing output
print(out)
```

**Output:**

```py
['Geeks', 'for', 'Geeks', 'paras.j', 'jain.l', 'india']

```

```py
# Python code to merge all strings into a single list.

# Initialization of strings
str1 ="'Geeks', 'for', 'Geeks'"
str2 = "'121', '142'"
str3 ="'extend', 'India'"

out = [str1, str2, str3]

out = eval('+'.join(out))

# printing output
print(list(out))
```

**Output:**

```py
['Geeks', 'for', 'Geeks121', '142extend', 'India']

```