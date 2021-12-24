# Python–用多个值替换 K

> 原文:[https://www . geesforgeks . org/python-replace-k-with-multiple-values/](https://www.geeksforgeeks.org/python-replace-k-with-multiple-values/)

有时，在使用 Python Strings 时，我们可能会遇到一个问题，即我们需要根据出现情况执行单个字符的替换/使用特定的值列表。这类问题在学校和日常编程中都有应用。让我们讨论执行这项任务的某些方法。

> **输入** : test_str = '*为*。推荐用于* '，repl_char = '* '，
> repl_list = ['Gfg '，' Best '，' CS']
> **输出** : Gfg 为 Best。推荐 CS 使用
> 
> **输入** : test_str = '* is * '，repl_char = '*，
> repl_list = ['Gfg '，' Best']
> **输出** : Gfg 为 Best

**方法#1:使用 loop + `replace()`**
以上功能的组合可以用来解决这个问题。在本例中，我们使用 replace()执行替换任务，并在每次替换后增加索引计数器。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Replace K with Multiple values
# Using loop + replace()

# initializing strings
test_str = '_ is _ . It is recommended for _'

# printing original string
print("The original string is : " + str(test_str))

# initializing repl_char
repl_char = '_'

# initializing repl_list 
repl_list = ['Gfg', 'Best', 'CS']

# Replace K with Multiple values
# Using loop + replace()
for ele in repl_list:
    test_str = test_str.replace(repl_char, ele, 1)

# printing result 
print("String after replacement : " + str(test_str)) 
```

**Output :**

```
The original string is : _ is _ . It is recommended for _
String after replacement : Gfg is Best . It is recommended for CS

```

**方法 2:使用`split() + join() + zip()`**
上述功能的组合提供了解决这个问题的另一种方法。在本文中，我们首先使用 split()拆分单词，使用 zip()压缩两个必需的列表，然后使用适当的替换重新加入。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Replace K with Multiple values
# Using split() + join() + zip()

# initializing strings
test_str = '_ is _ . It is recommended for _'

# printing original string
print("The original string is : " + str(test_str))

# initializing repl_char
repl_char = '_'

# initializing repl_list 
repl_list = ['Gfg', 'Best', 'CS']

# Replace K with Multiple values
# Using split() + join() + zip()
test_list = test_str.split(repl_char)
temp = zip(test_list, repl_list)
res = ''.join([ele for sub in temp for ele in sub])

# printing result 
print("String after replacement : " + str(res)) 
```

**Output :**

```
The original string is : _ is _ . It is recommended for _
String after replacement : Gfg is Best . It is recommended for CS

```