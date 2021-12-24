# Python–移除列表的第一个元素

> 原文:[https://www . geeksforgeeks . org/python-移除列表中的第一个元素/](https://www.geeksforgeeks.org/python-removing-first-element-of-list/)

队列数据结构是众所周知的数据结构，Python 中的列表通常会将元素追加到列表的末尾。为了实现队列数据结构，能够从列表中移除前端元素是非常重要的。

让我们讨论删除列表第一个元素的方法。

**方法#1:使用`pop(0)`**

这个方法弹出，即从列表中移除并打印第 I 个元素。此方法主要用于执行此任务的其他可用选项中。这将更改原始列表。

```py
# Python3 code to demonstrate 
# removing front element
# using pop(0)

# initializing list 
test_list = [1, 4, 3, 6, 7]

# Printing original list
print ("Original list is : " + str(test_list))

# using pop(0) to
# perform removal
test_list.pop(0)

# Printing modified list 
print ("Modified list is : " + str(test_list))
```

**输出:**

```py
Original list is : [1, 4, 3, 6, 7]
Modified list is : [4, 3, 6, 7]

```

**方法 2:使用`del list[0]`**
这只是执行前置删除的替代方法，该方法还执行了列表元素的移除到位，并将列表的大小减少 1。

```py
# Python3 code to demonstrate 
# removing front element
# using del list[0]

# initializing list 
test_list = [1, 4, 3, 6, 7]

# Printing original list
print ("Original list is : " + str(test_list))

# using del list[0] to
# perform removal
del test_list[0]

# Printing modified list 
print ("Modified list is : " + str(test_list))
```

**输出:**

```py
Original list is : [1, 4, 3, 6, 7]
Modified list is : [4, 3, 6, 7]

```

**方法三:使用切片**

切片是解决这个问题的另一种方法，我们可以将列表从第二个元素一直切片到最后一个元素，并分配给空列表。这不像上述两种方法那样进行就地转换。

```py
# Python3 code to demonstrate 
# removing front element
# using slicing 

# initializing list 
test_list = [1, 4, 3, 6, 7]

# Printing original list
print ("Original list is : " + str(test_list))

# using  slicing  to
# perform removal
res = test_list[1:]

# Printing modified list 
print ("Modified list is : " + str(res))
```

**输出:**

```py
Original list is : [1, 4, 3, 6, 7]
Modified list is : [4, 3, 6, 7]

```

**方法#4:使用`deque() + popleft()`**
这是一个不太为人所知的方法来实现这个特定的任务，将列表转换成 deque，然后执行 popleft，从列表的前面移除元素。

```py
# Python3 code to demonstrate 
# removing front element
# using deque() + popleft()
from collections import deque

# initializing list 
test_list = [1, 4, 3, 6, 7]

# Printing original list
print ("Original list is : " + str(test_list))

# using deque() + popleft() to
# perform removal
res = deque(test_list)
res.popleft()

# Printing modified list 
print ("Modified list is : " + str(list(res)))
```

**输出:**

```py
Original list is : [1, 4, 3, 6, 7]
Modified list is : [4, 3, 6, 7]

```