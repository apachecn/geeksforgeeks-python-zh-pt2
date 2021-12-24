# Python |从字符串列表中删除空字符串

> 原文:[https://www . geesforgeks . org/python-从字符串列表中删除空字符串/](https://www.geeksforgeeks.org/python-remove-empty-strings-from-list-of-strings/)

在许多场景中，我们会遇到在大量数据中获取空字符串的问题，并且处理这个问题有时会变得非常繁琐。让我们讨论从字符串列表中移除空字符串的某些方法。

**方法#1:使用 remove()**

这个特殊的方法相当幼稚，不建议使用，但确实是执行这个任务的方法。`remove()`一般会移除第一个出现的空字符串，我们会不断迭代这个过程，直到列表中没有找到空字符串。

```
# Python3 code to demonstrate 
# removing empty strings 
# using remove()

# initializing list 
test_list = ["", "GeeksforGeeks", "", "is", "best", ""]

# Printing original list
print ("Original list is : " + str(test_list))

# using remove() to
# perform removal
while("" in test_list) :
    test_list.remove("")

# Printing modified list 
print ("Modified list is : " + str(test_list))
```

**Output:**

```
Original list is : ['', 'GeeksforGeeks', '', 'is', 'best', '']
Modified list is : ['GeeksforGeeks', 'is', 'best']

```

**方法 2:使用列表理解**
更简洁更好的方法去除所有空字符串，它只是检查字符串是否为空，并用所有不为空的字符串重新制作列表。

```
# Python 3 code to demonstrate 
# removing empty strings 
# using list comprehension

# initializing list 
test_list = ["", "GeeksforGeeks", "", "is", "best", ""]

# Printing original list
print ("Original list is : " + str(test_list))

# using list comprehension to
# perform removal
test_list = [i for i in test_list if i]

# Printing modified list 
print ("Modified list is : " + str(test_list))
```

**Output:**

```
Original list is : ['', 'GeeksforGeeks', '', 'is', 'best', '']
Modified list is : ['GeeksforGeeks', 'is', 'best']

```

**方法三:使用`join() + split()`**
结合`join()`和`split()`的操作，也可以完成这个任务。我们首先将所有字符串连接起来，这样就可以去掉空白，然后将其拆分回列表，这样现在创建的新列表就没有空字符串了。

```
# Python3 code to demonstrate 
# removing empty strings 
# using join() +  split()

# initializing list 
test_list = ["", "GeeksforGeeks", "", "is", "best", ""]

# Printing original list
print ("Original list is : " + str(test_list))

# using join() +  split() to
# perform removal
test_list = ' '.join(test_list).split()

# Printing modified list 
print ("Modified list is : " + str(test_list))
```

**Output:**

```
Original list is : ['', 'GeeksforGeeks', '', 'is', 'best', '']
Modified list is : ['GeeksforGeeks', 'is', 'best']

```

**方法#4:使用`filter()`**
使用`filter()`是执行这个任务最优雅最快的方式。强烈建议使用这种方法，因为当我们处理可能包含空字符串的大型机器学习数据集时，速度很重要。

```
# Python 3 code to demonstrate 
# removing empty strings 
# using filter()

# initializing list 
test_list = ["", "GeeksforGeeks", "", "is", "best", ""]

# Printing original list
print ("Original list is : " + str(test_list))

# using filter() to
# perform removal
test_list = list(filter(None, test_list))

# Printing modified list 
print ("Modified list is : " + str(test_list))
```

**Output:**

```
Original list is : ['', 'GeeksforGeeks', '', 'is', 'best', '']
Modified list is : ['GeeksforGeeks', 'is', 'best']

```