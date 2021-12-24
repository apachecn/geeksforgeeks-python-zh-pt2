# Python 程序标记字符串中的重复元素

> 原文:[https://www . geesforgeks . org/python-程序-标记-重复-字符串元素/](https://www.geeksforgeeks.org/python-program-to-mark-duplicate-elements-in-string/)

给定一个列表，任务是编写一个 Python 程序，用渐进出现次数标记元素的重复出现。

> **输入:** test_list = ['gfg '，' is '，' best '，' gfg '，' best '，' for '，' all '，' gfg']
> 
> **输出:** ['gfg1 '，' is '，' best1 '，' gfg2 '，' best2 '，' for '，' all '，' gfg3']
> 
> **说明:** gfg 的所有出现都被标记为有多次重复(3)。
> 
> **输入:** test_list = ['gfg '，' is '，' best '，' best '，' for '，' all']
> 
> **输出:** ['gfg '，' is '，' best1 '，' best2 '，' for '，' all']
> 
> **说明:** best 的所有出现都被标记为有多次重复(2)。

**方法一:使用** [**计数()**](https://www.geeksforgeeks.org/python-string-count/) **+** [**枚举()**](https://www.geeksforgeeks.org/enumerate-in-python/) **+** [**列表理解**](https://www.geeksforgeeks.org/comprehensions-in-python/)**+**[T21】切片](https://www.geeksforgeeks.org/string-slicing-in-python/)

在这种情况下，为了获得重复计数，列表被分割到当前元素索引，并且使用 count()和 append 计算该元素直到当前索引的出现计数。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Mark duplicate elements
# Using count() + enumerate() + list comprehension + slicing 

# initializing list
test_list = ["gfg", "is", "best", "gfg", 
             "best", "for", "all", "gfg"]

# printing original list
print("The original list is : " + str(test_list))

# getting count till current using count() and slicing
res = [val + str(test_list[:idx].count(val) + 1) if test_list.count(val) > 1 else val for idx,
       val in enumerate(test_list)]

# printing result
print("Duplicates marked List : " + str(res))
```

**输出:**

> 原列表为:['gfg '，' is '，' best '，' gfg '，' best '，' for '，' all '，' gfg']
> 
> 标记为列表的重复项:['gfg1 '，' is '，' best1 '，' gfg2 '，' best2 '，' for '，' all '，' gfg3 '

**方法二:使用** [**地图()**](https://www.geeksforgeeks.org/python-map-function/) **+** [**计数()**](https://www.geeksforgeeks.org/python-string-count/)**+**[T15T17】](https://www.geeksforgeeks.org/python-lambda-anonymous-functions-filter-map-reduce/)

与上面的方法类似，唯一的区别是 map()用于获得一个使用 lambda 扩展到整个列表元素的函数。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Mark duplicate elements
# Using map() + count() + lambda

# initializing list
test_list = ["gfg", "is", "best", "gfg", 
             "best", "for", "all", "gfg"]

# printing original list
print("The original list is : " + str(test_list))

# getting count till current using count() and slicing
res = list(map(lambda ele: ele[1] + str(test_list[ : ele[0]].count(ele[1]) + 1) if test_list.count(ele[1]) > 1 else ele[1],
               enumerate(test_list)))

# printing result
print("Duplicates marked List : " + str(res))
```

**输出:**

> 原列表为:['gfg '，' is '，' best '，' gfg '，' best '，' for '，' all '，' gfg']
> 
> 标记为列表的重复项:['gfg1 '，' is '，' best1 '，' gfg2 '，' best2 '，' for '，' all '，' gfg3 '