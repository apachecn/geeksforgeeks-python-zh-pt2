# Python–从列表中删除重复项的方法

> 原文:[https://www . geesforgeks . org/python-从列表中删除重复项的方法/](https://www.geeksforgeeks.org/python-ways-to-remove-duplicates-from-list/)

本文重点介绍从包含可能重复的列表中获取唯一列表的操作之一。从列表操作中删除重复有大量的应用程序，因此，它的知识是好的。

**方法 1:天真方法**
在天真方法中，我们只需遍历列表，在新列表中追加元素的第一次出现，并忽略该特定元素的所有其他出现。

```py
# Python 3 code to demonstrate 
# removing duplicated from list 
# using naive methods 

# initializing list
test_list = [1, 3, 5, 6, 3, 5, 6, 1]
print ("The original list is : " +  str(test_list))

# using naive method
# to remove duplicated 
# from list 
res = []
for i in test_list:
    if i not in res:
        res.append(i)

# printing list after removal 
print ("The list after removing duplicates : " + str(res))
```

**输出:**

```py
The original list is : [1, 3, 5, 6, 3, 5, 6, 1]
The list after removing duplicates : [1, 3, 5, 6]

```

**方法二:使用列表理解**
这个方法的工作原理与上面的方法类似，但这只是借助列表理解完成的较长方法的一行速记。

```py
# Python 3 code to demonstrate 
# removing duplicated from list 
# using list comprehension

# initializing list
test_list = [1, 3, 5, 6, 3, 5, 6, 1]
print ("The original list is : " +  str(test_list))

# using list comprehension
# to remove duplicated 
# from list 
res = []
[res.append(x) for x in test_list if x not in res]

# printing list after removal 
print ("The list after removing duplicates : " + str(res))
```

输出:

```py
The original list is : [1, 3, 5, 6, 3, 5, 6, 1]
The list after removing duplicates : [1, 3, 5, 6]

```

**方法 3:使用 `set()`**
这是从列表中删除重复项最流行的方法。但是这种方法的主要缺点是在这种特殊的方法中元素的顺序丢失了。

```py
# Python 3 code to demonstrate 
# removing duplicated from list 
# using set()

# initializing list
test_list = [1, 5, 3, 6, 3, 5, 6, 1]
print ("The original list is : " +  str(test_list))

# using set()
# to remove duplicated 
# from list 
test_list = list(set(test_list))

# printing list after removal 
# distorted ordering
print ("The list after removing duplicates : " + str(test_list))
```

**输出:**

```py
The original list is : [1, 5, 3, 6, 3, 5, 6, 1]
The list after removing duplicates : [1, 3, 5, 6]

```

**方法四:使用列表理解+ `enumerate()`**
列表理解加上枚举功能也可以实现这个任务。它基本上寻找已经出现的元素，并跳过添加它们。它保留了列表顺序。

```py
# Python 3 code to demonstrate 
# removing duplicated from list 
# using list comprehension + enumerate()

# initializing list
test_list = [1, 5, 3, 6, 3, 5, 6, 1]
print ("The original list is : " +  str(test_list))

# using list comprehension + enumerate()
# to remove duplicated 
# from list 
res = [i for n, i in enumerate(test_list) if i not in test_list[:n]]

# printing list after removal 
print ("The list after removing duplicates : " + str(res))
```

**输出:**

```py
The original list is : [1, 5, 3, 6, 3, 5, 6, 1]
The list after removing duplicates : [1, 5, 3, 6]

```

**方法五:使用`collections.OrderedDict.fromkeys()`**
这是完成特定任务最快的方法。它首先删除重复项，并返回一个必须转换为列表的字典。这也适用于字符串。

```py
# Python 3 code to demonstrate 
# removing duplicated from list 
# using collections.OrderedDict.fromkeys()
from collections import OrderedDict

# initializing list
test_list = [1, 5, 3, 6, 3, 5, 6, 1]
print ("The original list is : " +  str(test_list))

# using collections.OrderedDict.fromkeys()
# to remove duplicated 
# from list 
res = list(OrderedDict.fromkeys(test_list))

# printing list after removal 
print ("The list after removing duplicates : " + str(res))
```

**输出:**

```py
The original list is : [1, 5, 3, 6, 3, 5, 6, 1]
The list after removing duplicates : [1, 5, 3, 6]

```