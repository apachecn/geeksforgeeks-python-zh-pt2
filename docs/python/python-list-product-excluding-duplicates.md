# Python–列出排除重复的产品

> 原文:[https://www . geesforgeks . org/python-list-product-exclude-duplicates/](https://www.geeksforgeeks.org/python-list-product-excluding-duplicates/)

本文着重于从包含可能重复的列表中获取唯一列表并找到其产品的操作之一。这种操作有大量的应用程序，因此它的知识很好。
**方法 1:天真方法**
在天真方法中，我们只需遍历列表并在新列表中追加元素的第一次出现，而忽略该特定元素的所有其他出现。执行产品的任务是使用循环完成的。

## 蟒蛇 3

```
# Python 3 code to demonstrate
# Duplication Removal List Product
# using naive methods

# getting Product
def prod(val) :
    res = 1
    for ele in val:
        res *= ele
    return res 

# initializing list
test_list = [1, 3, 5, 6, 3, 5, 6, 1]
print ("The original list is : " + str(test_list))

# using naive method
# Duplication Removal List Product
res = []
for i in test_list:
    if i not in res:
        res.append(i)
res = prod(res)

# printing list after removal
print ("Duplication removal list product : " + str(res))
```

**Output : **

```
The original list is : [1, 3, 5, 6, 3, 5, 6, 1]
Duplication removal list product : 90
```

**方法二:使用列表理解**
这种方法的工作原理与上述方法类似，但这只是借助列表理解完成的较长方法的一行速记。

## 蟒蛇 3

```
# Python 3 code to demonstrate
# Duplication Removal List Product
# using list comprehension

# getting Product
def prod(val) :
    res = 1
    for ele in val:
        res *= ele
    return res 

# initializing list
test_list = [1, 3, 5, 6, 3, 5, 6, 1]
print ("The original list is : " + str(test_list))

# using list comprehension
# Duplication Removal List Product
res = []
[res.append(x) for x in test_list if x not in res]
res = prod(res)

# printing list after removal
print ("Duplication removal list product : " + str(res))
```

**Output : **

```
The original list is : [1, 3, 5, 6, 3, 5, 6, 1]
Duplication removal list product : 90
```

**方法 3:使用 set()和 functools.reduce()【中间体】**

检查列表成员平均为 0(n)，因此建立非重复列表平均变成 0(n<sup>2</sup>)操作。人们可以将一个列表转换成一个集合，以消除重复，这是 O(n)的复杂性。此后，集合元素的乘积可以以通常的方式通过迭代来计算，或者，为了进一步减少代码，可以使用 functools 模块中的 [reduce()](https://docs.python.org/3/library/functools.html#functools.reduce) 方法。正如文档所解释的:

> 从左到右，将两个自变量的函数累计应用于可迭代项，以便将可迭代项减少到单个值。

下面是如何将代码简化为几行的

## 蟒蛇 3

```
import functools

functools.reduce(lambda x, y: x*y, set([1, 3, 5, 6, 3, 5, 6, 1]), 1)
```

这样做是将 lambda 应用于从列表中获得的集合。lambda 接受两个参数 x 和 y，并返回这两个数字的乘积。该λ累积应用于列表中的所有元素，即

> λ(λ(λ(1，3)，5)，6)…。

这产生最终产品 90。在 reduce()函数中添加一个初始参数来处理空序列，这样就可以返回默认值，这是非常谨慎的做法。在这种情况下，因为它是一个产品，所以该值应该是 1。因此类似于

> func tools . reduce(λx，y: x*y，set([])，1)

产生输出 1，尽管列表是空的。这个初始参数被添加到序列中的值之前，lambda 像往常一样被应用。

> lambda(lambda(lambda(1，1)，3)，5)，6)…。