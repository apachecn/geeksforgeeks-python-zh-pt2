# Python 中 range()对 xrange()

> 原文:[https://www.geeksforgeeks.org/range-vs-xrange-python/](https://www.geeksforgeeks.org/range-vs-xrange-python/)

range()和 xrange()是 Python 中[和](https://www.geeksforgeeks.org/loops-and-loop-control-statements-continue-break-and-pass-in-python/)循环中可以重复一定次数的两个函数。在 Python 3 中，没有 xrange，但是 range 函数的行为类似于 Python 2 中的 xrange。如果您想编写将在 Python 2 和 Python 3 上运行的代码，您应该使用 range()。

*   **range()**–返回一个 range 对象(一种可迭代的类型)。
*   **xrange()**–该函数返回**生成器对象**，该对象只能通过循环来显示数字。唯一的特定范围是按需显示的，因此被称为“T4”懒惰评估。

两者都以不同的方式实现，并具有不同的相关特性。比较的要点是:

*   返回类型
*   记忆
*   操作用途
*   速度

### 返回类型

range()返回–**range**对象。
xrange()返回–**xrange()**对象。

## 计算机编程语言

```
# Python code to demonstrate range() vs xrange()
# on  basis of return type

# initializing a with range()
a = range(1,10000)

# initializing a with xrange()
x = xrange(1,10000)

# testing the type of a
print ("The return type of range() is : ")
print (type(a))

# testing the type of x
print ("The return type of xrange() is : ")
print (type(x))
```

**输出:**

```
The return type of range() is : 
<type 'list'>
The return type of xrange() is : 
<type 'xrange'>
```

### 记忆

与使用 xrange()存储范围的变量相比，由 range() **创建的存储**范围的变量**需要更多的内存**。其基本原因是 range()的返回类型是 list，xrange()是 xrange()对象。

## 计算机编程语言

```
# Python code to demonstrate range() vs xrange()
# on  basis of memory

import sys

# initializing a with range()
a = range(1,10000)

# initializing a with xrange()
x = xrange(1,10000)

# testing the size of a
# range() takes more memory
print ("The size allotted using range() is : ")
print (sys.getsizeof(a))

# testing the size of x
# xrange() takes less memory
print ("The size allotted using xrange() is : ")
print (sys.getsizeof(x))
```

**输出:**

```
The size allotted using range() is : 
80064
The size allotted using xrange() is : 
40
```

### 操作使用

当 range()返回列表时，**可以应用于列表的所有操作都可以在上面使用。另一方面，当 xrange()返回 xrange 对象时，与列表**相关联的操作不能应用于它们，因此是一个缺点。****

## **计算机编程语言**

```
# Python code to demonstrate range() vs xrange()
# on  basis of operations usage

# initializing a with range()
a = range(1,6)

# initializing a with xrange()
x = xrange(1,6)

# testing usage of slice operation on range()
# prints without error
print ("The list after slicing using range is : ")
print (a[2:5])

# testing usage of slice operation on xrange()
# raises error
print ("The list after slicing using xrange is : ")
print (x[2:5])
```

****错误:****

```
Traceback (most recent call last):
  File "1f2d94c59aea6aed795b05a19e44474d.py", line 18, in 
    print (x[2:5])
TypeError: sequence index must be integer, not 'slice'
```

****输出:****

```
The list after slicing using range is : 
[3, 4, 5]
The list after slicing using xrange is : 
```

### **速度**

**由于 xrange()只计算只包含惰性计算所需值的生成器对象，因此**在实现上比 range()更快**。**

****要点:****

*   **如果您想编写将在 Python 2 和 Python 3 上运行的代码，请使用 range()，因为在 Python 3 中不推荐使用 xrange 函数。**
*   **如果多次迭代相同的序列，range()会更快。**
*   **xrange()每次都要重构整数对象，但是 range()会有实整数对象。(然而，就内存而言，它的性能总是更差)**

<figure class="table">

| **范围()** | **xrange()** |
| --- | --- |
| 返回整数列表。 | 返回生成器对象。 |
| 执行速度较慢 | 执行速度更快。 |
| 占用更多内存，因为它将整个元素列表保留在内存中。 | 占用更少的内存，因为它一次只在内存中保留一个元素。 |
| 当它返回一个列表时，可以执行所有的算术运算。 | 此类操作不能在 xrange()上执行。 |
| 在 python 3 中，不支持 xrange()。 | 在 python 2 中，xrange()用于循环迭代。 |

</figure>

**本文由 [**【曼吉特·辛格】**](https://www.facebook.com/manjeet.04.singh) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](http://www.write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。**

**如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。**