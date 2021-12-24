# Python |反转元组

> 原文:[https://www.geeksforgeeks.org/python-reversing-tuple/](https://www.geeksforgeeks.org/python-reversing-tuple/)

我们知道，在 Python 中，元组是不可变的，因此它不能被更改或更改。这为我们提供了有限的反转元组的方法，不像列表。我们将介绍一些关于 python 中元组如何反转的技术。
示例:

```py
Input : tuples = ('z','a','d','f','g','e','e','k')
Output : ('k', 'e', 'e', 'g', 'f', 'd', 'a', 'z')

Input : tuples = (10, 11, 12, 13, 14, 15)
Output : (15, 14, 13, 12, 11, 10)

```

**方法 1:采用切片技术。**
在这种技术中，元组被复制，并且元组没有被就地排序。因为元组是不可变的，所以没有办法就地反转元组。创建副本需要更多空间来容纳所有现有元素。因此，这会耗尽记忆。

```py
# Reversing a tuple using slicing technique
# New tuple is created
def Reverse(tuples):
    new_tup = tuples[::-1]
    return new_tup

# Driver Code
tuples = ('z','a','d','f','g','e','e','k')
print(Reverse(tuples))
```

输出:

```py
('k', 'e', 'e', 'g', 'f', 'd', 'a', 'z')

```

**方法二:使用反向()内置函数。**
在这个方法中，我们不做任何元组的拷贝。相反，我们得到一个反向迭代器，用于循环遍历元组，类似于列表。

```py
# Reversing a list using reversed()
def Reverse(tuples):
    new_tup = ()
    for k in reversed(tuples):
        new_tup = new_tup + (k,)
    print new_tup

# Driver Code
tuples = (10, 11, 12, 13, 14, 15)
Reverse(tuples)
```

输出:

```py
(15, 14, 13, 12, 11, 10)

```