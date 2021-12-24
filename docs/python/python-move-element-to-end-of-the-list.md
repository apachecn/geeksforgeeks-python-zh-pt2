# Python |将元素移动到列表末尾

> 原文:[https://www . geesforgeks . org/python-将元素移动到列表末尾/](https://www.geeksforgeeks.org/python-move-element-to-end-of-the-list/)

列表操作在日常编程中非常常见。人们可能会遇到各种问题，希望只使用一行代码就能完成。一个这样的问题是将列表元素移到后面(列表的末尾)。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`append() + pop() + index()`**
通过组合这些功能，可以在一行中执行该特定功能。append 函数使用 index 函数提供的索引添加 pop 函数移除的元素。

```py
# Python3 code to demonstrate  
# moving element to end 
# using append() + pop() + index()

# initializing list
test_list = ['3', '5', '7', '9', '11']

# printing original list 
print ("The original list is : " + str(test_list))

# using append() + pop() + index()
# moving element to end 
test_list.append(test_list.pop(test_list.index(5)))

# printing result
print ("The modified element moved list is : " + str(test_list))
```

**Output :**

```py
The original list is : ['3', '5', '7', '9', '11']
The modified element moved list is : ['3', '7', '9', '11', '5']

```