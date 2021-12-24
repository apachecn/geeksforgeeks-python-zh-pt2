# Python–后字符串分类

> 原文:[https://www . geesforgeks . org/python-后置-字符串-分类/](https://www.geeksforgeeks.org/python-rear-character-string-categorization/)

有时候，我们有一个用例，在这个用例中，我们需要通过各种因素对字符串进行分组，比如最后一个字母或者任何其他因素。这些类型的问题是数据库查询的典型问题，因此可能会在编程时出现在 web 开发中。本文重点介绍了一种通过字符串的最后一个字母进行分组的方法。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`next() + lambda + loop`**
以上 3 个函数的组合就是用朴素的方法来解决这个特殊的问题。lambda 函数执行查找类似后置字符的任务，next 函数有助于向前迭代。

```py
# Python3 code to demonstrate 
# Rear character String categorization
# using next() + lambda + loop 

# initializing list 
test_list = ['an', 'apple', 'geek', 'for', 'greek', 'free'] 

# printing original list 
print("The original list : " + str(test_list)) 

# using next() + lambda + loop 
# Rear character String categorization
util_func = lambda x, y: x[len(x) - 1] == y[len(y) - 1] 
res = [] 
for sub in test_list: 
    ele = next((x for x in res if util_func(sub, x[len(x) - 1])), []) 
    if ele == []: 
        res.append(ele) 
    ele.append(sub) 

# print result 
print("The list after Categorization : " + str(res)) 
```

**Output :**

```py
The original list : ['an', 'apple', 'geek', 'for', 'greek', 'free']
The list after Categorization : [['an'], ['apple', 'free'], ['geek', 'greek'], ['for']]

```