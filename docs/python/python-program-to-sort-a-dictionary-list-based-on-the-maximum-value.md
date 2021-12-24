# Python 程序根据最大值对字典列表进行排序

> 原文:[https://www . geeksforgeeks . org/python-程序对字典进行排序-基于列表的最大值/](https://www.geeksforgeeks.org/python-program-to-sort-a-dictionary-list-based-on-the-maximum-value/)

给定以字典为元素的列表，编写一个 Python 程序，根据字典键值对中的最大值对字典进行排序。简单来说，首先将检查列表(字典)的每个元素，这意味着将比较每个键值对，以找到具有最大值的元素。然后，在列表中排序将根据哪个元素包含如此获得的最大值来完成。

**示例:**

> **输入** : test_list = [{1:5，6: 7，9:1}，{2:6，9: 10，1:4}，{6:5，9: 3，1:6}]
> **输出** : [{6: 5，9:3，1:6}，{1:5，6:7，9: 1}，{2: 6，9:10，1: 4}]
> **解释** : 6 < 7
> 
> *   在键值对中有 5、3、6 个值的字典中，6 是最大值
> *   在键值对中有 5、7、1 个值的字典中，7 是最大值
> *   在键值对中有 6、10、4 个值的字典中，10 是最大值。
> 
> **输入** : test_list = [{1:5，6: 7，9:1}，{2:6，9: 10，1:4}]
> **输出** : [{1: 5，6:7，9: 1}，{2: 6，9:10，1: 4}]
> **解释** : 7 < 10，
> 
> *   在键值对中有 5、7、1 个值的字典中，7 是最大值
> *   在键值对中有 6、10、4 个值的字典中，10 是最大值

**方法#1 :** *使用* [*值()*](https://www.geeksforgeeks.org/python-dictionary-values/)*[*max()*](https://www.geeksforgeeks.org/max-min-python/)和 [*sort()*](https://www.geeksforgeeks.org/sort-in-python/)*

*在本例中，我们使用 sort()执行就地排序任务，使用 max()获取最大值，使用 values()获取值。外部函数作为参数传递，以实现所需的功能。* 

***示例:***

## *蟒蛇 3*

```
*# getting max value
def get_max(dicts):
    return max(list(dicts.values()))

# initializing list
test_list = [{1: 5, 6: 7, 9: 1}, {2: 6, 9: 10, 1: 4}, {6: 5, 9: 3, 1: 6}]

# printing original list
print("The original list is : " + str(test_list))

# sorting dictionary list by maximum value
test_list.sort(key=get_max)

# printing result
print("Sorted List : " + str(test_list))*
```

***输出:***

> *原始列表为:[{1: 5，6: 7，9: 1}，{2: 6，9: 10，1: 4}，{6: 5，9: 3，1: 6}]*
> 
> *排序列表:[{6: 5，9: 3，1: 6}，{1: 5，6: 7，9: 1}，{2: 6，9: 10，1: 4}]*

***方法#2 :** *使用* [*排序()、*](https://www.geeksforgeeks.org/sorted-function-python/)*[*λ*](https://www.geeksforgeeks.org/python-lambda/)*、*[*max()*](https://www.geeksforgeeks.org/max-min-python/)*和* [*值()*](https://www.geeksforgeeks.org/python-dictionary-values/)**

**在本文中，我们使用 sorted()和 lambda 函数执行排序，以提供单语句过滤，而不是调用外部函数。**

****示例:****

## **蟒蛇 3**

```
**# initializing list
test_list = [{1: 5, 6: 7, 9: 1}, {2: 6, 9: 10, 1: 4}, {6: 5, 9: 3, 1: 6}]

# printing original list
print("The original list is : " + str(test_list))

# sorting dictionary list by maximum value
# one statement sort
res = sorted(test_list, key=lambda dicts: max(list(dicts.values())))

# printing result
print("Sorted List : " + str(res))**
```

****输出:****

> **原始列表为:[{1: 5，6: 7，9: 1}，{2: 6，9: 10，1: 4}，{6: 5，9: 3，1: 6}]**
> 
> **排序列表:[{6: 5，9: 3，1: 6}，{1: 5，6: 7，9: 1}，{2: 6，9: 10，1: 4}]**