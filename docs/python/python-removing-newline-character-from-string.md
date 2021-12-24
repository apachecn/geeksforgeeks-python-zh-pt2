# Python |从字符串中删除换行符

> 原文:[https://www . geesforgeks . org/python-remove-newline-character-from-string/](https://www.geeksforgeeks.org/python-removing-newline-character-from-string/)

很多时候，在使用 Python 字符串时，我们会遇到一个问题，那就是我们有大量的数据，我们需要执行某种预处理。这也可以是删除字符串中多余的换行符。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这个任务可以使用蛮力来执行，在蛮力中，我们检查字符串中的字符串“\n”，并使用循环从每个字符串中替换它。

```
# Python3 code to demonstrate working of
# Removing newline character from string
# using loop

# initialize list 
test_list = ['gf\ng', 'i\ns', 'b\nest', 'fo\nr', 'geeks\n']

# printing original list 
print("The original list : " + str(test_list))

# Removing newline character from string
# using loop
res = []
for sub in test_list:
    res.append(sub.replace("\n", ""))

# printing result
print("List after newline character removal : " + str(res))
```

**Output :**

```
The original list : ['gf\ng', 'i\ns', 'b\nest', 'fo\nr', 'geeks\n']
List after newline character removal : ['gfg', 'is', 'best', 'for', 'geeks']

```