# 用偶数频率元素提取矩阵行的 Python 程序

> 原文:[https://www . geeksforgeeks . org/python-程序提取偶数频率元素矩阵的行/](https://www.geeksforgeeks.org/python-program-to-extract-rows-of-a-matrix-with-even-frequency-elements/)

给定一个矩阵，任务是编写一个 Python 程序来提取元素频率为偶数的所有行。

**示例:**

> **输入:** [[4，5，5，2]，[4，4，4，4，2，2]，[6，5，6，5]，[1，2，3，4]]
> 
> **输出:** [[4，4，4，4，2，2]，[6，5，6，5]]
> 
> **说明:**
> 
> *   4-> 4 的频率是偶数
> *   频率为 2-> 2，也就是偶数
> *   6-> 2 的频率是偶数
> *   5-> 2 的频率是偶数

**方法一:** *使用* [*列表理解*](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)*[*计数器()*](https://www.geeksforgeeks.org/python-counter-objects-elements/) *和* [*全部()*](https://www.geeksforgeeks.org/any-all-in-python/)*

*在这种情况下，使用 Counter()维护计数，all()用于检查是否所有频率都是偶数，如果不是，则在结果列表中不输入行。*

***程序:***

## *蟒蛇 3*

```
*from collections import Counter

# initializing list
test_list = [[4, 5, 5, 2], [4, 4, 4, 4, 2, 2],
             [6, 5, 6, 5], [1, 2, 3, 4]]

# printing original list
print("The original list is : " + str(test_list))

# Counter() gets the required frequency
res = [sub for sub in test_list if all(
    val % 2 == 0 for key, val in list(dict(Counter(sub)).items()))]

# printing result
print("Filtered Matrix ? : " + str(res))*
```

***输出:***

> *原来的名单是:[[4，5，5，2]，[4，4，4，4，2，2]，[6，5，6，5]，[1，2，3，4]]*
> 
> *过滤矩阵？: [[4, 4, 4, 4, 2, 2], [6, 5, 6, 5]]*

***方法二:** *使用* [*滤镜()*](https://www.geeksforgeeks.org/filter-in-python/)*[*计数器()*](https://www.geeksforgeeks.org/python-counter-objects-elements/) *和物品()***

**与上述方法类似，使用 filter()和 lambda 函数之间的差异来过滤偶数频率行。**

****程序:****

## **蟒蛇 3**

```
**from collections import Counter

# initializing list
test_list = [[4, 5, 5, 2], [4, 4, 4, 4, 2, 2], 
             [6, 5, 6, 5], [1, 2, 3, 4]]

# printing original list
print("The original list is : " + str(test_list))

# Counter() gets the required frequency
# filter() used to perform filtering
res = list(filter(lambda sub: all(val % 2 == 0 for key,
                                  val in list(dict(Counter(sub)).items())), test_list))

# printing result
print("Filtered Matrix ? : " + str(res))**
```

****输出:****

> **原来的名单是:[[4，5，5，2]，[4，4，4，4，2，2]，[6，5，6，5]，[1，2，3，4]]**
> 
> **过滤矩阵？: [[4, 4, 4, 4, 2, 2], [6, 5, 6, 5]]**