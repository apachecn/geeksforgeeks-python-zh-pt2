# Python |截断列表

> 原文:[https://www.geeksforgeeks.org/python-truncate-a-list/](https://www.geeksforgeeks.org/python-truncate-a-list/)

有时需要将列表大小限制在一个特定的数字，并从列表中删除在某个数字之后出现的所有元素，该数字被确定为列表大小。这是一个使用 Python 进行网络开发的有用工具。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`pop()`**
`pop` 功能可以重复多次，直到列表大小达到列表大小所需的阈值。这使用了一个完整的循环，因此比较繁琐。

```py
# Python3 code to demonstrate 
# to truncate list using pop()

# initializing list  
test_list = [1, 4, 5, 6, 7, 3, 8, 9, 10]

# printing original list
print ("The original list is : " + str(test_list))

# size desired
k = 5

# using pop()
# to truncate list 
n = len(test_list)
for i in range(0, n - k ):
    test_list.pop()

# printing result
print ("The truncated list is : " +  str(test_list))
```

**Output:**

```py
The original list is : [1, 4, 5, 6, 7, 3, 8, 9, 10]
The truncated list is : [1, 4, 5, 6, 7]

```