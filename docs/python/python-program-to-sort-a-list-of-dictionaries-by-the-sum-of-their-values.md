# Python 程序根据字典值的总和对字典列表进行排序

> 原文:[https://www . geesforgeks . org/python-program-to-sort-list-dictionary-by-sum-of-values/](https://www.geeksforgeeks.org/python-program-to-sort-a-list-of-dictionaries-by-the-sum-of-their-values/)

给定字典列表，按其值的总和排序。

> **输入** : test_list = [{1 : 3，4 : 5，3 : 5}，{1 : 100}，{8 : 9，7 : 3}]
> **输出** : [{8: 9，7 : 3}，{1 : 3，4: 5，3: 5}，{1: 100}]
> **解释** : 12 < 13 < 100，按数值总和排序。
> 
> **输入** : test_list = [{1 : 100}，{8 : 9，7 : 3}]
> **输出** : [{8: 9，7 : 3}，{1: 100}]
> **解释** : 12 < 100，按数值总和排序。

**方法#1:使用** [**排序()**](https://www.geeksforgeeks.org/sort-in-python/) **+** [**求和()**](https://www.geeksforgeeks.org/sum-function-python/) **+** [**取值()**](https://www.geeksforgeeks.org/python-dictionary-values/)

在这种情况下，执行排序的任务是使用 sort()完成的，sum()和值()用于获得字典中所有值的总和。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Sort Dictionaries by Values Sum
# Using sort() + sum() + values()

def values_sum(row):

    # return values sum 
    return sum(list(row.values()))

# initializing list
test_list = [{1 : 3, 4 : 5, 3 : 5}, {1 : 7, 10 : 1, 3 : 10}, {1 : 100}, {8 : 9, 7 : 3}]

# printing original list
print("The original list is : " + str(test_list))

# performing sort  
test_list.sort(key = values_sum)

# printing result 
print("Sorted Dictionaries List : " + str(test_list))
```

**输出:**

> 原始列表为:[{1: 3，4: 5，3: 5}、{1: 7，10: 1，3: 10}、{1: 100}、{8: 9，7: 3}]
> 排序词典列表:[{8: 9，7: 3}、{1: 3，4: 5，3: 5}、{1: 7，10: 1，3: 10}、{1: 100}]

**方法 2:使用** [**排序()**](https://www.geeksforgeeks.org/sorted-function-python/)**+**[**λ**](https://www.geeksforgeeks.org/python-lambda/)**+sum()+values()**

在本文中，我们使用 sorted()执行排序，并使用 lambda 函数提供逻辑。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Sort Dictionaries by Values Sum
# Using sorted() + lambda + sum() + values()

# initializing list
test_list = [{1 : 3, 4 : 5, 3 : 5}, {1 : 7, 10 : 1, 3 : 10}, {1 : 100}, {8 : 9, 7 : 3}]

# printing original list
print("The original list is : " + str(test_list))

# lambda function to get values sum 
res = sorted(test_list, key = lambda row : sum(list(row.values())))

# printing result 
print("Sorted Dictionaries List : " + str(res))
```

**输出:**

> 原始列表为:[{1: 3，4: 5，3: 5}、{1: 7，10: 1，3: 10}、{1: 100}、{8: 9，7: 3}]
> 排序词典列表:[{8: 9，7: 3}、{1: 3，4: 5，3: 5}、{1: 7，10: 1，3: 10}、{1: 100}]