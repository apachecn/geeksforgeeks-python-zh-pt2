# Python 程序根据元组的最大元素

对元组进行排序

> 原文:[https://www . geesforgeks . org/python-程序-按最大元素对元组进行排序/](https://www.geeksforgeeks.org/python-program-to-sort-tuples-by-their-maximum-element/)

给定一个[元组](https://www.geeksforgeeks.org/python-tuples/)列表，按照元组中的最大元素对元组进行排序。

> **输入** : test_list = [(4，5，5，7)，(1，3，7，4)，(19，4，5，3)，(1，2)]
> **输出** : [(19，4，5，3)，(4，5，5，7)，(1，3，7，4)，(1，2)]
> **解释** : 19 > 7 = 7 > 2，是顺序，因此按最大元素反向排序。
> 
> **输入** : test_list = [(4，5，5，7)，(19，4，5，3)，(1，2)]
> **输出** : [(19，4，5，3)，(4，5，7)，(1，2)]
> **解释** : 19 > 7 > 2，是顺序，因此按最大元素反向排序。

**方法#1:使用**[**max()**](https://www.geeksforgeeks.org/max-min-python/)**+**[**sort()**](https://www.geeksforgeeks.org/sort-in-python/#:~:text=Like%20C%2B%2B%20sort()%2C%20Java,the%20list%20in%20ascending%20order.&text=%23%20This%20will%20sort%20the%20given%20list%20in%20ascending%20order.)

在本文中，我们使用 max()执行获取元组中最大元素的任务，并使用 sort()操作来执行排序。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Sort Tuples by Maximum element
# Using max() + sort()

# helper function
def get_max(sub):
    return max(sub)

# initializing list
test_list = [(4, 5, 5, 7), (1, 3, 7, 4), (19, 4, 5, 3), (1, 2)]

# printing original list
print("The original list is : " + str(test_list))

# sort() is used to get sorted result
# reverse for sorting by max - first element's tuples
test_list.sort(key = get_max, reverse = True)

# printing result 
print("Sorted Tuples : " + str(test_list))
```

**输出:**

> 原列表为:[(4，5，5，7)，(1，3，7，4)，(19，4，5，3)，(1，2)]
> 排序元组:[(19，4，5，3)，(4，5，7)，(1，3，7，4)，(1，1，2)]

**方法 2:使用 sort()+**[**【λ】**](https://www.geeksforgeeks.org/python-lambda-anonymous-functions-filter-map-reduce/)**+反向**

在这种情况下，我们使用类似的功能，唯一的区别是使用了 lambda fnc。而不是获取反向排序任务的外部函数。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Sort Tuples by Maximum element
# Using sort() + lambda + reverse

# initializing list
test_list = [(4, 5, 5, 7), (1, 3, 7, 4), (19, 4, 5, 3), (1, 2)]

# printing original list
print("The original list is : " + str(test_list))

# lambda function getting maximum elements 
# reverse for sorting by max - first element's tuples
test_list.sort(key = lambda sub : max(sub), reverse = True)

# printing result 
print("Sorted Tuples : " + str(test_list))
```

**输出:**

> 原列表为:[(4，5，5，7)，(1，3，7，4)，(19，4，5，3)，(1，2)]
> 排序元组:[(19，4，5，3)，(4，5，7)，(1，3，7，4)，(1，1，2)]