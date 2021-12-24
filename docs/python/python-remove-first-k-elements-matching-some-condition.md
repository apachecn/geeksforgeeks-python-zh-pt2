# Python |移除匹配某些条件的前 K 个元素

> 原文:[https://www . geesforgeks . org/python-remove-first-k-elements-matching-some-condition/](https://www.geeksforgeeks.org/python-remove-first-k-elements-matching-some-condition/)

移除列表中的元素可以使用许多内置函数来执行。移除所有或仅一次移除这两个函数都存在于 Python 库中。本文讨论如何删除与特定条件匹配的元素的第一个 *K* 出现。

**方法#1:天真的方法**
我们可以在 *K* 元素出现后追加匹配条件的元素，从而执行类似于移除的任务。

```
# Python3 code to demonstrate 
# to remove first K elements matching condition
# using Naive Method 

# initializing list
test_list = [3, 5, 1, 6, 7, 9, 8, 5]

# printing original list
print ("The original list is : " + str(test_list))

# using Naive Method 
# to remove first K elements matching condition 
# removes first 4 odd occurrences
counter = 1
res = []
for i in test_list:
    if counter > 4 or not (i % 2 != 0):
        res.append(i)
    else:
        counter += 1

# printing result
print ("The filtered list is : " + str(res))
```

**Output:**

```
The original list is : [3, 5, 1, 6, 7, 9, 8, 5]
The filtered list is : [6, 9, 8, 5]

```

**方法 2:使用`itertools.filterfalse() + itertools.count()`**
这是执行这个特殊任务的不同而优雅的方式。当计数器达到 K 并与条件匹配时，它会过滤掉所有大于 K 的数字。这是实现这一任务的一种线性和首选方法。

```
# Python3 code to demonstrate 
# to remove first K elements matching condition
# using itertools.filterfalse() + itertools.count()
from itertools import filterfalse, count

# initializing list
test_list = [3, 5, 1, 6, 7, 9, 8, 5]

# printing original list
print ("The original list is : " + str(test_list))

# using itertools.filterfalse() + itertools.count()
# to remove first K elements matching condition 
# removes first 4 odd occurrences
res = filterfalse(lambda i, counter = count(): i % 2 != 0 and
                                next(counter) < 4, test_list)

# printing result
print ("The filtered list is : " + str(list(res)))
```

**Output:**

```
The original list is : [3, 5, 1, 6, 7, 9, 8, 5]
The filtered list is : [6, 9, 8, 5]

```