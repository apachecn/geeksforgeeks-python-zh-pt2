# Python |在字典列表中设置差异

> 原文:[https://www . geesforgeks . org/python-set-差异词典列表/](https://www.geeksforgeeks.org/python-set-difference-in-list-of-dictionaries/)

两个列表的差异已经讨论过很多次了，但是有时我们有大量的数据，我们需要找到差异，即 dict2 中的元素而不是 in 1，以减少冗余。让我们讨论一下实现这一点的某些方法。

**方法#1:使用列表理解**
迭代列表和提取差异的幼稚方法可以缩短为使用列表理解来缩短代码和增加可读性的方法。

```
# Python3 code to demonstrate 
# set difference in dictionary list 
# using list comprehension

# initializing list 
test_list1 = [{"HpY" : 22}, {"BirthdaY" : 2}, ]
test_list2 = [{"HpY" : 22}, {"BirthdaY" : 2}, {"Shambhavi" : 2019}]

# printing original lists
print ("The original list 1 is : " + str(test_list1))
print ("The original list 2 is : " +  str(test_list2))

# using list comprehension
# set difference in dictionary list 
res = [i for i in test_list1 if i not in test_list2] \
      + [j for j in test_list2 if j not in test_list1]

# printing result 
print ("The set difference of list is : " +  str(res))
```

**输出:**

> 原列表 1 为:[{'HpY': 22}，{ '生日':2}]
> 原列表 2 为:[{'HpY': 22}，{ '生日':2}，{ '香巴拉维:2019}]
> 列表的集差为:[{ '香巴拉维:2019}]

**方法 2:使用`itertools.filterfalse()`**
这是一种不同的方式，使用内置的 python 函数可以执行这个特定的任务。filterfalse 方法过滤一个列表中不存在的元素。

```
# Python3 code to demonstrate 
# set difference in dictionary list 
# using itertools.filterfalse()
import itertools

# initializing list 
test_list1 = [{"HpY" : 22}, {"BirthdaY" : 2}, ]
test_list2 = [{"HpY" : 22}, {"BirthdaY" : 2}, {"Shambhavi" : 2019}]

# printing original lists
print ("The original list 1 is : " + str(test_list1))
print ("The original list 2 is : " +  str(test_list2))

# using itertools.filterfalse()
# set difference in dictionary list 
res = list(itertools.filterfalse(lambda i: i in test_list1, test_list2)) \
    + list(itertools.filterfalse(lambda j: j in test_list2, test_list1))

# printing result 
print ("The set difference of list is : " +  str(res))
```

**输出:**

> 原列表 1 为:[{'HpY': 22}，{ '生日':2}]
> 原列表 2 为:[{'HpY': 22}，{ '生日':2}，{ '香巴拉维:2019}]
> 列表的集差为:[{ '香巴拉维:2019}]