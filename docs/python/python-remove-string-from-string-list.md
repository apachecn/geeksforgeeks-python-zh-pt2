# Python–从字符串列表中移除字符串

> 原文:[https://www . geesforgeks . org/python-remove-string-from-string-list/](https://www.geeksforgeeks.org/python-remove-string-from-string-list/)

这篇特别的文章对于机器学习爱好者来说确实非常有用，因为它为他们解决了一个很好的问题。在机器学习中，我们通常会遇到在大量数据中获取特定字符串并进行处理的问题，这有时会成为一项乏味的任务。让我们讨论解决这个问题的某些方法。

**方法#1:使用`remove()`**
这个特定的方法相当幼稚，不建议使用，但确实是执行这个任务的方法。remove()通常会删除第一个出现的 K 字符串，我们会一直迭代这个过程，直到在列表中没有找到 K 字符串。

```
# Python 3 code to demonstrate 
# Remove K String from String List
# using remove()

# initializing list 
test_list = ["bad", "GeeksforGeeks", "bad", "is", "best", "bad"]

# Printing original list
print ("Original list is : " + str(test_list))

# initializing K 
K = "bad"

# using remove() to
# Remove K String from String List
while(K in test_list) :
    test_list.remove(K)

# Printing modified list 
print ("Modified list is : " + str(test_list))
```

**Output :**

```
Original list is : ['bad', 'GeeksforGeeks', 'bad', 'is', 'best', 'bad']
Modified list is : ['GeeksforGeeks', 'is', 'best']

```