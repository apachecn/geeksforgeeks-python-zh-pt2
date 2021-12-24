# Python |在列表中加扰字符串

> 原文:[https://www . geesforgeks . org/python-scramble-string-in-list/](https://www.geeksforgeeks.org/python-scramble-strings-in-list/)

有时，在使用不同的应用程序时，我们可能会遇到一个问题，即我们需要打乱列表输入中的所有字符串。这种问题尤其可能发生在游戏领域。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用列表理解+ `sample() + join()`**
以上功能的组合可以用来解决这个问题。在这种情况下，我们需要将字符串分解成字符列表，使用 sample()进行加扰，使用 join()重新连接它们，然后使用列表理解重新制作列表。

```
# Python3 code to demonstrate working of
# Scramble strings in list
# using list comprehension + sample() + join()
from random import sample 

# initialize list 
test_list = ['gfg', 'is', 'best', 'for', 'geeks']

# printing original list 
print("The original list : " + str(test_list))

# Scramble strings in list
# using list comprehension + sample() + join()
res = [''.join(sample(ele, len(ele))) for ele in test_list]

# printing result
print("Scrambled strings in lists are : " + str(res))
```

**Output :**

```
The original list : ['gfg', 'is', 'best', 'for', 'geeks']
Scrambled strings in lists are : ['fgg', 'is', 'btse', 'rof', 'sgeke']

```