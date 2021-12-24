# 从集合列表中提取元素的 Python 程序

> 原文:[https://www . geesforgeks . org/python-程序-从集合列表中提取元素/](https://www.geeksforgeeks.org/python-program-to-extract-elements-from-list-in-set/)

给定一个列表，任务是编写一个 Python 程序来提取集合中出现匹配的所有元素。

> **输入:** test_list = [5，6，2，3，2，6，5，8，9]，search_set = {6，2，8}
> 
> **输出:**【6，2，2，6，8】
> 
> **解释:** 2、6 出现两次，并按照相对于其他元素的顺序输出。
> 
> **输入:** test_list = [5，6，2，3，2，6，5，8，9]，search_set = {8，3，5}
> 
> **输出:**【5，3，5，8】
> 
> **解释:** 5 出现两次，按照相对于其他元素的顺序输出。

**方法#1:使用循环**

在这种情况下，使用 In 运算符迭代并检查每个列表元素在集合中的存在性，如果找到，则将其附加到结果中。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Elements from list in set
# Using loop

# initializing list
test_list = [5, 6, 2, 3, 2, 6, 5, 8, 9]

# printing original list
print("The original list is : " + str(test_list))

# initializing search set
search_set = {6, 2, 8}

res = []
for ele in test_list:

    # check if element is present in set
    if ele in search_set:
        res.append(ele)

# printing result
print("Set present list elements : " + str(res))
```

**输出:**

```
The original list is : [5, 6, 2, 3, 2, 6, 5, 8, 9]
Set present list elements : [6, 2, 2, 6, 8]
```

**方法 2:使用** [**重复()**](https://www.geeksforgeeks.org/python-itertools-repeat/)**+from _ iterable()+**[**计数()**](https://www.geeksforgeeks.org/python-list-function-count/)

在本例中，我们对列表中的每个 set 元素进行测试，并使用 repeat()重复使用 count()计算所需的计数。在此结果中不维护订单。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Elements from list in set
# Using repeat() + from_iterable() + count()
from itertools import chain, repeat

# initializing list
test_list = [5, 6, 2, 3, 2, 6, 5, 8, 9]

# printing original list
print("The original list is : " + str(test_list))

# initializing search set
search_set = {6, 2, 8}

# repeat repeats all the occurrences of elements
res = list(chain.from_iterable((repeat(ele, test_list.count(ele)) 
                                for ele in search_set)))

# printing result
print("Set present list elements : " + str(res))
```

**输出:**

```
The original list is : [5, 6, 2, 3, 2, 6, 5, 8, 9]
Set present list elements : [6, 2, 2, 6, 8]
```